## line-height 和 font-size
* line-height = font-size + half leading * 2
* font-size = top + middle + baseline + bottom
* 改变line-height时，font-size(行内框的高度)不变，改变的是行距

## 四个盒子
* inline box 行内框的高度 = font-size
* content area 内容区的高度 = font-size
* line box 行框高度等于本行中所有行内框高度的最大值。当有多行内容时，每一行都有自己的行框。
* containing box 包裹着上述三种box的box

## 补充
* 只有在simsun字体(也即宋体)下，content area 的高度 = font-size。所以准确的公式是：* line-height = content-area height + half leading * 2
* 考虑到继承特性，一般来数，设置行高的值为*纯数字*是最推荐的方式，因为其会随着对应的 font-size 而缩放。默认的normal是1.2。
* 如果一个空div里面打入了一个空格或是文字，则此div就会有一个高度。那么这个高度是什么呢？并不是很直观的font-size，而是line-height。
* 虽然行内元素设置行高之后会有位置的变化，但是并没有改变盒子大小（字体大小），所以在为行内元素设置背景时，还是默认高度的地方有背景。（line-height只是撑开了边框。）
* You can think of the content-area as the area where the background property applies。
* `<p><img>xxx</p>`当图片的高度大于p设置的line-height时，line box的高度是：`图片的高度` + `base line 到 bottom line （text-bottom、content area底部）的距离` + `下半行距`
* 只有一个元素属于inline或是inline-block水平，其身上的vertical-align属性才会起作用
* middle：把该盒的竖直中点和父级盒的基线加上父级的半x-height对齐
* text-top：把该盒的top和父级的内容区（content area）的top对齐
* text-bottom：把该盒的bottom和父级的内容区的bottom对齐
* "该盒"必须是inline或是inline-block水平, 所以并不是text，“该盒”没有content area top 和 bottom


