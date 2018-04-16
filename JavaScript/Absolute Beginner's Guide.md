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
        // return; // simply exits
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

> Once the function hits the `return` keyword, returns whatever value specified to whatever called it, and exits.

## Conditional statements `if`, `else` and `switch`
``` js
'use strict';

; (function () {

    var color = "red"; // this will alert `red`
    //var color; // this will alert `no color`

    switch (color) {
        case "yellow":
            alert("yellow");
            break;
        case "red":
            alert("red");
            break;
        case "blue":
            alert("blue");
            break;
        default:
            alert("no color");
    }

})();

```

or 

``` js
'use strict';

; (function () {

    var number = 19;

    switch (number > 10) {

        case true:
            alert("it's greater than 10");
            break;
        case false:
            alert("no, it's not greater than 10");
            break;

    }

})();

```
> This will alert `it's greater than 10`

## Loops: `for`, `while` and `do...while`

### `for`
``` js
'use strict';

; (function () {

    var count = 3;

    function saySomething(i) {
        console.log("Hey! " + i); // this will show `Hey! /[012]/` (three times)
    }

    for (var i = 0; i < count; i++) {

        if (i == 1) {
            // continue; this will skip the second iteration
        }

        saySomething(i);

        // break; // this will show `Hey! 0` (just once)

    }

})();

```

### `while`
``` js
'use strict';

; (function () {

    var count = 0;

    while (count < 3) {
        console.log("count has the value of " + count);
        count++;
    }

})();

```

### `do...while`
``` js
'use strict';

; (function () {

    var count = 0;

    do {
        console.log("count has the value of " + count);
        count++;
    } while (count < 3)

    console.log("final value of count is " + count);

})();


// count has the value of 0
// count has the value of 1
// count has the value of 2
// final value of count is 3

```

## Timers `setTimeout`, `setInterval` and `requestAnimationFrame`

### `setTimeout`
``` js
'use strict';

; (function () {

    function showAfterDelay() {
        alert('foo');
    }

    var delayInMilliseconds = 5000;
    var id = setTimeout(showAfterDelay, delayInMilliseconds);
    // `id` returned immediately
    // alert `foo` will show after five seconds

    alert(id);
    // id starts at 1 with the app launch
    // each page refresh will do id++

    alert('bar');

    // clearTimeout(id); // `showAfterDelay()` will not be called

})();

```

___Detecting Inactivity with `setTimeout`___
``` js
'use strict';

; (function () {

    var id;

    function setup() {
        window.addEventListener("mousemove", resetTimer, false);
        window.addEventListener("mousedown", resetTimer, false);
        window.addEventListener("keypress", resetTimer, false);
        window.addEventListener("DOMMouseScroll", resetTimer, false);
        window.addEventListener("mousewheel", resetTimer, false);
        window.addEventListener("touchmove", resetTimer, false);
        window.addEventListener("MSPointerMove", resetTimer, false);

        startTimer();
    }
    setup();

    function startTimer() {
        // wait 3 seconds before calling goInactive
        id = window.setTimeout(goInactive, 3000);
    }

    function resetTimer(e) {
        window.clearTimeout(id);
        // console.log(e); // debug the event
        goActive();
    }

    function goInactive() {
        alert("You're inactive!");
        // do something    
    }

    function goActive() {
        startTimer();
        // do something
    }

})();

```




### ``
