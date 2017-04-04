**old solution:**
```javascript
function translatePigLatin(str) { 
	var result = "";
	if (/[auioe]/.test(str.charAt(0))) {
		result = str + "way";
		return result;
	}
	else {
		var index = str.search(/[auioe]/);
		result = str.slice(index) + str.slice(0,index) + "ay";
		return result;
	}
}
```

**new solution:**
```javascript
function translatePigLatin(str) {
    if (/[aiuoe]/.test(str[0])) {
        return str + "way";
    }
    var index = str.search(/[aiuoe]/);
    return str.slice(index) + str.slice(0,index) + "ay";
}
```
**comment:**

using bracket notation with strings in the new solution instead of charAt() method, minor difference.
