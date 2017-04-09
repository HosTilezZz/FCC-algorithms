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
this challenge made me a bit more comfortable with regexp, i included a flowchart explaining the algorithm as well
