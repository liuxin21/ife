## 水平居中
分两大类：行内元素&块级元素
1. 行内元素
行内元素很简单，直接给行内元素的父元素设置`text-align:center`。但是，父元素内的所有子元素都会继承`text-align:cente`，比如父元素里还有另外一个div, 这个div里面的字会自动水平居中，因此需要对子元素的文本居中方式单独设定。
2. 块级元素
块级元素分定宽和不定宽。
* 定宽
方法一：定宽可以用`margin: 0 auto;`（若子元素的宽度是已知的，那么我们可以设置子元素的左右margin为auto即可）。
方法二：定宽也可以`position, left, margin-left`。
* 不定宽
方法一：不定宽可以为需要设置的居中的元素外面加入`<table><tbody><tr><td>`，然后再`table{margin:0 auto;}`。
方法二：改变块级元素的 dispaly 为 inline 或 inline-block 类型，然后在父容器使用`text-align:center`来实现居中效果。
方法三：通过给父元素设置 `float:left`，然后给父元素设置 `position:relative` 和 `left:50%`，子元素设置 `position:relative` 和 `left:-50%` 来实现水平居中。


