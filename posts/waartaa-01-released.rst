.. title: Waartaa 0.1 released!
.. slug: waartaa-01-released
.. date: 2014/07/02 01:27:36
.. tags: release,0.1,irc,waartaa
.. link: 
.. description: 
.. type: text

It's a great pleasure to inform you that we have released Waartaa 0.1,
finally. Again, a big thanks goes to the team of contributors for Waartaa
to make this happen.

This release includes all the basic IRC functionalities, centralized logging,
notifications, etc. implemented in release v0.1-rc1. We worked on a lot of
optimizations and automated the deployment process for Waartaa to make
using and maintaining Waartaa as simple as possible. You can get the source
in the following way:

.. code-block:: bash
   :number-lines:

   $ git clone https://github.com/waartaa/waartaa.git
   $ cd waartaa
   $ git checkout 0.1

What's new?
===========
- Backend optimizations

  - OPLOG support
  - Rate limit tasks using queues
  - Async calls to database
  - Improve MongoDB performance in limited RAM
  - Reduce storage complexity for channel logs
- Client optimizations and improvements

  - Smooth rendering of chat logs
  - Use latency compensation to make improve user experience
  - Optimize client side memory usage
- Upgrade to Meteor 0.8.1
- Easy server provisioning
- Easy app deployment
- Vagrant script for easy setup of dev sandbox

Anatomy
=======

.. image:: /galleries/waartaa/waartaa_0.1_stack.png
    :align: center
    :width: 75%


Currently, Waartaa runs as a monolithic app. In the future, we'd be
dividing Waartaa into several components/layers so that it becomes
possible to horizantally scale a Waartaa service.

