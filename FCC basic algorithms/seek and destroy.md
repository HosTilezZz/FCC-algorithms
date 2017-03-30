**old solution:**
```javascript
var argnum;
var args;
var compareMe;
function destroyer(arr) {
    argnum = arguments.length-1;
    args = Array.from(arguments);
    args.shift();
    compareMe = Array.from(arguments[0]);
    var filtered = compareMe.filter(cleaner);
    return filtered;
}
function cleaner(value) {
    for (i=0; i<argnum ; i++) {
        if (value == args[i]) {
            return false;
        }
    }
    return true;
}
```

**new solution:**
```javascript
function destroyer(arr) {
    var completeArr = Array.from(arguments);
    var mainArr = completeArr[0];
    var checkList = completeArr.slice(1);
    var result = mainArr.filter(function(val) {
        for (i=0;i<checkList.length;i++) {
        if (val === checkList[i]) {
            return false;
        }
        }
        return true;
    });
  return result;
}
```
**comment:**

i think that i declare way too many variables in most of my solutions, the new solution is a better, but i still believe
that the optimal code should be something like this:

```javascript
function destroyer(arr) {
  var output = Array.prototype.slice.call(arguments, 1);
  return arr.filter(function destroy(value) {
    return output.indexOf( value ) < 0;
  });
}
```

