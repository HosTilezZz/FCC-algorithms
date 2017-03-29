**old solution:**
```javascript
function largestOfFour(arr) {
    var results = [];
    for (i=0 ; i<arr.length ; i++) {
        for (j=0 ; j<arr[i].length ; j++) {
            if (results.length == i) {
                var emptyadder = results.push(arr[i][j]);
            }
            else if (arr[i][j] > results[i]) {
                results.pop();
            var adder = results.push(arr[i][j]);
            }
        }
    }
    return results;
}
```

**new solution:**
```javascript
function largestOfFour(arr) {
    var result = arr.map(function(val) {
        var largestNumber = 0;
        for (i=0 ; i<val.length ; i++) {
            if (val[i]>largestNumber) {
                largestNumber = val[i];
            }
        }
        return largestNumber;
    });
    return result;
}
```
**comment:**

i really don't like the old solution, the idea is obviously the same since the algorithm is too simple to have any real
difference in the used approach, but the nested for loop is really unneccsaary and uncomfortable to read, at least for me.

