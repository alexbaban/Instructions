# Absolute Beginner's Guide

## Naming variables, functions, arguments and parameters
``` js
; (function () {

    var defaultName = "World";

    function sayHello(name) {
        if (name === undefined) {
            alert("Hello " + defaultName + "!");
        } else {
            alert("Hello " + name + "!");
        }
    }

    sayHello();

    sayHello("Alexandru");

})();

```

> The names of the variables can start with a letter, underscore `_` or the dollar sign `$`. They can't start with a number.

_Douglas Crockford's Code Conventions:_ (https://crockford.com/javascript/code.html)   
_Douglas Crockford's JavaScript Resources:_ (http://crockford.com/javascript/)   

## The `return` keyword
``` js
'use strict';

var message;

; (function () {

    var defaultName = "World";

    function sayHello(name) {
        var message = "";

        if (name === undefined) {
            message = ("Hello " + defaultName + "!");
        } else {
            message = ("Hello " + name + "!");
        }
        
        console.log(message);

        return message;
    }

    message = sayHello(); // this will alert `Hello World!`
    // var message = sayHello(); // this will alert `undefined`

    sayHello("Alexandru");

})();

alert(message);

```

1. console shows `Hello World!`
2. console shows `Hello Alexandru!`
3. alert shows `Hello World!`
