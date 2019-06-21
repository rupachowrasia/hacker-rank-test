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
 
