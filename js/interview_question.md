## this

## hoisting

## closure

## event loop

## higher order function

## cookie vs local storage vs session storage
三者皆保存在瀏覽器中
### cookie 
> 由後端給予的，可設定失效時間，搭配 httpOnly 阻止從 client side 取得或是修改 cookie

> 用 Cookie 搭配 session id 在後段儲存資料 稱為 Session Based Authentication <br>
將 Cookie 加密稱為 Cookie-based session<br>
題外話: 還有一種 Token Based Authentication 與 JWT 相關的作法

### local storage and session storage

> 是新的 html5 的存儲方式

local storage
>除了被主動清除時，屬於永久性保存，分頁等也都是吃同一份 local storage 

session storage
>一個分頁一份 session storage，被關閉時也就消失了