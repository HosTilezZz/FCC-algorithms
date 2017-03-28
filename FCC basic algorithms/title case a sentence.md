**old solution:**
```javascript
function titleCase(str) {
    str = str.toLowerCase();
    var words = str.split(" ");
    for (i=0 ; i<words.length ; i++) {
        words[i] = words[i].charAt(0).toUpperCase() + words[i].substr(1);
    }
    var stringed = words.toString();
    stringed = stringed.replace(/[,]/g," ");
    return (stringed);

}
```

**new solution:**
```javascript
function titleCase(str) {
    var splitArr = str.split(" ");
    var capitalizedArr = splitArr.map(function(val) {
       var capitalized = val.toLowerCase();
        capitalized = capitalized[0].toUpperCase() + capitalized.substring(1);
        return capitalized;
    }); 
    var result = capitalizedArr.join(" ");
    return result;
}
```
**comment:**

used map instead of the for loop, i was actually going to use a for loop again, but i forced myself to use map to get
comfortable with it, i don't like the usage of toString in the old solution,  i do however prefer the usage of charAt in the old solution, because using bracket notation with strings doesn't work in IE7, it's not a huge disadvantage nowadays, but it's still something.

