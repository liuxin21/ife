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

![](https://iamvdo.me/content/01-blog/30-css-avance-metriques-des-fontes-line-height-et-vertical-align/line-boxes.png)


A `<p>` (black border) is made of 3 `line-boxes` (white borders) that contain `inline elements` (solid borders) and `anonymous inline elements` (dashed borders)

第二个`line-box`比另外两个高，因为其中一个`inline element` (第三个Ba) 的content-area比其他`inline element`都要高。