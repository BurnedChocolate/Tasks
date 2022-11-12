# CSS基础

## 0.学习要求

1. 学习理解CSS的作用 【重点】
2. 学习理解CSS选择器 【`此阶段学习 通用选择器、元素选择器、类选择器、ID选择器即可`】 【重点】
3. 能够利用CSS设置元素的基础样式，如大小、颜色、文字字体等
4. 学习理解CSS的盒模型 【重点】
5. CSS的5种position定位 【重点】
6. 了解CSS常用的布局方式
7. CSS的伪类

## 1.CSS是什么？

✔**CSS = Cascading Style Sheets（层叠样式表）**

CSS是一种用来为结构化文档（如 HTML 文档或 XML 应用）添加样式（字体、间距和颜色等）的计算机语言，它描述了如何在屏幕、纸张或其他媒体上显示 HTML 元素，可以同时控制多个网页的布局与样式。CSS文件的扩展名为 `.css`。 

✔**HTML与CSS的联系**

HTML描述网页的**内容**，CSS定义网页的**样式**。

> 🤔：只有内容没有排版和装饰性元素的网页是寡淡无味且让人不想读下去的，whitch means，整点花活。

## 2.CSS基础知识

### ①CSS语法

#### 📕语法结构

```css
形式：

选择器{
    属性:属性值;
    属性:属性值;
}

示例：

h1{
    width:600px;
    hight:1200px;
    margin:auto;
}
```

它的拆分分析如下图所示：

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E8%AF%AD%E6%B3%95-%E7%BB%93%E6%9E%84.jpg)

**分析**：

- `h1`：**选择器**，用于指向需要进行设置的HTML元素。选择器有多种，此处指向的是HTML中的`<h1>`标签。
- `{ }`：**开始大括号和结束大括号**，被框起来的内容是**CSS规则**。
- `width:600px;`、`hight:1200px;`、`margin:auto;`：这三条都是**声明**。**声明**由**属性**（`width`、`hight`、`margin`）和**属性值**（`600px`、`1200px`、`auto`）组成，属性和属性值之间用`:`连接。

#### 📕样式类型

样式类型有三种：内联样式、内部样式、外部样式。

- 内联样式 ：直接写在HTML标签中，仅对当前的HTML元素有效。使用`style`属性，直接进行声明，不使用选择器。

```css
例如：<p style="color:blue">这是一行测试段落</p>
```

- 内部样式 ：写在html head中，用`<style>`标签框起来。style标签内可以有多个CSS规则，仅针对当前页面有效。

```css
例如：
<style>
    h1{
        width:600px;
        hight:1200px;
        margin:auto;
        color: brown;
    }
</style>
```

- 外部样式：写在外部.css文件中，放在\<head>\</head>标签内，通过指定\<link>标签的`herf`属性来连接外部CSS文件路径，从而引入外部样式表。（例子见截图）

```css
放在<head></head>标签内的部分：<link rel="stylesheet" href="csstest.css">
外部样式表（.css文件）里的内容：
h3{
    color:aqua;
}
```

该部分测试截图如下。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css-%E6%A0%B7%E5%BC%8F%E7%B1%BB%E5%9E%8B.jpg)

### ②选择器

#### 📕通用选择器

选择并影响页面上的**所有**的HTML元素。

通用选择器是一个`*`。

```css
*{
    text-align:center;
}
```

以上例子中，该HTML中的所有元素都会居中对齐。

#### 📕元素选择器

根据**元素名称**选择HTML元素，选择所有相应元素名称的元素。

```css
h1{
    color:aqua;
}
```

以上例子中，该HTML文件中的所有h1元素都会变成青色。


#### 📕类选择器

选择具有**特定class属性**的HTML元素，用`.`+class类名来表示。

```css
.center {
  text-align:center;
  color:aqua;
}
```

以上例子中，所有带有`class="center"`的HTML元素都会变成青色且居中对齐。

#### 📕ID选择器

用于选择一个特定**唯一**的元素。使用HTML元素的id属性来选择特定的元素，用`#`+id名来表示。

```css
#test2{
    color:aquamarine;
}
```

以上例子中，id为test2的元素会变成蓝绿色。

该部分测试截图如下。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E9%80%89%E6%8B%A9%E5%99%A8.jpg)

### ③设置元素的基础样式

#### 📕颜色

