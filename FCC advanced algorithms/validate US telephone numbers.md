**solution:**
```javascript
function telephoneCheck(str) {
    if (/[^0-9-() ]/.test(str)) { return false; }
    if (/[\()]/.test(str)) {
        if (/\([\d]{3}\)/.test(str)) {
            return secondStage();
        }
        return false;
    }
    return secondStage();
    
    function secondStage() {
        if (str[0] !== "-" && str[str.length-1] !== "-" && 
            !/\-(?=\-)/.test(str)) {
        var numArr = str.split("").filter(function cleaner(val) {
            return (/[\d]/.test(val));
        });
        if (numArr.length===10) {return true;}
        if (numArr.length===11 && numArr[0]==="1") {return true;}
        }
        return false;
    }
}
```

**comment:**

i'm not very happy with solution, but this challenge made me a bit more comfortable with regexp, the following table explains
each regexp used:

| RegExp        | Pattern           |
| ------------- |:-------------:|
| [^0-9-() ]      | anything that isn't a number (0-9), a hyphen "-" or parentheses "(" ")" |
| [\()]      | parentheses "(" ")" |
| \([\d]{3}\) | a single parentheses "(" followed by 3 numbers and then by a single closing parentheses ")"      |
| \-(?=\-)      | a hyphen "-" followed by another hyphen |
| [\d]      | any number |
