**old solution:**
```javascript
function chunkArrayInGroups(arr, size) {
    var original = arr;
    var collector = [];
    var starter = 0;
    counter = 0;
    while (counter < arr.length/size) {
        var adder = arr.slice(starter,starter+size);
        Array.prototype.push.apply(collector, [adder]);
        counter++;
        starter = starter + size;
    }   
    return collector;
}
```

**new solution:**
```javascript
function chunkArrayInGroups(arr, size) {
    var result = [];
    for (i=0 ; i<arr.length ; i+=size){
        result.push(arr.slice(i,i+size));
    }
    return result;
}
```
**comment:**

obviously, the new solution is cleaner, i kind of created my own initializer and final expression with the "starter"
and "counter" variables in the old solution, not using the push() method directly with the "collector" array is also
something i didn't like. 