- 颜色的定义方式：
	- 十六进制（#ff0000）
	- RGB（rgb(255,0,0)）
	- 颜色名称（red）

> 🤔：在已安装css support的前提下，感觉用颜色名称定义是最简单快捷的（不需要使用特定颜色的时候）。

- 改变文本颜色

 ```css
 style="color:red;"
 或
 h1{
 	color:red;
 }
 ```

- 改变背景颜色

```css
style="background-color:red;"
或
h1{
    background-color:red;
}
```

#### 📕字体

CSS中，有五个通用字体族：

- 衬线字体（Serif）- 在每个字母的边缘都有一个小的笔触。给人以形式感和优雅感。
- 无衬线字体（Sans-serif）- 字体线条简洁（没有小笔画）。具有现代而简约的外观。
- 等宽字体（Monospace）- 这里所有字母都有相同的固定宽度。机械式的外观。
- 草书字体（Cursive）- 模仿人类笔迹的字体。
- 幻想字体（Fantasy）- 装饰性/俏皮的字体。

所有不同的字体名称都属于这五个通用字体系列之一。以下是一些典型的字体展示，使用时可以进行参考。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%20%E5%AD%97%E4%BD%93.jpg)

修改元素字体的**属性**是`font-family`，其后可接多个字体以提高浏览器兼容性，不同字体间用`,`隔开，如果字体名称超过一个单词则用`""`框起来。（推荐以通用系列字体结束。）

```css
<p>{
    font-family:"Times New Roman",Times,serif;
}
```

在以上例子中，首选字体是Times New Roman，但如果浏览器不支持该字体，就会选择之后的字体来使用。

> 🤔：多写几个长得像的字体在一起，提高容错率，也更美观。

#### 📕大小

普通文本（如段落）的默认大小为16px，修改字体的大小可在网页页面中产生不同的效果。

设置字体大小的属性是`font-size`。font-size值可以是绝对尺寸或相对尺寸。

| 绝对尺寸                                                     | 相对尺寸                                                    |
| ------------------------------------------------------------ | ----------------------------------------------------------- |
| 将文本设置为指定大小<br/>不允许用户在所有浏览器中更改文本大小<br/>当输出的物理尺寸已知时，绝对尺寸很有用 | 设置相对于周围元素的大小<br/>允许用户在浏览器中更改文本大小 |

- 绝对尺寸

可以使用像素（px）来规定元素的绝对尺寸大小。

```css
h1 {
  font-size:40px;
}
```

- 相对尺寸

通常使用em来规定元素的相对尺寸大小。1em等于当前字体大小。浏览器中的默认文本大小为16px，故1em的默认大小为16px。

```css
h2 {
  font-size:2em;
}
```

>  🤔：学计算机还是得多学点英语……

该部分测试截图如下。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E5%85%83%E7%B4%A0%E5%9F%BA%E7%A1%80%E6%A0%B7%E5%BC%8F%E8%AE%BE%E7%BD%AE%EF%BC%88%E5%AD%97%E4%BD%93%E9%A2%9C%E8%89%B2%E7%AD%89.jpg)

### ④盒模型

盒模型又称框模型。所有HTML元素都可以视为一个盒子，盒模型实质上就是对这个包围HTML元素的盒子的定义。它包括：**外边距、边框、内边距**以及**内容**。

- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。
- **Content(内容)** - 盒子的内容，显示文本和图像。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E7%9B%92%E6%A8%A1%E5%9E%8B.jpg)

> 🤔：盒模型，像一个盒子一样把HTML元素中的所有东西装起来，这些装起来的东西就是外边距、边框、内边距和内容。形象好记。

盒模型的最内部分是**内容**（文本或图片），**内边框**直接包围**内容**。**内边距**呈现了元素的**背景**。内边距的边缘是**边框**。边框以外是**外边距**，外边距默认是透明的，因此不会遮挡其后的任何元素。

我们可以对外边距、边框、内边距的属性进行调整。下面的例子用一个外部样式的div来进行测试。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E7%9B%92%E6%A8%A1%E5%9E%8B%E5%9B%BE%E7%A4%BA1.jpg)

外边距、边框、内边距的属性可以直接指定大小值（上），也可以分别指定上下左右的大小值（中），也可以简写成四个大小值放在需要修改的属性之后（下），最后这种的四个大小值是按照顺时针的方向指示，即上、右、下、左。

