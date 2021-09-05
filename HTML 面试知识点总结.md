# **HTML** **面试知识点总结**

## **DOCTYPE** **的作用是什么？**

```
IE5.5 引入了文档模式的概念，而这个概念是通过使用文档类型（DOCTYPE）切换实现的。

<!DOCTYPE> 声明一般位于文档的第一行，它的作用主要是告诉浏览器以什么样的模式来解析文档。一般指定了之后会以标准模式来进行文档解析，否则就以兼容模式进行解析。在标准模式下，浏览器的解析规则都是按照最新的标准进行解析的。而在兼容模式下，浏览器会以向后兼容的方式来模拟老式浏览器的行为，以保证一些老的网站的正确访问。 
```

## **标准模式与兼容模式各有什么区别**

```
标准模式的渲染方式和 JS 引擎的解析方式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示，模拟老式浏览器的行为以防止站点无法工作。
```

## **HTML5** **为什么只需要写** <**!DOCTYPE HTML>**，而不需要引入 **DTD**

```
HTML5 不基于 SGML，因此不需要对 DTD 进行引用，但是需要DOCTYPE 来规范浏览器的行为（让浏览器按照它们应该的方式来运行）。而 HTML4.01 基于 SGML ，所以需要对DTD 进行引用，才能告知浏览器文档所使用的文档类型
```

## **SGML** **、** **HTML** **、**XML **和** **XHTML** **的区别**

```
SGML 是标准通用标记语言，是一种定义电子文档结构和描述其内容的国际标准语言,是所有电子文档标记语言的起源

HTML 是超文本标记语言，主要是用于规定怎么显示网页。

XML 是可扩展标记语言是未来网页语言的发展方向，XML 和 HTML 的最大区别就在于XML 的标签是可以自己创建的，数量无限多，而 HTML 的标签都是固定的而且数量有限。

XHTML 也是现在基本上所有网页都在用的标记语言，他其实和 HTML 没什么本质的区别，标签都一样，用法也都一样，就是比 HTML 更严格，比如标签必须都用小写，标签都必须有闭合标签等
```

## **DTD** 介绍

```
DTD（ Document Type Definition 文档类型定义）是一组机器可读的规则，它们定义 XML 或 HTML 的特定版本中所有允许元素及它们的属性和层次关系的定义。在解析网页时，浏览器将使用这些规则检查页面的有效性并且采取相应的措施。 
DTD 是对 HTML 文档的声明，还会影响浏览器的渲染模式（工作模式）。
```

## **行内元素定义**

```
HTML4 中，元素被分成两大类: inline （内联元素）与 block（块级元素）。一个行内元素只占据它对应标签的边框所包含的空间

常见的行内元素有 a b span img strong sub sup button input label select textarea
```

## **块级元素定义**

```
块级元素占据其父元素（容器）的整个宽度，因此创建了一个“块”。 

常见的块级元素有 div ul ol li dl dt dd h1 h2 h3 h4 h5 h6 p
```

## **行内元素与块级元素的区别**

```
1. 格式上，默认情况下，行内元素不会以新行开始，而块级元素会新起一行

2. 内容上，默认情况下，行内元素只能包含文本和其他行内元素。而块级元素可以包含行内元素和其他块级元素

3. 行内元素与块级元素属性的不同，主要是盒模型属性上：行内元素设置 width 无效，height 无效（可以设置 line-height），设置 margin 和 padding 的上下不会对其他元素产生影响
```

## **HTML5** **元素的分类**

```
HTML5 中，元素主要分为 7 类：Metadata Flow Sectioning Heading Phrasing Embedded Interactive
```

## **空元素定义**

```
标签内没有内容的 HTML 标签被称为空元素。空元素是在开始标签中关闭的。 

常见的空元素有：br hr img input link meta
```

## **link** **标签定义**

