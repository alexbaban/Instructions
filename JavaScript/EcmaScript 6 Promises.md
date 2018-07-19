# ECMAScript 6 Promises

Send an SMS using Node.js and Twilio

* `cd / && cd apps && mkdir twilio-node && cd twilio-node`
* `cd twilio-node && touch sms_promises.js && code .`

### `sms_promises.js`

```js
const client = require("twilio")(
    process.env.TWILIO_ACCOUNT_SID,
    process.env.TWILIO_AUTH_TOKEN
  );
  
  class Message {
    constructor(to, text) {
      this.to = to;
      this.text = text;
    }
  
    send(text) {
      return new Promise((resolve, reject) => {
        client.messages
          .create({
            from: process.env.TWILIO_PHONE_NUMBER,
            to: this.to,
            body: this.text
          })
          .then(message => resolve(message))
          .catch(err => reject(err));
      });
    }
  }
  
  var m1 = new Message("+13335557777", "Hey, how are you?");
  m1.send()
    .then(resp => console.log(resp.sid))
    .catch(err => console.log(err));
    
```

**run `node sms_promises.js`**
