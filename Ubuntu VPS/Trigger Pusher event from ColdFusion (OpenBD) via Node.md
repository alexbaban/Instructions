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

## Calling `node index.js` from ColdFusion

* Install OpenBD JAM Stack (http://openbd.org/jam/)  
    `cd ~`  
    `wget http://openbd.org//download/3.1/OpenBDJAM.sh`  
    `bash OpenBDJAM.sh` 
    
* Start OpenBD JAM server  
    `cd /opt/openbdjam/ && ./openbdjam start`
    
**new file** `pusher.cfm` (create in /opt/openbdjam/webroot/)
``` coldfusion
<cfset args = [
	'/opt/apps/node-pusher/index.js'
] />

<cfdump var="#args#" label="args" />
<hr />

<!--- // trigger a "Pusher event" using the "Pusher Node.js REST library" --->
<cfexecute 
	name="node" 
	arguments="#args#" 
	variable="output" 
	errorVariable="error" 
	timeout="5" 
/>

<cfdump var="#output#" />
<hr />

<cfdump var="#error#" />
<hr />

```

**open** `/pusher.cfm` page in browser and check event triggered in Pusher's "Debug Console" page

## Passing arguments (object) from ColdFusion (OpenBD) to Node.js to Pusher

**update file** `pusher.cfm`
``` coldfusion
<cfset payload = {
	'action': 'end',
	'id': '1234',
	'name': 'Alex Baban',
	'timestamp': '2018-07-05 17:43'
} />

<cfdump var="#payload#" label="payload" />
<hr />

<cfset args = [
	'/opt/apps/node-pusher/index.js',
	'#urlFromStruct(payload)#'
] />

<cfdump var="#args#" label="args" />
<hr />

<!--- // trigger a "Pusher event" using the "Pusher Node.js REST library" --->
<cfexecute 
	name="node" 
	arguments="#args#" 
	variable="output" 
	errorVariable="error" 
	timeout="5" 
/>

<cfdump var="#output#" />
<hr />

<cfdump var="#error#" />
<hr />

```

**update file** `index.js`
``` js
var querystring = require('querystring');
var Pusher = require('pusher');

// credentials below are fake, replace with valid values
var pusher = new Pusher({
  appId: '123456',
  key: '359ead95925c5657cbe0',
  secret: '6cc6cc121e87ea5b3885',
  cluster: 'us2',
  encrypted: true
});

const payload = process.argv[2] || '';

pusher.trigger('my-channel', 'my-event', {
  "payload": querystring.parse(payload)
});

```

**open** `/pusher.cfm` page in browser and check event triggered in Pusher's "Debug Console" page

**result**
``` json
{
  "payload": {
    "action": "end",
    "id": "1714",
    "name": "Alex Baban",
    "timestamp": "2018-07-05 17:43"
  }
}

```
