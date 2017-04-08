**old solution:**
```javascript
function truthCheck(collection, pre) {
	var result = collection.map(checkMe);
	if (result.indexOf(false) !== -1) {
		return false;
	}
	else {
		return true;
	}
	
	function checkMe(currentValue) {
		if (currentValue[pre]) {
			return true;
		}
		return false;
	}
}
```

**new solution:**
```javascript
function truthCheck(collection, pre) {
    for (var i=0; i<collection.length ; i++) {
        if(!collection[i].hasOwnProperty(pre) || !collection[i][pre]) {
            return false;
        }
    }
    return true;
}
```
**comment:**

the new solution is better as it stops immediately after finding the finding a falsy value or not finding the property at all
in the first place.
