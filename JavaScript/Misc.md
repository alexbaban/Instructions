
# Misc

## Reverse a string
(https://github.com/mathiasbynens/esrever)

```[...str].reduceRight( (prev, curr) => prev + curr )```

## Generate a random number
```js
// generate a random number between 1 and 200 inclusive
(Math.floor(Math.random() * 200) + 1));

```

## Generate 10 random numbers within 1 to 20 (inclusive) range
``` js
var randomNumbers = [];

while (randomNumbers.length < 10) {

    var randomnumber = Math.floor(Math.random() * 20) + 1;

    if (randomNumbers.indexOf(randomnumber) > -1) continue;

    randomNumbers.push(randomnumber);

}

console.log(randomNumbers);

```

## Identify 'white space', 'letter' and 'decimal digit'
```js

function isWhiteSpace(ch) {
  return (ch === 'u0009') || (ch === ' ') || (ch === 'u00A0');
}


function isLetter(ch) {
  return (ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z');
}


function isDecimalDigit(ch) {
  return (ch >= '0') && (ch <= '9');
}

```

