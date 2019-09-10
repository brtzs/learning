# 第三天
## 1. 什么是CSS？
CSS即层叠样式表 (Cascading Style Sheets)，，用于定义如何显示HTML元素；通常存储在样式表中

## 2. CSS解决了什么问题？
解决了HTML中内容与表现分离的问题

## 3. CSS的效果优先级
内联样式（HTML内部元素）>内部样式表（位于\<head>标签内部）>外部样式表>浏览器缺省设置

## 4. CSS是如何工作的？
![image](rendering.svg)
（1）浏览器载入HTML文件
（2）将HTML文件转化为DOM
（3）浏览器拉取相关资源（图片、视频、CSS等）
（4）浏览器拉取到CSS进行解析，根据不同类型的选择器进行分类，然后将不同的规则应用在对应的DOM节点中，并添加节点依赖的样式，该过程成为渲染树
（5）渲染树依照应出现的结构进行布局
（6）网页展示在屏幕上

## 5. CSS基本语法的构成
选择器+一条或多条声明
选择器是要改变样式的HTML元素
声明由一个属性和一个值组成
```
selector {property: value}
```

## 6. CSS选择题有哪些？
- 派生选择器(后代选择器、子元素选择器、相邻兄弟选择器)
```
li strong {
    font-style: italic;
    font-weight: normal;
}
```
- id选择器
- 类选择器
- 属性选择器
```
input[type="text"] {
    width: 150px;
    display: block;
}
```

## 7. 文本样式属性
text-indent: 15px | 5em | 10%;  调整文本第一行缩进
text-align: left | right | center | justify | inherit;  影响一个元素中的文本行互相之间的对齐方式
word-spacing: normal | *length* | inherit;  增加或减少单词间的空白（即字间隔）
letter-spacing: normal | *length* | ingerit;    加或减少字符间的空白（字符间距）
text-transform: none | capitalize | uppercase | lowercase | inherit;    控制文本的大小写
text-decoration: none | underline | overline | line-through | blink | inherit;  规定添加到文本的修饰
white-space: normal | pre | nowrap | pre-wrap | pre-line | inherit; 设置如何处理元素内的空白
direct: ltr | rtl | inherit;    规定文本的方向 / 书写方向

## 8. 字体样式属性
font-family: *FONT_NAME*;   定义文本的字体系列
font-style: normal | italic | oblique;  常用于规定斜体文本（italic和oblique的区别：斜体（italic）是一种简单的字体风格，对每个字母的结构有一些小改动，来反映变化的外观。与此不同，倾斜（oblique）文本则是正常竖直文本的一个倾斜版本。）
font-variant：normal | small-caps | inherit;    设置小型大写字母的字体显示文本，这意味着所有的小写字母均会被转换为大写，但是所有使用小型大写字体的字母与其余文本相比，其字体尺寸更小
font-weight: normal | bold | [100~900]; 设置文本的粗细
font-size: 32px | 5em | 100%;   设置文本的大小
