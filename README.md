pyMeteor
========

A package for interacting with Meteor via Python!

Supports Python2/3

Tested on:
 - Windows 7
 - OSX
 - Linux Mint/Ubuntu

Feature List
============

 - Implements DDP (pre1) specification.
   - Connect + version transaction
   - Implements all ddp messages
   - Sync/async method calls
   - Subscriptions and subscription handles
 - Beginning minimongo implementation
   - insert/find/findOne/remove
   - Only supports basic selectors
 - SRP based login, interfacing with accounts-password
