**old solution:**
```javascript
function booWho(bool) {
	var i = false;
	if (bool===true || bool===false) {
		i=true;
	}
  return i;
}
```

**new solution:**
```javascript
function booWho(bool) {
    return (typeof bool === "boolean");
}
```
**comment:**

the new solution is better, using the typeof operator is a better way to check for the type of a value.
