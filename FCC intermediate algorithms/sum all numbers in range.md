**old solution:**
```javascript
function sumAll(arr) {
    var max = Math.max(...arr);
    var min = Math.min(...arr);
    var counter = 0;
    for (i=min ; i<=max ; i++) {
        counter += i;
    }
    return counter;
}
```

**new solution:**
```javascript
function sumAll(arr) {
    var min = Math.min(...arr), max = Math.max(...arr), result = 0;
    for (var i=min ; i<=max ; i++) {
        result += i;
    }
    return result;
}
```
**comment:**

using "var" to declare the loop initializer is considered good practice since it attaches the variable "i" to the scope of 
the loop, unlike the old solution which attaches it to the global scope, minor difference.
