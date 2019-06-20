# hacker-rank-test
## 1.
// Complete the sockMerchant function below.
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
