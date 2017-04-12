**solution:**
```javascript
function sym(args) {
    var argsArr = Array.from(arguments); 
    
    function diff(arr1, arr2) {
        if ( !arr2 ) { return arr1; }
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
        argsArr.shift();
        argsArr.shift();
        argsArr.push(result);
        return diff(argsArr[0],argsArr[1]);
    }
    return diff(argsArr[0],argsArr[1]);
}
```

**comment:**

the idea of this challenge is to make you more comfortable with reduce() method which i'm not even using here, i might add
a different solution later.
