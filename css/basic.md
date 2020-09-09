
| property       | meaning         |
|----------------|-----------------|
| height         | parent’s height |
| width          | parent’s width  |
| top            | parent’s height |
| left           | parent’s width  |
| margin-top     | parent’s width  |
| margin-left    | parent’s width  |
| padding-top    | parent’s width  |
| padding-left   | parent’s width  |
| translate-top  | self’s height   |
| translate-left | self’s width    |

https://wattenberger.com/blog/css-percents


# 垂直、水平置中

## 需要知道子元素的寬高
```css
.father {
    position: relative;
}
.child {
    position: absolute;
    top: calc(50% - 50px);
    left: calc(50% - 50px);
}
```

## transform: tanslate(-50%, -50%) 使用本身元素的寬高

```css
.father {
    position: relative;
}
.child {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

## 利用 margin auto 自動分配的特性
```css
.father {
    position: relative;
}
.child {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
}
```

## flex 

```css
.father {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

## grid
```css
.father {
    display: grid;
}
.child {
    align-self: center;
    justify-self: center;
}
```