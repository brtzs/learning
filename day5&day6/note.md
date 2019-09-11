# 第五天和第六天
1. 盒模型包括：边距（margin）、边框（border）、填充（padding）、实际内容（content）
![盒模型示意图](box-model.png)

2. 元素的总宽度计算：\
元素的总宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距\
元素的总高度计算：\
元素的总高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距

3. block、inline和inline-block的对比
- display: block
(1) block元素会独占一行，多个block元素会各自新起一行。默认情况下，block元素宽度自动填满其父元素宽度。
(2) block元素可以设置width,height属性。块级元素即使设置了宽度,仍然是独占一行。
(3) block元素可以设置margin和padding属性。
- display: inline
(1) inline元素不会独占一行，多个相邻的行内元素会排列在同一行里，直到一行排列不下，才会新换一行，其宽度随元素的内容而变化。
(2) inline元素设置width,height属性无效。
(3) inline元素的margin和padding属性，水平方向的padding-left, padding-right, margin-left, margin-right都产生边距效果；但竖直方向的padding-top, padding-bottom, margin-top, margin-bottom不会产生边距效果。
- display: inline-block
简单来说就是将对象呈现为inline对象，但是对象的内容作为block对象呈现。之后的内联对象会被排列在同一行内。比如我们可以给一个link（a元素）inline-block属性值，使其既具有block的宽度高度特性又具有inline的同行特性。

4. 浮动：浮动的框可以向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。
清除浮动：规定元素的哪一侧不允许其他浮动元素。