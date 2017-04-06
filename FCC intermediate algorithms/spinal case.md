**old solution:**
```javascript
function spinalCase(str) {
	var result =  str.replace(/\s|_/g, "-");
	var capitalRegex = /[A-Z]/g;
	var pos;
	var what = "";
	var index = [];
	var extraLetters = 0;
	while ((pos=capitalRegex.exec(result)) !== null) {
		if (capitalRegex.lastIndex-2 >=0) {
		index.push(capitalRegex.lastIndex-2);
		}
	}
	for (var i=0 ; i<index.length ; i++) {
		position = index[i];
		if(result[position].search(/[a-z]|[1-9]|[@#!$&\-]/g) === -1) {
			result = result.slice(0, position+extraLetters+1) + "-" +
      result.slice(position+extraLetters+1);
			extraLetters++;
		}
		else if (result[position+extraLetters].search(/-/g) > -1) {
			continue;
		}
		else if(result[position].search(/[a-z]|[1-9]|[@#!$&]/g) > -1) {
			result = result.slice(0,position+extraLetters+1) + "-" + 
      result.slice(position+extraLetters+1);
			extraLetters++;
		}
	}
result = result.toLowerCase();
	return result;
}
```

**new solution:**
```javascript
function spinalCase(str) {
    return result = str.replace(/[A-Z]/g, function match(val) {
        return " " + val;
    }).split(/[-_\s]/g).filter(function cleaner(val) {
       if (val !== "") { return true; } 
    }).join("-").toLowerCase();
}
```
**comment:**

the new solution is a bit "hacky", if you will, as i'm adding a space before every capital letter in order to be keep them
after the split() method, i then filter out the empty array elements caused by the spaces i added using filter() method, but
it is still a lot better than the old solution, the new solution might be easier to read in the following format:
```javascript
function spinalCase(str) {
    var spaceAdded = str.replace(/[A-Z]/g, function match(val) {
        return " " + val;
    });
    var splitArr = spaceAdded.split(/[-_\s]/g).filter(function cleaner(val) {
       if (val !== "") { return true; } 
    });
    var result = splitArr.join("-").toLowerCase();
    return result;
}
```