```
link 标签定义文档与外部资源的关系。 

link 元素是空元素，它仅包含属性。 此元素只能存在于 head 部分，不过它可出现任何次数。

link 标签中的 rel 属性定义了当前文档与被链接文档之间的关系。常见的 stylesheet 指的是定义一个外部加载的样式表。
```

## **页面导入样式时，使用** **link** **和** **@import** **有什么区别？**

```
1. 从属关系区别。 @import 是 CSS 提供的语法规则，只有导入样式表的作用；link 是 HTML 提供的标签，不仅可以加载 CSS 文件，还可以定义 RSS、rel 连接属性、引入网站图标等

2. 加载顺序区别。加载页面时，link 标签引入的 CSS 被同时加载；@import 引入 的 CSS 将在页面加载完毕后被加载

3. 兼容性区别。@import 是 CSS2.1 才有的语法，故只可在IE5+ 才能识别；link 标签作为 HTML 元素，不存在兼容性问题。

4. DOM 可控性区别。可以通过 JS 操作 DOM ，插入 link 标签来改变样式；由于 DOM 方法是基于文档的，无法使用 @import 的方式插入样式。
```

## HTML5有哪些新特性、移除了那些元素

HTML5现在已经不是SGML的子集，主要是关于图像，位置，存储，多任务等功能的增加。

新增的有：

1. 绘画canvas;
2. 用于媒介回放的video和audio元素;
3. 本地离线存储localStorage长期存储数据，浏览器关闭后数据不丢失;sessionStorage的数据在浏览器关闭后自动删除;
4. 语意化更好的内容元素，比如article、footer、header、nav、section;
5. 表单控件，calendar、date、time、email、url、search;
6. 新的技术webworker,websocket;
7. 新的文档属性document.visibilityState

移除的元素有：

1. 纯表现的元素：basefont，big，center，font,s，strike，tt，u;
2. 对可用性产生负面影响的元素：frame，frameset，noframes；

## 如何处理HTML5新标签的浏览器兼容问题

```
（1）IE8/IE7/IE6支持通过document.createElement方法产生的标签，可以利用这一特性让这些浏览器支持HTML5新标签，浏览器支持新标签后，还需要添加标签默认的样式。（2）当然也可以直接使用成熟的框架，比如html5shim`<!--[ifltIE9]><script>src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script><![endif]-->`[iflteIE9]……[endif]判断IE的版本，限定只有IE9以下浏览器版本需要执行的语句。
```

## 简述一下你对HTML语义化的理解

相关知识点：

（1）用正确的标签做正确的事情。

（2）html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;

（3）即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;

（4）搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;

（5）使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

回答：

​		我认为html语义化主要指的是我们应该使用合适的标签来划分网页内容的结构。html的本质作用其实就是定义网页文档的结构，

​		一个语义化的文档，能够使页面的结构更加清晰，易于理解。这样不仅有利于开发者的维护和理解，同时也能够使机器对文档内容进

​		行正确的解读。比如说我们常用的b标签和strong标签，它们在样式上都是文字的加粗，但是strong标签拥有强调的语义。

​		对于一般显示来说，可能我们看上去没有差异，但是对于机器来说，就会有很大的不同。如果用户使用的是屏幕阅读器来访问网页的话，使用strong标签就会有明显的语调上的变化，而b标签则没有。如果是搜索引擎的爬虫对我们网页进行分析的话，那么它会依赖于html标签来确定上下文和各个关键字的权重，一个语义化的文档对爬虫来说是友好的，是有利于爬虫对文档内容解读的，从而有利于我们网站的SEO。从html5我们可以看出，标准是倾向于以语义化的方式来构建网页的，比如新增了header、footer这些语义标签，删除了big、font这些没有语义的标签。

