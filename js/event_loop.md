# EventLoop

一個一個 function 會根據被 call 的順序，堆疊在 stack 中

計時器(setTimeout setInterval) 會把 callback function 放進 Macrotask queue 中

Microtask 通常由 Promise 產生，Promise 裡用到的 .then / .catch 函式會以非同步的方式來被執行， 每一個 Marcotask 會執行 Microtask 

![](https://i.imgur.com/yrQbb9g.png)

## Event Loop 的監測順序：

1. 看 stack
2. 如果 stack 為空，且 task queue 有東西，將 task queue (Marcotask) 的第一個項目移到 stack，回到步驟 (1.)

3. 如果我們在 mircotask 中也有 microtask 他也會全執行完，才回到 marcotask

## example

```javascript=
setTimeout(() => alert("timeout"));

Promise.resolve()
  .then(() => alert("promise"));

alert("global ex. context");
```

所有的 Queue 都會等待執行環境 stack 被清空， <br>
alert 肯定會先執行 <br>
setTimeout 對應的函式會被當作一個 Macrotask ，等待時間到之後被送入 Macrotask Queue<br>
Promise 對應的 .then 或 .catch 的函式會被當作一個 Microtask 送入 Microtask<br> Ｑueue
在執行環境堆疊清空之後，通常網頁會先做一次 Render，Render 的動作同時也算是一個 Macrotask

```
"global ex. contenxt"
"promise"
"timeout"
```

原因是對於瀏覽器來說 render 畫面也是一個 Marcotask，所以 promise.then 裡的 Microtask 會優先於 setTimeout 裡的這個 Microtask 被執行