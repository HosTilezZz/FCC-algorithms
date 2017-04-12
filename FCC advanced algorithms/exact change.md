**solution:**
```javascript
function checkCashRegister(price, cash, cid) {
    var change = (cash - price)*100, result = [], acc = 0, left = 0;
    var values = [10000,2000,1000,500,100,25,10,5,1];
    cid.reverse().map(function calc(val, index) {
        val[1] *= 100;
        var pushMe = [val[0], 0];
        while (val[1] > 0 && acc + values[index] <= change) {
            val[1] -= values[index];
            pushMe[1] += values[index] / 100;
            acc += values[index];
        }
        if (pushMe[1] > 0) {
            result.push(pushMe);
            if (pushMe[1] < val[1] / 100) { left++; }
        }
    });
    if (change > acc) { return "Insufficient Funds"; }
    if (!left) { return "Closed"; }
    return result;
}
```

**comment:**

i did all my calculation in cents to avoid floating-point sum errors, the approach is rather imperative, but is still
acceptable in my opinion.
