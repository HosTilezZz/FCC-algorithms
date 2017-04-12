**solution:**
```javascript
function sym(args) {
    var argsArr = Array.from(arguments);
    while (argsArr.length>1) {
        var diffArr = diff(argsArr[0],argsArr[1]);
        argsArr.shift();
        argsArr.shift();
        argsArr.push(diffArr);
    }
    
    function diff(arr1, arr2) {
        var result = [];
        for (var i=0 ; i<arr1.length ; i++) {
            if (arr2.indexOf(arr1[i])===-1 && result.indexOf(arr1[i])===-1) {
                result.push(arr1[i]);
            }
        }
        for (var j=0 ; j<arr2.length ; j++) {
            if (arr1.indexOf(arr2[j])===-1 && result.indexOf(arr2[j])===-1) {
                result.push(arr2[j]);
            }
        }
        return result;
    }
    return argsArr[0].sort(function compare(a, b) {
        return a-b;
    });
}
```

**comment:**

this solution is too simple, the idea of this challenge is to make you more comfortable with the reduce() method, i'll be
adding more solutions later
