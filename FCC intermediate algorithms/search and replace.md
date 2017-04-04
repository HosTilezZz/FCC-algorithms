**old solution:**
```javascript
function myReplace(str, before, after) {
	var newStr = str.replace(before, replacer(before, after));
	return newStr;
}

function replacer (before, after) {
	var result = "";
	if (/[A-Z]/.test(before)) {
		result = after.charAt(0).toUpperCase() + after.slice(1);
	}
	else {
		result = after;
	}
	return result;
}
```

**new solution:**
```javascript
function myReplace(str, before, after) {
    var result = str.replace(before, function caseCheck() {
       if (/[A-Z]/.test(before[0])) {
           return after = after[0].toUpperCase() + after.slice(1);
       }
        return after;
    });
    return result;
}
```
**comment:**

passed a named function expression as the second argument in the new solution instead, minor difference.
