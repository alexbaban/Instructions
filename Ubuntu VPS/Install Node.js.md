# Install Node.js on Ubuntu

* `curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -`
* `sudo apt-get install -y nodejs`

## Verify Node is installed

* `node --version`
* `npm --version`

## Make a simple REST API request

We’ll be using NASA’s Astronomy Picture of the Day API (https://api.nasa.gov/api.html#apod) as the JSON API that we are interacting with.

### Verify with curl first   
* `curl https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY`

### Make request with Node

* `cd /opt`
* `mkdir apps && cd apps`
* `mkdir node-test && cd node-test`

**new file** `index.js`

``` js
const https = require('https');

https.get('https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY', (resp) => {
  let data = '';

  // A chunk of data has been recieved.
  resp.on('data', (chunk) => {
    data += chunk;
  });

  // The whole response has been received. Print out the result.
  resp.on('end', () => {
    console.log(JSON.parse(data).explanation);
  });

}).on("error", (err) => {
  console.log("Error: " + err.message);
});

```

* run `node index.js` // will make the request and print out the explanation

## 5 Ways to Make HTTP Requests in Node.js
(https://www.twilio.com/blog/2017/08/http-requests-in-node-js.html)
