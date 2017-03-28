**new solution:**
```javascript
function findLongestWord(str) {
    wordsArr = str.split(" ");
    var result = 0;
    for (i=0 ; i<wordsArr.length ; i++) {
        if (wordsArr[i].length > result) {
            result = wordsArr[i].length;
        }
    }
    console.log(result);
    return result;
}
```
**comment:**

couldn't find the old solution.

