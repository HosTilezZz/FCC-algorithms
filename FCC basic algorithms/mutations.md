**old solution:**
```javascript
function mutation(arr) {
    lowered = [];
    for (i=0 ; i<arr.length ; i++) {
        lowered.push(arr[i].toLowerCase());
    }   
    for (i=0 ; i<lowered[1].length ; i++) {
        var log = 0;
        var breaker = 0;
        for (j=0 ; log !== -1 ; j++ ) {
        var letter = lowered[1][j];
            if (breaker == lowered[1].length ) {
                return true;
            }
            else {
            log = lowered[0].indexOf(letter);
            breaker++;
            }
    }
    return false;
        }
}
```

**new solution:**
```javascript
function mutation(arr) {
    var word = arr[0].toLowerCase();
    var letters = arr[1].toLowerCase();
    for (i=0 ; i<letters.length ; i++) {
        if (word.indexOf(letters[i])===-1) {
            return false;
        }
    }
    return true;
}
```
**comment:**

the approach in the new solution is better, it's a lot easier to focus on NOT finding all letters, thus returning
a false value.

