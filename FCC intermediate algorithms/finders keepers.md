**old solution:**
```javascript
function findElement(arr, func) {
	var result = arr.filter(func);
  return result[0];
	}
```

**new solution:**
```javascript
function findElement(arr, func) {
	return result = arr.filter(func)[0];
	}
```
**comment:**

the challenge is too simple to say anything
