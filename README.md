# hacker-rank-test
#### **1. Complete the sockMerchant function below**
```sh
function sockMerchant(n, ar) {
    var gObj = {};
    var count = 0;
    if (n >= 1 && n <= 100) {
        for (var i = 0; i < ar.length; i++){
            var key = ar[i];
            if (!gObj.hasOwnProperty(key)) {
                gObj[key] = 1;
            } else {
                gObj[key] = gObj[key] + 1;
            }
        }
        for (var num in gObj) {
            count+= Math.floor(gObj[num] / 2);
        }
        return count;  
    }
}
```
#### **2. Complete the pageCount function below**
```sh
function pageCount(n, p) {
    if (n >= 1 && n <= 100000) {
        var gArr = [];
        gArr[0] = [1];
        var temp = 1;
        for (var i = 1; i <= n / 2; i++) {
            var elm1 = temp + 1;
            var elm2 = elm1 + 1;
            temp = elm2;
            if (elm1 <= n & elm2 <= n) {
                gArr[i] = [elm1, elm2];
            } else if (elm1 <= n & elm2 >= n) {
                gArr[i] = [elm1];
            }
        }
        if (p > n / 2) {
            gArr.reverse();
        } 
        for (var num in gArr) {
            var arr = gArr[num];
            if (arr.indexOf(p) != -1) {
                return num;
            }      
        }
    }
}
```

#### **3. Complete the countingValleys function below**
```sh
function countingValleys(n, s) {
    let seaLevel = 1;
    let up_down = 1; 
    let totalVally =0;
    var gArr = Array.from(s); // convert string to array
    gArr.forEach(function (x) {
        if (x == 'U') {
            up_down = up_down + 1; 
        } else {
            up_down = up_down - 1;
        } 

        if (x=='U' && up_down == seaLevel) {
            totalVally = totalVally + 1;
        } 
    });
    return totalVally; 
}
```

#### **4. Complete the jumpingOnClouds function below**
```sh
function jumpingOnClouds(c) {
    let totalJump = c.length;
    let jump = 0;
    let gArr = [];
    while (jump < totalJump) {
        if (c[jump + 2] == 0 && jump < totalJump) {
            jump = jump + 2;
            gArr.push(jump); 
        } else if (c[jump + 1] == 0 && jump < totalJump) {
            jump++;
            gArr.push(jump); 
        } else {
            break;
        }    
    }
    return gArr.length;
}
```

#### **5. Complete the repeatedString function below**
```sh
function repeatedString(s, n) {
    // better way, passed in all cases
    s = Array.from(s);
    let strLen = s.length;
    let s1Count = 0;
    let s2Count = 0;

    let s1 = Math.floor(n / strLen);
    let s2 = n % strLen;
    
    s.map(function (value, key) {
        if (value == 'a') {
            s1Count++;
        }
    });

    s.map(function (value, key) {
        if (value == 'a' && key<s2) {
            s2Count++;
        }
    });

    return (s1Count * s1) + s2Count;

    // bad way failed in some cases e.g: s = a and n = 1000000000000
    /*let gArr = [];
    let count = 0;
    let i = 0;

    while (i < n) {
        for (let j = 0; j < s.length; j++) {
                if (gArr.length < n) {
                    gArr.push(s[j]);
                } else {
                    break;
                }
                i++;
        }
    }
    gArr.map(function (e) {
        if (e == 'a') {
            count++;
        }
    });
    return count; */   
}
```

#### **6. Complete the birthdayCakeCandles function below**
```sh
function birthdayCakeCandles(ar) { 
    if (ar.length >= 1 && ar.length <= 1000000) {
        const max = Math.max(...ar);
        return ar.filter(x => x === max).length;
        // failed in some case
        /*ar.sort();
        let talestCandel = ar[ar.length - 1];
        let count = 0;
        ar.map((value, key) => {
            if (value == talestCandel) {
                count++;
            }
        });
        return count;*/  
    }
}
```

#### **7. Complete the alternatingCharacters function below**
```sh
function alternatingCharacters(s) {
    let s1 = [];
    for (let i = 0; i < s.length; i++) {
            if (s[i] == s[i + 1]) {
                s1.push(s[i]);
            }
    }
    return s1.length;
}
```

#### **8. Complete the libraryFine function below**
```sh
function libraryFine(d1, m1, y1, d2, m2, y2) {
    let fine = 0;

    if (d1 <= d2 && m1==m2 && y1==y2) {
        fine = 0;
    }
    else if (d1 > d2 && m1 == m2 && y1 ==y2) {
        fine = 15 * (d1-d2);
    }
    else if (m1 > m2 && y1 == y2) {
        fine = 500 * (m1 - m2);
    }
    else if (y1 > y2) {
        fine = 10000;
    }
    return fine;
}
```

