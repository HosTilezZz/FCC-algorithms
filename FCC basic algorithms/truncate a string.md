**old solution:**
```javascript
function truncateString(str, num) {
    var cut;
    if (num <= 3) {
        cut = str.slice(0,num);
        cut = cut + "...";
    }
    else if(num > 3) {
        if (num >= str.length) {
        cut = cut + "...";
        cut = str.slice(0,num);
    }
        else {
        cut = str.slice(0,num-3);
        cut = cut + "...";   
         
        }
    }
      return cut;
}
```

**new solution:**
```javascript
function truncateString(str, num) {
    var result = "";
    if (str.length <= num) {
        return str;
    }
    else if (num > 3) {
        result = str.slice(0, num-3) + "...";
        return result;
    }
    else {
        result = str.slice(0, num) + "...";
        return result;
    }
}
```
**comment:**

used return after the end of every condition instead of just putting it in the end, minor difference .