详细资料可以参考：[《语义化的HTML结构到底有什么好处？》](https://www.html.cn/archives/1668)[《如何理解Web语义化？》](https://www.zhihu.com/question/20455165)[《我的HTML会说话——从实用出发，谈谈HTML的语义化》](https://juejin.cn/post/6844903569590583304)

## b与strong的区别和i与em的区别

从页面显示效果来看，被<b>和<strong>包围的文字将会被加粗，而被<i>和<em>包围的文字将以斜体的形式呈现。

但是<b><i>是自然样式标签，分别表示无意义的加粗，无意义的斜体，表现样式为{font-weight:bolder}，仅仅表示「这里应该用粗体显示」或者「这里应该用斜体显示」，此两个标签在HTML4.01中并不被推荐使用。

而<em>和<strong>是语义样式标签。<em>表示一般的强调文本，而<strong>表示比<em>语义更强的强调文本。

使用阅读设备阅读网页时：<strong>会重读，而<b>是展示强调内容。

详细资料可以参考：[《HTML5中的b/strong，i/em有什么区别？》](https://www.zhihu.com/question/19551271)

## HTML5的离线储存怎么使用，工作原理能不能解释一下

在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。

原理：HTML5的离线存储是基于一个新建的.appcache文件的缓存机制（不是存储技术），通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。

（1）创建一个和html同名的manifest文件，然后在页面头部像下面一样加入一个manifest的属性。

<html lang="en" manifest="index.manifest">

（2）在如下cache.manifest文件的编写离线存储的资源

CACHEMANIFEST

/#v0.11

CACHE:

js/app.js

css/style.css

NETWORK:resourse/logo.png

FALLBACK:

//offline.html

CACHE:表示需要离线存储的资源列表，由于包含manifest文件的页面将被自动离线存储，所以不需要把页面自身也列出来。

NETWORK:表示在它下面列出来的资源只有在在线的情况下才能访问，他们不会被离线存储，所以在离线情况下无法使用这些资源。不过，如果在CACHE和NETWORK中有一个相同的资源，那么这个资源还是会被离线存储，也就是说CACHE的优先级更高。

FALLBACK:表示如果访问第一个资源失败，那么就使用第二个资源来替换他，比如上面这个文件表示的就是如果访问根目录下任何一个资源失败了，那么就去访问offline.html。

（3）在离线状态时，操作window.applicationCache进行离线缓存的操作。

如何更新缓存：

（1）更新manifest文件

（2）通过javascript操作

（3）清除浏览器缓存

注意事项：

（1）浏览器对缓存数据的容量限制可能不太一样（某些浏览器设置的限制是每个站点5MB）。

（2）如果manifest文件，或者内部列举的某一个文件不能正常下载，整个更新过程都将失败，浏览器继续全部使用老的缓存。

（3）引用manifest的html必须与manifest文件同源，在同一个域下。

（4）FALLBACK中的资源必须和manifest文件同源。

（5）当一个资源被缓存后，该浏览器直接请求这个绝对路径也会访问缓存中的资源。

（6）站点中的其他页面即使没有设置manifest属性，请求的资源如果在缓存中也从缓存中访问。

（7）当manifest文件发生改变时，资源请求本身也会触发更新。

详细的使用可以参考：[《HTML5离线缓存-manifest简介》](https://yanhaijing.com/html/2014/12/28/html5-manifest/)[《有趣的HTML5：离线存储》](https://segmentfault.com/a/1190000000732617)

## 浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢

在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储

离线的情况下，浏览器就直接使用离线存储的资源。

## 常见的浏览器端的存储技术有哪些

浏览器常见的存储技术有cookie、localStorage和sessionStorage。

还有两种存储技术用于大规模数据存储，webSQL（已被废除）和indexDB。

IE支持userData存储数据，但是基本很少使用到，除非有很强的浏览器兼容需求。

详细的资料可以参考：[《很全很全的前端本地存储讲解》](https://segmentfault.com/a/1190000012578794)

## 请描述一下cookies，sessionStorage和localStorage的区别？

**相关资料：**

SessionStorage，LocalStorage，Cookie这三者都可以被用来在浏览器端存储数据，而且都是字符串类型的键值对。区别在于前两者属于HTML5WebStorage，创建它们的目的便于客户端存储数据。而cookie是网站为了标示用户身份而储存在用户本地终端上的数据（通常经过加密）。cookie数据始终在同源（协议、主机、端口相同）的http请求中携带（即使不需要），会在浏览器和服务器间来回传递。

存储大小：

cookie数据大小不能超过4k

sessionStorage和localStorage虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大

过期时间:

1. localStorage存储持久数据，浏览器关闭后数据不丢失除非主动删除数据。

2. sessionStorage数据在页面会话结束时会被清除。页面会话在浏览器打开期间一直保持，并且重新加载或恢复页面仍会保持原来的页面会话。在新标签或窗口打开一个页面时会在顶级浏览上下文中初始化一个新的会话。

3. cookie设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭。

作用域：

1. sessionStorage只在同源的同窗口（或标签页）中共享数据，也就是只在当前会话中共享。

2. localStorage在所有同源窗口中都是共享的。

3. cookie在所有同源窗口中都是共享的。

答案

浏览器端常用的存储技术是cookie、localStorage和sessionStorage。

cookie其实最开始是服务器端用于记录用户状态的一种方式，由服务器设置，在客户端存储，然后每次发起同源请求时，发送给服务器端。cookie最多能存储4k数据，它的生存时间由expires属性指定，并且cookie只能被同源的页面访问共享。

sessionStorage是html5提供的一种浏览器本地存储的方法，它借鉴了服务器端session的概念，代表的是一次会话中所保存的数据。它一般能够存储5M或者更大的数据，它在当前窗口关闭后就失效了，并且sessionStorage只能被同一个窗口的同源页面所访问共享

localStorage也是html5提供的一种浏览器本地存储的方法，它一般也能够存储5M或者更大的数据。它和sessionStorage不同的是，除非手动删除它，否则它不会失效，并且localStorage也只能被同源页面所访问共享。

上面几种方式都是存储少量数据的时候的存储方式，当我们需要在本地存储大量数据的时候，我们可以使用浏览器的indexDB这是浏览器提供的一种本地的数据库存储机制。它不是关系型数据库，它内部采用对象仓库的形式存储数据，它更接近NoSQL数据库。

详细的资料可以参考：[《请描述一下cookies，sessionStorage和localStorage的区别？》](https://segmentfault.com/a/1190000017423117)[《浏览器数据库IndexedDB入门教程》](http://www.ruanyifeng.com/blog/2018/07/indexeddb.html)

## iframe有那些缺点

iframe元素会创建包含另外一个文档的内联框架（即行内框架）。

主要缺点有

（1）iframe会阻塞主页面的onload事件。window的onload事件需要在所有iframe加载完毕后（包含里面的元素）才会触发。在Safari和Chrome里，通过JavaScript动态设置iframe的src可以避免这种阻塞情况。

（2）搜索引擎的检索程序无法解读这种页面，不利于网页的SEO。（3）iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。

（4）浏览器的后退按钮失效。

（5）小型的移动设备无法完全显示框架。

详细的资料可以参考：[《使用iframe的优缺点》](https://blog.csdn.net/yintianqin/article/details/72625785)[《iframe简单探索以及iframe跨域处理》](https://segmentfault.com/a/1190000009891683)

## Label的作用是什么？是怎么用的？

```
label标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。<label for="Name" >Number:</label><input type=“text“ name="Name" id="Name"/>
```

## HTML5的form的自动完成功能是什么

autocomplete属性规定输入字段是否应该启用自动完成功能。默认为启用，设置为autocomplete=off可以关闭该功能

自动完成允许浏览器预测对字段的输入。当用户在字段开始键入时，浏览器基于之前键入过的值，应该显示出在字段中填写的选项。

autocomplete属性适用于<form>，以及下面的<input>类型：text,search,url,telephone,email,password,datepickers,range以及color。

