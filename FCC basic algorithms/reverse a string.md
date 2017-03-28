old solution:
```javascript
function reverseString(str) {
  var result = str.split("");
  result = result.reverse();
  result = result.join("");
  return result;
}
```

new solution:
```javascript
function reverseString(str) {
    newArray = str.split("");
    newArray.reverse();
    result = newArray.join("");
    return result;   
}
```


