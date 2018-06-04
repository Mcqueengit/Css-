参考文献https://css-tricks.com/centering-css-complete-guide/
# 水平居中
## 是inline或者inline-*元素（比如text或links）
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
