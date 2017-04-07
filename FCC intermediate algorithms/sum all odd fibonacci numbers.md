**old solution:**
```javascript
function sumFibs(num) {
    var myArray = [1,1];
    var total = 0;
    while (myArray[myArray.length-1] + myArray[myArray.length-2]<=num) {
        total = myArray[myArray.length-1] + myArray[myArray.length-2];
        myArray.push(total);
    }
    var odd = myArray.map(function(currentValue) {
        if (currentValue % 2 === 1) {
            return currentValue;
        }
    });
    var filtered = odd.filter(function(value) {
        if (value !== undefined) {
            return value;
        }
    });
    var result = filtered.reduce(function(a, b) {
     return a + b;
    }, 0);
    return result;
}
```

**new solution:**
```javascript
function sumFibs(num) {
    var fib = [1,1], result = 0;
    for (i=1 ; fib[i]+fib[i-1]<=num ; i++) {
        fib.push(fib[i]+fib[i-1]);
    }
    for (j=1 ; typeof fib[3*j-3]==="number" ; j++) {
        result += fib[3*j-3];
        if (typeof fib[3*j-2]==="number") { result += fib[3*j-2]};
    }
    return result;
}
```
**comment:**

the new solution is easier to read and performs faster as well, the approach of the new solution is that Fibonacci numbers
follow an [odd,odd,even] pattern, which means that 3n-3 and 3n-2 indices are always going to be odd, there is also the common
solution which goes like this:
```javascript
function sumFibs(num) {
    var fib = [1,1], result = 0;
    for (i=1 ; fib[i]+fib[i-1]<=num ; i++) {
        fib.push(fib[i]+fib[i-1]);
    }
    for (i=0 ; i<fib.length ; i++) {
        if (fib[i]%2===1) { result += fib[i]; }
    }
    return result;
}
```
