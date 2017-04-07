**old solution:**
```javascript
function sumPrimes(num) {
	var arr = [];
	var result = [];
	for( var i=2 ; i<=num ; i++) {
		arr.push(i);
	}
	function primeMe(currentValue) {
		for ( var j=2 ; j<=currentValue ; j++) {
			if (currentValue % j===0 && currentValue!==j ) {
				break;
			}
			else if (currentValue % j===0 && currentValue===j) {
				result.push(currentValue);
			}
		}
	}
	arr.forEach(primeMe);
	var total = result.reduce(function(a,b) {
		return a+b;
	});
	return total;
}
```

**new solution:**
```javascript
function sumPrimes(num) {
    var primes = [];
    for (i=2 ; i<=num ; i++) {
        for (var j=1, counter=1 ; j<=Math.floor(Math.sqrt(i)) ; j++) {
            if (i % j !== 0) { counter++; }
            if (counter===Math.floor(Math.sqrt(i))) { primes.push(i); }
        }
    }
    return primes.reduce(function sum(a, b) {
        return a+b;
    });
}
```
**comment:**

the new solution is easier to read, it also uses a more efficient approach. it's based on the fact that we only need
to test for factors less than or equal to the square root.
