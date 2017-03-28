**old solution:**
```javascript
function factorialize(num) {
  var total = 1;
  for (i=1; i<=num; i++) {
    total = total * i;
  }
  return total;
}
```

**new solution:**
```javascript
function factorialize(num) {
    var result = 1;
    for (i=num ; i>0 ; i--) {
        result *= i;
    }
    return result;
}
```
**comment:**

minor difference, i probably used i++ in the old solution because the whole "(i=0 ; i<>x ; i++)" format was stuck in my head.

