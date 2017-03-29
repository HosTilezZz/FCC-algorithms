**old solution:**
```javascript
function repeatStringNumTimes(str, num) {
  var results = "";
  for (i=0 ; i<num ; i++)
    {
      results = results + str;
    }
  return results;
}
```

**new solution:**
```javascript
function repeatStringNumTimes(str, num) {
    var result = "";
    if (num > 0) {
        for (i=0 ; i<num ; i++) {
            result = result + str;
        } 
    }
    else {
        return "";
    }
    return result;
}
```
**comment:**

added a check to see if num > 0, minor difference.

