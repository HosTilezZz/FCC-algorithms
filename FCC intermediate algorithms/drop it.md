**old solution:**
```javascript
function dropElements(arr, func) {
	while (arr.length>0 && !func(arr[0])) {
		arr.shift();
	}
	return arr;
}
```

**new solution:**
```javascript
function dropElements(arr, func) {
    var result = [];
    for (var i=0 ; i<arr.length ; i++) {
        if (func(arr[i])) { result = arr.slice(i); break;}
    }
    return result;
}
```
**comment:**

the old solution is better
