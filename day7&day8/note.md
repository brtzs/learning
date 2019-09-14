# 第七天和第八天
1. 当display: none;时，生成的元素没有框，该框及其所有内容就不再显示，不占用文档中的空间。

2. position: static | relative | absolute | fixed;
- static
元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。
- relative
元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。
- absolute
元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。
- fixed
元素框的表现类似于将 position 设置为 absolute，不过其包含块是视窗本身。

3. display: none;和visibility: hidden;的区别
display: none;不会占据空间，visibility: hidden;仍然会占据空间。

4. 网页中块的三种关系：相邻、嵌套、重叠。

5. 面试常见问题：圣杯布局（又叫双飞翼布局），即左右两栏固定大小，中间栏自适应大小的三栏布局
常见解决办法有三种：绝对定位法、margin负值法和自身浮动法

6. 绝对定位法：左右两栏采用绝对定位，分别固定于页面的左右两侧，中间的主体栏用左右margin值撑开距离。于是实现了三栏自适应布局
- HTML代码：
```
<body>
    <div id="left"></div>
    <div id="main"></div>
    <div id="right"></div>
</body>
```
- CSS代码：
```
html, body {
    margin: 0;  height: 100%;
}
#left, #right {
    position: absolute; top: 0; width: 200px;   height: 100%;
}
#left {
    left:0; background: lightblue;
}
#right {
    right: 0;   background: wheat;
}
#main {
    margin: 0 200px; background: lightgreen; height: 100%;
}
```
优点：理解容易，上手简单，受内部元素影响而破坏布局的概率低
缺点：如果中间栏含有最小宽度限制，或是含有宽度的内部元素，当浏览器宽度小到一定程度，会发生层重叠的情况。

7.margin负值法：首先，中间的主体要使用双层标签。外层div宽度100%显示，并且浮动（本例左浮动，下面所述依次为基础），内层div为真正的主体内容，含有左右210像素的margin值。左栏与右栏都是采用margin负值定位的，左栏左浮动，margin-left为-100%，由于前面的div宽度100%与浏览器，所以这里的-100% margin值正好使左栏div定位到了页面的左侧；右侧栏也是左浮动，其margin-left也是负值，大小为其本身的宽度即200像素。
- HTML代码：
```
<body>
    <div id="main">
        <div id="body"></div>
    </div>
    <div id="left"></div>
    <div id="right"></div>
</body>
```
- CSS代码：
```
html, body {
    margin: 0;  height: 100%;
}
#main {
    width: 100%;    height: 100%;   float: left;
}
#main #body {
    margin: 0 200px;    background: lightgreen; height: 100%;
}
#left, #right {
    width: 200px;   height: 100%;   float: left;
}
#left {
    margin-left: -100%;     background: lightblue;
}
#right {
    margin-left: -200px;    background: wheat;
}
```
优点：三栏相互关联，可谓真正意义上的自适应，有一定的抗性——布局不易受内部影响。
缺点：相对比较难理解些，上手不容易，代码相对复杂。出现百分比宽度，过多的负值定位，如果出现布局的bug，排查不易。

8.自身浮动法：此方法代码最简单。应用了标签浮动跟随的特性。左栏左浮动，右栏右浮动，主体直接放后面，就实现了自适应。
- HTML代码：
```
<body>
    <div id="left"></div>
    <div id="right"></div>
    <div id="main"></div>
</body>
```
- CSS代码：
```
html, body {
    margin: 0;  height: 100%;
}
#main {
    height: 100%;   margin: 0 200px;
}
#left, #right {
    width: 200px;   height: 100%;
}
#left {
    float: left;     background: lightblue;
}
#right {
    float: right;    background: wheat;
}
```
优点：代码足够简洁与高效
缺点：中间主体存在克星，clear:both属性。如果要使用此方法，需避免明显的clear样式。