**old solution:**
```javascript
function uniteUnique(arr) {
	var result =[];
	for (var key in arguments) {
		if (arguments.hasOwnProperty(key)) {
			arguments[key].forEach(plug);
		}
	}
    
	function plug (num) {
		if (result.indexOf(num) === -1) {
			result.push(num);
		}
	}	
	return result;
}
```

**new solution:**
```javascript
function uniteUnique(arr) {
    var result = [];
    [...arguments].forEach(function checkMe(val) {
        for (var i=0 ; i<val.length ; i++) {
            if (result.indexOf(val[i])===-1) { result.push(val[i]); }
        }
    });
    return result;
}
```
**comment:**

the new solution is more straightforward, minor difference.
