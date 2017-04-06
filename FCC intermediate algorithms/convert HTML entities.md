**old solution:**
```javascript
function convertHTML(str) {
	var pattern =  /[<>&'"]/g;
	function checkMe (symbol) {
		switch (symbol) {
			case "&":
				return "&amp;";
				
			case "<":
				return "&lt;";
				
			case ">":
				return "&gt;";
				
			case '"':
				return "&quot;";
				
			case "'":
				return "&apos;";
		}
		
	}
	var val = str.replace(pattern, checkMe);
	return val;
}
```

**new solution:**
```javascript
function convertHTML(str) {
    var result = str.replace(/[&<>\"\']/g, function checkMe(val) {
        switch (val) {
            case "&":
                return "&amp;";
            case "<":
                return "&lt;";
            case ">":
                return "&gt;";
            case "'" :
                return "&apos;";
            case "\"" :
                return "&quot;";
               }
    });
    return result;
}
}
```
**comment:**

exact same approach, minor difference
