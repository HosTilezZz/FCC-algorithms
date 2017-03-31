**old solution:**
```javascript
function getIndexToIns(arr, num) {
    var value = arguments[1];
    var index = 0;
    arr.sort(compareNumbers);
    for (i=0 ; i<arr.length ; i++) {
        if (value > arr[i]) {
            if (value == arr[i]) {
            }
        else {
            index = i+1;
        }
        }
    }
    arr.splice(index, 0, value);
    return arr.indexOf(value);
}

function compareNumbers(a, b) {
  return a - b;
}

```

**new solution:**
```javascript
function getIndexToIns(arr, num) {
    var sortedArr = arr.sort(function(a, b) {
        return a-b;
    });
    var result = 0;
    for (i=0 ; i<sortedArr.length ; i++) {
        result = num > sortedArr[i] ?  i+1 : result;
    }
    return result; 
}
```
**comment:**

the new solution is just shorter, the approach is exactly the same, minor difference.