此外，如果想看到盒模型的每一部分具体占多少大小，可以在网页中使用快捷键`F12`打开开发者工具，选择相应的div即可看到清晰的该div的盒模型图解。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E7%9B%92%E6%A8%A1%E5%9E%8B%E5%9B%BE%E7%A4%BA2.jpg)

> 🤔：在上一部分设置元素的基础样式的实操测试中，调整字体大小时，字体周边的空白部分也会随之增减，应该就是系统对盒模型进行了一定自动调整。

### ⑤定位

CSS的定位指的是`position`属性，position属性有五个值：relative（相对定位）、absolute（绝对定位）、static（静态定位）、fixed（固定定位）和sticky（粘性定位）。position属性必须结合这五个值一起使用。

> 🤔：定位的效果是让元素固定在某个位置，而五个值决定了不同的固定方式。

- **static（静态定位）**

HTML元素的**默认定位方式**。

```css
position:static;
```

- **relative（相对定位）**

相对于其正常位置进行的定位。依据 `top`、`right`、`bottom` 或 `left` 等属性在正常文档流中**偏移**自身位置。移动相对定位元素，它原本所占的空间不会改变，也不会对其余内容进行调整来适应元素留下的任何空间。

```css
position:relative;
```

- **fixed（固定定位）**

相对于视口进行定位，即使滚动页面，具有fixed属性的元素它也始终位于同一位置。使用 `top`、`right`、`bottom` 或 `left` 进行定位。

```css
position:fixed;
```

> 🤔：在一些网站右下角常见的【回到顶部】按钮，使用的就是固定定位。

- **absolute（绝对定位）**

相对于**最近的定位父元素**进行定位。使用 `top`、`right`、`bottom` 或 `left` 等属性相对于父元素进行绝对定位。

如果绝对定位的元素没有已定位的父元素，它将使用文档主体（body），并随页面滚动一起移动。

**注意：**“被定位的”元素是其位置除 `static` 以外的最近的任何元素。

```css
position:absolute;
```

- **sticky（粘性定位）**

粘性定位的元素根据滚动位置在相对（`relative`）和固定（`fixed`）之间切换。起先它会被相对定位，直到在视口中遇到给定的偏移位置为止，然后将其“粘贴”在适当的位置。此外，还需要至少指定 `top`、`right`、`bottom` 或 `left` 之一来让粘性定位起作用（粘在上部/右边……）

```css
position:sticky;
top:0;
```

该部分测试截图如下。

![](https://github.com/BurnedChocolate/Tasks/blob/30cafd9015150e1b056ece4e4a2be0e759d1bc3d/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/css%E5%AE%9A%E4%BD%8D.jpg)

> 🤔：感觉这部分有点抽象……

### ⑥常用布局方式

- 单列布局
- 两列自适应布局
- 三栏布局
- 粘连布局
- ……

### ⑦伪类

伪类（pseudo-class）用于定义元素的特殊状态。它的作用有：

- 设置鼠标悬停在元素上时的样式
- 为已访问和未访问链接设置不同的样式
- 设置元素获得焦点时的样式

格式：

```css
选择器:伪类 {
  属性:属性值;
}
```

伪类：`link`，未访问的链接；`visited`，已访问的链接；`hover`，鼠标悬停链接；`active`，已选择的链接。

示例：

```css
a:link {
  color: #FF0000;
}
```

## 3. 参考资料

- 入门教程：
	- [CSS快速入门教程 - bilibili](https://www.bilibili.com/video/BV1mS4y1Z7Ga)
- 更加专业的教程：
	- [qianguyihao/Web：前端图文教程 - github](https://github.com/qianguyihao/Web)
	- [CSS 教程 - 菜鸟教程](https://www.runoob.com/css/css-tutorial.html)
	- [CSS 教程 - w3school](https://www.w3school.com.cn/css/index.asp)

- 常用布局方式参考：
  - [几种常见的 CSS 布局 - CSDN](https://blog.csdn.net/VhWfR2u02Q/article/details/84076421?ops_request_misc=%7B%22request%5Fid%22%3A%22166817247816782425139735%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=166817247816782425139735&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-84076421-null-null.142^v63^control,201^v3^add_ask,213^v2^t3_control1&utm_term=css常用的几种布局方式&spm=1018.2226.3001.4187)