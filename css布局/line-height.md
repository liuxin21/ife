## line-height 和 font-size
* line-height = font-size + 半行距 * 2
* font-size = top + middle + baseline + bottom
* 改变line-height时，font-size(行内框的高度)不变，改变的是行距

## 四个盒子
* inline box 行内框的高度 = font-size
* content area 内容区的高度 = font-size + padding-top + padding-bottom
* line box 行框高度等于本行中所有行内框高度的最大值。当有多行内容时，每一行都有自己的行框。
* containing box 包裹着上述三种box的box

考虑到继承特性，一般来数，设置行高的值为*纯数字*是最推荐的方式，因为其会随着对应的 font-size 而缩放。默认的normal是1.2。