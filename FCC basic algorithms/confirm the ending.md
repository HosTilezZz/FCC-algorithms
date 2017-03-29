**old solution:**
```javascript
function confirmEnding(str, target) {
    var single = str.substring(str.length-target.length);
    console.log(single);
    if (single == target) {
        return true;
    }
    else {
        return false;
    }
}
```

**new solution:**
```javascript
function confirmEnding(str, target) {
      var strEnding = str.substr(-(target.length));
      var result = (strEnding===target);
      return result;
}
```
**comment:**

using substr() negative index number to count from the ending of the string instead of using substring, a minor difference .

