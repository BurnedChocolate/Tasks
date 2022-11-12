# JavaScirpt基础

## 0.学习要求

+ JavaScript【可以和C语言去类比，任何语言学习都离开这些，所以不要害怕】
  + 学习JavaScript基本语法
  + 了解JavaScript数据类型
    + 字符串（String）
    + 数字（Number）
    + 布尔（Boolean）
    + Null
    + Undefined
    + 对象（Object）
    + 数组（Array）
  + 了解HTML/CSS/JavaScript三者之间的关系 【重点】

## 1.JavaScript是什么？

**✔JavaScript是一种轻量级的编程语言**

JavaScript是互联网上最流行的脚本语言，用于HTML和web，是一种轻量级、大功能强大的脚本语言。
**脚本语言**：并非在计算机CPU直接去识别的语言，运行不用进行编译，但执行需要平台。

✔**JavaScript、HTML、CSS之间的联系**

JavaScript是web开发三件套之一。三件套如下：

- HTML定义网页的内容；
- CSS规定网页的布局；
- JavaScript对网页行为进行编程。

简单来说，这三者间有这样的对应关系：

- HTML——控制网页内容（即“显示哪些内容？”）；

- CSS——控制网页外观（即“如何显示有关内容？”）；

- JavaScript——控制网页行为（即“内容应该如何对事件做出反应？”）。

或者可以用这样一个比喻进行理解：现在想象一辆车！🚗

- HTML——车子最基础的架构，例如车门车轮车架车坐椅等，是车辆在喷漆等美化以前最基本的外观；

- CSS——喷漆和零件角度，炫酷的涂装，让车显得漂亮和独特；
- JavaScript——汽车动力系统和其他系统，可以决定怎么启动车辆，运动多块，何时停止，怎么与卫星通信，怎样接收车载广播等等，是整个车的灵魂，让整辆车从**静态**变得**动态**起来。没有JavaScript，整辆车就只是一堆漂亮的废铁。

## 2.JavaScript基础知识

### 📕样式类型

HTML中的 Javascript 脚本代码必须位于`<script>`与 `</script>` 标签之间。

Javascript脚本代码可被放置在 HTML 页面的`<body>`和`<head>`部分中。

JavaScript的几种写法与CSS的内联样式、内部样式、外部样式三种样式类型比较相似。JavaScript使用的属性是`script`，以下是三种写法示例：


- head中的js脚本

```js
<head>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</head>

<body>
<button type="button" onclick="myFunction()">尝试一下</button>
</body>
```

- body中的js脚本

```javascript
<body>
<button type="button" onclick="myFunction()">尝试一下</button>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</body>
```

- 外部脚本

```js
<script src="script.js"></script>
```

**注：**一般而言，在`<body>`中，我们一般把`script`写在最末尾。因浏览器解析文件自顶向下，脚本编译会拖慢显示，最后再渲染`script`文件可以提高速度，增加用户体验。

### 📕基本语法

#### ①值

JavaScript语句定义两种类型的值：混合值和变量值。混合值被称为**字面量**。变量值被称为**变量**。

**字面量**可以是整数或小数，有无小数点均可。

**变量**用于储存数据的值，用关键字`var`定义变量，用等号为变量赋值。

```js
5
3.14
var a,b
a = 5
b = 3.14
```

字面量分为：

- **数字字面量**：`3`、`5`、`10086`
- **字符串字面量**（可以使用单引号或双引号）：`'Never gonna give you up'` 、`"Never gonna let you down"`
- **表达式字面量**（用于计算）：`5+6`、`5*6`
- **数组字面量**：`[1,2,3,4,5]`
- ……

#### ②操作符

| 类型                 | 实例      |
| -------------------- | --------- |
| 赋值、算数、位运算   | = + - * / |
| 条件、比较、逻辑运算 | == != < > |

#### ③语句

JavaScript语句用于向浏览器发出命令，语句之间用`;`隔开。

```js
x=3+2;
y=4*5;
```

#### ④关键字

关键字用于标识要执行的操作。这一部分可以类比其他编程语言（如c的`int`、`printf`）。刚才的`var`关键字就是告诉浏览器创建一个新的变量。

### 📕数据类型

- **JavaScript的动态类型**

JavaScript 拥有动态类型。也就是说相同的变量可用作不同的类型：

```js
var x = 5;           // x为数字
var x = "John";      // 现在x为字符串
```

+ **字符串（String）**

存储字符的变量。单双引号均可使用。

```js
var lyric1 = 'Never gonna give you up'；
var lyric2 = "Never gonna let you down";
```

+ **数字（Number）**

JavaScript中，数字只有一种类型。带不带小数点均可。也可以用科学计数法书写。

```js
var x = 3;
var y = 3.00;
var z = 3e-5;
```

+ **布尔（Boolean）**

**布尔**即**逻辑**，只有两个值：true 或 false。

```js
var t = true;
var f = false;
```

+ **Null**

Null表示该值被定义为空。

可通过将变量的值设置为 null 来清空变量。

```js
var m = null;
```

+ **Undefined**

Undefined表示该变量不含有值。

```js
var n = undefined;
```

+ **对象（Object）**

对象由花括号分隔。在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义。属性由逗号分隔：

```js
var object1 ={
    name:"Rick Astley",
    song:"Never gonna give you up",
    release year:1987
};
```

对象的寻址方式是：

```js
a = object1.name;
b = object1["song"];
```

+ **数组（Array）**

数组的基本写法和例子如下：

```js
var array-name = [item1, item2, ...];
                  
var array1 = ["js","css","html"];
var array2 = [1,2,3,4,5]
```

和c中的数组一样，[0]是数组中的第一个元素，[1]是第二个。

访问、修改数组元素的例子如下：

```js
var name = array1[0]; //访问数组中第一个元素的值
array1[0] = "yeah";//修改数组第一个元素的值
array2[1] = 666 ;//修改数组第二个元素的值
```

## 3.参考资料

- 入门教程
  - [7 分钟掌握 JavaScript 核心语法 - bilibili](https://www.bilibili.com/video/BV1y3411g7WM)
  - [JavaScript快速入门 - bilibili](https://www.bilibili.com/video/BV15L4y1a7or)
  - [为初学者准备的：JavaScript 速成 - bilibili](https://www.bilibili.com/video/BV1Jt411D7j6)
- 更加专业的教程
  - [JavaScript 教程 - 菜鸟教程](https://www.runoob.com/js/js-tutorial.html)
  - [JavaScript 教程 - w3school](https://www.w3school.com.cn/js/index.asp)
