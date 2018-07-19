# ECMAScript 6 Classes

Send an SMS using Node.js and Twilio

* `cd / && cd apps && mkdir twilio-node && cd twilio-node`
* `cd twilio-node && touch sms_classes.js && code .`

### `sms_classes.js`

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

    send() {

        client.messages
            .create({
                from: process.env.TWILIO_PHONE_NUMBER,
                to: this.to,
                body: this.text
            })
            .then(message => console.log(message))
            .catch(err => console.log(err));

    }
}

var m1 = new Message("+13335557777", "Hey, how are you?");
m1.send()
```

**run `node sms_classes.js`**
