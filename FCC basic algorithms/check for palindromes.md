**old solution:**
```javascript
function palindrome(str) {
  str = str.replace (/\W/g,"");
  str = str.replace("_","");
  str = str.toLowerCase();
  str = str.replace(/\s/g,"");
  var word = str.split("");
  word = word.reverse();
  word = word.join("");
  
  if (word==str) {
    return true;
  }
  else {
    return false;
  }
}
```

**new solution:**
```javascript
function palindrome(str) {
    var cleanString = str.replace(/[^A-Za-z0-9]/g, "");
    cleanString = cleanString.toLowerCase();
    var reversedString = cleanString.split("");
    reverseString = reversedString.reverse();
    reversedString= reversedString.join("");
    if (cleanString === reversedString) {
        return true;
    }
    else {
        return false;
    }
}
```
**comment:**

used a characters set that includes "underscore" instead of doing multiple replace methods with character Classes.

