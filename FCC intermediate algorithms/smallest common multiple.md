**old solution:**
```javascript
function smallestCommons(arr) {
	var minNum = Math.min(arr[0],arr[1]);
	var maxNum = Math.max(arr[0],arr[1]);
	var myArgs = [];
	for ( var i=minNum ; i<=maxNum ; i++) { myArgs.push(i); }
	return lcmm(myArgs);
}

function gcd(a,b) {
	var t;
	while (b!==0) {
		t = b;
		b = a % b;
		a = t;
	}
	return a;
}

function lcm(a,b) {
	return ((a*b)/gcd(a,b));
}

function lcmm(args){
    if(args.length == 2){
        return lcm(args[0], args[1]);
    } else {
        var arg0 = args[0];
        args.shift();
        return lcm(arg0, lcmm(args));
    }
}
```

**new solution:**
```javascript
function smallestCommons(arr) {
    var range = [], num=Math.min(arr[0],arr[1]), max=Math.max(arr[0],arr[1]);
    for ( num ; num<=max ; num++) { range.push(num); }
    
    function recur(elems) {
        if (elems.length!==2) {
            var elem = elems[elems.length-1];
            elems.pop();
            return lcm(elem, recur(elems));
        }
        else {
            return lcm(elems[0],elems[1]);
        }
    }

    function lcm(a,b) {
        return a*b/gcd(a,b);
    }
      
    function gcd(a,b) {
        while (a!==b) {
            if (a>b) { a=a-b; }
            else { b=b-a; }
        }
        return a;
    }
    return recur(range);
}
```
**comment:**

both solutions are using the exact same approach, using the "Reduction by the greatest common divisor" method and then
calculating the GCD using the Euclidean algorithm.
