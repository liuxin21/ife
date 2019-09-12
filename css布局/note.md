1. display: none; 不占据空间(二级导航) visibility: hidden; 占据空间
2. 把 li 元素修改成 inline，制作成水平菜单
3. 水平居中 max-width; margin: 0 auto;
4. box-sizing: border-box;
5. 左边固定，右边自适应：可以把父类定为relative或absolute，div1定为absolute，这样div1脱离文档流，div2上去与div1重叠，再把div2的margin-left定为div1的宽度，则div2跑到div1右边。
6. 清除浮动。div1设置了浮动，div2可以设置clear: both; 或者div1的父元素设置 overflow: auto;
7. eg: .parents->{nav section section} nav{float:left, width:200px} section{margin-left:200px} 
8. relative: 相对于以前的位置移动，偏移前的位置保留不动。在使用相对定位时，就算元素被偏移了，但是他仍然占据着它没偏移前的空间。
9. absolute: 将元素从文档流中拖出来。被设置了绝对定位的元素，在文档流中是不占据空间的，如果某元素设置了绝对定位，那么它在文档流中的位置会被删除。
10. float: 和absolute一样将元素从文档流中拖出来，但是文字不会占据这部分空间。
11. img是替换内联元素 replaced inline element，属于inline element类目。和其它的内联元素有什么不同呢？它在计算height/margin/width等值或在绝对定位的时候，有一些额外的规则。（CSS2.1 第10章）比如设定了width但未设置height, img的height会根据比列缩放。
12. 正常的img中间是会有空格的，因为多个<img>标签会有换行，而浏览器识别换行为空格，这也是很正常的。img增加了float:left的样式，这就使得img之间没有了空格，四个img紧紧挨着。为什么float适合用于网页排版（俗称“砌砖头”）？就是因为float排版出来的网页严丝合缝，中间连个苍蝇都飞不进去。“清空格”这一特性的根本原因是由于float会导致节点脱离文档流结构。它都不属于文档流结构了，那么它身边的什么换行、空格就都和它没关系的，它就尽量的往一边去靠拢，能靠多近就靠多近，这就是清空格的本质。
13. 最常用的清除浮动方法：.clearfix:after{}
14. 设置float属性后，元素实际上会inline-block块状化（包裹性）
15. 设置浮动后，元素就变为块级元素了。但最好的应用还是应该让他去实现文字的环绕效果，比如单侧固定的流体布局，用：float+margin来实现。大布局时可以用一下，小的布局时可以考虑用inline-block来砌砖头（但是会有小间距，具体应用时看），尽量不要滥用。
16. float是部分脱离文档流，而absolute是完全脱离文档流。也就是说，使用float属性时，其他元素会无视这个float元素，但是其他元素内的文本依然会为这个元素让出位置，环绕在周围，所以称为部分无视。而使用absolute脱离文档流的元素，其它盒子无论是本身还是盒子内的文本都会无视这个元素，也就是所谓的完全脱离文档流。
17. 写结构的时候要注意，父元素的的三栏务必先写中间盒子。因为中间盒子是要被优先渲染嘛~并且设置其自适应，也就是width:100%。
18. 现代布局: 弹性盒子模型布局(Flexbox Layout)，格栅布局(Grid Layout)
19. BFC自适应布局固定搭配：.l { float: left; margin-right: 20px} .ovh { overflow: hidden; }
20. BFC自适应(overflow: hidden)布局优势：1. 自适应内容由于封闭，更健壮，容错性强。比方说，内部clear:both不会与兄弟float产生矛盾。而纯流体布局，clear:both会让后面内容无法和float元素在一个水平上，产生布局问题。2. 自适应内容自动填满浮动以为区域，无需关心浮动元素宽度，可以整站大规模应用。而纯流体布局，需要大小不确定的margin/padding等值撑开合适间距，无法CSS组件化。
21. 两栏或多栏自适应布局的通用类语句是（block水平标签，需配合浮动）：.cell {
    display: table-cell; width: 9999px;
    *display: inline-block; *width: auto;}
22. 由于和浮动元素合作，清除浮动还是要的，于是，就有了.fix + .l/.r + .cell的无敌组合，可以多栏，也可以无限嵌套。如果是局部，且确认安全；或有连续英文字符换行的隐患，你也可以使用.fix + .l/.r + .ovh的无敌组合，可以多栏，也可以无限嵌套。
23. **双inline-block** 和 **双float**都得用 width: calc(100% - 140px); **float+margin-left** 和 **absolute+margin-left** 利用了block元素填满父元素的流动特性，但是还是需要通过左侧盒子的宽度，计算某个值（width或者margin-left）。**float+BFC** 同样是利用了左侧浮动，但是右侧盒子通过overflow: auto;形成了BFC，因此右侧盒子不会与浮动的元素重叠。**flex**容器的一个默认属性值:align-items: stretch;。这个属性导致了列等高的效果。为了让两个盒子高度自动，需要设置: align-items: flex-start; **grid**布局也有列等高的默认效果。需要设置: align-items: start;。grid布局还有一个值得注意的小地方和flex不同:在使用margin-left的时候，grid布局默认是box-sizing设置的盒宽度之间的位置。而flex则是使用两个div的border或者padding外侧之间的距离。
24. 设置浮动之后，display会自动转为block，而不是inline，自然就没有间距的问题。但是如果不用浮动的话，可以设置inline元素的父元素font-size: 0; inline元素再设置回font-size: 12px.
