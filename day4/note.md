# 第四天
1. CSS中背景相关的background-color属性不可继承，background-image属性也不可继承（甚至说所有背景属性都不可继承）

2. 边框的三个主要属性：宽度、样式、颜色

3. 边框绘制在元素的背景之上

4. 所有H1元素如果不设置border-style，就没有边框，即使设置了border-width也没有

5. 非描述性文本的任何内容都可以作为列表

6. 链接的特殊性：可以根据其状态来设置其样式

7. 链接的四种状态：未访问的链接（a:link）、已访问的链接（a:visited）、鼠标悬停于上方（a:hover）、链接被点击时（a:active）

8. 链接状态样式的设置次序：
- a:hover必须位于a:link和a:visited之后
- a:active必须位于a:hover之后

9. 选择器的定义
- 派生选择器：通过依据元素在其位置的上下文关系来定义样式
- 伪类选择器：分为锚伪类（:link、:visited、:hover、:active）、element:first-child伪类（选择某元素的第一个子元素为element的那些项）、:lang为不同的语言定义特殊的规则

10. 组合选择符
- 后代选择器（以空格 分隔）
- 子元素选择器（以大于号>分隔）
- 相邻兄弟选择器（以加号+分隔）
- 后续兄弟选择器（以波浪号~分隔）

11. 选择器的优先级
- 通用选择器<派生选择器<类选择器<属性选择器<伪类选择器<id选择器<内联样式
- 内联样式权值最高1000>ID选择器权值100>类选择器权值10>派生选择器权值1

12. CSS优先级规则
（1）选择器都有一个权值，权值越大越优先。\
（2）当权值相等时，后出现的样式表设置要优于先出现的样式表设置。\
（3）创作者的规则高于浏览者：即网页编写者设置的CSS 样式的优先权高于浏览器所设置的样式。\
（4）继承的CSS 样式不如后来指定的CSS 样式\
（5）在同一组属性设置中标有“!important”规则的优先级最大。