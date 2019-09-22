```
<p>
    Good design will be better.
    <span class="a">Ba</span>
    <span class="b">Ba</span>
    <span class="c">Ba</span>
    We get to make a consequence.
</p>
<style>
    p  { font-size: 100px }
    .a { font-family: Helvetica }
    .b { font-family: Gruppo    }
    .c { font-family: Catamaran }
</style>
```

![](https://iamvdo.me/content/01-blog/30-css-avance-metriques-des-fontes-line-height-et-vertical-align/line-boxes.png)


A `<p>` (black border) is made of 3 `line-boxes` (white borders) that contain `inline elements` (solid borders) and `anonymous inline elements` (dashed borders)

第二个`line-box`比另外两个高，因为其中一个`inline element` (第三个Ba) 的content-area比其他`inline element`都要高。

inline element 的高度就是该元素的 line-height。

只有在simsun字体(宋体)下，content area 的高度 = font-size。所以准确的公式是：`line-height = content-area height + half leading * 2`。由上面的公式可知：content area 总是在line-height 的中心。


There are also other kind of inline elements:
* replaced inline elements (`<img>, <input>, <svg>`, etc.)
* `inline-block` and all `inline-*` elements
* inline elements that participate in a specific formatting context (eg. in a flexbox element, all flex items are blocksified)

For these specific inline elements, height is computed based on their height, margin and border properties. If height is auto, then line-height is used and the content-area is strictly equal to the line-height.

```
<p>
    <span>Ba</span>
    <span>Ba</span>
</p>
p {
    font-family: Catamaran;
    font-size: 100px;
    line-height: 200px;
}
span:last-child {
    font-size: 50px;
}
```

![](https://iamvdo.me/content/01-blog/30-css-avance-metriques-des-fontes-line-height-et-vertical-align/vertical-align-baseline-nok.png)

上图中，第二个span element字体变小后，明显baseline会靠上，为了使baseline对齐，第二个元素会下沉，造成line-box的height比两个元素的line-hight都高。

```
<p>
    <span>Ba</span>
</p>
p {
    line-height: 200px;
}
span {
    font-family: Catamaran;
    font-size: 100px;
}
```

![](https://iamvdo.me/content/01-blog/30-css-avance-metriques-des-fontes-line-height-et-vertical-align/vertical-align-strut.png)

上图中，p元素默认的字体serif与span元素中的字体的baseline不同，所以会造成错位，使line-box的height比两个元素的line-hight都高。