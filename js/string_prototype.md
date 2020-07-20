# Sring 用法的特別之處

## String.prototype.padStart()
## String.prototype.padEnd()
看起來適合用在時間補零的處理
```javascript
const str1 = 'Breaded Mushrooms';

console.log(str1.padEnd(25, '.'));
// expected output: "Breaded Mushrooms........"

const str2 = '200';

console.log(str2.padEnd(5));
// expected output: "200  "

```

## String.prototype.substr()
Syntax: string.substr(start, stop);
跟 python 字串可以使用 [ start : stop ] 基本一樣

## String.prototype.slice() 
## String.prototype.subString

slice() works like substring() with a few different behaviors.
Syntax: string.slice(start, stop);
Syntax: string.substring(start, stop);


相同點: 
如果 start = stop 回傳 ""
如果沒有給 stop 參數， 會給到最後一個字
如果參數給大於數字，會給 string 總長度

substring() 特點:
如果 start > stop, function 會交換這兩個參數
如果參數為負數或 NaN，相當於給 0

slice() 特點:

如果 start > stop, function 會回傳 ""
如果 start 為負 Firefox 跟 IE 中行為 跟 substring 相同
如果 stop 為負: 會從後往前數