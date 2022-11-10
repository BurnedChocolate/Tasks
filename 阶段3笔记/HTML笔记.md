# HTML基础

# 0.学习要求

1. 学习并能够使用常用的HTML标签 如【`<div>、<p>、<a>、<button> 等等`】 【重点】
2. 学习理解各类标签中的块级元素与内联元素 【重点】
3. 学习HTML标签的样式 【重点】

## 1.HTML是什么？

✔**HTML 是用来描述网页的一种语言**

HTML是我们目前看到的所有网站的基础。HTML使用**标记标签（标签）**来描述网页，它的文档中包含HTML标签及文本内容。**HTML文档= web 页面**。

✔**HTML 是一种标记语言**

**H**yper**T**ext **M**arkup **L**anguage（HTML），即“超文本标记语言”。

标记语言和编程语言是**完全不同**的概念。

- **编程语言：**向计算机提供逻辑或指令以执行某些任务，以从计算机获取所需的输出。编程语言广泛地用于制作软件或驱动程序。例如C、C++、Python、java等。

  > 🤔：由一系列代码，通过逻辑计算，得到一定输出的语言

- **标记语言：**表示性语言，不包含任何逻辑或算法。用于表示Web浏览器中的视图，或以特定方式对页面进行样式设置。标记语言广泛地用于设计网站。例如HTML、CSS等。

  > 🤔：用来进行设计和页面调整的表示性语言，不处理数据，只处理外观

## 2.HTML常用标签

### 🎞一些基础概念

**HTML标签**：由`<>`包围的关键词，**通常**成对出现，出现在一行内容的开始和结尾处，分别称为开始标签和结束标签。结束标签与开始标签的区别是多了一个`/`。

```html
形式：<标签>这里写入内容</标签>
示例：<title>Document</titlet>
```

**HTML标签属性**：写在开始标签之内。属性的使用规则是：属性名=“属性值”

```HTML
示例：<a herf="https://www.bilibili.com/">哔哩哔哩</a>
```

`herf="https://www.bilibili.com/"`这一部分就是标签的属性。

**HTML元素**：以**开始标签**起始，以**结束标签**终止。**元素的内容**是开始标签与结束标签之间的内容。

> 🤔：注意区别标签与元素。

**HTML标签的分类**：

- **文本级标签**：文本级标签里**只能**放**文字、图片、表单元素**。(\<p>、\<span>、\<a>、\<b>等)
- **容器级标签**：容器级标签里可以放置**任何东西**。(\<div>、\<h1>-\<h6>等)

### 🎞HTML文档的基本结构

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
    </head>
    <body>
        
    </body>
</html>
```

它的拆分分析如下图所示。

![](https://github.com/BurnedChocolate/Tasks/blob/13e2acf4b849996e6f65f0185de016693fd05c61/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/html%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84.jpg)

**分析：**

- `<!DOCTYPE html>`：**<!DOCTYPE>声明**，有助于浏览器中正确显示网页。网络上有很多不同的文件，如果能够正确声明HTML的版本，浏览器就能正确显示网页内容。此处是在声明：这里是一个HTML5文档。
- `<html lang="en">`与`</html>`：**HTML根元素**，提供了一个完整的HTML页面。

- `<head>`与`</head>`：**HTML头**，一般放入原数据、搜索引擎的keyword、title、脚本、css文件链接等。
- `<body>` 与`</body>`：**HTML body**里放入HTML元素，对应网页内看到的所有的页面内容。

> 🤔：声明，告诉浏览器这是一个html文档；根元素，产生一个空白的html页面；html头，放入与文档相关的重要的东西，一般不会被渲染在网页内；html body，构成主体，也就是我们可以在网页里直接看到的部分。

### 🎞HTML的标签与元素

#### 📕常用标签

- 标题

标题标签：从`<h1></h1>`到`<h6></h6>`，分别对应由大到小的六种字号。

- 段落

段落标签：`<p></p>`，中间输入段落内容。段落内可插入属性align=""`，修改该段的对齐方式。属性值包括left/center/right，分别指向左对齐、居中、向右对齐。

- 链接

链接标签：`<a herf=""></a>`，一般都要带有属性`herf=""`。herf是超文本引用（hypertext reference）的缩写。意思是此处需要引用一个链接。

