HTML和CSS学习

# HTML与CSS简介

- HTML指的是超文本标记语言 (Hyper Text Markup Language)，超文本指的是超链接, 标记指的是标签, 是一种用来制作网页的语言, 这种语言由一系列的标签组成，通过这些标签可以将网络上的文档格式统一，使分散的Internet资源连接为一个逻辑整体。 用这种语言制作的文件保存的是一个文本文件, 文件的扩展名为 .html 或者 .htm。现在已经发展到5.0版, 即HTML5。
- CSS级联样式表，通常又称为“风格样式表（Style Sheet），它是用来进行网页风格设计的。使用 CSS 来更改内容的字体、颜色、大小、间距，将内容分为多列，或者添加动画及其他的装饰效果。
- HTML 用于定义内容的结构和语义，形成页面的基本框架，CSS 用于设计风格和布局，改变内容的外观。

# HTML基础

## HTML框架(!快捷生成）

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

1. `<!DOCTYPE html>`，文档声明，告诉浏览器使用哪种HTML版本来显示网页，位于文档最前面位置。
2. `<lang>`,用来定义当前文档显示的语言。 en定义语言为英语，zh-CN定义语言为中文
3. `<meta>`,定义文档元数据，常用来描述当前页面的特性，比如文档字符集 `charset="utf-8"`
4. `<head>`, HTML 头部包含 HTML元素的内容，页面在浏览器加载后它的内容不会在浏览器中显示，它的作用是保存页面的一些[元数据](https://developer.mozilla.org/zh-CN/docs/Glossary/Metadata)，可以设置meta，title以及导入css。
5. `<body>`存放的是页面会显示的内容以及元素。 

## HTML常用标签

1. 标题标签

`<h>`标签定义标题，由`<h1>`到`<h6>`字体逐渐变小

```HTML
<h1>标题1</h1>
<h2>标题2</h2>
<h3>标题3</h3>
<h4>标题4</h4>
<h5>标题5</h5>
<h6>标题6</h6>
```

1. 盒子标签

<div>标签定义一个盒子，一行只能放一个盒子。<span>是小盒子，一行可以放多个。

div和span的区别是，div标签是块级元素，每个div标签都会从新行开始显示，占据一行，且div标签可以通过css样式来设置自身的宽度（也可省略，当没有使用css自定义宽度时，div标签的宽度为其的容器的100%）、高度，且还可以设置标签之间的距离（外边距和内边距）；div标签内可以添加其他的标签元素（行内元素、块级元素都行）。而span标签是行内元素，会在一行显示；span标签内只能添加行内元素的标签或文本。

   2.a标签

<a>标签用于链接到一个网址或者一个文件，是一个超链接。

```HTML
<a href="http://www.baidu.com" target="_blank">百度</a>
```

这里的href规定的是指向页面的URL地址，target属性指的是规定打开链接网页的方式。

target属性的几种属性值的取值分别为：

- _blank 代表在新窗口中打开页面的链接地址；
- _self 代表在自身窗口打开页面链接，默认为self；
- _parent 代表是在父窗口中打开此网页；
- _top 代表的是在最顶层打开此网页，测试的效果与self相同；

通过css可以改变当鼠标点击，经过，浏览后的a标签的颜色。

```CSS
a {
    text-decoration: none;/* 用于取消a标签自带的下划线 */
    color: #000;
}
/* 状态一: 未被访问过的链接 */
a:link {
    text-decoration: none;
    color: #000;
}
/* 状态二: 已经访问过的链接 */
a:visited {
    text-decoration: none;
    color: red;
}
/* 状态三: 鼠标划过(停留)的链接(默认红色) */
a:hover {
    text-decoration: none;
    color: royalblue;
}
/* 状态四: 被点击的链接 */
a:active {
    text-decoration: none;
    color: orange;
}
```

​     3.img标签

<img/>标签是单标签，用于在页面中嵌入照片。

```HTML
<img src="photos/郁金香.jpg"  alt="郁金香" title="tulip"/>
```

- `src` 属性是必须的，它包含了你想嵌入的图片的路径。
- `alt` 属性包含一条对图像的文本描述，是在图片不能正常显示时，例如路径错误时出现的文本提示。
- `title` 属性是在鼠标在移动到元素上的文本提示。

​     4.input标签

 `<input>` 元素用于为基于 Web 的表单创建交互式控件，以便接受来自用户的数据，也是单标签。

不同类型的input标签可以输入的内容不同，常见属性为type和value，value 属性中的值表示输入框中的值。

```HTML
<input type="text" placeholder="请在这里输入用户名">
<input type="button">
<input type="password">
<input type="radio"name="gender"value="girl">
<input type="radio" name="gender"value="boy"> 
```

- type = 'text' 表示文本输入框。
- type = 'password' 就是表示密码框，用户输入的内容是不可见的。
- type = 'radio'表示选择框,通常使用同一name属性的多个选择框只能选择一个。
- type = 'button'表示按钮框。

# CSS

## 基础语法

### selector{property：value}

CSS规则由两个主要部分构成：选择器以及一条或多条声明。每条声明由一个属性和一个值组成，及以键值对的形式出现。属性(property)是设置的样式属性，每个属性有一个值(value)，属性和值被冒号分开。

## 三种引入方式

1. 外部样式：即CSS代码保存在外部，HTML文件通过链接式link或者导入式@import引用这个外部样式表。

```HTML
 <!--链接式:常用-->
  <link type="text/css" rel="stylesheet" href="css/style.css" /> 
  <!--导入式-->
  <style type="text/css">
    @import url("css/style.css");
  </style>
```

   2.内部样式：整体放在head标签，在style标签内写CSS代码，作用仅在本页。

```HTML
<!DOCTYPE>
<html>
<head>
  <meta charset="utf-8" />
  <title>内部样式表</title>
  <!--使用内部样式表引入CSS-->
  <style>
    div{
        width: 65px;
        height: 50px;
        background: green;
    }
  </style>
</head>
<body>
     <div>我是DIV</div>
</body>
</html>
```

​    3.行内样式：直接在html元素内使用style，不推荐使用。

```HTML
 <h1 style="color:red;">111111</h1>
 <p style="color:red;font-size:30px;">我是p标签</p>
```

## [盒模型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model)

在css中，任何元素都可以看成是一个盒子。一个盒子是由四部分组成的：内容（content）、内边框（padding）、边框（border）和外边框（margin）。

盒模型有两种：**标准盒模型（content-box）**和**IE盒模型（border-box）**。

标准盒模型下，盒子的实际尺寸=内容（设置的宽/高）+ 内边距 + 边框。

IE盒模型下，盒子的实际尺寸=设置的宽/高= 内容 -内边距 - 边框。（实际盒子空间不包括padding和border）

![image-20231025135230592](https://s2.loli.net/2023/10/25/nMLgsf7PBaSxFYq.png)

## 块级元素，行内元素，行内块元素

### 块级元素

- 每个块元素通常都会独自占据一整行或多整行，可以对其设置宽度、高度、对齐等属性、常用于网页布局和网页结构的搭建
- 块级元素的特点:
  - 总是从新行开始。
  - 高度、行高、外边距以及内边距都可以控制。
  - 宽度默认是容器的100%。
  - 可以容纳内联元素和其他块元素。
- 常见的块元素有:

```
<h1>~<h6>`、`<p>`、`<div>`、`<ul>`、`<ol>`、`<li>
```

### 行内元素

- 行内元素(内联元素)不占有独立的区域,仅仅靠自身的字体大小和图像尺寸来支撑结构，一般不可以设置宽度，高度，对齐等属性，常用于控制页面中文本的样式。
- 行内元素的特点：
  - 和相邻行元素在一行上。
  - 高、宽设置无效，但水平方向的`padding`和`margin`可以设置，垂直方向的无效。
  - 默认宽度就是它本身内容的宽度。
  - 行内元素只能容纳文本或者其他行内元素。(a特殊，容纳链接)
- 常见的行内元素有:

`<a>`、`<strong>`、`<b>`、`<em>`、`<i>`、`<del>`、`<s>`、`<span>`、`<u>`、`<ins>`

### 行内块元素(特殊的行内元素)

- 在行内元素中有几个特殊的标签 `<img>`、`<input>`、 `<td>`,可以对他们设置宽高和对齐属性，有些资料可能会称它们为`行内块`元素。
- 行内块元素的特点：
  - 和相邻行内元素(行内块)在一行上，但是之间会有空白缝。
  - 默认宽度就是它本身内部的宽度。
  - 高度、行高、外边距以及内边距都可以控制。

### 显示模式转换

- 块级标签转为行内标签模式

```CSS
div  {display:inline;  
  }
```

- 行内标签模式转为块级模式

```CSS
span {display:block; 
 }
```

- 行内标签模式转为行内块模式

```CSS
a {display:inline-block;  
  }
```

## 选择器

[CSS选择器-MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Selectors)

选择器可以根据不同需求选择不同的标签。

CSS选择器主要可以分为**基础选择器**和**复合选择器**两个大类。

### 基础选择器

基础选择器是由单个选择器组成的，主要包括：**标签选择器**、**类选择器**、**id 选择器**和**通配符选择器**。

1. 标签选择器：

标签选择器用于将HTML的标签作为选择器，能快速为页面中同类型的标签统一设置样式，但不能设计差异化样式。

```CSS
div{ font-size: 12px; color: red }
/* 页面里所有盒子都将改变成此样式 */
```

   2.类选择器：

类选择器以" . " 进行标识，可以用于给多个HTML标签设置相同的样式，也可以给一个标签指定多个类名，从而达到更多的选择目的。

```HTML
<style>
.test1  {color:royalblue;font-size:12px }
.test2  { color: red }
</style>
<div class="test1">hi</div>
<div class="test1 test2">天气很好</div>
```

   3.id选择器：

id 选择器以" # " 进行标识，可以为标有特定 id 的 HTML 元素指定特定的样式。id属性唯一。

```HTML
<style>
#wrap  { background-color:orange}
</style>

<div id="wrap"> 你好</div>
```

   4.通配符选择器：

通配符选择器使用 " * " 定义，它表示选取页面中所有元素（标签）。

### 复合选择器

复合选择器是建立在基础选择器之上，由两个或多个基础选择器，通过不同的方式组合而成的。 常用的复合选择器包括：**后代选择器**、**子选择器**、**并集选择器**、**伪类****选择器**等等。

1. 后代选择器:

后代选择器又称为包含选择器，可以选择父元素里面子元素。其写法就是把外层标签写在前面，内层标签写在后面，*中间用空格分隔*。当标签发生嵌套时，内层标签就成为外层标签的后代。

```CSS
/* 元素1 元素2 { 样式声明 } 
  表示选择元素 1 里面的所有元素 2 (后代元素)。*/

div p  { font-size: 12px; color: red; }    
/* 选择 div 里面所有的 p 标签元素 */
```

   2.子选择器:

子元素选择器（子选择器）只能选择作为某元素的**最近一级子元素**。

```CSS
/*元素1 > 元素2 { 样式声明 } 
选择元素1 里面的所有直接后代(子元素) 元素2。*/

div > p { font-size: 12px; color: red; } 
/* 选择 div 里面所有最近一级 p 标签元素 */
```

  3.并集选择器:

并集选择器可以选择多组标签, 同时为他们定义相同的样式，通过英文逗号" , "连接而成。通常用于集体声明。

```CSS
/*元素1,元素2,元素3 { 样式声明 } */
div,.myclass,#psd { 样式声明 }
 /* 选择 div、.myclass和#psd元素 */ 
```

   4.[伪类选择器和伪元素](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)：

伪类是选择器的一种，它用于选择处于特定状态的元素，伪类和伪元素是用来修饰不在文档树中的部分。比如当它们是这一类型的第一个元素时，或者是当鼠标指针悬浮在元素上面的时候。伪类的操作对象是文档树中已有的元素，而伪元素则创建了一个文档数外的元素。因此，伪类与伪元素的区别在于：有没有创建一个文档树之外的元素。

```CSS
<p>Hello World, and wish you have a good day!</p>
p:first-letter {font-size: 5em ;color:orange;}
 /* 可以通过设置<p>的:first-letter伪元素来为其添加样式。这个时候，看起来好像是创建了一个虚拟的<span>元素并添加了样式，但实际上文档树中并不存在这个<span>元素。*/ 
```

![image-20231010141448332](https://s2.loli.net/2023/10/25/XwKUGVpxSjhqmTe.png)

### 选择器权重

权重规则概述：

- !important 优先级最高，但也会被权重高的important所覆盖，一般不推荐使用important。
- 行内样式总会覆盖外部样式表的任何样式(除了!important)
- 单独使用一个选择器的时候，不能跨等级使css规则生效。(无论多少个类选择器，都没有一个id选择器权重高）
- 如果两个权重不同的选择器作用在同一元素上，权重值高的css规则生效
- 如果两个相同权重的选择器作用在同一元素上：以后面出现的选择器为最后规则.
- 一般为!important > 行内样式 > ID选择器 > 类选择器 > 标签 > 通配符 > 继承 > 浏览器默认属性 
- （注意:“权值”和“权级”的概念是为了更好的理解权重而提出的，并不是真的存在的)
  - ![image-20231010141523323](https://s2.loli.net/2023/10/25/zWmjvU9oKEsPy3A.png)

## [CSS文本样式](https://www.runoob.com/css/css-text.html)

### 文本颜色

- 十六进制值 - 如: ＃FF0000
- 一个RGB值 - 如: RGB(255,0,0)
- 颜色的名称 - 如: red

### 文本对齐方式

text-align属性有四个值：left，center，right，justify(两端对齐)；属性默认值为auto。

### 文本修饰

- text-decoration 属性用来设置或删除文本的修饰。
- text-decoration:none，主要是用来删除超链接的下划线，也可以使用其他值来设置文本的修饰；
- text-decoration:overline，设置文本上划线。
- text-decoration:line-through; 设置文本中间划线。
- text-decoration:underline; 设置文本下划线。

```CSS
h1 {text-decoration:overline;}
h2 {text-decoration:line-through;}
h3 {text-decoration:underline;}
```

### 文本阴影

text-shadow用于设置页面文本的阴影

```CSS
selector {
    text-shadow: color offset-x offet-y blur-raduis;
}
```

1. color：

- 可选项，设置文本内容的阴影颜色。

   2.offset-x：

- 必选项，阴影在水平方向的偏移量。
- 如果值小于 0 的话，则表示向左偏移。
- 如果值等于 0 的话，则表示水平方向不发生任何偏移。
- 如果值大于 0 的话，则表示向右偏移。

   3.offset-y：

- 必选项，垂直方向阴影的偏移值。
- 如果值小于 0 的话，则表示向上偏移。
- 如果值等于 0 的话，则表示垂直方向不发生任何偏移。
- 如果值大于 0 的话，则表示向下偏移。

   4.blur-raduis：

- 可选项，设置文本内容的阴影模糊半径。
- 不允许负值，如果没有指定，则默认为 0。值越大，阴影半径越大。
- 设置多重阴影效果需要设置多个阴影值，这些值之间使用逗号分隔。

### 文本间距

line-height:行高，也就是文本行的高度。

`line-height=上距离+内容高度+下距离`。

#### 单行文字垂直居中

当 line-hieght 等于 height，内容垂直居中 当 line-hieght 大于 height，内容向下移动 当 line-hieght 小于 height，内容向上移动

```CSS
div{line-height:40px}
/*同时设置div的高度也为40px,则div中的单行文字垂直居中*/
```

### 字体粗细

font-weight：设置文字是否加粗显示。

| 属性值  | 作用        |
| ------- | ----------- |
| normal  | 默认（400） |
| bold    | 加粗（700） |
| bolder  | 更粗        |
| lighter | 细体        |

```CSS
 p{
        font-weight: bold;
      }
 span{
        font-weight:600;
      }
```

### 文本单位

- 像素（px）：是页面布局的基础，常用单位，一个像素表示终端（电脑、手机、平板等）屏幕所能显示的最小的区域，像素分为两种类型：CSS像素（为web开发者提供，在CSS中使用的一个抽象单位）和物理像素（只与设备的硬件密度有关，任何设备的物理像素都是固定的）。
- 百分比（%）：当浏览器的宽度或者高度发生变化时，通过百分比单位可以使得浏览器中的组件的宽和高随着浏览器的变化而变化，从而实现响应式的效果。一般认为子元素的百分比相对于直接父元素。
- em和rem：对于px更具灵活性，它们都是相对长度单位，它们之间的区别：em相对于自身或者父元素字体，rem相对于根元素（html字体大小：`document.documentElement.style.fontSize`）。
  - em： 文本相对长度单位。相对于当前对象内文本的字体尺寸。如果当前行内文本的字体尺寸未被人为设置，则相对于浏览器的默认字体尺寸(默认16px)。(相对父元素的字体大小倍数)。
  - rem： rem是CSS3新增的一个相对单位，相对于根元素（html元素）的font-size的倍数。作用：利用rem可以实现简单的响应式布局，可以利用html元素中字体的大小与屏幕间的比值来设置font-size的值，以此实现当屏幕分辨率变化时让元素也随之变化。
  -  px、em、rem的区别及使用场景
  -  **区别:**
  - px 是固定的像素，一旦设置了就无法因为适应页面大小而改变。
  - em 和 rem 相对于 px 更具有灵活性，他们是相对长度单位，其长度不是固定的，更适用于响应式布局。 
    -   em 是以自身的 font-size 为参考的，当 em 没有设置自身的 font-size ，则会以父元素的 font-size 为标准；
    -   rem 是相对于根元素，这样就意味着，只需要在根元素确定一个参考值即可。
  -  **适用场景:**
  - 对于只需要适配少部分移动设备，且分辨率对页面影响不大的，使用px即可 。
  - 对于需要适配各种移动设备，使用rem，例如需要适配iPhone和iPad等分辨率差别比较挺大的设备。

### 字体样式

[font-family](https://zhuanlan.zhihu.com/p/56275402)

## CSS背景

### 背景颜色

background-color 属性定义了元素的背景颜色.

```CSS
body {background-color:#b0c4de;}
```

### 背景图像

#### background-image 

**`background-image`** 属性描述了元素的背景图像.

`语法`：`background-image: url('图片的路径')` -- 路径可以是本地的也可以是网上的

**多张图片**的话可以使用`,`隔开

```
语法`：`background-image: url('图片的路径'),url('图片的路径')
```

#### background-repeat

**`background-repeat`** 设置元素背景图像在页面中呈**水平或垂直**方向**平铺**

可设置的值：

- `repeat`：**水平和垂直**方向上平铺，默认
- `no-repeat`：不平铺
- `repeat-x`：在**水平**方向上平铺
- `repeat-y`：在**垂直**方向上平铺

#### background-position

**`background-position`** 设置背景图像在背景中的**位置**

可设置的值：

- `left top/center/bottom`：`左上/左中/左下`(水平位置，垂直位置)
- `right top/center/bottom`：`右上/右中/右下`(水平位置，垂直位置)
- `center top/center/bottom`：`中上/居中/中下`(水平位置，垂直位置)
- `x% y%`：百分比 (水平位置，垂直位置)
- `x y`：具体值 (水平位置，垂直位置)

**`注意`**：如果**只设置一个**属性值，则**另一个**属性值默认为 `center`

#### background-attachment

**`background-attachment`** 设置背景图像是否**固定**或者随着页面的其余部分**滚动**。

可设置的值：

- `scroll`：滚动，默认 (跟随页面)
- `fixed`：固定
- `local`：滚动 (跟随元素内容)

#### 简写

**background简写没有顺序要求**

**`background：背景颜色 背景图片地址 背景是否平铺 背景图像滚动 背景图片位置`**

#### background-size

**`background-size`**  设置元素的背景图片的**大小**

可设置的值：

- `width height`：具体值 (宽度，高度)
- `width% height%`：百分比 (宽度，高度)
- `cover`：等比例缩放，图片**完全覆盖**到**整个盒子**，有可能图片**显示不完全**
- `contain`：等比例缩放，当**高或宽**其中有一个与盒子的尺寸**相等**，就**不再缩放**了

**`注意`**：如果**只设置一个**属性值，则**另一个**属性值默认为 `auto`

## 边框属性

CSS边框属性允许你指定一个元素边框的样式和颜色。

### 边框样式

border-style属性可以有1-4个值

![image-20231010141618388](https://s2.loli.net/2023/10/25/2YiILtCd7uqrBaS.png)

### 边框宽度

border-width 属性为边框指定宽度。

为边框指定宽度有两种方法：可以指定长度值，比如 2px 或 0.1em(单位为 px, pt, cm, em 等)，或者使用 3 个关键字之一，它们分别是 thick 、medium（默认值） 和 thin。

## 布局与定位

### 文档流

[相关资料](https://zhuanlan.zhihu.com/p/64190768)

文档流：可以理解为元素的一种状态，处于这种状态下的元素具有一些特性。标准文档流就是一个“默认”状态，即元素排版布局过程中，元素会自动从左往右，从上往下的流式排列。并最终窗体自上而下分成一行行，并在每行中从左至右的顺序排放元素。

#### 脱离文档流

也就是将元素从普通的布局排版中拿走，不占据位置（悬空了），其他盒子在定位的时候，会当做脱离文档流的元素不存在而进行定位。需要注意的是，使用float脱离文档流时，其他盒子会无视这个元素，但其他盒子内的文本依然会为这个元素让出位置，环绕在周围。而对于使用position脱离文档流的元素，其他盒子与其他盒子内的文本都会无视它，及会占据其原先的位置。

### position

position 属性指定了元素的定位类型。

position 属性的五个值：

static relative fixed absolute sticky

#### static 定位

HTML 元素的默认值，即没有定位，遵循正常的文档流对象。

静态定位的元素不会受到 top, bottom, left, right影响。

#### fixed 定位

元素的位置相对于**浏览器窗口是固定位置。**

**即使窗口是滚动的它也不会移动：**

```CSS
p{
    position:fixed;
    top:30px;}
```

#### relative 定位

相对定位元素的定位是相对其正常位置，relative定位的元素未脱离文档流**。**

```CSS
h2
{
    position:relative;
    left:20px;}
```

#### absolute 定位

绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于整个html页面调整，开启绝对定位的元素脱离文档流:

```CSS
h2
{
    position:absolute;
    left:100px;
    top:150px;}
```

#### sticky 定位

https://blog.csdn.net/weixin_51081257/article/details/121305642

粘性定位的元素是依赖于用户的滚动，元素定位表现为在跨越特定阈值前为相对定位，（这个特定阈值指的是 top, right, bottom 或 left 之一，换言之，指定 top, right, bottom 或 left 四个阈值其中之一，才可使粘性定位生效。否则其行为与相对定位相同之后为固定定位。）而当页面滚动超出目标区域时，它的表现就像 position:fixed;它会固定在目标位置。

注意: Internet Explorer, Edge 15 及更早 IE 版本不支持 sticky 定位。

### CSS布局

#### flex布局

- Flexbox布局也叫Flex布局，弹性盒子布局。它的**目标**是提供一个更有效地布局、对齐方式，并且能够使父元素在子元素的大小未知或动态变化情况下仍然能够分配好子元素之间的间隙。**主要思想**是使父元素能够调整子元素的宽度、高度、排列方式，从而更好的适应可用的布局空间。设定为flex布局的元素能够放大子元素使之尽可能填充可用空间，也可以收缩子元素使之不溢出。 
- Flex布局更适合小规模的布局，可以简便、完整、响应式的实现各种页面布局。但是，设为Flex布局以后，其子元素的`float`、`clear`和`vertical-align`属性将失效。
- Flex布局是一个完整的模块，它包括了一套完整的属性。其中采用 Flex 布局的元素，称为 Flex 容器，简称"**容器**"。它的所有子元素就是容器成员，称为 Flex 项目，简称"**项目**"。容器默认存在两个轴：**水平轴**（main axis）和**垂直轴**（cross axis），项目默认沿主轴排列（水平轴）：

![image-20231010141704221](https://s2.loli.net/2023/10/25/pCAVRGJdj9rqwBm.png)

- **main** **axis**: Flex 父元素的主轴是指子元素布局的主要方向轴，它由属性flex-direction来确定主轴是水平还是垂直的，默认为水平轴。
- **main-start & main-end**: 分别表示主轴的开始和结束，子元素在父元素中会沿着主轴从main-start到main-end排布。
- **main** **size**: 单个项目占据主轴的长度大小。
- **cross** **axis**: 交叉轴，与主轴垂直。
- **cross-start & cross-end**: 分别表示交叉轴的开始和结束。子元素在交叉轴的排布从cross-start开始到cross-end。
- **cross size**: 子元素在交叉轴方向上的大小。

#### 父元素属性

使用flex布局，首先需要给父元素指定为flex布局，这样容器内的元素才能实现flex布局：

```CSS
/*任何一个容器都可以指定为flex布局*/
<div class="container"></div>

.container {
    display: flex | inline-flex;
}
/*这里有两种方式可以设置flex布局，使用display: flex;会生成一个块状的flex容器盒子，使用display: inline-flex;会生成一个行内的flex容器盒子。如果我们使用块状元素，比如div标签，就可以使用flex，如果使用行内元素，就可以使用inline-flex。多数情况下，我们会使用display: flex;。*/
```

父元素（容器）可以设置以下六个属性：

- **flex-direction**：主轴方向，它决定了容器内元素排列方向，它有四个属性值：

```CSS
.container {    flex-direction: row | row-reverse | column | column-reverse;}
```

`flex-direction: row`：默认值，沿水平主轴从左到右排列，起点在左沿

`flex-direction: row-reverse`：沿水平主轴从右到左排列，起点在右沿

`flex-direction: column`：沿垂直主轴从上到下排列，起点在上沿

`flex-direction: column-reverse`：沿垂直主轴从下到上排列，起点在下沿

![image-20231010141725406](https://s2.loli.net/2023/10/25/pGvy2j1kMBVJLqW.png)

- **flex-wrap**：容器内元素是否可以换行，它有三个属性值：

```CSS
.container {    flex-wrap: nowrap | wrap | wrap-reverse;}
```

`flex-wrap: nowrap`：默认值，不换行。当主轴的长度是固定并且空间不足时，项目尺寸会随之进行调整，而不会换行。

`flex-wrap: wrap`：换行，第一行在上面

`flex-wrap: wrap-reverse`：换行，第一行在下面

- **flex-flow：**

**`flex-flow`** 是 **`flex-direction`** 属性和**`flex-wrap`**属性的简写，默认为:**`flex-flow:row nowrap`**，用处不大，最好还是分开来写。

- **justify-content**：定义元素在主轴的对齐方式，它有五个属性值：

```CSS
.container {    justify-content: flex-start | flex-end | center | space-between | space-around;}
```

![image-20231010141755578](https://s2.loli.net/2023/10/25/PzZFemb19xE2shl.png)

- **align-items：**定义flex子项在flex容器的当前行的侧轴（纵轴）方向上的对齐方式。元素在交叉轴上的对齐方式，它有五个属性值：

```CSS
.container {  align-items: flex-start | flex-end | center | baseline | stretch;}
```

![image-20231010141815053](https://s2.loli.net/2023/10/25/w8qJPSGHjeZiQIB.png)

- **align-content**：与 justify-content 属性类似，可以在容器的侧轴还有多余空间时调整项目的对齐方式。它有六个属性值：

```CSS
.container {    align-content: flex-start | flex-end | center | space-between | space-around | stretch;}
```

#### 子元素属性

子元素有以下六个属性：

- order
- flex-grow
- flex-shrink
- flex-basis
- flex
- align-self

[相关资料](https://blog.csdn.net/u010377383/article/details/78976516)

#### 浮动

float属性指定一个元素应沿其容器的左侧或右侧放置，允许文本和内联元素环绕它。该元素从网页的正常流动（文档流）中移除，但是仍然保持部分的流动性（与绝对定位相反）。

[MDN](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Floats)

[相关博客](https://www.cnblogs.com/iyangyuan/archive/2013/03/27/2983813.html)

## 渐变

[css渐变-MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Images/Using_CSS_gradients)

[相关知识](https://juejin.cn/post/6844903692974424078)

颜色渐变可以分为两种，线性渐变和径向渐变。

### 线性渐变

方向： 在关键字 to 后面加上 top、bottom、right、left 中的某一个关键字或多个关键字。

当然我们可以使用多个关键字，例如 to bottom right ，表示从左上到右下结束。

```CSS
background-image: linear-gradient( 方向/角度 , 颜色1，颜色2，颜色3....);
```

1.有过渡色渐变：

```CSS
.div1{background:linear-gradient(red,yellow,green);}
  /*还可以设置百分比改变每个颜色的比例*/
```

2.无过渡色渐变：

```CSS
  .div1{background:linear-gradient(red 0%,red 50%,yellow 50%,yellow 100%);}
  /*一半红一半黄，简写background：linear-gradient(red 50%,yellow 50%);*/
```

### 径向渐变

径向渐变就是沿着圆周或者椭圆周向外扩散的渐变。

我们通过 radial-gradient();来定义一个径向的渐变。

```CSS
background-image: radial-gradient(shape size at position, start-color, ..., last-color);
```

shape 为椭圆形，size 为最远角，position 为中心。

- **shape** 参数定义形状。它可接受 circle 或 ellipse 值。默认值为 ellipse（椭圆）。
- **size** 参数定义渐变的大小。它可接受四个值：

![image-20231010141839811](https://s2.loli.net/2023/10/25/hf2Nx1EsS9kGCdB.png)

```CSS
    .item1 {
        height: 150px;
        width: 150px;
        background-image: radial-gradient(farthest-corner at 60% 55%, red, yellow,orange);
    }
```

### 重复渐变

#### 重复性线性渐变

重复性线性渐变是用许多线性渐变组成的 ，它与线性渐变的区别在于，它会在所有方向上重复渐变来覆盖整个元素。 其语法格式为：

```CSS
background-image: repeating-linear-gradient(side-or-corner|angle, color-stop);
```

- side-or-corner 是描述渐变线的起始位置，它包含 to 和两个关键词：第一个指出水平位置 left or right，第二个指出垂直位置 top or bottom。
- angle 是用角度值来指定渐变的方向。
- color-stop 是由一个组成，并且跟随一个可选的终点位置。

#### 重复性径向渐变

重复性径向渐变是用重复性的径向渐变组成的图像。它与径向渐变的区别在于，它会从原点开始重复径向渐变来覆盖整个元素。其语法格式为：

```CSS
background: repeating-radial-gradient(extent-keyword, color-stop);
```

- extent-keyword 是描述边缘轮廓的具体位置。
- color-stop 是某个确定位置的固定颜色值。

## 动画

css中实现动画有两种方式：`transition`过渡动画、 `animation`自定义动画。

### 过渡动画

[过渡动画详解](https://juejin.cn/post/6970885478967050254)

| 属性                       | 描述                                         | CSS  |
| -------------------------- | -------------------------------------------- | ---- |
| transition                 | 简写属性，用于在一个属性中设置四个过渡属性。 | 3    |
| transition-property        | 规定应用过渡的 CSS 属性的名称。              | 3    |
| transition-duration        | 定义过渡效果花费的时间。默认是 0。           | 3    |
| transition-timing-function | 规定过渡效果的时间曲线。默认是 "ease"。      | 3    |
| transition-delay           | 规定过渡效果何时开始。默认是 0。             | 3    |

### 自定义动画

[animation动画详解](https://juejin.cn/post/6970883520168198158#comment)

CSS animations 使得可以将从一个 CSS 样式配置转换到另一个 CSS 样式配置。动画包括两个部分：描述动画的样式规则和用于指定动画开始、结束以及中间点样式的关键帧。

#### 关键帧@keyframes

- @keyframes 规则是创建动画并为动画命名，可以在其中对每一帧进行设置。
- @keyframes 规则内指定一个 CSS 样式和动画将逐步从目前的样式更改为新的样式（关键帧）。
- 需要规定一个关键帧名称@keyframes-name。
- 用百分比来规定变化发生的时间:0%-100%，之间可以是任意多的变化次数，也可以倒放100%-0%
- 使用自定义动画的元素，需要通过`animation`相关属性进行配置。

```CSS
.dv{
    width: 40px;
    height: 40px;
    background-color: aliceblue;
}
.dv:hover {
    animation-name: myAnimaiton;
    animation-duration: 3s;
  }
  @keyframes myAnimaiton {
    0% {
      padding: 0;
      background: burlywood;
    }
    100% {
      padding: 150px;
      background-color: royalblue;
    }
  }
```

- `animation-name`
  - 需要绑定的`keyframe`的名称
- `animation-duration`
  - 动画执行的时间
  - 默认是0, 无动画执行
  - 单位是秒`s`或者毫秒`ms`
- `animation-timing-function`
  - 动画执行的速度
- `animation-delay`
  - 规定延迟多久后开始执行动画
- `animation-iteration-count`
  - 动画循环执行的次数
  - `infinite`: 无限次
- `animation-direction`
  - 动画的方向
  - `normal`: 正常方向
  - `reverse`: 反方向（ 从100%-0%的执行）
  - `alternate`: 交替执行, 从正常方向开始
  - `alternate-reverse`: 交替执行, 从反方向开始

### 2D及3D转换

[2D转换相关资料](https://blog.csdn.net/m0_72959685/article/details/126836784#:~:text=二、2D转换的属性及其基本属性值 1 1.translate 平移 2 2.rotate () 旋转,设置变形原点 4 4.scale 缩放 5 5.skew () 倾斜)

[3D转换相关资料](https://www.runoob.com/css3/css3-3dtransforms.html)

2D转换是通过css来改变元素的形状或位置，也可以叫做变形。

3D转换将页面看作是一个三维空间来对页面中的元素进行移动、旋转、缩放和倾斜等操作。

属性对照表

| 值                    | 描述                                  |
| --------------------- | ------------------------------------- |
| none                  | 定义不进行转换。                      |
| matrix(n,n,n,n,n,n)   | 定义 2D 转换，使用六个值的矩阵。      |
| translate(x,y)        | 定义 2D 转换。                        |
| translate3d(x,y,z)    | 定义 3D 转换。                        |
| translateX(x)         | 定义转换，只是用 X 轴的值。           |
| translateY(y)         | 定义转换，只是用 Y 轴的值。           |
| translateZ(z)         | 定义 3D 转换，只是用 Z 轴的值。       |
| scale(x,y)            | 定义 2D 缩放转换。                    |
| scale3d(x,y,z)        | 定义 3D 缩放转换。                    |
| scaleX(x)             | 通过设置 X 轴的值来定义缩放转换。     |
| scaleY(y)             | 通过设置 Y 轴的值来定义缩放转换。     |
| scaleZ(z)             | 通过设置 Z 轴的值来定义 3D 缩放转换。 |
| rotate(angle)         | 定义 2D 旋转，在参数中规定角度。      |
| rotate3d(x,y,z,angle) | 定义 3D 旋转。                        |
| rotateX(angle)        | 定义沿着 X 轴的 3D 旋转。             |
| rotateY(angle)        | 定义沿着 Y 轴的 3D 旋转。             |
| rotateZ(angle)        | 定义沿着 Z 轴的 3D 旋转。             |
| skew(x-angle,y-angle) | 定义沿着 X 和 Y 轴的 2D 倾斜转换。    |
| skewX(angle)          | 定义沿着 X 轴的 2D 倾斜转换。         |
| skewY(angle)          | 定义沿着 Y 轴的 2D 倾斜转换。         |
| perspective(n)        | 为 3D 转换元素定义透视视图。          |

## 作业

**提交邮箱：** **frontend@lanshan.email**    

**提交格式：**标题命名为**学号-姓名-第一次作业** ,内容为**github地址**。

1.写一个类似的html页面

![image-20231010142032534](https://s2.loli.net/2023/10/25/oK4qHiAXPmbJxey.png)

2.用flex实现以下画面效果

<img src="https://img-blog.csdnimg.cn/20210613155720998.gif#pic_center" style="zoom: 100%" />

3.轮播图
