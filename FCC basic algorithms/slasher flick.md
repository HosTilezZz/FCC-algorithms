**old solution:**
```javascript
function slasher(arr, howMany) {
    var cut = [];
    for ( i=0 ; i<=howMany ; i++) {
         cut = arr.slice(i, arr.length);
    }
    return cut;
}
```

**new solution:**
```javascript
function slasher(arr, howMany) {
    for (i=0; i<howMany ; i++) { arr.shift() }
    return arr;
}
```
**comment:**

shift() instead of slice(), minor difference.