#### **9. Complete the countApplesAndOranges function below**
```sh
function countApplesAndOranges(s, t, a, b, apples, oranges) {
    let appleCount = 0;
    let orangeCount = 0;

    let applesArr = apples.map(key => a + key);
    let orangesArr = oranges.map(key => b + key);

    applesArr.forEach(key => {
        if (key >= s && key <= t) {
            appleCount = appleCount + 1;
        }
    });
    orangesArr.forEach(key => {
        if (key >= s && key <= t) {
            orangeCount = orangeCount + 1;
        }
    });
    console.log(appleCount);
    console.log(orangeCount);
}
```

#### **10. Complete the simpleArraySum function below**
```sh
function simpleArraySum(ar) {
    let sum = 0;
    for (let i = 0; i < ar.length; i++){
        sum = sum + ar[i];
    }
    return sum;
}
```

#### **11. Complete the 'diagonalDifference' function below**
```sh
function diagonalDifference(n, arr) {
    let sumLeft = 0;
    let sumRight = 0;
    for (let i = 0; i < n; i++){
        sumLeft = sumLeft + arr[i][i];
    }

    for (let i = 0; i < n; i++) {
        sumRight = sumRight + arr[i][n-1-i];
    }

    return Math.abs(sumLeft - sumRight);
}
```

#### **12. Complete the getMoneySpent function below**
```sh
function getMoneySpent(keyboards, drives, b) {
    let totalCost = [];

    keyboards.forEach(keyboard => drives.forEach(drive => {
        totalCost.push(keyboard + drive)
    }));
    let cost = totalCost.filter(c => c <= b);

    return (Math.max(...cost) == '-Infinity') ? "-1" : Math.max(...cost);
}
```

#### **13. Complete the compareTriplets function below**
```sh
function compareTriplets(a, b) {
    let alice_count = 0;
    let bob_count = 0;
    for (let i = 0; i < a.length; i++){
        if (a[i] > b[i]) {
            alice_count = alice_count + 1;
        } else if (a[i] < b[i]) {
            bob_count = bob_count + 1;
        } else if (a[i] == b[i]) {

        }
    }
    return [alice_count, bob_count];
}
```

#### **14. Complete the aVeryBigSum function below**
```sh
function aVeryBigSum(ar) { 
    return ar.reduce((accumulator, currentValue) => accumulator + currentValue);
}
```

#### **15. Complete the plusMinus function below**
```sh
function plusMinus(arr) {
    let total = arr.length;
    let positive = 0;
    let negative = 0;
    let zeros = 0;
    for (let i = 0; i < arr.length; i++){
        if (arr[i] == 0) {
            zeros = zeros + 1; 
        }
        if (arr[i] > 0) {
            positive = positive + 1;
        }
        if (arr[i] < 0) {
            negative = negative + 1;
        }
    }
    console.log(positive / total);
    console.log(negative / total);
    console.log(zeros / total);
}
```

`summation formula: 
1+2+3+......20 = n(n+1)/2
1*2 + 2*2 + 3*2 + ........ n*2 = {n(n+1)(2n+1)}/6
1*3 + 2*3 + 3*3 + ........ n*3 = (n(n+1)/2)*2

tn = a + (n - 1)d;
sn = [2a+(n-1)d]n/2`

#### **16. Multiples of 3 and 5**
```sh
function main() {

    var BigNumber = require('bignumber.js'); // add this library

    var t = parseInt(readLine()); // given
    for (var a0 = 0; a0 < t; a0++) { // given
        var n = new BigNumber(readLine()); //given, just add new BigNumber instead of parseInt

        const a = n.minus(1).dividedBy(3).floor();
        const b = n.minus(1).dividedBy(5).floor();
        const c = n.minus(1).dividedBy(15).floor();
        const sum3 = a.times(3).times(a.plus(1)).dividedBy(2);
        const sum5 = b.times(5).times(b.plus(1)).dividedBy(2)
        const sum15 = c.times(15).times(c.plus(1)).dividedBy(2)
        const sum = sum3.plus(sum5).minus(sum15);
        console.log(sum.toString());

        // failed in some cases
        /*let arr = [];
        for (let i = 0; i < n; i++) {
            if (i % 3 == 0 || i % 5 == 0) {
                arr.push(i);
            }
        }
        let uniArr = [...new Set(arr)].reduce((x, y) => x + y);
        console.log(uniArr);*/
    }  
}
```

#### **17. Complete the bonAppetit function below**
```sh
function bonAppetit(bill, k, b) {
    let bActual = (bill.filter((value, index, arr) => index!=k)).reduce((x,y) => x+y)/2;
    if (b== bActual) {
        console.log("Bon Appetit");
    }
    if (b > bActual) {
        console.log(b - bActual);
    }
}
```





