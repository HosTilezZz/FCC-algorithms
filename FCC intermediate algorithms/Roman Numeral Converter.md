**old solution:**
```javascript
function convertToRoman(num) {
	numString = num.toString();
	numArray = numString.split("");
	var result = "";
	console.log(numArray);
	var counter = 4-numArray.length;
	for (i=0 ; i<numArray.length ; i++) {
		if (numArray.length == 4 && counter===0 ) {
			if (numArray[i] < 4) {
				result = result + "M".repeat(numArray[i]);
				counter++;
				continue;
			}
		}
		if (numArray.length >= 3 && counter===1) {
			if (numArray[i] == 9) {
				result = result + "CM";
				counter++;
				continue;
			}
			else if (numArray[i] >= 5 && numArray[i] < 9) {
				result = result + "D" + "C".repeat(numArray[i]-5);
				counter++;
				continue;
			}
			else if (numArray[i] == 4) {
				result = result + "CD";
				counter++;
				continue;
			}
			else if (numArray[i] < 5 && numArray[i] !== 4) {
				result = result + "C".repeat(numArray[i]);
				counter++;
				continue;
			}
		}
		if (numArray.length >=2 && counter===2) {
			if (numArray[i] == 9) {
				result = result + "XC";
				counter++;
				continue;
			}
			if (numArray[i] >= 5 && numArray[i] <9) {
				result = result + "L" + "X".repeat(numArray[i]-5);
				counter++;
				continue;
			}
			if (numArray[i] == 4) {
				result = result + "XL";
				counter++;
				continue;
			}
			if (numArray[i] < 4) {
				result = result + "X".repeat(numArray[i]);
				counter++;
				continue;
			}
		}
			if (numArray.length >=1 && counter===3) {
			if (numArray[i] == 9) {
				result = result + "IX";
				counter++;
				continue;
			}
			if (numArray[i] >= 5 && numArray[i] < 9) {
				result = result + "V" + "I".repeat(numArray[i]-5);
				counter++;
				continue;
			}
			if (numArray[i] == 4) {
				result = result + "IV";
				counter++;
				continue;
			}
			if (numArray[i] < 4) {
				result = result + "I".repeat(numArray[i]);
				counter++;
				continue;
			}
		}
	}
  return result;
}
```

**new solution:**
```javascript
function convertToRoman(num) {
    var romans = [
        ["I","II","III","IV","V","VI","VII","VIII","IX"],
        ["X","XX","XXX","XL","L","LX","LXX","LXXX","XC"],
        ["C","CC","CCC","CD","D","DC","DCC","DCCC","CM"],
        ["M","MM","MMM"]
    ];
    var number = num.toString().split(""), result="";
    for (let i=number.length, counter=0 ; i>0 ; i--, counter++) {
        if (number[counter] > 0) {
        result += romans[i-1][number[counter]-1];
        }
    }
    return result;
}
}
```
**comment:**

i'm quite disappointed with both of my solutions, in my opinion, the first one is difficult to read, and the second one just
provides an array that has all the required strings, which makes it difficult to increase the range of numbers accepted by
this function, i've tried a few different approaches but it seems that i always end up with "unpleasant-looking" code.
