# Trigger Pusher event from ColdFusion (OpenBD) via Node

* Install Node.js

## Test

* Create app folder `cd /opt/apps && mkdir node-pusher && cd node-pusher`
* Install Pusher Node.js server library `npm install pusher --save`

**new file** `index.js`

``` js
var Pusher = require('pusher');

// credentials below are fake, replace with valid values
var pusher = new Pusher({
  appId: '123456',
  key: '359ead95925c5657cbe0',
  secret: '6cc6cc121e87ea5b3885',
  cluster: 'us2',
  encrypted: true
});

pusher.trigger('my-channel', 'my-event', {
  "message": "hello world"
});
```

**run** `node index.js` and check event triggered in Pusher's "Debug Console" page
