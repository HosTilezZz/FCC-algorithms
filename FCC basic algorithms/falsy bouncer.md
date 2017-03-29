**old solution:**
```javascript
function bouncer(arr) {
var filtered = arr.filter(cleaner);
return filtered;
}      
function cleaner(value) {
        if (value === false ||
            value === null ||
            value === "" ||
            value !== value ||
            value === 0 ||
            value === undefined) {
                return false;
            }
        else {return true;}
}
```

**new solution:**
```javascript
function bouncer(arr) {
    var falseySquad = [false, null, 0, "", undefined];
    var result = arr.filter(function(val) {
            if (falseySquad.indexOf(val) !== -1 || val !== val) {
                return false;
            }
        return true;
    });
    return result;
}
```
**comment:**

the old solution is easier to read, but i just don't feel comfortable listing all the falsey values like that, the idea behind
this algorithm challenge is to introduce the student to falsey values and the fact that NaN is the only value that doesn't
equal itself.

