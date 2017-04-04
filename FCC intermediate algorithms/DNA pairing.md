**old solution:**
```javascript
function pairElement(str) {	
	var myArray = str.split("");
	var i;
	for( i=0 ; i<myArray.length ; i++) {
		myArray[i] = myArray[i].split("");
	}
	
	function pairMe(currentValue, index, array) {
		if (currentValue[0] === "G") {
			array[index].push("C");
		}
		else if (currentValue[0] === "C") {
			array[index].push("G");
		}
		else if (currentValue[0] === "A") {
			array[index].push("T");
		}
		else if (currentValue[0] === "T") {
			array[index].push("A");
		}	
	}
	myArray.map(pairMe);
	return myArray;
}
```

**new solution:**
```javascript
function pairElement(str) {
    var result=[];
    for (var i=0 ; i<str.length ; i++) {
        switch (str[i]) {
            case "G":
                result.push(["G","C"]);
                break;
            case "C":
                result.push(["C","G"]);
                break;
            case "A":
                result.push(["A","T"]);
                break;
            case "T":
                result.push(["T","A"]);
                break;
                      }
    }
    return result;
}
```
**comment:**

i'm quite sure that i forced myself to use map() method in the old solution to get more comfortable with it back then, the
new solution is easier to read.
