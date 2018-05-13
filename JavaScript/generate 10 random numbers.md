# How to generate 10 random numbers within 1 to 20 (inclusive) range

``` js
var randomNumbers = [];

while (randomNumbers.length < 10) {

    var randomnumber = Math.floor(Math.random() * 20) + 1;

    if (randomNumbers.indexOf(randomnumber) > -1) continue;

    randomNumbers.push(randomnumber);

}

console.log(randomNumbers);

```
