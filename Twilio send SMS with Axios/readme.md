# Twilio send SMS with Axios

Axios is a promise based HTTP client for the browser and node.js   
(https://github.com/axios/axios)

Using application/x-www-form-urlencoded format   
(https://github.com/axios/axios#using-applicationx-www-form-urlencoded-format)

Sample code works with either `qs` or Node.js's native `querystring`

## new file `index.js`

``` js
// send Twilio SMS using axios

const axios = require('axios');
const querystring = require('querystring');

const accountSid = process.env.TWILIO_ACCOUNT_SID;
const authToken = process.env.TWILIO_AUTH_TOKEN;
const messagesURI = `https://api.twilio.com/2010-04-01/Accounts/${accountSid}/Messages.json`;

let payload = {
    Body: "First line\r\nHere is my second line...",
    From: "+13335557777",
    To: "+17775553333"
};

axios
    .post(messagesURI, querystring.stringify(payload), {
        auth: {
            username: accountSid,
            password: authToken
        },
        headers: {
            'Content-Type': 'application/x-www-form-urlencoded'
        }
    })
    .then(response => console.log(response.data.sid))
    .catch(error => console.log(error));
    
```

