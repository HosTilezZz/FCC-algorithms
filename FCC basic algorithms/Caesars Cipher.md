**old solution:**
```javascript
function rot13(str) {
    var results = "";
    for (i=0 ; i<str.length ; i++) {
        var required = str.charCodeAt(i);
        if (required >= 65 && required <91 ) {
            if (required - 13 >= 65) {
                results = results + String.fromCharCode(required-13);
            }
            else {results = results + String.fromCharCode(required+13);}          
        }               
        else {results = results + String.fromCharCode(required);}
    }  
    return results;  
}
```

**new solution:**
```javascript
function rot13(str) {
    var result = "";
    for (var i = 0 ; i<str.length ; i++ ) {
        var char = str.charAt(i);
        var charCode = str.charCodeAt(i);
        if(/[A-Z]/.test(char)) {
            if (charCode+13 > 90) {
                result += String.fromCharCode(charCode-13);
            }
            else {
                result += String.fromCharCode(charCode+13);
            }
           }
        else {
            result += str.charAt(i);
        }
    }
    return result;
}
```
**comment:**

the new solution is a bit better, the test() method is easier to understand than using multiple if conditions and
logical operators.

