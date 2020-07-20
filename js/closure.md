# closure

## 私有變數
此處 value 就成了私有變數
```javascript
let Counter = function () {
    let value = 0;
    return {
        value: function () {
            return value;
        },
        increment: function () {
            value += 1;
        },
    };
};

const counter = Counter();

console.log(counter.value());
// Output: 0

counter.increment();
console.log(counter.value());
// Output: 1
```

## 擁有記憶功能的 function
利用閉包裡的 variable 在 function 結束時不會被刪除的特色，
但就要注意該變數不會被 garbage collection 的問題了，

```javascript
const cache = function (func) {
    const cacheResult = {};
    return function (...args) {
        const key = JSON.stringify(args);
        if (!cacheResult[key]) {
            console.log("Caculate...");
            cacheResult[key] = func(...args);
        }
        return cacheResult[key];
    };
};

const sum = function (a, b) {
    return a + b;
};

let cacheSum = cache(sum);

console.log(cacheSum(5, 6));
// Caculate...
// 11

console.log(cacheSum(5, 6));
// 11


console.log(cacheSum(5, 7));
// Caculate...
// 12
```