**old solution:**
```javascript
function binaryAgent(str) {
	var result = "";
	for ( var i=0 ; i<str.length ; ) {
		if (str[i] === " ") {
			i++;
			continue;
		}
		else {
			result += String.fromCharCode(parseInt(str.slice(i,i+8),2));
			i += 8;
		}
	}
	return result;
}
```

**new solution:**
```javascript
function binaryAgent(str) {
    var array = str.split(" ").map(function convert(val) {
       return String.fromCodePoint(parseInt(val, 2)); 
    });
    return array.join("");
}
```
**comment:**

both solutions are using the same approach, passing every 8-bit to the praseInt() method with a base of 2, and then
passing the result as the argument of fromCodePoint() method
