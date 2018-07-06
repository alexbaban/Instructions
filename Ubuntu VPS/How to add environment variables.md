# How to add environment variables

To set it permanently, and system wide (all users, all processes) add set variable in **/etc/environment**

* `sudo -H nano /etc/environment`
* add new line `FOO="bar"` then save

Then, logout from current user and login again so environment variables changes take place.

* Verify with `echo $FOO`

## Access environment variables from Node 

* `cd /opt/apps && mkdir node-env && cd node-env && touch index.js`

**index.js**

``` js
const FOO = process.env.FOO || 'baz';
console.log('The value of FOO is:', FOO);


```

## Working with Environment Variables in Node.js
(https://www.twilio.com/blog/2017/08/working-with-environment-variables-in-node-js.html)
