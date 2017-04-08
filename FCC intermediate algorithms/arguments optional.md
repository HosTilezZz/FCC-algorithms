**old solution:**
```javascript
function addTogether(firstTime) {
	if (arguments.length==2) {
		if (typeof arguments[0]==="number" && typeof arguments[1]==="number") {
		return arguments[0]+arguments[1];
		}
		return undefined;
	}
	else {
		if (typeof arguments[0]==="number") {
			return function (secondTime) {
				if (typeof firstTime ==="number" && typeof secondTime ==="number") {
					return firstTime+secondTime;
				}
			return undefined;
			};
		}
	}
}
```

**new solution:**
```javascript
function addTogether() {
    if (arguments.length===2 && typeof arguments[0]==="number" && typeof arguments[1]==="number") {
        return arguments[0]+arguments[1];
    }
    if (arguments.length===1 && typeof arguments[0]==="number") {
        var x = arguments[0];
        return function(num) {
            if (typeof num==="number") { return num + x; }
        };
    }
    else { return undefined; }
}
```
**comment:**

in the new solution, if only one number has been passed, it is assigned to x, while the old solution pre-defined as a the
function parameter in the very first line.

