**old solution:**
```javascript
function updateRecords(id, prop, value) {
  if(prop != "tracks" && value !== "") {
    collection[id][prop] = value;
    return collection;
  }
  else if (prop == "tracks" && collection[id].hasOwnProperty("tracks") === false) {
    collection[id].tracks = [ ];
    collection[id].tracks.push(value);  
    return collection;
  }
  else if(prop == "tracks" && value !== "" ) {
    collection[id][prop].push(value);
    return collection;
  }
  else if (value === "") {
    delete collection[id][prop];
    return collection;
  }
  return collection;
}
```

**new solution:**
```javascript
function updateRecords(id, prop, value) {
    if (!value) {
        delete collection[id][prop];
        return collection;
    }
    if (prop==="tracks") { 
        if (collection[id].hasOwnProperty("tracks")) {
            collection[id]["tracks"].push(value);
            return collection;
            }
        else {
            collection[id]["tracks"]=[value];
            return collection;
        }
    }
    else {
        collection[id][prop]=value; 
        return collection;
    }
}
```
**comment:**

the new solution is a bit better, the point of this challenge is to get you a bit more comfortable with "complex objects
manipulation".
