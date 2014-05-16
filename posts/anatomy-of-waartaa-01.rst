.. title: The road to Waartaa 0.1
.. slug: anatomy-of-waartaa-01
.. date: 2014/05/16 14:33:19
.. tags: waartaa,irc,technology
.. link: 
.. description: 
.. type: text

Waartaa is a realtime web IRC client as a service. Waartaa is powered by:

- Meteor JS
- MongoDB
- node-irc, amongst other cool NPM packages
- a bunch of meteorite packages from `atmospherejs.com <http://atmospherejs.com>`_


Basic feature set
=================

- Send server, channel, personal messages.
- Support basic IRC commands: join, away, me, whois, msg, part
- Centralized logging for every user for every channel, server
- Realtime update across multiple clients


Shortcomings
============

- Huge storage complexity, proportional to number of users active on a
  channel and number of logs generated per channel.
- High CPU and memory usage due to high number of writes on collections being published for reactivity.
- RAM starvation due to increased data size of channel_logs collection.


Solution
========

- Upgrading to OPLOG driver in Meteor 0.8 fixed the issue by enhancing OPLOG's
  support to complex mongo queries.
- Minimized DB writes by:

  - during updating channel's nicks data
  - write a channel log once per channel irrespective of number of waartaa users on channel
- Reduce resource utilization by the app server by async writes to MongoDB.

Currently, waartaa's stack looks something like this


.. image:: https://raw.githubusercontent.com/waartaa/waartaa/master/gallery/waartaa_0.1_stack.png
    :align: center


The current model of Waartaa works fine as a single standalone instance.
It's not that great for horizontal scaling yet. It's in our roadmap
to make waartaa scalable.

For now, this is all we have to offer for the 0.1 release.
