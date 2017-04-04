**old solution:**
```javascript
function fearNotLetter(str) {
	var letter, i;
	for( i=1 ; i<str.length ; i++) {
		var comp = (str.charCodeAt(i-1)+1);
		if (str.charCodeAt(i) !== comp) {
			letter = String.fromCharCode(comp);
		}
	}
	return letter;
}
```

**new solution:**
```javascript
function fearNotLetter(str) {
    for (var i=0 ; i<str.length-1 ; i++) {
        if (str.charCodeAt(i+1) !== str.charCodeAt(i)+1) {
            return String.fromCharCode(str.charCodeAt(i)+1);
        }
    }
    return undefined;
}
```
**comment:**

identical solutions.
