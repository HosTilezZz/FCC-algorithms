**old solution:**
```javascript
function steamrollArray(arr) {
	var result =[];
	arr.map(checkFirst);
  	return result;
  	
	function checkFirst (element) {
		if (!Array.isArray(element)) {
			result.push(element);
		}
		else {
			element.forEach(checkMe);
		}
	}
    
	function checkMe (currentValue) {
		if (Array.isArray(currentValue)) {
			checkFirst(currentValue);
		}
		else {
			result.push(currentValue);
		}
	}
}
```

**new solution:**
```javascript
function steamrollArray(arr) {
    var result = [];
    for (var j=0 ; j<arr.length ; j++) {
        var currentElem = arr[j];
        checkMe(currentElem);
    }
     
    function checkMe(val) {
        if (!Array.isArray(val)) { result.push(val); }
        if (val !== undefined && val !== null && typeof val !== "string") {
            for (var i=0; i<val.length ; i++) {
                checkMe(val[i]);
            }
        }
    }
    return result;
}

```
**comment:**

the old solution is better, after solving this algorithm i ended up with a code that is identical to the old solution, so i
felt like trying to solve it using loops, i don't know why but ... for some reason i find this challenge quite fun.
