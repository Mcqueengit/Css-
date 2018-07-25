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
2. 
