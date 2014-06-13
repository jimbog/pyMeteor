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

Example
=======


```python3

from pyDDP import DDPClient
c = DDPClient("ws://localhost:3000/websocket", debugPrint=True, printDDP=True, attemptReconnect=False)
c.connectDDP()

loggedIn = c.loginWithPassword('myUserName', 'p4ssw0rd')
if not loggedIn:
    print('Failed login.')
    sys.exit(1)

posts = c.newCollection('posts')
sub = c.subscribe('posts')
sub.blockOnReady()
print(posts) # should print an array containing the documents in the subscription

methodResult = c.methodSync('myMethodName', params=['firstParam', 1, 2, 'Fourth Param'])

```