> 🤔：如果只添加`herf`属性，用户点击该链接时，页面就会被所连接到的那个网站覆盖。如果想要在新建页面中打开该链接，需要添加属性`target="_blank"`。

- 图片

图片标签：`<img src="" alt="">`，其中`src=""`和`alt=""`这两个标签属性的意思分别是**源**（source）和**代替**（alternative）。前者的意思是指出该图片在哪里；后者是如果该图片不可用时，在此处显示给读者的文本（例如：该图片不可用）。

![](https://github.com/BurnedChocolate/Tasks/blob/1360f90cf0a1a006c91ef1f38b549551a8cb94e8/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/%E5%9B%BE%E7%89%87%E4%B8%8D%E5%8F%AF%E7%94%A8.jpg)

常用的图片标签属性还有`width=""` 、`height=""`，它们表示该图片的**宽**和**高**，可以根据需求调整。

另外，在HTML中，`./`的意思是**当前路径**。比方说如果我们要引用同一文件夹内的另一图片，可直接输入`./`+文件路径。（输入`src=""`属性时很有用。）

![](https://github.com/BurnedChocolate/Tasks/blob/1360f90cf0a1a006c91ef1f38b549551a8cb94e8/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/%E8%B7%AF%E5%BE%84img.jpg)


下图是该部分的所有操作截图。

![](https://github.com/BurnedChocolate/Tasks/blob/1360f90cf0a1a006c91ef1f38b549551a8cb94e8/%E9%98%B6%E6%AE%B53%E7%AC%94%E8%AE%B0/pictures/%E6%A0%87%E9%A2%98%E7%AD%89%E6%93%8D%E4%BD%9C%E6%88%AA%E5%9B%BE%E4%B8%80%E8%A7%88.jpg)

>  🤔：从标题大小个数，到链接与图片插入，很多地方都与使用markdown时的感受相似甚至相同。它们之间是否有联系？

- 按钮

按钮标签：`<button>`，单标签，\<button type="button" onclick="alert('你好，世界!')">

另外还有一些常用标签：

- 换行：`<br>`，单标签
- 水平线：`<hr>`，单标签
- 注释：`<!-- 这个位置写注释 -->`（快捷键ctrl+/）
- 粗体、斜体、表格等……

HTML标签种类繁多，所有元素可在该网站中查询：[HTML 元素参考](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element)

#### 📕块级元素（Block）、内联元素（Inline）

- **块级元素：**独占一行的元素。块级元素用来搭建网站架构、布局、承载内容，负责整体的大的方面。块级元素其高度、行高和边距都是可控的。（eg：\<div>、\<h1>-\<h6>、\<p>）
- **内联元素：**通常在一行内显示。内联元素负责局部和细节，其高度、行高和边距不可控。（eg：\<a>、\<img>）

#### 📕\<div>、\<span>标签【重要】

\<div>，division，分割；\<span>，span，范围、跨度。

|          | \<div>                                                   | \<span>                     |
| -------- | -------------------------------------------------------- | --------------------------- |
| **分类** | 容器级标签                                               | 文本级标签                  |
| **作用** | 把标签中的内容分割为独立的区块。编写时必须单独占据一行。 | 和div的作用一致，但不换行。 |

总体来说\<div>和\<span>的唯一区别是**是否换行**。

\<div>在浏览器中默认不会增加任何效果，它的唯一作用是改变\<div>中元素的语义，将其中的所有元素是变成一个小区域。

由于\<div>是一个容量级标签，\<div>里面什么都能放，也能\<div>套\<div>。但因为\<span>是个文本级标签，所以\<span>里面只能放入文字、图片、表单元素。这也决定了为什么\<span>不会自动换行。

\<div>通常与css一起使用，称**“div+css”**：\<div>标签负责布局、结构、分块，css负责样式。

## 3.参考资料

- [HTML｜超简单HTML入门教程 - bilibili](https://www.bilibili.com/video/BV1gP4y1E75S)
- [为初学者准备的：HTML 速成 -bilibili](https://www.bilibili.com/video/BV1vs411M7aT)
- [HTML 教程 - 菜鸟教程](https://www.runoob.com/html/html-tutorial.html)
- [qianguyihao/Web：前端图文教程 - github](https://github.com/qianguyihao/Web)