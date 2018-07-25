参考文献https://css-tricks.com/centering-css-complete-guide/
# 水平居中
## inline或者inline-*元素（比如text或links）
对inline元素添加一个block的父元素，并设置text-align:center
 ```
 <header>
 This text is centered.
 </header>
 <nav>
  <a href="#0">One</a>
  <a href="#0">Two</a>
 </nav>
 ```
 ```
 header,nav{
  text-align:center;
 }
 ```
## block元素
对于block元素，设置固定的宽度，并设置margin：0 auto即可（例子太简单，不再写代码）。
## 多个block元素
修改block元素的display属性，如inline-block或者flex。
```
<main class="inline-block-center">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</main>
<main class="flex-center">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</main>
```
```

main div {
  background: black;
  color: white;
  padding: 15px;
  max-width: 125px;
  margin: 5px;
}

.inline-block-center {
  text-align: center;
}
.inline-block-center div {
  display: inline-block;
}

.flex-center {
  display: flex;
  justify-content: center;
}
```
注意，上面介绍了两种居中方法：
1. 第一种是外部为block元素，设置text-align:center，同时将内部的div设置为display:inline-block;
2. 第二种是将外部block元素设置display:flex,同时设置justfy-content:center（不需要设置内部div元素的display）。

如果是多个block元素（不在同一行）的居中，则只需参照上面的block元素居中即可。
# 垂直居中
## inline或者inline-*元素（比如text或links）
### 单行
1. 设置相同的padding-top和padding-bottom；
2. line-height的高度等于height的高度。
### 多行
1. 设置相同的padding-top和padding-bottom;
2. 将包含文字的容器设置为table-cell，同时设置verticle-align:center
3. 使用flexbox，需要子元素个数为1
4. 使用幽灵元素
需要注意的是，2和3的实现需要父元素具有确定的高度，因此如果父元素高度不确定，则使用4.

使用table-cell的居中
```
<div class="center-table">
  <p>I'm vertically centered multiple lines of text in a CSS-created table layout.</p>
</div>
```
```
.center-table {
  display: table;
  height: 250px;
  background: red;
  width: 240px;
  margin: 20px;
}
.center-table p {
  display: table-cell;
  background: black;
  color: white;
  padding: 20px;
  vertical-align: middle;
}
```
使用flexbox的居中
```
<div class="flex-center">
  <p>I'm vertically centered multiple lines of text in a flexbox container.</p>
</div>
```
```
.flex-center {
  background: black;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 200px;
}
.flex-center p {
  margin: 0;
  padding: 20px;
}
```
使用幽灵元素的居中
```
<div class="ghost-center">
  <p>I'm vertically centered multiple lines of text in a container. Centered with a ghost pseudo element</p>
</div>
```
```
.ghost-center {
  position: relative;
}
.ghost-center::before {
  content: " ";
  display: inline-block;
  height: 100%;
  width: 1%;
  vertical-align: middle;
}
.ghost-center p {
  display: inline-block;
  vertical-align: middle;
  width: 300px;
  color:white;
  padding: 20px;
  background: black;
}
```
## block元素
### 高度已知
父元素使用相对定位，子元素使用绝对定位。
```
<main>
  <div>
    I'm a block-level element with a fixed height, centered vertically within my parent.
  </div>
</main>
```
```
main {
  background: white;
  height: 300px;
  width: 300px;
  position: relative;
}

main div {
  position: absolute;
  top: 50%;
  height: 100px;
  margin-top: -70px;
  background: gray;
  padding: 20px;
}
```
