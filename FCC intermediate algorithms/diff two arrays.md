**old solution:**
```javascript
function diffArray(arr1, arr2) {
    var results = [];   
        for (j=0 ; j<arr1.length ; j++) {
            var counter1=0;
            for (i=0 ; i<arr2.length ; i++) {
                if (arr1[j]==arr2[i]) {
                counter1++;
                }
            }
            if (counter1===0) {
                results.push(arr1[j]);
            }
        }
        for (j=0 ; j<arr2.length ; j++) {
            var counter2=0;
            for (i=0 ; i<arr1.length ; i++) {
                if (arr2[j]==arr1[i]) {
                counter2++;
                }
            }
            if (counter2===0) {
                results.push(arr2[j]);
            }
        }
    
    return results;
}
```

**new solution:**
```javascript
function diffArray(arr1, arr2) {
    var result = arr1.filter(compareMe.bind(null, arr2));
    result = [...result,...arr2.filter(compareMe.bind(null, arr1))];
    return result;
    
    function compareMe(b, val) {
        for (var i=0 ; i<b.length ; i++) {
            if (val === b[i]) { return false; }
        }
        return true;
    }
}
```
**comment:**

anyone who is fammiliar with the bind() method and spread syntax should find the new solution to be better, i did however overcomplicate things with this solution.
