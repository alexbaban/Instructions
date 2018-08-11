# Misc ES6

## Map to JSON
```js

function mapToJSON(map) {
  var obj = {};
  map.forEach((val, key) => {
    obj[key] = val;
  });
  
  return JSON.stringify(obj);
}

```
