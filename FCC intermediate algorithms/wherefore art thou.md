**old solution:**
```javascript
function whatIsInAName(collection, source) {
  var result = [];
  function propCheck(element) {
    var props = Object.keys(source);
    var i;
    var counter = 0;
    for ( i=0 ; i<props.length ; i++ ) {
        if (element.hasOwnProperty(props[i]) === true) {
        	if (element[props[i]] === source[props[i]]) {
        		counter++;
        	}
        	else {
        		break;
        	}
        }
        else {
        	break;
        }
    }
    if (counter === props.length) {
    result.push(element);	
    }    
  }
    collection.forEach(propCheck);
  return result;
}
```

**new solution:**
```javascript
function whatIsInAName(collection, source) {
    var result = [];
    var arr = Object.keys(source);
    for (var prop in collection) {
            for (var i=0, counter=0 ; i<arr.length ; i++) {
                if (collection[prop].hasOwnProperty(arr[i]) && collection[prop][arr[i]]===source[arr[i]]) {
                counter++;
                }
                if (counter===arr.length) {
                result.push(collection[prop]);
                }
            }
    }
    return result;
}
```
**comment:**

both solutions are using the same approach, i do however find that the old solution is easier to read.
