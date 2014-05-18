.. title: Optimizing Waartaa 0.1
.. slug: optimizing-waartaa-01
.. date: 2014/05/16 14:33:19
.. tags: waartaa,irc,technology,meteorjs
.. link: 
.. description: 
.. type: text

Overview
========

Waartaa is a realtime web IRC client as a service. Waartaa is powered by:

- **Meteor** JS
- **MongoDB**
- **node-irc**, amongst other cool NPM packages
- a bunch of **meteorite** packages from
  `atmospherejs.com <http://atmospherejs.com>`_

We'd released version **0.1-rc1** a few months back with some basic feature
set.

- Send server, channel, personal messages
- Support basic IRC commands: join, away, me, whois, msg, part
- Centralized logging for every user for every channel, server
- Realtime update across multiple clients
- Mail notifications on nick mention when the user is away


Issues
======

- **High storage complexity**

  Storing logs per channel per user led to high storage complexity.

- **High CPU usage**

  Meteor 0.6 was not optimized to handle heavy writes to a collection
  which was published in realtime. In our case, the *UserChannelLogs* collection
  was the one published in realtime and with heavy writes. Meteor would use
  to poll the collection to find and push updates on the existing
  publications. The increased reads led to increased CPU usage and network
  IO for the MongoDB service. CPU usage would spike to 400%. Also, handling
  too many user tasks in the application server led to CPU spikes.

- **Slow app performance**

  By default, Meteor apps work synchronously, unlinke other typical nodejs
  apps. However, Meteor being a NodeJS framework itself, it's single threaded
  and it'd make other requests wait until it's done with processing the current
  request, which mostly involved waiting of database responses.

- **High RAM usage**

  The MongoDB server for `https://try.waartaa.com <https://try.waartaa.com>`_
  runs on a mere 1 GB memory. With the new users listening to variegated
  channels, the size of the collection spiked in a few days. Because, the
  same collection was also the most heavily read collection, this led
  to increased RAM usage and finally RAM starvation, We started experiencing
  latencies in write to MongoDB and the realtime app was no longer realtime.

- **Difficult setup**
- **Painful to deploy**


Working in limited resource sometimes has its benefits. We were forced to
optimize Waartaa to make it usable in the real world.


Optimizations & solutions
=========================

- **The OPLOG hack**

  The meteor community came up with a hack using MongoDB OPLOG to make MongoDB
  a really live database. Initially it was SmartCollections, then the OPLOG
  driver in Meteor 0.7 and finally an improved OPLOG driver supporting complex
  MongoDB queries in Meteor 0.8. OPLOG is a proven technology used by MongoDB to
  replicate databases. Meteor is now able to check for publication updates
  just by following MongoDB's OPLOG stream. So, goodbye to polling and high
  useless reads. With the OPLOG driver, waartaa's MongoDB instance finally
  became stable and the CPU usage came down to under 5% on an average.

- **Async read/writes to DB**

  Meteor comes with an option to do DB read/writes in an asynchronous way.
  Switching to async DB read and write wherever possible made waartaa more
  responsive by leaving room for the app to handle new requests while
  the app is waiting for DB IO.

- **Log once per channel**

  Logging once per channel was a challenge for Waartaa as we don't have
  a single bot to listen to. We worked on a crude algorithm to do this.
  We pick up a few clients from the pool of available clients listening
  to a channel that waartaa will monitor for new channel messages. We
  use CappedArray to keep a track of a limited number of recent channel
  logs written to the DB and use it to determine if a new channel log
  from a client should be written or not. Now, we save channel logs
  in *ChannelLogs* collection instead of *UserChannelLogs*.

  This has helped Waartaa reduce the storage complexity for channel logs
  to **O(c)**, where c is the number of channels Waartaa is listening
  to.

- **Get MongoDB perform better in less RAM**

  Waartaa now stores only a limited number of recent logs per channel
  in the *ChannelLogs* collection to keep the size of this collection
  in check and simultaneously archives older logs. This reduces the size
  of the working set of data needed for realtime publication and hence,
  it reduces the memory usage of the MongoDB service.

- **Task queues**

  Some operations like joining servers and channels during app restart
  were very costly operations and would lead to high CPU usage for some
  time. Hence, the application would become slow during server restart.
  Similarly, there were instances when there'd be high number of requests
  for updating data for channel nicks, nicks leaving/joining channels, etc.
  This would lead to CPU spikes. Implementing in memory task queues helped
  to rate limit such operations and keep the CPU load in check. In the
  longer run, we need to consider better task queuing solutions.

- **Easy sandbox setup with Vagrant**
- **Automated deployment with Ansible**

Below is a snapshot showing the CPU, network load on the app server of
`https://try.waartaa.com <https://try.waartaa.com>`_ during the initial days
of testing our optimizations.

.. image:: /galleries/waartaa/waartaa_app_optimize_cpu_usage.png
    :align: center
    :width: 80%

.. raw:: html

    <br/><br/>

The above steps have enabled us to keep our demo instance running at
`https://try.waartaa.com <https://try.waartaa.com>`_ using limited resources.
The current model of Waartaa works fine as a single standalone instance.
It's not that great for horizontal scaling yet. It's in our roadmap
to make waartaa scalable.

For now, this is all we have to offer for our upcoming 0.1 release.

