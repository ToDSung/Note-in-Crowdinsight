# note

### 計算程式碼執行時間的裝飾器寫法

```python

from functools import wraps
 
def fn_timer(function):
 
    @wraps(function)
    def function_timer(*args, **kwargs):
        import time
        t0 = time.time()
        result = function(*args, **kwargs)
        t1 = time.time()
        print('%s costs %s (s)' %(function.func_name, t1 - t0))
        return result
    return function_timer
 
 
@fn_timer
def get_alpha_str1(s):
    result = ''.join([x for x in s if x.isalpha()])
    return result

#作者：风中静行 
#来源：CSDN 
#原文：https://blog.csdn.net/sxb0841901116/article/details/78508841 
#版权声明：本文为博主原创文章，转载请附上博文链接！

```
