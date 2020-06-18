# 與 path 相關的撰寫習慣

## \__file__

首先 __file__ 的值其實就是在命令列上 invoke Python 時給的 script 名稱:

```shell
$ python test.py          # 此時 __file__ 是 test.py
$ python ../test.py       # 此時 __file__ 是 ../test.py
$ python hello/../test.py # 此時 __file__ 是 hello/../test.py
```

## os.path


使用 os.path 在執行的程式中取得檔案路徑，<br>
使其在不管是 import or crontab 等等不同的執行方式都能正常地抓到檔案

```python
dirname, filename = os.path.split(os.path.abspath(__file__))
```

#### hint 
os.path.abspath(path) = normpath(join(os.getcwd(), path)) <br>
os.path.split = (head, tail) <br>
tail is the last pathname component<br>
head is everything leading up to that<br>
\

## 用 join 取代 拼接

好處是在不同的 os 都可以 work

```python
if not os.path.exists(f'{dirname}/crawled_source'):
    os.mkdir(f'{dirname}/crawled_source')
```

```python
if not os.path.exists(os.path.join(dirname, 'crawled_source')):
    os.mkdir(os.path.join(dirname, 'crawled_source'))
```

## reference 
https://github.com/dokelung/Python-QA/blob/master/questions/standard_lib/Python%20%E7%8D%B2%E5%8F%96%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%91%E5%8F%8A%E6%96%87%E4%BB%B6%E7%9B%AE%E9%8C%84(__file__%20%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95).md