## HTML 面试知识点总结

整理了 HTML 面试的部分知识点

### 目录

- [html5新特性、移除了哪些元素？](#html5新特性-移除了哪些元素)
  - [html5新增的表单元素](#html5新增的表单元素)
  - [如何处理html5新标签的浏览器兼容问题](#如何处理html5新标签的浏览器兼容问题)
- [html5元素分类](#html5元素分类)
  - [行内元素、块级元素、空元素](#行内元素-块级元素-空元素)
- [HTML全局属性(global attribute)有哪些](#HTML全局属性global-attribute有哪些)

- [语义化](#语义化)
- [优化](#优化)
  - [前端需要注意哪些SEO](#前端需要注意哪些SEO)
  - [如何进行网站性能优化](#如何进行网站性能优化)
  - [前端性能优化](#前端性能优化)
  - [渲染优化](#渲染优化)
  - [关键渲染路径优化（浏览器渲染过程）](#关键渲染路径优化浏览器渲染过程)
  - [大量图片加载慢如何优化](#大量图片加载慢如何优化)
 
- [常见的浏览器端的存储技术](#常见的浏览器端的存储技术)
  - [cookies、sessionStorage、localStorage的区别](#cookiessessionStoragelocalStorage的区别)
- [html5的离线储存怎么使用，解释工作原理](#html5的离线储存怎么使用解释工作原理)
- [浏览器是怎么对html5的离线储存资源进行管理和加载的](#浏览器是怎么对html5的离线储存资源进行管理和加载的)

- [重绘和回流（浏览器绘制过程）](#重绘和回流浏览器绘制过程)
  - [如何减少回流（浏览器绘制过程）](#如何减少回流浏览器绘制过程)
- [怎么重构页面](#怎么重构页面)

- [从浏览器地址栏输入url到显示页面的步骤](#从浏览器地址栏输入url到显示页面的步骤)
- [浏览器](#浏览器)
  - [对浏览器的理解](#对浏览器的理解)
  - [对浏览器内核的理解](#对浏览器内核的理解)
  - [常见的浏览器内核比较](#常见的浏览器内核比较)
  - [常见浏览器所用内核](#常见浏览器所用内核)
  - [浏览器的渲染原理](#浏览器的渲染原理)
  - [浏览器架构](#浏览器架构)
  - [如何实现浏览器内多个标签页之间的通信](#如何实现浏览器内多个标签页之间的通信)
  - [跨标签页通讯](#跨标签页通讯)
  - [内存泄露](#内存泄露)
  - [浏览器API](#浏览器API)
    - [1.Web Worker](#1Web-Worker)
    - [2.Service Worker](#2Service-Worker)
    - [3.requestAnimationFrame用法](#3requestAnimationFrame用法)
  - [页面加载执行](#页面加载执行)
    - [1.浏览器事件循环](#1浏览器事件循环)
    - [2.怎么判断页面是否加载完成](#2怎么判断页面是否加载完成)
    - [3.css加载会造成阻塞吗](#3css加载会造成阻塞吗)
    - [4.为什么JS阻塞页面加载](#4为什么JS阻塞页面加载)
    - [5.DOMContentLoaded与load的区别](#5DOMContentLoaded与load的区别)
    - [6.什么是CRP,即关键渲染路径?如何优化](#6什么是CRP即关键渲染路径如何优化)
  - [history路由和hash路由](#history路由和hash路由)
  - [performance相关](#performance相关)
- [浏览器解析过程](#浏览器解析过程)
  - [渲染过程中遇到js文件怎么处理？（浏览器解析过程）](#渲染过程中遇到js文件怎么处理浏览器解析过程)
  - [async和defer的作用是什么？有什么区别？（浏览器解析过程）](#async和defer的作用是什么有什么区别浏览器解析过程)
  - [script标签中defer和async的区别](#script标签中defer和async的区别)
  - [什么是文档的预解析？（浏览器解析过程）](#什么是文档的预解析浏览器解析过程)
  - [css如何阻塞文档解析？（浏览器解析过程）](#css如何阻塞文档解析浏览器解析过程)
- [浏览器渲染过程](#浏览器渲染过程)
  - [渲染机制](#渲染机制)
    - [1.浏览器的渲染机制一般分为以下几个步骤](#1浏览器的渲染机制一般分为以下几个步骤)
    - [2.图层](#2图层)
    - [3.重绘与回流](#3重绘与回流)
    - [4.JavaScript会阻塞DOM生成](#4JavaScript会阻塞DOM生成)
    - [5.缩短白屏时长，可以有以下策略](#5缩短白屏时长可以有以下策略)
  - [渲染页面时常见哪些不良现象？（浏览器渲染过程）](#渲染页面时常见哪些不良现象浏览器渲染过程)
- [浏览器绘制过程](#浏览器绘制过程)
  - [为什么操作DOM慢？（浏览器绘制过程）](#为什么操作dom慢浏览器绘制过程)
- [DOMContentLoaded事件和Load事件的区别](#domcontentloaded事件和load事件的区别)
- [浏览器缓存](#浏览器缓存)
  - [1.强缓存](#1强缓存)
  - [2.协商缓存](#2协商缓存)
  - [3.缓存场景](#3缓存场景)
  - [4.讲讲304](#4讲讲304)
  - [5.强缓存、协商缓存什么时候用哪个](#5强缓存协商缓存什么时候用哪个)
  - [6.缓存总结](#6缓存总结)
  - [7.cookie和localSrorage、session、indexDB的区别](#7cookie和localSroragesessionindexDB的区别)

- [跨域](#跨域)
  - [JSONP](#JSONP)
  - [CORS](#CORS)
  - [document.domain](#documentdomain)
  - [postMessage](#postMessage)
- [网页验证码是干嘛的，是为了解决什么安全问题](#网页验证码是干嘛的是为了解决什么安全问题)
- [扫描二维码登录网页是什么原理，前后两个事件是如何联系的](#扫描二维码登录网页是什么原理前后两个事件是如何联系的)

- [SGML、HTML、XML 和 XHTML 的区别](#SGMLHTMLXML-和-XHTML-的区别)
- [DHTML 是什么](#DHTML-是什么)
- [DOCTYPE、标准模式与兼容模式、DTD](#DOCTYPE标准模式与兼容模式DTD)
  - [DOCTYPE 的作用是什么](#DOCTYPE-的作用是什么)
  - [标准模式与兼容模式各有什么区别](#标准模式与兼容模式各有什么区别)
  - [DTD](#DTD)
  - [HTML5 为什么只需要写 &lt;!DOCTYPE HTML&gt;，而不需要引入 DTD](#html5-为什么只需要写-doctype-html而不需要引入-dtd)

- [页面导入样式时，使用 link 和 @import 有什么区别](#页面导入样式时使用-link-和-import-有什么区别)
  - [link标签定义](#link标签定义)

- [head标签中必不可少的是](#head标签中必不可少的是)
- [常用的meta标签](#常用的meta标签)
  - [viewport](#viewport)
  - [延伸提问：怎样处理移动端 1px 被渲染成 2px 问题](#延伸提问怎样处理移动端-1px-被渲染成-2px=问题)
- [用于预格式化文本的标签是](#用于预格式化文本的标签是)
- [iframe有哪些缺点](#iframe有哪些缺点)
- [label的作用是什么？是怎么用的](#label的作用是什么是怎么用的)
- [html5的form的自动完成功能是什么](#html5的form的自动完成功能是什么)

- [title与h1的区别](#title与h1的区别)
- [b与strong的区别、i与em的区别](#b与strong的区别i与em的区别)
- [img的title和alt有什么区别](#img的title和alt有什么区别)
- [Canvas和SVG有什么区别？](#canvas和svg有什么区别)
- [src与href的区别](#src与href的区别)
- [disabled和readonly的区别](#disabled和readonly的区别)
- [attribute和property的区别](#attribute和property的区别)
- [css reset和normalize.css有什么区别](#css-reset和normalizecss有什么区别)
- [div+css的布局较table布局有什么优点](#divcss的布局较table布局有什么优点)

- [http](#http)
  - [http的几种请求方法用途](#http的几种请求方法用途)
  - [http状态码及其含义](#HTTP状态码及其含义)
  - [html规范中为什么要求引用资源不加协议头http或者https](#html规范中为什么要求引用资源不加协议头http或者https)
  - [HTTP request报文结构是怎样的](#HTTP-request报文结构是怎样的)
  - [HTTP response报文结构是怎样的](#HTTP-response报文结构是怎样的)

- [对web标准 可用性、可访问性的理解](#对web标准-可用性可访问性的理解)
- [WEB标准以及W3C标准是什么](#WEB标准以及W3C标准是什么)
- [web开发中会话跟踪的方法有哪些](#web开发中会话跟踪的方法有哪些)
- [IE各版本和Chrome可以并行下载多少个资源](#ie各版本和chrome可以并行下载多少个资源)
- [Chrome中的Waterfall](#chrome中的waterfall)
- [webSocket如何兼容低版本浏览器](#websocket如何兼容低版本浏览器)
- [Flash、Ajax各自的优缺点，在使用中如何取舍](#flashajax各自的优缺点在使用中如何取舍)
- [git fetch和git pull的区别](#git-fetch和git-pull的区别)
- [为什么利用多个域名来存储网站资源会更有效](#为什么利用多个域名来存储网站资源会更有效)
- [页面可见性（Page Visibility API）可以有哪些用途](#页面可见性page-visibility-api可以有哪些用途)
- [从用户刷新网页开始，一次js请求一般情况下有哪些地方会有缓存处理](#从用户刷新网页开始一次js请求一般情况下有哪些地方会有缓存处理)
- [在html5中，哪个方法用于获得用户的当前位置](#在html5中哪个方法用于获得用户的当前位置)
- [渐进增强和优雅降级的定义](#渐进增强和优雅降级的定义)
- [主流浏览器内核私有属性css前缀](#主流浏览器内核私有属性css前缀)
- [知道的网页制作会用到的图片格式有哪些](#知道的网页制作会用到的图片格式有哪些)
- [文档的不同注释方式](#文档的不同注释方式)

- [实现不使用border画出1px高的线，在不同浏览器的标准模式与怪异模式下都能保持一致的效果](#实现不使用border画出1px高的线在不同浏览器的标准模式与怪异模式下都能保持一致的效果)
- [如何在页面上实现一个圆形的可点击区域](#如何在页面上实现一个圆形的可点击区域)
- [HTML5 drag api](#HTML5-drag-api)
- [拖拽有哪些知识点](#拖拽有哪些知识点)
- [web worker](#web-worker)
- [用一个div模拟textarea的实现](#用一个div模拟textarea的实现)
- [资源预加载prefetch/preload](#资源预加载prefetchpreload)
- [如何解决a标签点击后hover事件失效的问题](#如何解决a标签点击后hover事件失效的问题)
- [点击一个input依次触发的事件](#点击一个input依次触发的事件)
- [有写过原生的自定义事件吗](#有写过原生的自定义事件吗)
- [addEventListener和attachEvent的区别](#addEventListener和attachEvent的区别)
- [addEventListener函数的第三个参数](#addEventListener函数的第三个参数)
- [DOM事件流是什么](#DOM事件流是什么)
- [冒泡和捕获的具体过程](#冒泡和捕获的具体过程)
- [如何阻止冒泡和默认事件(兼容写法)](#如何阻止冒泡和默认事件兼容写法)
- [所有的事件都有冒泡吗](#所有的事件都有冒泡吗)
- [关于一些兼容性](#关于一些兼容性)
- [offset、scroll、client的区别](#offsetscrollclient的区别)
- [target="_blank"有哪些问题](#targetblank有哪些问题)
- [children以及childNodes的区别](#children以及childNodes的区别)







### html5新特性 移除了哪些元素

   ```
    HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。

    新增的有：
    绘画 canvas;
    用于媒体播放的 video 和 audio 元素;
    本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
    sessionStorage 的数据在浏览器关闭后自动删除;
    语意化更好的内容元素，比如 article、footer、header、nav、section;
    表单控件，calendar、date、time、email、url、search;
    多任务 webworker；全双工通信协议 websocket；
    新的文档属性 document.visibilityState
    页面可见性改变事件 visibilitychange
    新增选择器 document.querySelector、document.querySelectorAll
    拖拽释放(Drag and drop) API
    离线应用 manifest
    桌面通知 Notifications
    地理位置 Geolocation
    历史管理 history
    跨域资源共享(CORS) Access-Control-Allow-Origin
    跨窗口通信 PostMessage
    Form Data 对象

    移除的元素有：
    纯表现的元素：basefont，big，center，font, s，strike，tt，u;
    对可用性产生负面影响的元素：frame，frameset，noframes；
   ```

H5的新特性有哪些
- 画布(Canvas) API
- 地理(Geolocation) API
- 音频、视频API(audio,video)
- localStorage和sessionStorage
- webworker, websocket
- 新的一套标签 header,nav,footer,aside,article,section
- web worker是运行在浏览器后台的js程序，他不影响主程序的运行，是另开的一个js线程，可以用这个线程执行复杂的数据操作，然后把操作结果通过postMessage传递给主线程，这样在进行复杂且耗时的操作时就不会阻塞主线程了。
- HTML5 History两个新增的API：history.pushState 和 history.replaceState，两个 API 都会操作浏览器的历史记录，而不会引起页面的刷新。
```
Hash就是url 中看到 # ,我们需要一个根据监听哈希变化触发
的事件( hashchange) 事件。我们用 window.location处理
哈希的改变时不会重新渲染页面，而是当作新页面加到历史记录中，
这样我们跳转页面就可以在 hashchange 事件中注册 ajax 
从而改变页面内容。 可以为hash的改变添加监听事件：

window.addEventListener("hashchange", funcRef, false)
```

- WebSocket 使用ws或wss协议，Websocket是一个持久化的协议，相对于HTTP这种非持久的协议来说。WebSocket API最伟大之处在于服务器和客户端可以在给定的时间范围内的任意时刻，相互推送信息。WebSocket并不限于以Ajax(或XHR)方式通信，因为Ajax技术需要客户端发起请求，而WebSocket服务器和客户端可以彼此相互推送信息；XHR受到域的限制，而WebSocket允许跨域通信
```
// 创建一个Socket实例
var socket = new WebSocket('ws://localhost:8080');
// 打开Socket
socket.onopen = function(event) {
  // 发送一个初始化消息
  socket.send('I am the client and I\'m listening!');
  // 监听消息
  socket.onmessage = function(event) {
    console.log('Client received a message',event);
  };
  // 监听Socket的关闭
  socket.onclose = function(event) {
    console.log('Client notified socket has closed',event);
  };
  // 关闭Socket....
  //socket.close()
};
```

#### html5新增的表单元素
   ```
    datalist 规定输入域的选项列表，通过 option 创建！ 
    keygen 提供一种验证用户的可靠方法，密钥对生成器，私钥存于客户端，公钥发到服务器，用于之后验证客户端证书！
    output 元素用于不同类型的输出！
   ```

#### 如何处理html5新标签的浏览器兼容问题
   ```
    （1） IE8/IE7/IE6 支持通过 document.createElement 方法产生的标签，可以利用这一特性让这些浏览器
        支持 HTML5 新标签，浏览器支持新标签后，还需要添加标签默认的样式。

    （2） 当然也可以直接使用成熟的框架，比如 html5shiv ;
         `<!--[if lt IE 9]>
         <script> src="https://cdn.jsdelivr.net/npm/html5shiv/dist/html5shiv.min.js"</script>
         <![endif]-->`

         [if lte IE 9]……[endif] 判断 IE 的版本，限定只有 IE9 以下浏览器版本需要执行的语句。
   ```

### html5元素分类

   ```
   HTML4中，元素被分成两大类: inline（内联元素）与 block（块级元素）。但在实际的开发过程中，因为页面表现的需要，
   前端工程师经常把 inline 元素的 display 值设定为 block （比如 a 标签），也经常把 block 元素的 display 值
   设定为 inline 之后更是出现了 inline-block 这一对外呈现 inline 对内呈现 block 的属性。
   因此，简单地把 HTML 元素划分为 inline 与 block 已经不再符合实际需求。
   
   HTML5中，元素主要分为7类：Metadata Flow Sectioning Heading Phrasing Embedded Interactive
   ```

#### 行内元素 块级元素 空元素

   ```
   HTML4 中，元素被分成两大类: inline （内联元素）与 block（块级元素）。
   
   一个行内元素只占据它对应标签的边框所包含的空间。行内元素不可以设置宽高，不独占一行
   常见的行内元素有 a b span img strong sub sup button input label select textarea
   
   块级元素占据其父元素（容器）的整个宽度，因此创建了一个“块”。块级元素可以设置宽高，独占一行
   常见的块级元素有  div ul ol li dl dt dd h1 h2 h3 h4 h5 h6 p 
   
   （1） 格式上，默认情况下，行内元素不会以新行开始，而块级元素会新起一行。
   （2） 内容上，默认情况下，行内元素只能包含文本和其他行内元素。而块级元素可以包含行内元素和其他块级元素。
   （3） 行内元素与块级元素属性的不同，主要是盒模型属性上：行内元素设置 width 无效，height 无效
        （可以设置 line-height），设置 margin 和 padding 的上下不会对其他元素产生影响。
   
   标签内没有内容的 HTML 标签被称为空元素。空元素是在开始标签中关闭的。
   常见的空元素有：br hr img input link meta
   ```

### HTML全局属性(global attribute)有哪些
```
class:为元素设置类标识
data-*: 为元素增加自定义属性
draggable: 设置元素是否可拖拽
id: 元素id，文档内唯一
lang: 元素内容的的语言
style: 行内css样式
title: 元素相关的建议信息
```

### 语义化

   ```
    （1） 用正确的标签做正确的事情。
    （2） html 语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
    （3） 即使在没有样式 CSS 情况下也以一种文档格式显示，并且是容易阅读的;
    （4） 搜索引擎的爬虫也依赖于 HTML 标记来确定上下文和各个关键字的权重，利于 SEO ;
    （5） 使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。
   ```

   ```
    我认为 html 语义化主要指的是我们应该使用合适的标签来划分网页内容的结构。html 的本质作用其实就是定义网页文档的结构，
    一个语义化的文档，能够使页面的结构更加清晰，易于理解。这样不仅有利于开发者的维护和理解，同时也能够使机器对文档内容
    进行正确的解读。比如说我们常用的 b 标签和 strong 标签，它们在样式上都是文字的加粗，但是 strong 标签拥有强调的语义。
    对于一般显示来说，可能我们看上去没有差异，但是对于机器来说，就会有很大的不同。如果用户使用的是屏幕阅读器来访问网页的话，
    使用 strong 标签就会有明显的语调上的变化，而 b 标签则没有。如果是搜索引擎的爬虫对我们网页进行分析的话，那么它会
    依赖于 html 标签来确定上下文和各个关键字的权重，一个语义化的文档对爬虫来说是友好的，是有利于爬虫对文档内容解读的，
    从而有利于我们网站的 SEO 。从 html5 我们可以看出，标准是倾向于以语义化的方式来构建网页的，比如新增了 header 、
    footer 这些语义标签，删除了 big 、font 这些没有语义的标签。
   ```

   ```
   所谓“语义”就是为了更易读懂，这要分两部分：让人（写程序、读程序）更易读懂；让机器（浏览器、搜索引擎）更易读懂
   1. 让人更易读懂
   对于人来说，代码可读性、语义化就是一个非常广泛的概念了，例如定义 JS 变量的时候使用更易读懂的名称，
   定义 CSS class 的时候也一样，例如length list等，而不是使用a b这种谁都看不懂的名称。
   不过我们平常考查的“语义化”并不会考查这么广义、这么泛的问题，而是考查 HTML 的语义化，是为了更好地让机器读懂 HTML。
   2. 让机器更易读懂
   HTML 符合 XML 标准，但又和 XML 不一样 —— HTML 不允许像 XML 那样自定义标签名称，HTML 有自己规定的标签名称。
   问题就在这里 —— HTML 为何要自己规定那么多标签名称呢，例如p div h1 ul等 —— 就是为了语义化。其实，
   如果你精通 CSS 的话，你完全可以全部用<div>标签来实现所有的网页效果，其他的p h1 ul等标签可以一个都不用。
   但是我们不推荐这么做，这样做就失去了 HTML 语义化的意义。
   拿搜索引擎来说，爬虫下载到我们网页的 HTML 代码，它如何更好地去理解网页的内容呢？—— 就是根据 HTML 既定的标签。
   h1标签就代表是标题；p里面的就是段落详细内容，权重肯定没有标题高；ul里面就是列表；strong就是加粗的强调的内容 …… 
   如果我们不按照 HTML 语义化来写，全部都用<div>标签，那搜索引擎将很难理解我们网页的内容。
   为了加强 HTML 语义化，HTML5 标准中又增加了header section article等标签。因此，书写 HTML 时，
   语义化是非常重要的，否则 W3C 也没必要辛辛苦苦制定出这些标准来。
   ```
   
### 优化

#### 前端需要注意哪些SEO

   ```
    （1）合理的 title、description、keywords：搜索对着三项的权重逐个减小，title 值强调重点即可，
    重要关键词出现不要超过2次，而且要靠前，不同页面 title 要有所不同；description 把页面内容高度概括，
    长度合适，不可过分堆砌关键词，不同页面 description 有所不同；keywords 列举出重要关键词即可。
    （2）语义化的 HTML 代码，符合 W3C 规范：语义化代码让搜索引擎容易理解网页。
    （3）重要内容 HTML 代码放在最前：搜索引擎抓取 HTML 顺序是从上到下，有的搜索引擎对抓取长度有限制，
    保证重要内容肯定被抓取。
    （4）重要内容不要用 js 输出：爬虫不会执行 js 获取内容
    （5）少用 iframe：搜索引擎不会抓取 iframe 中的内容
    （6）非装饰性图片必须加 alt
    （7）提高网站速度：网站速度是搜索引擎排序的一个重要指标
   ```

#### 如何进行网站性能优化
```
content方面：
减少HTTP请求：合并文件、CSS精灵、inline Image
减少DNS查询：DNS缓存、将资源分布到恰当数量的主机名
减少DOM元素数量

Server方面：
使用CDN
配置ETag
对组件使用Gzip压缩

Cookie方面：
减小cookie大小

css方面：
将样式表放到页面顶部
不使用CSS表达式
使用<link>不使用@import

Javascript方面：
将脚本放到页面底部
将javascript和css从外部引入
压缩javascript和css
删除不需要的脚本
减少DOM访问

图片方面：
优化图片：根据实际颜色需要选择色深、压缩
优化css精灵
不要在HTML中拉伸图片
```

#### 前端性能优化

   ```
    前端性能优化主要是为了提高页面的加载速度，优化用户的访问体验。我认为可以从这些方面来进行优化。

    第一个方面是页面的内容方面：
    （1）通过文件合并、css 雪碧图(CSS Sprite)、使用 base64 等方式来减少 HTTP 请求数，避免过多的请求造成等待的情况。
    （2）通过 DNS 缓存等机制来减少 DNS 的查询次数。
    （3）通过设置缓存策略，对常用不变的资源进行缓存。
    （4）使用延迟加载的方式，来减少页面首屏加载时需要请求的资源。延迟加载的资源当用户需要访问时，再去请求加载。
    （5）通过用户行为，对某些资源使用预加载的方式，来提高用户需要访问资源时的响应速度。

    第二个方面是服务器方面：
    （1）使用 CDN 服务，来提高用户对于资源请求时的响应速度。
    （2）服务器端启用 Gzip、Deflate 等方式对于传输的资源进行压缩，减小文件的体积。
    （3）尽可能减小 cookie 的大小，并且通过将静态资源分配到其他域名下，来避免对静态资源请求时携带不必要的 cookie

    第三个方面是 CSS 和 JavaScript 方面：
    （1）把样式表放在页面的 head 标签中，减少页面的首次渲染的时间。
    （2）避免使用 @import 标签。
    （3）尽量把 js 脚本放在页面底部或者使用 defer 或 async 属性，避免脚本的加载和执行阻塞页面的渲染。
    （4）通过对 JavaScript 和 CSS 的文件进行压缩，来减小文件的体积。
   ```
   
   用过哪些前端性能优化的方法？
   ```
前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数
当需要设置的样式很多时设置className而不是直接操作style
少用全局变量、缓存DOM节点查找的结果。减少IO读取操作
避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)
图片预加载，将样式表放在顶部，将脚本放在底部 加上时间戳
避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示比div+css布局慢
   ```
   
   前端性能优化最佳实践？
   ```
性能评级工具（PageSpeed 或 YSlow）
合理设置 HTTP 缓存：Expires 与 Cache-control
静态资源打包，开启 Gzip 压缩（节省响应流量）
CSS3 模拟图像，图标base64（降低请求数）
模块延迟(defer)加载/异步(async)加载
Cookie 隔离（节省请求流量）
localStorage（本地存储）
使用 CDN 加速（访问最近服务器）
启用 HTTP/2（多路复用，并行加载）
前端自动化（gulp/webpack）
   ```
   
性能优化问题：
```
代码层面：避免使用css表达式，避免使用高级选择器，通配选择器
缓存利用：缓存Ajax，使用CDN，使用外部js和css文件以便缓存，添加Expires头，服务端配置Etag，减少DNS查找等
请求数量：合并样式和脚本，使用css图片精灵，初始首屏之外的图片资源按需加载，静态资源延迟加载
请求带宽：压缩文件，开启GZIP
```

#### 渲染优化

```
（1）禁止使用iframe（阻塞父文档onload事件）：
   iframe会阻塞主页面的Onload事件
   搜索引擎的检索程序无法解读这种页面，不利于SEO
   iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载
   使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
   动态给iframe添加src属性值，这样可以绕开以上两个问题

（2）禁止使用gif图片实现loading效果（降低CPU消耗，提升渲染性能）

（3）使用CSS3代码代替JS动画（尽可能避免重绘重排以及回流）

（4）对于一些小图标，可以使用base64位编码，以减少网络请求。但不建议大图使用，比较耗费CPU
   小图标优势在于：
      减少HTTP请求
      避免文件跨域
      修改及时生效

（5）页面头部的<style></style> <script></script> 会阻塞页面；（因为 Renderer进程中 JS线程和渲染线程是互斥的）

（6）页面中空的 href 和 src 会阻塞页面其他资源的加载 (阻塞下载进程)

（7）网页gzip，CDN托管，data缓存 ，图片服务器

（8）前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数

（9）用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能

（10）当需要设置的样式很多时设置className而不是直接操作style

（11）少用全局变量、缓存DOM节点查找的结果。减少IO读取操作

（12）图片预加载，将样式表放在顶部，将脚本放在底部 加上时间戳

（13）对普通的网站有一个统一的思路，就是尽量向前端优化、减少数据库操作、减少磁盘IO
```


#### 关键渲染路径优化（浏览器渲染过程）

   ```
    为尽快完成首次渲染，我们需要最大限度减小以下三种可变因素：
    （1）关键资源的数量。
    （2）关键路径长度。
    （3）关键字节的数量。

    关键资源是可能阻止网页首次渲染的资源。这些资源越少，浏览器的工作量就越小，对 CPU 以及其他资源的占用也就越少。

    同样，关键路径长度受所有关键资源与其字节大小之间依赖关系图的影响：
    某些资源只能在上一资源处理完毕之后才能开始下载，并且资源越大，下载所需的往返次数就越多。

    最后，浏览器需要下载的关键字节越少，处理内容并让其出现在屏幕上的速度就越快。
    要减少字节数，我们可以减少资源数（将它们删除或设为非关键资源），
    此外还要压缩和优化各项资源，确保最大限度减小传送大小。

    优化关键渲染路径的常规步骤如下：
    （1）对关键路径进行分析和特性描述：资源数、字节数、长度。
    （2）最大限度减少关键资源的数量：删除它们，延迟它们的下载，将它们标记为异步等。
    （3）优化关键字节数以缩短下载时间（往返次数）。
    （4）优化其余关键资源的加载顺序：您需要尽早下载所有关键资产，以缩短关键路径长度。
   ```

#### 大量图片加载慢如何优化

```
(1)图片懒加载，在页面上的未可视区域可以添加一个滚动事件，判断图片位置与浏览器顶端的距离与页面的距离，如果前者小于后者，优先加载。
(2)如果为幻灯片、相册等，可以使用图片预加载技术，将当前展示图片的前一张和后一张优先下载。
(3)如果图片为css图片，可以使用CSSsprite，SVGsprite，Iconfont、Base64等技术。
(4)如果图片过大，可以使用特殊编码的图片，加载时会先加载一张压缩的特别厉害的缩略图，以提高用户体验。
(5)如果图片展示区域小于图片的真实大小，则因在服务器端根据业务需要先行进行图片压缩，图片压缩后大小与展示一致。
```

### 常见的浏览器端的存储技术
   ```
    浏览器常见的存储技术有 cookie、localStorage 和 sessionStorage。

    还有两种存储技术用于大规模数据存储，webSQL（已被废除）和 indexDB。

    IE 支持 userData 存储数据，但是基本很少使用到，除非有很强的浏览器兼容需求。
   ```

#### cookies、sessionStorage、localStorage的区别

```
    浏览器端常用的存储技术是 cookie 、localStorage 和 sessionStorage。

    cookie 其实最开始是服务器端用于记录用户状态的一种方式，由服务器设置，在客户端存储，
    然后每次发起同源请求时，发送给服务器端。cookie 最多能存储 4 k 数据，
    它的生存时间由 expires 属性指定，并且 cookie 只能被同源的页面访问共享。

    sessionStorage 是 html5 提供的一种浏览器本地存储的方法，它借鉴了服务器端 session 的概念，
    代表的是一次会话中所保存的数据。它一般能够存储 5M 或者更大的数据，
    它在当前窗口关闭后就失效了，并且 sessionStorage 只能被同一个窗口的同源页面所访问共享。

    localStorage 也是 html5 提供的一种浏览器本地存储的方法，它一般也能够存储 5M 或者更大的数据。
    它和 sessionStorage 不同的是，除非手动删除它，否则它不会失效，并且 localStorage 也只能被同源页面所访问共享。

    上面几种方式都是存储少量数据的时候的存储方式，当我们需要在本地存储大量数据的时候，
    我们可以使用浏览器的 indexDB 这是浏览器提供的一种本地的数据库存储机制。
    它不是关系型数据库，它内部采用对象仓库的形式存储数据，它更接近 NoSQL 数据库。
```

```
    SessionStorage， LocalStorage， Cookie 这三者都可以被用来在浏览器端存储数据，而且都是字符串类型
    的键值对。区别在于前两者属于 HTML5 WebStorage，创建它们的目的便于客户端存储数据。而 cookie 是
    网站为了标示用户身份而储存在用户本地终端上的数据（通常经过加密）。cookie 数据始终在同源
    （协议、主机、端口相同）的 http 请求中携带（即使不需要），会在浏览器和服务器间来回传递。
    
    存储大小：
      	cookie 数据大小不能超过4 k 。
      	sessionStorage 和 localStorage 虽然也有存储大小的限制，但比 cookie 大得多，可以达到 5M 或更大。

    有期时间：
      	localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据。
      	sessionStorage  数据在页面会话结束时会被清除。页面会话在浏览器打开期间一直保持，
                        并且重新加载或恢复页面仍会保持原来的页面会话。
                        在新标签或窗口打开一个页面时会在顶级浏览上下文中初始化一个新的会话。
      	cookie          设置的 cookie 过期时间之前一直有效，即使窗口或浏览器关闭。
     
    作用域：
        sessionStorage  只在同源的同窗口（或标签页）中共享数据，也就是只在当前会话中共享。
        localStorage    在所有同源窗口中都是共享的。
        cookie          在所有同源窗口中都是共享的。
        
    操作：
        localStroage：localStroage.setItem('a' , '111')
        sessionStroage：sessionStroage.setItem('a' , '111')
```

Cookie的弊端
```
cookie虽然在持久保存客户端数据提供了方便，分担了服务器存储的负担，但还是有很多局限性的

每个特定的域名下最多生成20个cookie
IE6或更低版本最多20个cookie
IE7和之后的版本最后可以有50个cookie
Firefox最多50个cookie
chrome和Safari没有做硬性限制
IE 和 Opera 会清理近期最少使用的 cookie，Firefox 会随机清理 cookie
cookie 的最大大约为 4096 字节，为了兼容性，一般设置不超过 4095 字节
如果 cookie 被人拦截了，就可以取得所有的 session 信息
```

### html5的离线储存怎么使用，解释工作原理

   ```
    在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。

    原理：HTML5 的离线存储是基于一个新建的 .appcache 文件的缓存机制（不是存储技术），
        通过这个文件上的解析清单离线存储资源，这些资源就会像 cookie 一样被存储了下来。
        之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。

    如何使用：
    （1）创建一个和 html 同名的 manifest 文件，然后在页面头部像下面一样加入一个 manifest 的属性。
        <html lang="en" manifest="index.manifest">

    （2）在如下 cache.manifest 文件的编写离线存储的资源。
      	CACHE MANIFEST
      	#v0.11
      	CACHE:
      	js/app.js
      	css/style.css
      	NETWORK:
      	resourse/logo.png
      	FALLBACK:
      	/ /offline.html

        CACHE: 表示需要离线存储的资源列表，由于包含 manifest 文件的页面将被自动离线存储，所以不需要把页面自身也列出来。

        NETWORK: 表示在它下面列出来的资源只有在在线的情况下才能访问，他们不会被离线存储，
                 所以在离线情况下无法使用这些资源。不过，如果在 CACHE 和 NETWORK 中有一个相同的资源，
                 那么这个资源还是会被离线存储，也就是说 CACHE 的优先级更高。

        FALLBACK: 表示如果访问第一个资源失败，那么就使用第二个资源来替换他，比如上面这个文件表示的就是
                  如果访问根目录下任何一个资源失败了，那么就去访问 offline.html 。

    （3）在离线状态时，操作 window.applicationCache 进行离线缓存的操作。

    如何更新缓存：
    （1）更新 manifest 文件
    （2）通过 javascript 操作
    （3）清除浏览器缓存

    注意事项：
    （1）浏览器对缓存数据的容量限制可能不太一样（某些浏览器设置的限制是每个站点 5MB）。
    （2）如果 manifest 文件，或者内部列举的某一个文件不能正常下载，整个更新过程都将失败，浏览器继续全部使用老的缓存。
    （3）引用 manifest 的 html 必须与 manifest 文件同源，在同一个域下。
    （4）FALLBACK 中的资源必须和 manifest 文件同源。
    （5）当一个资源被缓存后，该浏览器直接请求这个绝对路径也会访问缓存中的资源。
    （6）站点中的其他页面即使没有设置 manifest 属性，请求的资源如果在缓存中也从缓存中访问。
    （7）当 manifest 文件发生改变时，资源请求本身也会触发更新。
   ```

### 浏览器是怎么对html5的离线储存资源进行管理和加载的
   ```
    在线的情况下，浏览器发现 html 头部有 manifest 属性，它会请求 manifest 文件，
    如果是第一次访问 app ，那么浏览器就会根据 manifest 文件的内容下载相应的资源
    并且进行离线存储。如果已经访问过 app 并且资源已经离线存储了，那么浏览器就会
    使用离线的资源加载页面，然后浏览器会对比新的 manifest 文件与旧的 manifest 文件，
    如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。

    离线的情况下，浏览器就直接使用离线存储的资源。
   ```

### 重绘和回流（浏览器绘制过程）
  
```
    重绘: 当渲染树中的一些元素需要更新属性，而这些属性只是影响元素的外观、风格，
          而不会影响布局的操作，比如 background-color，我们将这样的操作称为重绘。
    
    回流：当渲染树中的一部分（或全部）因为元素的规模尺寸、布局、隐藏等改变
         而需要重新构建的操作，会影响到布局的操作，这样的操作我们称为回流。

    常见引起回流属性和方法：
    任何会改变元素几何信息（元素的位置和尺寸大小）的操作，都会触发回流。
    （1）添加或者删除可见的 DOM 元素；
    （2）元素尺寸改变——边距、填充、边框、宽度和高度
    （3）内容变化，比如用户在 input 框中输入文字
    （4）浏览器窗口尺寸改变——resize事件发生时
    （5）计算 offsetWidth 和 offsetHeight 属性
    （6）设置 style 属性的值
    （7）当你修改网页的默认字体时。

    回流必定会发生重绘，重绘不一定会引发回流。回流所需的成本比重绘高的多，
    改变父节点里的子节点很可能会导致父节点的一系列回流。
```

```
   常见引起重绘属性和方法：


   常见引起回流属性和方法：
```

```
重绘：当渲染树中的元素外观（如：颜色）发生改变，不影响布局时，产生重绘
回流：当渲染树中的元素的布局（如：尺寸、位置、隐藏/状态状态）发生改变时，产生重绘回流
注意：JS获取Layout属性值（如：offsetLeft、scrollTop、getComputedStyle等）
     也会引起回流。因为浏览器需要通过回流计算最新值
回流必将引起重绘，而重绘不一定会引起回流
```

如何最小化重绘(repaint)和回流(reflow)：
```
需要要对元素进行复杂的操作时，可以先隐藏(display:"none")，操作完成后再显示
需要创建多个DOM节点时，使用DocumentFragment创建完后一次性的加入document
缓存Layout属性值，如：var left = elem.offsetLeft; 这样，多次使用 left 只产生一次回流
尽量避免用table布局（table元素一旦触发回流就会导致table里所有的其它元素回流）
避免使用css表达式(expression)，因为每次调用都会重新计算值（包括加载页面）
尽量使用 css 属性简写，如：用 border 代替 border-width, border-style, border-color
批量修改元素样式：elem.className 和 elem.style.cssText 代替 elem.style.xxx
```

#### 如何减少回流（浏览器绘制过程）
   ```
    （1）使用 transform 替代 top
    （2）不要把节点的属性值放在一个循环里当成循环里的变量
    （3）不要使用 table 布局，可能很小的一个小改动会造成整个 table 的重新布局
    （4）把 DOM 离线后修改。如：使用 documentFragment 对象在内存里操作 DOM
    （5）不要一条一条地修改 DOM 的样式。与其这样，还不如预先定义好 css 的 class，然后修改 DOM 的 className。
   ```

### 怎么重构页面
   ```
    （1） 编写 CSS
    （2） 让页面结构更合理化，提升用户体验
    （3） 实现良好的页面效果和提升性能
   ```

### 从浏览器地址栏输入url到显示页面的步骤

基础版本
```
浏览器根据请求的URL交给DNS域名解析，找到真实IP，向服务器发起请求；
服务器交给后台处理完成后返回数据，浏览器接收文件（HTML、JS、CSS、图象等）；
浏览器对加载到的资源（HTML、JS、CSS等）进行语法解析，建立相应的内部数据结构（如HTML的DOM）；
载入解析到的资源文件，渲染页面，完成。
```

详细版
```
1.在浏览器地址栏输入URL
2.浏览器查看缓存，如果请求资源在缓存中并且新鲜，跳转到转码步骤
  (1)如果资源未缓存，发起新请求
  (2)如果已缓存，检验是否足够新鲜，足够新鲜直接提供给客户端，否则与服务器进行验证。
  (3)检验新鲜通常有两个HTTP头进行控制Expires和Cache-Control：
      HTTP1.0提供Expires，值为一个绝对时间表示缓存新鲜日期
      HTTP1.1增加了Cache-Control: max-age=,值为以秒为单位的最大新鲜时间
3.浏览器解析URL获取协议，主机，端口，path
4.浏览器组装一个HTTP（GET）请求报文
5.浏览器获取主机ip地址，过程如下：
  (1)浏览器缓存
  (2)本机缓存
  (3)hosts文件
  (4)路由器缓存
  (5)ISP DNS缓存
  (6)DNS递归查询（可能存在负载均衡导致每次IP不一样）
6.打开一个socket与目标IP地址，端口建立TCP链接，三次握手如下：
  (1)客户端发送一个TCP的SYN=1，Seq=X的包到服务器端口
  (2)服务器发回SYN=1， ACK=X+1， Seq=Y的响应包
  (3)客户端发送ACK=Y+1， Seq=Z
7.TCP链接建立后发送HTTP请求
8.服务器接受请求并解析，将请求转发到服务程序，如虚拟主机使用HTTP Host头部判断请求的服务程序
9.服务器检查HTTP请求头是否包含缓存验证信息如果验证缓存新鲜，返回304等对应状态码
10.处理程序读取完整请求并准备HTTP响应，可能需要查询数据库等操作
11.服务器将响应报文通过TCP连接发送回浏览器
12.浏览器接收HTTP响应，然后根据情况选择关闭TCP连接或者保留重用，关闭TCP连接的四次握手如下：
  (1)主动方发送Fin=1， Ack=Z， Seq= X报文
  (2)被动方发送ACK=X+1， Seq=Z报文
  (3)被动方发送Fin=1， ACK=X， Seq=Y报文
  (4)主动方发送ACK=Y， Seq=X报文
13.浏览器检查响应状态吗：是否为1XX，3XX， 4XX， 5XX，这些情况处理与2XX不同
14.如果资源可缓存，进行缓存
15.对响应进行解码（例如gzip压缩）
16.根据资源类型决定如何处理（假设资源为HTML文档）
17.解析HTML文档，构件DOM树，下载资源，构造CSSOM树，执行js脚本，这些操作没有严格的先后顺序，以下分别解释
18.构建DOM树：
  (1)Tokenizing：根据HTML规范将字符流解析为标记
  (2)Lexing：词法分析将标记转换为对象并定义属性和规则
  (3)DOM construction：根据HTML标记关系将对象组成DOM树
19.解析过程中遇到图片、样式表、js文件，启动下载
20.构建CSSOM树：
  (1)Tokenizing：字符流转换为标记流
  (2)Node：根据标记创建节点
  (3)CSSOM：节点创建CSSOM树
21.根据DOM树和CSSOM树构建渲染树 (opens new window):
  (1)从DOM树的根节点遍历所有可见节点，不可见节点包括：1）script,meta这样本身不可见的标签。2)被css隐藏的节点，如display: none
  (2)对每一个可见节点，找到恰当的CSSOM规则并应用
  (3)发布可视节点的内容和计算样式
22.js解析如下：
  (1)浏览器创建Document对象并解析HTML，将解析到的元素和文本节点添加到文档中，此时document.readystate为loading
  (2)HTML解析器遇到没有async和defer的script时，将他们添加到文档中，然后执行行内或外部脚本。
  这些脚本会同步执行，并且在脚本下载和执行时解析器会暂停。这样就可以用document.write()把文本插入到输入流中。
  同步脚本经常简单定义函数和注册事件处理程序，他们可以遍历和操作script和他们之前的文档内容
  (3)当解析器遇到设置了async属性的script时，开始下载脚本并继续解析文档。脚本会在它下载完成后尽快执行，
  但是解析器不会停下来等它下载。异步脚本禁止使用document.write()，它们可以访问自己script和之前的文档元素
  (4)当文档完成解析，document.readState变成interactive
  (5)所有defer脚本会按照在文档出现的顺序执行，延迟脚本能访问完整文档树，禁止使用document.write()
  (6)浏览器在Document对象上触发DOMContentLoaded事件
  (7)此时文档完全解析完成，浏览器可能还在等待如图片等内容加载，等这些内容完成载入并且
  所有异步脚本完成载入和执行，document.readState变为complete，window触发load事件
23.显示页面（HTML解析过程中会逐步显示页面）
```

详细简版
```
1.从浏览器接收url到开启网络请求线程（这一部分可以展开浏览器的机制以及进程与线程之间的关系）
2.开启网络线程到发出一个完整的HTTP请求（这一部分涉及到dns查询，TCP/IP请求，五层因特网协议栈等知识）
3.从服务器接收到请求到对应后台接收到请求（这一部分可能涉及到负载均衡，安全拦截以及后台内部的处理等等）
4.后台和前台的HTTP交互（这一部分包括HTTP头部、响应码、报文结构、cookie等知识，可以提下静态资源的cookie优化，以及编码解码，如gzip压缩等）
5.单独拎出来的缓存问题，HTTP的缓存（这部分包括http缓存头部，ETag，catch-control等）
6.浏览器接收到HTTP数据包后的解析流程（解析html-词法分析然后解析成dom树、解析css生成css规则树、合并成render树，
  然后layout、painting渲染、复合图层的合成、GPU绘制、外链资源的处理、loaded和DOMContentLoaded等）
7.CSS的可视化格式模型（元素的渲染规则，如包含块，控制框，BFC，IFC等概念）
8.JS引擎解析过程（JS的解释阶段，预处理阶段，执行阶段生成执行上下文，VO，作用域链、回收机制等等）
9.其它（可以拓展不同的知识模块，如跨域，web安全，hybrid模式等等内容）
```

### 浏览器

#### 对浏览器的理解
   ```
   浏览器的主要功能是将用户选择的 web 资源呈现出来，它需要从服务器请求资源，并将其
   显示在浏览器窗口中，资源的格式通常是 HTML，也包括 PDF、image 及其他格式。
   用户用 URI（Uniform Resource Identifier 统一资源标识符）来指定所请求资源的位置。

   HTML 和 CSS 规范中规定了浏览器解释 html 文档的方式，由 W3C 组织
   对这些规范进行维护，W3C 是负责制定 web 标准的组织。

   但是浏览器厂商纷纷开发自己的扩展，对规范的遵循并不完善，这为 web 开发者带来了严重的兼容性问题。

   简单来说浏览器可以分为两部分，shell 和 内核。

   其中 shell 的种类相对比较多，内核则比较少。shell 是指浏览器的外壳：例如菜单，工具栏等。
   主要是提供给用户界面操作，参数设置等等。它是调用内核来实现各种功能的。内核才是浏览器的核心。
   内核是基于标记语言显示内容的程序或模块。也有一些浏览器并不区分外壳和内核。
   从 Mozilla 将 Gecko 独立出来后，才有了外壳和内核的明确划分。
   ```

#### 对浏览器内核的理解
   ```
   主要分成两部分：渲染引擎和 JS 引擎。

   渲染引擎的职责就是渲染，即在浏览器窗口中显示所请求的内容。默认情况下，
   渲染引擎可以显示 html、xml 文档及图片，它也可以借助插件（一种浏览器扩展）
   显示其他类型数据，例如使用 PDF 阅读器插件，可以显示 PDF 格式。

   JS 引擎：解析和执行 javascript 来实现网页的动态效果。

   最开始渲染引擎和 JS 引擎并没有区分的很明确，后来 JS 引擎越来越独立，内核就倾向于只指渲染引擎。
   ```

#### 常见的浏览器内核比较
   ```
   Trident：这种浏览器内核是 IE 浏览器用的内核，因为在早期 IE 占有大量的市场份额，所以这种内核比较流行，
   以前有很多网页也是根据这个内核的标准来编写的，但是实际上这个内核对真正的网页标准支持不是很好。
   但是由于 IE 的高市场占有率，微软也很长时间没有更新 Trident 内核，就导致了 Trident 内核
   和 W3C 标准脱节。还有就是 Trident 内核的大量 Bug 等安全问题没有得到解决，加上一些专家学者
   公开自己认为 IE 浏览器不安全的观点，使很多用户开始转向其他浏览器。

   Gecko：这是 Firefox 和 Flock 所采用的内核，这个内核的优点就是功能强大、丰富，
   可以支持很多复杂网页效果和浏览器扩展接口，但是代价是也显而易见就是要消耗很多的资源，比如内存。

   Presto：Opera 曾经采用的就是 Presto 内核，Presto 内核被称为公认的浏览网页速度最快的内核，
   这得益于它在开发时的天生优势，在处理 JS 脚本等脚本语言时，会比其他的内核快3倍左右，
   缺点就是为了达到很快的速度而丢掉了一部分网页兼容性。

   Webkit：Webkit 是 Safari 采用的内核，它的优点就是网页浏览速度较快，虽然不及 Presto 
   但是也胜于 Gecko 和 Trident，缺点是对于网页代码的容错性不高，也就是说对网页代码的兼容性较低，
   会使一些编写不标准的网页无法正确显示。WebKit 前身是 KDE 小组的 KHTML 引擎，
   可以说 WebKit 是 KHTML 的一个开源的分支。

   Blink：谷歌在 Chromium Blog 上发表博客，称将与苹果的开源浏览器核心 Webkit 分道扬镳，
   在 Chromium 项目中研发 Blink 渲染引擎（即浏览器核心），内置于 Chrome 浏览器之中。
   其实 Blink 引擎就是 Webkit 的一个分支，就像 webkit 是KHTML 的分支一样。
   Blink 引擎现在是谷歌公司与 Opera Software 共同研发，上面提到过的，
   Opera 弃用了自己的 Presto 内核，加入 Google 阵营，跟随谷歌一起研发 Blink。
   ```

#### 常见浏览器所用内核
   ```
    （1） IE 浏览器内核：Trident 内核，也是俗称的 IE 内核；
    （2） Chrome 浏览器内核：统称为 Chromium 内核或 Chrome 内核，以前是 Webkit 内核，现在是 Blink内核；
    （3） Firefox 浏览器内核：Gecko 内核，俗称 Firefox 内核；
    （4） Safari 浏览器内核：Webkit 内核；
    （5） Opera 浏览器内核：最初是自己的 Presto 内核，后来加入谷歌大军，从 Webkit 又到了 Blink 内核；
    （6） 360浏览器、猎豹浏览器内核：IE + Chrome 双内核；
    （7） 搜狗、遨游、QQ 浏览器内核：Trident（兼容模式）+ Webkit（高速模式）；
    （8） 百度浏览器、世界之窗内核：IE 内核；
    （9） 2345浏览器内核：好像以前是 IE 内核，现在也是 IE + Chrome 双内核了；
    （10）UC 浏览器内核：这个众口不一，UC 说是他们自己研发的 U3 内核，
          但好像还是基于 Webkit 和 Trident ，还有说是基于火狐内核。
   ```

#### 浏览器的渲染原理
   ```
    （1）首先解析收到的文档，根据文档定义构建一棵 DOM 树，DOM 树是由 DOM 元素及属性节点组成的。

    （2）然后对 CSS 进行解析，生成 CSSOM 规则树。

    （3）根据 DOM 树和 CSSOM 规则树构建渲染树。渲染树的节点被称为渲染对象，渲染对象是
    一个包含有颜色和大小等属性的矩形，渲染对象和 DOM 元素相对应，但这种对应关系不是一对一的，
    不可见的 DOM 元素不会被插入渲染树。还有一些 DOM 元素对应几个可见对象，
    它们一般是一些具有复杂结构的元素，无法用一个矩形来描述。

    （4）当渲染对象被创建并添加到树中，它们并没有位置和大小，所以当浏览器生成渲染树以后，
    就会根据渲染树来进行布局（也可以叫做回流）。这一阶段浏览器要做的事情是要弄清楚各个节点
    在页面中的确切位置和大小。通常这一行为也被称为“自动重排”。

    （5）布局阶段结束后是绘制阶段，遍历渲染树并调用渲染对象的 paint 方法将它们的内容显示在屏幕上，
        绘制使用 UI 基础组件。

     值得注意的是，这个过程是逐步完成的，为了更好的用户体验，渲染引擎将会尽可能早的将内容呈现到屏幕上，
     并不会等到所有的html 都解析完成之后再去构建和布局 render 树。它是解析完一部分内容就
     显示一部分内容，同时，可能还在通过网络下载其余内容。
   ```

#### 浏览器架构
   ```
    * 用户界面
      * 主进程
      * 内核
          * 渲染引擎
          * JS 引擎
              * 执行栈
          * 事件触发线程
              * 消息队列
                  * 微任务
                  * 宏任务
          * 网络异步线程
          * 定时器线程
   ```

- 用户界面
- 主进程
- 内核
  - 渲染引擎
  - JS 引擎
    - 执行栈
- 事件触发线程
  - 消息队列
    - 微任务
    - 宏任务
- 网络异步线程
- 定时器线程

#### 如何实现浏览器内多个标签页之间的通信

 ```
    实现多个标签页之间的通信，本质上都是通过中介者模式来实现的。因为标签页之间没有办法直接通信，
    因此我们可以找一个中介者，让标签页和中介者进行通信，然后让这个中介者来进行消息的转发。

    第一种实现的方式是使用 websocket 协议，因为 websocket 协议可以实现服务器推送，
    所以服务器就可以用来当做这个中介者。标签页通过向服务器发送数据，然后由服务器向其他标签页推送转发。

    第二种是使用 ShareWorker 的方式，shareWorker 会在页面存在的生命周期内创建一个唯一的线程，
    并且开启多个页面也只会使用同一个线程。这个时候共享线程就可以充当中介者的角色。
    标签页间通过共享一个线程，然后通过这个共享的线程来实现数据的交换。

    第三种方式是使用 localStorage 的方式，我们可以在一个标签页对 localStorage 的变化事件进行监听，
    然后当另一个标签页修改数据的时候，我们就可以通过这个监听事件来获取到数据。
    这个时候 localStorage 对象就是充当的中介者的角色。

    还有一种方式是使用 postMessage 方法，如果我们能够获得对应标签页的引用，
    我们就可以使用 postMessage 方法，进行通信。
```

   ```
    （1）使用 WebSocket，通信的标签页连接同一个服务器，发送消息到服务器后，服务器推送消息给所有连接的客户端。

    （2）使用 SharedWorker （只在 chrome 浏览器实现了），两个页面共享同一个线程，
         通过向线程发送数据和接收数据来实现标签页之间的双向通行。

    （3）可以调用 localStorage、cookies 等本地存储方式，localStorge 另一个浏览上下文里被添加、修改或删除时，
         它都会触发一个 storage 事件，我们通过监听 storage 事件，控制它的值来进行页面信息通信；

    （4）如果我们能够获得对应标签页的引用，通过 postMessage 方法也是可以实现多个标签页通信的。
   ```
    
1.使用WebSocket 可以实现多个标签页之间的通信
2.调用localStorage
- 在一个标签页里面使用 localStorage.setItem(key,value) 添加（修改、删除）内容；
- 在另一个标签页里面监听 storage 事件。
- 即可得到 localstorge 存储的值，实现不同标签页之间的通信

标签页1
```
<input id="name">  
<input type="button" id="btn" value="提交">  
<script type="text/javascript">  
    $(function(){    
        $("#btn").click(function(){    
            var name=$("#name").val();    
            localStorage.setItem("name", name);   
        });    
    });    
</script>  
```
标签页2：
```
<script type="text/javascript">  
    $(function(){   
        window.addEventListener("storage", function(event){    
            console.log(event.key + "=" + event.newValue);    
        });     
    });  
</script>  
```
3.调用cookie+setInterval()
```
将要传递的信息存储在cookie中，每隔一定时间读取cookie信息，
即可随时获取要传递的信息。
```
页面1：
```
<input id="name">  
<input type="button" id="btn" value="提交">  
<script type="text/javascript">  
    $(function(){    
        $("#btn").click(function(){    
            var name=$("#name").val();    
            document.cookie="name="+name;    
        });    
    });    
</script>  
```
页面2：
```
<script type="text/javascript">  
    $(function(){   
        function getCookie(key) {    
            return JSON.parse("{\"" + document.cookie.replace(/;\s+/gim,"\",\"").replace(/=/gim, "\":\"") + "\"}")[key];    
        }     
        setInterval(function(){    
            console.log("name=" + getCookie("name"));    
        }, 10000);    
    });  
</script>  
 ```

#### 跨标签页通讯
- 不同标签页间的通讯，本质原理就是去运用一些可以 共享的中间介质，因此比较常用的有以下方法:
  - 通过父页面window.open()和子页面postMessage
    - 异步下，通过 window.open('about: blank') 和 tab.location.href = '*'
  - 设置同域下共享的localStorage与监听window.onstorage
    - 重复写入相同的值无法触发
    - 会受到浏览器隐身模式等的限制
  - 设置共享cookie与不断轮询脏检查(setInterval)
  - 借助服务端或者中间层实现

#### 内存泄露
- 意外的全局变量: 无法被回收
- 定时器: 未被正确关闭，导致所引用的外部变量无法被释放
- 事件监听: 没有正确销毁 (低版本浏览器可能出现)
- 闭包: 会导致父级中的变量无法被释放
- dom 引用: dom 元素被删除时，内存中的引用未被正确清空

- 可用 chrome 中的 timeline 进行内存标记，可视化查看内存的变化情况，找出异常点。

#### 浏览器API
#### 1.Web Worker
- 现代浏览器为JavaScript创造的 多线程环境。可以新建并将部分任务分配到worker线程并行运行，两个线程可 独立运行，互不干扰，可通过自带的 消息机制 相互通信。

基本用法:
```
// 创建 worker
const worker = new Worker('work.js');

// 向主进程推送消息
worker.postMessage('Hello World');

// 监听主进程来的消息
worker.onmessage = function (event) {
  console.log('Received message ' + event.data);
}
```
限制:
- 同源限制
- 无法使用 document / window / alert / confirm
- 无法加载本地资源

#### 2.Service Worker
- Service workers 本质上充当Web应用程序与浏览器之间的代理服务器，也可以在网络可用时作为浏览器和网络间的代理。它们旨在（除其他之外）使得能够创建有效的离线体验，拦截网络请求并基于网络是否可用以及更新的资源是否驻留在服务器上来采取适当的动作。他们还允许访问推送通知和后台同步API

目前该技术通常用来做缓存文件，提高首屏速度
```
// index.js
if (navigator.serviceWorker) {
  navigator.serviceWorker
    .register("sw.js")
    .then(function(registration) {
      console.log("service worker 注册成功");
    })
    .catch(function(err) {
      console.log("servcie worker 注册失败");
    });
}
// sw.js
// 监听 `install` 事件，回调中缓存所需文件
self.addEventListener("install", e => {
  e.waitUntil(
    caches.open("my-cache").then(function(cache) {
      return cache.addAll(["./index.html", "./index.js"]);
    })
  );
});

// 拦截所有请求事件
// 如果缓存中已经有请求的数据就直接用缓存，否则去请求数据
self.addEventListener("fetch", e => {
  e.respondWith(
    caches.match(e.request).then(function(response) {
      if (response) {
        return response;
      }
      console.log("fetch source");
    })
  );
});
```
- 打开页面，可以在开发者工具中的 Application 看到 Service Worker 已经启动了
- 在 Cache 中也可以发现我们所需的文件已被缓存
- 当我们重新刷新页面可以发现我们缓存的数据是从 Service Worker 中读取的

#### 3.requestAnimationFrame用法
- 在Web应用中，实现动画效果的方法比较多，Javascript 中可以通过定时器 setTimeout 来实现，css3 可以使用 transition 和 animation 来实现，html5 中的 canvas 也可以实现。除此之外，html5 还提供一个专门用于请求动画的API，那就是 requestAnimationFrame，顾名思义就是请求动画帧

1.页面可见
- 当页面被最小化或者被切换成后台标签页时，页面为不可见，浏览器会触发一个 visibilitychange事件,并设置document.hidden属性为true；切换到显示状态时，页面为可见，也同样触发一个 visibilitychange 事件，设置document.hidden属性为false

2.动画帧请求回调函数列表
- 每个Document都有一个动画帧请求回调函数列表，该列表可以看成是由<handlerId, callback>元组组成的集合。其中handlerId是一个整数，唯一地标识了元组在列表中的位置；callback是回调函数

3.屏幕刷新频率
- 即图像在屏幕上更新的速度，也即屏幕上的图像每秒钟出现的次数，它的单位是赫兹(Hz)。 对于一般笔记本电脑，这个频率大概是60Hz， 这个值的设定受屏幕分辨率、屏幕尺寸和显卡的影响

4.动画原理
- 根据上面的原理我们知道，你眼前所看到图像正在以每秒60次的频率刷新，由于刷新频率很高，因此你感觉不到它在刷新。而动画本质就是要让人眼看到图像被刷新而引起变化的视觉效果，这个变化要以连贯的、平滑的方式进行过渡。 那怎么样才能做到这种效果呢

- 刷新频率为60Hz的屏幕每16.7ms刷新一次，我们在屏幕每次刷新前，将图像的位置向左移动一个像素，即1px。这样一来，屏幕每次刷出来的图像位置都比前一个要差1px，因此你会看到图像在移动；由于我们人眼的视觉停留效应，当前位置的图像停留在大脑的印象还没消失，紧接着图像又被移到了下一个位置，因此你才会看到图像在流畅的移动，这就是视觉效果上形成的动画

5.requestAnimationFrame用法
异步，传入的函数在重绘之前调用
- 1. 写法：handlerId = requestAnimationFrame(callback)
  - 传入一个callback函数，即动画函数
  - 返回值handlerId为浏览器定义的、大于0的整数，唯一标识了该回调函数在列表中位置

- 2. 浏览器执行过程
  - 首先要判断document.hidden属性是否为true,即页面处于可见状态下才会执行
  - 浏览器清空上一轮的动画函数
  - 这个方法返回的handlerId 值会和动画函数callback，以<handlerId , callback> 进入到动画帧请求回调函数列
  - 浏览器会遍历动画帧请求回调函数列表，根据handlerId 的值大小，依次去执行相应的动画函数

- 3. 取消动画函数的方法
```
cancelAnimationFrame(handlerId)
```

- 6.与setTimeout对比
- 理解了上面的概念以后，我们不难发现，setTimeout 其实就是通过设置一个间隔时间来不断的改变图像的位置，从而达到动画效果的。但利用seTimeout实现的动画在某些低端机上会出现卡顿、抖动的现象。 这种现象的产生有两个原因

  - setTimeout的执行时间并不是确定的。在Javascript中， setTimeout 任务被放进了异步队列中，只有当主线程上的任务执行完以后，才会去检查该队列里的任务是否需要开始执行，因此 setTimeout 的实际执行时间一般要比其设定的时间晚一些
  - 刷新频率受屏幕分辨率和屏幕尺寸的影响，因此不同设备的屏幕刷新频率可能会不同，而 setTimeout只能设置一个固定的时间间隔，这个时间不一定和屏幕的刷新时间相同。

- 以上两种情况都会导致setTimeout的执行步调和屏幕的刷新步调不一致，从而引起丢帧现象。 那为什么步调不一致就会引起丢帧呢
- 首先要明白，setTimeout的执行只是在内存中对图像属性进行改变，这个变化必须要等到屏幕下次刷新时才会被更新到屏幕上。如果两者的步调不一致，就可能会导致中间某一帧的操作被跨越过去，而直接更新下一帧的图像。假设屏幕每隔16.7ms刷新一次，而setTimeout每隔10ms设置图像向左移动1px， 就会出现如下绘制过程：
  - 第0ms: 屏幕未刷新，等待中，setTimeout也未执行，等待中；
  - 第10ms: 屏幕未刷新，等待中，setTimeout开始执行并设置图像属性left=1px；
  - 第16.7ms: 屏幕开始刷新，屏幕上的图像向左移动了1px， setTimeout 未执行，继续等待中；
  - 第20ms: 屏幕未刷新，等待中，setTimeout开始执行并设置left=2px;
  - 第30ms: 屏幕未刷新，等待中，setTimeout开始执行并设置left=3px;
  - 第33.4ms: 屏幕开始刷新，屏幕上的图像向左移动了3px， setTimeout未执行，继续等待中； …

- 从上面的绘制过程中可以看出，屏幕没有更新left=2px的那一帧画面，图像直接从1px的位置跳到了3px的的位置，这就是丢帧现象，这种现象就会引起动画卡顿

- 与setTimeout相比，requestAnimationFrame最大的优势是由系统来决定回调函数的执行时机。具体一点讲，如果屏幕刷新率是60Hz,那么回调函数就每16.7ms被执行一次，如果刷新率是75Hz，那么这个时间间隔就变成了1000/75=13.3ms，换句话说就是，requestAnimationFrame的步伐跟着系统的刷新步伐走。它能保证回调函数在屏幕每一次的刷新间隔中只被执行一次，这样就不会引起丢帧现象，也不会导致动画出现卡顿的问题。
```
var progress = 0;
//回调函数
function render() {  
  progress += 1; //修改图像的位置  
  if (progress < 100) {  //在动画没有结束前，递归渲染    
    window.requestAnimationFrame(render); 
  }
}
//第一帧渲染
window.requestAnimationFrame(render)
```
除此之外，requestAnimationFrame还有以下两个优势
- CPU节能：使用setTimeout实现的动画，当页面被隐藏或最小化时，setTimeout 仍然在后台执行动画任务，由于此时页面处于不可见或不可用状态，刷新动画是没有意义的，完全是浪费CPU资源。而requestAnimationFrame则完全不同，当页面处理未激活的状态下，该页面的屏幕刷新任务也会被系统暂停，因此跟着系统步伐走的requestAnimationFrame也会停止渲染，当页面被激活时，动画就从上次停留的地方继续执行，有效节省了CPU开销
- 函数节流：在高频率事件(resize,scroll等)中，为了防止在一个刷新间隔内发生多次函数执行，使用requestAnimationFrame可保证每个刷新间隔内，函数只被执行一次，这样既能保证流畅性，也能更好的节省函数执行的开销。一个刷新间隔内函数执行多次时没有意义的，因为显示器每16.7ms刷新一次，多次绘制并不会在屏幕上体现出来

- 7.优雅降级
  - 由于requestAnimationFrame目前还存在兼容性问题，而且不同的浏览器还需要带不同的前缀。因此需要通过优雅降级的方式对requestAnimationFrame进行封装，优先使用高级特性，然后再根据不同浏览器的情况进行回退，直至只能使用setTimeout的情况。下面的代码就是有人在github上提供的polyfill，详细介绍请参考github代码 requestAnimationFrame(opens new window)
```
if (!Date.now)
    Date.now = function() { return new Date().getTime(); };
 
(function() {
    'use strict';
     
    var vendors = ['webkit', 'moz'];
    for (var i = 0; i < vendors.length && !window.requestAnimationFrame; ++i) {
        var vp = vendors[i];
        window.requestAnimationFrame = window[vp+'RequestAnimationFrame'];
        window.cancelAnimationFrame = (window[vp+'CancelAnimationFrame']
                                   || window[vp+'CancelRequestAnimationFrame']);
    }
    if (/iP(ad|hone|od).*OS 6/.test(window.navigator.userAgent) // iOS6 is buggy
        || !window.requestAnimationFrame || !window.cancelAnimationFrame) {
        var lastTime = 0;
        window.requestAnimationFrame = function(callback) {
            var now = Date.now();
            var nextTime = Math.max(lastTime + 16, now);
            return setTimeout(function() { callback(lastTime = nextTime); },
                              nextTime - now);
        };
        window.cancelAnimationFrame = clearTimeout;
    }
}())
```

### 页面加载执行
#### 1.浏览器事件循环
- 事件循环是指: 执行一个宏任务，然后执行清空微任务列表，循环再执行宏任务，再清微任务列表

- 微任务 microtask(jobs): promise / process.nextTick / MutationObserver
- 宏任务 macrotask(task): setTimout / setInterval / setImmediate / script / IO / UI Rendering

- 宏任务中包括了 script ，浏览器会先执行一个宏任务，接下来有异步代码的话就先执行微任务

#### 2.怎么判断页面是否加载完成
- Load 事件触发代表页面中的 DOM，CSS，JS，图片已经全部加载完毕。
- DOMContentLoaded 事件触发代表初始的 HTML 被完全加载和解析，不需要等待 CSS，JS，图片加载

#### 3.css加载会造成阻塞吗
- DOM 和 CSSOM 通常是并行构建的,所以 CSS 加载不会阻塞 DOM 的解析。
- 然而,由于 Render Tree 是依赖于 DOM Tree 和 CSSOM Tree 的,
- 所以他必须等待到 CSSOM Tree 构建完成,也就是 CSS 资源加载完成(或者 CSS 资源加载失败)后,才能开始渲染。
- 因此,CSS 加载会阻塞 Dom 的渲染。
- 由于 JavaScript 是可操纵 DOM 和 css 样式的,如果在修改这些元素属性同时渲染界面（即 JavaScript 线程和 UI线程同时运行）,那么渲染线程前后获得的元素数据就可能不一致了。
- 因此为了防止渲染出现不可预期的结果,浏览器设置 GUI 渲染线程与 JavaScript 引擎为互斥的关系。因此,样式表会在后面的 js 执行前先加载执行完毕,所以css 会阻塞后面 js 的执行

#### 4.为什么JS阻塞页面加载
- 由于 JavaScript 是可操纵 DOM 的,如果在修改这些元素属性同时渲染界面（即 JavaScript 线程和 UI 线程同时运行）,那么渲染线程前后获得的元素数据就可能不一致了
- 因此为了防止渲染出现不可预期的结果,浏览器设置 GUI 渲染线程与 JavaScript 引擎为互斥的关系
- 当 JavaScript 引擎执行时 GUI 线程会被挂起,GUI 更新会被保存在一个队列中等到引擎线程空闲时立即被执行
- 从上面我们可以推理出,由于 GUI 渲染线程与 JavaScript 执行线程是互斥的关系,
- 当浏览器在执行 JavaScript 程序的时候,GUI 渲染线程会被保存在一个队列中,直到 JS 程序执行完成,才会接着执行
- 因此如果 JS执行的时间过长,这样就会造成页面的渲染不连贯,导致页面渲染加载阻塞的感觉

#### 5.DOMContentLoaded与load的区别
- 当 DOMContentLoaded 事件触发时,仅当 DOM 解析完成后,不包括样式表,图片。我们前面提到 CSS 加载会阻塞 Dom 的渲染和后面 js 的执行,js 会阻塞 Dom 解析,所以我们可以得到结论:
- 当文档中没有脚本时,浏览器解析完文档便能触发 DOMContentLoaded 事件。如果文档中包含脚本,则脚本会阻塞文档的解析,而脚本需要等 CSSOM 构建完成才能执行。在任何情况下,DOMContentLoaded 的触发不需要等待图片等其他资源加载完成
- 当 onload 事件触发时,页面上所有的 DOM,样式表,脚本,图片等资源已经加载完毕
- DOMContentLoaded -> load

#### 6.什么是CRP,即关键渲染路径?如何优化
- 关键渲染路径是浏览器将 HTML CSS JavaScript 转换为在屏幕上呈现的像素内容所经历的一系列步骤。也就是我们上面说的浏览器渲染流程。

为尽快完成首次渲染,我们需要最大限度减小以下三种可变因素:
- 关键资源的数量: 可能阻止网页首次渲染的资源。
- 关键路径长度: 获取所有关键资源所需的往返次数或总时间。
- 关键字节: 实现网页首次渲染所需的总字节数,等同于所有关键资源传送文件大小的总和

1. 优化 DOM
- 删除不必要的代码和注释包括空格,尽量做到最小化文件。
- 可以利用 GZIP 压缩文件。
- 结合 HTTP 缓存文件

2. 优化 CSSOM
- 缩小、压缩以及缓存同样重要,对于 CSSOM 我们前面重点提过了它会阻止页面呈现,因此我们可以从这方面考虑去优化。

- 减少关键 CSS 元素数量
- 当我们声明样式表时,请密切关注媒体查询的类型,它们极大地影响了 CRP 的性能

3. 优化 JavaScript
- 当浏览器遇到 script标记时,会阻止解析器继续操作,直到 CSSOM 构建完毕,JavaScript 才会运行并继续完成 DOM 构建过程。

- async: 当我们在 script 标记添加 async 属性以后,浏览器遇到这个 script 标记时会继续解析 DOM,同时脚本也不会被 CSSOM 阻止,即不会阻止 CRP。
- defer: 与 async 的区别在于,脚本需要等到文档解析后（ DOMContentLoaded 事件前）执行,而 async 允许脚本在文档解析时位于后台运行（两者下载的过程不会阻塞 DOM,但执行会）
- 当我们的脚本不会修改 DOM 或 CSSOM 时,推荐使用 async
- 预加载 —— preload & prefetch
- DNS 预解析 —— dns-prefetch

总结
- 分析并用 关键资源数 关键字节数 关键路径长度 来描述我们的 CRP
- 最小化关键资源数:消除它们（内联）、推迟它们的下载（defer）或者使它们异步解析（async）等
- 优化关键字节数（缩小、压缩）来减少下载时间 优化加载剩余关键资源的顺序:
- 让关键资源（CSS）尽早下载以减少 CRP 长度

### history路由和hash路由
hash 路由
- hash 路由，在 html5 前，为了解决单页路由跳转问题采用的方案， hash 的变化不会触发页面渲染，服务端也无法获取到 hash 值，前端可通过监听 hashchange 事件来处理hash值的变化
```
window.addEventListener('hashchange', function(){ 
    // 监听hash变化，点击浏览器的前进后退会触发
})
```

history 路由
- history 路由，是 html5 的规范，提供了对history栈中内容的操作，常用api有：
```
window.history.pushState(state, title, url) 
// let currentState = history.state; 获取当前state
// state：需要保存的数据，这个数据在触发popstate事件时，可以在event.state里获取
// title：标题，基本没用，一般传 null
// url：设定新的历史记录的 url。新的 url 与当前 url 的 origin 必须是一樣的，否则会抛出错误。url可以是绝对路径，也可以是相对路径。
//如 当前url是 https://www.baidu.com/a/,执行history.pushState(null, null, './qq/')，则变成 https://www.baidu.com/a/qq/，
//执行history.pushState(null, null, '/qq/')，则变成 https://www.baidu.com/qq/

window.history.replaceState(state, title, url)
// 与 pushState 基本相同，但她是修改当前历史记录，而 pushState 是创建新的历史记录

window.addEventListener("popstate", function() {
    // 监听浏览器前进后退事件，pushState 与 replaceState 方法不会触发              
});
```

### performance相关
window.performance.getEntries()
- 浏览器获取网页时，会对网页中每一个对象（脚本文件、样式表、图片文件等等）发出一个HTTP请求。而通过window.performance.getEntries方法，则可以以数组形式，返回这些请求的时间统计信息，每个数组成员均是一个PerformanceResourceTiming对象！

用它小玩儿一下，统计页面上的静态资源加载耗时：
```
(function () {
    // 浏览器不支持，就算了！
    if (!window.performance && !window.performance.getEntries) {
        return false;
    }

    var result = [];
    // 获取当前页面所有请求对应的PerformanceResourceTiming对象进行分析
    window.performance.getEntries().forEach(function (perf) {
        result.push({
            'url': perf.name,
            'entryType': perf.entryType,
            'type': perf.initiatorType,
            'duration(ms)': perf.duration
        });
    });

    // 控制台输出统计结果
    console.table(result);
})();
```


### 浏览器解析过程

#### 渲染过程中遇到js文件怎么处理？（浏览器解析过程）

   ```
    JavaScript 的加载、解析与执行会阻塞文档的解析，也就是说，在构建 DOM 时，
    HTML 解析器若遇到了 JavaScript，那么它会暂停文档的解析，将控制权移交给 JavaScript 引擎，
    等 JavaScript 引擎运行完毕，浏览器再从中断的地方恢复继续解析文档。

    也就是说，如果你想首屏渲染的越快，就越不应该在首屏就加载 JS 文件，
    这也是都建议将 script 标签放在 body 标签底部的原因。当然在当下，
    并不是说 script 标签必须放在底部，因为你可以给 script 标签添加 defer 或者 async 属性。
   ```

#### async和defer的作用是什么？有什么区别？（浏览器解析过程）

   ```
    （1）脚本没有 defer 或 async，浏览器会立即加载并执行指定的脚本，
        也就是说不等待后续载入的文档元素，读到就加载并执行。

    （2）defer 属性表示延迟执行引入的 JavaScript，即这段 JavaScript 加载时 
    HTML 并未停止解析，这两个过程是并行的。当整个 document 解析完毕后再执行脚本文件，
    在 DOMContentLoaded 事件触发之前完成。多个脚本按顺序执行。

    （3）async 属性表示异步执行引入的 JavaScript，与 defer 的区别在于，
        如果已经加载好，就会开始执行，也就是说它的执行仍然会阻塞文档的解析，
        只是它的加载过程不会阻塞。多个脚本的执行顺序无法保证。
   ```

#### script标签中defer和async的区别
- defer:浏览器指示脚本在文档被解析后执行，script被异步加载后并不会立刻执行，而是等待文档被解析完毕后执 行。
- async:同样是异步加载脚本，区别是脚本加载完毕后立即执行，这导致async属性下的脚本是乱序的，对于 script 有先后依赖关系的情况，并不适用

```
蓝色线代表网络读取，红色线代表执行时间，这俩都是针对脚本的;
绿色线代表 HTML 解析
```

#### 什么是文档的预解析？（浏览器解析过程）

   ```
    Webkit 和 Firefox 都做了这个优化，当执行 JavaScript 脚本时，另一个线程解析
    剩下的文档，并加载后面需要通过网络加载的资源。这种方式可以使资源并行加载从而
    使整体速度更快。需要注意的是，预解析并不改变 DOM 树，它将这个工作留给主解析过程，
    自己只解析外部资源的引用，比如外部脚本、样式表及图片。
   ```

#### css如何阻塞文档解析？（浏览器解析过程）

   ```
    理论上，既然样式表不改变 DOM 树，也就没有必要停下文档的解析等待它们，然而，
    存在一个问题，JavaScript 脚本执行时可能在文档的解析过程中请求样式信息，
    如果样式还没有加载和解析，脚本将得到错误的值，显然这将会导致很多问题。

    所以如果浏览器尚未完成 CSSOM 的下载和构建，而我们却想在此时运行脚本，
    那么浏览器将延迟 JavaScript 脚本执行和文档的解析，直至其完成 CSSOM 的下载和构建。
    也就是说，在这种情况下，浏览器会先下载和构建 CSSOM，然后再执行 JavaScript，
    最后再继续文档的解析。
   ```

### 浏览器渲染过程

#### 渲染机制
#### 1.浏览器的渲染机制一般分为以下几个步骤
- 处理 HTML 并构建 DOM 树。
- 处理 CSS 构建 CSSOM 树。
- 将 DOM 与 CSSOM 合并成一个渲染树。
- 根据渲染树来布局，计算每个节点的位置。
- 调用 GPU 绘制，合成图层，显示在屏幕上
- 在构建 CSSOM 树时，会阻塞渲染，直至 CSSOM 树构建完成。并且构建 CSSOM 树是一个十分消耗性能的过程，所以应该尽量保证层级扁平，减少过度层叠，越是具体的 CSS 选择器，执行速度越慢。
- css 是阻塞渲染的资源。需要将它尽早、尽快地下载到客户端，以便缩短首次渲染的时间
- 当 HTML 解析到 script 标签时，会暂停构建 DOM，完成后才会从暂停的地方重新开始。也就是说，如果你想首屏渲染的越快，就越不应该在首屏就加载 JS 文件。并且 CSS 也会影响 JS 的执行，只有当解析完样式表才会执行 JS，所以也可以认为这种情况下，CSS 也会暂停构建 DOM

#### 2.图层
- 一般来说，可以把普通文档流看成一个图层。特定的属性可以生成一个新的图层。不同的图层渲染互不影响，所以对于某些频繁需要渲染的建议单独生成一个新图层，提高性能。但也不能生成过多的图层，会引起反作用

- 通过以下几个常用属性可以生成新图层
  - 3D变换：translate3d、translateZ
  - will-change
  - video、iframe 标签
  - 通过动画实现的 opacity 动画转换
  - position: fixed

#### 3.重绘与回流
- 当元素的样式发生变化时，浏览器需要触发更新，重新绘制元素。这个过程中，有两种类型的操作，即重绘与回流。

- 重绘(repaint): 当元素样式的改变不影响布局时，浏览器将使用重绘对元素进行更新，此时由于只需要UI层面的重新像素绘制，因此 损耗较少
- 回流(reflow): 当元素的尺寸、结构或触发某些属性时，浏览器会重新渲染页面，称为回流。此时，浏览器需要重新经过计算，计算后还需要重新页面布局，因此是较重的操作。会触发回流的操作:
- 页面初次渲染
- 浏览器窗口大小改变
- 元素尺寸、位置、内容发生改变
- 元素字体大小变化
- 添加或者删除可见的 dom 元素
- 激活 CSS 伪类（例如：:hover）
- 查询某些属性或调用某些方法
  - clientWidth、clientHeight、clientTop、clientLeft
  - offsetWidth、offsetHeight、offsetTop、offsetLeft
  - scrollWidth、scrollHeight、scrollTop、scrollLeft
  - getComputedStyle()
  - getBoundingClientRect()
  - scrollTo()
- 回流必定触发重绘，重绘不一定触发回流。重绘的开销较小，回流的代价较高。

回流的优化
- 对树的局部甚至全局重新生成是非常耗性能的，所以要避免频繁触发回流

- 现代浏览器已经帮我们做了优化，采用队列存储多次的回流操作，然后批量执行，但获取布局信息例外，因为要获取到实时的数值，浏览器就必须要清空队列，立即执行回流。
- 编码上，避免连续多次修改，可通过合并修改，一次触发
- 减少dom的增删次数，可使用 字符串 或者 documentFragment 一次性插入
- 对于大量不同的 dom 修改，可以先将其脱离文档流，比如使用绝对定位，或者 display:none，在文档流外修改完成后再放回文档里中
- 将动画效果应用到position属性为absolute或fixed的元素上
- 动画实现的速度的选择，动画速度越快，回流次数越多，也可以选择使用 requestAnimationFrame
- 通过节流和防抖控制触发频率
- css3 硬件加速，transform、opacity、filters，开启后，会新建渲染层

开启GPU加速的方法
- 开启后，会将 dom元素提升为独立的渲染层，它的变化不会再影响文档流中的布局。

- transform: translateZ(0)
- opacity
- filters
- Will-change

很多人不知道的是，重绘和回流其实和 Event loop 有关
- 当 Event loop 执行完 Microtasks 后，会判断 document 是否需要更新。因为浏览器是 60Hz的刷新率，每 16ms才会更新一次。
- 然后判断是否有 resize 或者 scroll ，有的话会去触发事件，所以 resize 和 scroll 事件也是至少 16ms 才会触发一次，并且自带节流功能。
- 判断是否触发了media query
- 更新动画并且发送事件
- 判断是否有全屏操作事件
- 执行 requestAnimationFrame 回调
- 执行 IntersectionObserver 回调，该方法用于判断元素是否可见，可以用于懒加载上，但是兼容性不好
- 更新界面
- 以上就是一帧中可能会做的事情。如果在一帧中有空闲时间，就会去执行 requestIdleCallback 回调

#### 4.JavaScript会阻塞DOM生成
- JavaScript 会阻塞 DOM生成，而样式文件又会阻塞 JavaScript 的执行，所以在实际的工程中需要重点关注 JavaScript 文件和样式表文件，使用不当会影响到页面性能的

- 当渲染进程接收 HTML 文件字节流时，会先开启一个预解析线程，如果遇到 JavaScript 文件或者 CSS 文件，那么预解析线程会提前下载这些数据

- 如果代码里引用了外部的 CSS 文件，那么在执行 JavaScript 之前，还需要等待外部的 CSS 文件下载完成，并解析生成 CSSOM 对象之后，才能执行 JavaScript 脚本。
- 而 JavaScript 引擎在解析 JavaScript 之前，是不知道 JavaScript 是否操纵了 CSSOM 的，所以渲染引擎在遇到 JavaScript 脚本时，不管该脚本是否操纵了 CSSOM，都会执行 CSS 文件下载，解析操作，再执行 JavaScript 脚本。
- 不管 CSS 文件和 JavaScript 文件谁先到达，都要先等到 CSS 文件下载完成并生成 CSSOM，然后再执行 JavaScript 脚本，最后再继续构建 DOM，构建布局树，绘制页面

#### 5.缩短白屏时长，可以有以下策略
- 通过内联 JavaScript、内联 CSS 来移除这两种类型的文件下载，这样获取到 HTML 文件之后就可以直接开始渲染流程了。
- 但并不是所有的场合都适合内联，那么还可以尽量减少文件大小，比如通过 webpack 等工具移除一些不必要的注释，并压缩 JavaScript 文件。
- 还可以将一些不需要在解析 HTML 阶段使用的 JavaScript 标记上 sync 或者 defer
- 对于大的 CSS 文件，可以通过媒体查询属性，将其拆分为多个不同用途的 CSS 文件，这样只有在特定的场景下才会加载特定的 CSS 文件。

#### 渲染页面时常见哪些不良现象？（浏览器渲染过程）

   ```
    FOUC：主要指的是样式闪烁的问题，由于浏览器渲染机制（比如firefox），在 CSS 加载之前，
          先呈现了 HTML，就会导致展示出无样式内容，然后样式突然呈现的现象。
          会出现这个问题的原因主要是 css 加载时间过长，或者 css 被放在了文档底部。

    白屏：有些浏览器渲染机制（比如chrome）要先构建 DOM 树和 CSSOM 树，构建完成后再进行渲染，
          如果 CSS 部分放在 HTML 尾部，由于 CSS 未加载完成，浏览器迟迟未渲染，从而导致白屏；
          也可能是把 js 文件放在头部，脚本的加载会阻塞后面文档内容的解析，从而页面迟迟未渲染出来，出现白屏问题。
   ```


### 浏览器绘制过程
#### 为什么操作DOM慢？（浏览器绘制过程）

   ```
    一些 DOM 的操作或者属性访问可能会引起页面的回流和重绘，从而引起性能上的消耗。
   ```

#### DOMContentLoaded事件和Load事件的区别

   ```
    当初始的 HTML 文档被完全加载和解析完成之后，DOMContentLoaded 事件被触发，
    而无需等待样式表、图像和子框架的加载完成。

    Load 事件是当所有资源加载完成后触发的。
   ```

### 浏览器缓存
- 我们经常需要对业务中的一些数据进行存储，通常可以分为 短暂性存储 和 持久性储存。

- 短暂性的时候，我们只需要将数据存在内存中，只在运行时可用
- 持久性存储，可以分为 浏览器端 与 服务器端
  - 浏览器:
    - cookie: 通常用于存储用户身份，登录状态等
      - http 中自动携带， 体积上限为 4K， 可自行设置过期时间
    - localStorage / sessionStorage: 长久储存/窗口关闭删除， 体积限制为 4~5M
    - indexDB
  - 服务器:
    - 分布式缓存 redis
    - 数据库
- 提示：如果平常有遇到过缓存的坑或者很好的利用缓存，可以讲解一下自己的使用场景。如果没有使用注意过缓存问题你也可以尝试讲解一下和我们息息相关的Webpack构建（每一次构建静态资源名称的hash值都会变化），它其实就跟缓存相关

- 缓存分为强缓存和协商缓存。强缓存不过服务器，协商缓存需要过服务器，协商缓存返回的状态码是304。两类缓存机制可以同时存在，强缓存的优先级高于协商缓存。当执行强缓存时，如若缓存命中，则直接使用缓存数据库中的数据，不再进行缓存协商。

#### 1.强缓存
- Expires(HTTP1.0)：Exprires的值为服务端返回的数据到期时间。当再次请求时的请求时间小于返回的此时间，则直接使用缓存数据。但由于服务端时间和客户端时间可能有误差，这也将导致缓存命中的误差。另一方面，Expires是HTTP1.0的产物，故现在大多数使用Cache-Control替代

- 缺点：使用的是绝对时间，如果服务端和客户端的时间产生偏差，那么会导致命中缓存产生偏差。

Cache-Control(HTTP1.1)：有很多属性，不同的属性代表的意义也不同
- private：客户端可以缓存
- public：客户端和代理服务器都可以缓存
- max-age=t：缓存内容将在t秒后失效
- no-cache：需要使用协商缓存来验证缓存数据
- no-store：所有内容都不会缓存

- 请注意no-cache指令很多人误以为是不缓存，这是不准确的，no-cache的意思是可以缓存，但每次用应该去向服务器验证缓存是否可用。no-store才是不缓存内容。当在首部字段Cache-Control 有指定 max-age 指令时，比起首部字段 Expires，会优先处理 max-age 指令。命中强缓存的表现形式：Firefox浏览器表现为一个灰色的200状态码。Chrome浏览器状态码表现为200 (from disk cache)或是200 OK (from memory cache)

#### 2.协商缓存
- 协商缓存需要进行对比判断是否可以使用缓存。浏览器第一次请求数据时，服务器会将缓存标识与数据一起响应给客户端，客户端将它们备份至缓存中。再次请求时，客户端会将缓存中的标识发送给服务器，服务器根据此标识判断。若未失效，返回304状态码，浏览器拿到此状态码就可以直接使用缓存数据了

- Last-Modified：服务器在响应请求时，会告诉浏览器资源的最后修改时间
- if-Modified-Since：浏览器再次请求服务器的时候，请求头会包含此字段，后面跟着在缓存中获得的最后修改时间。服务端收到此请求头发现有if-Modified-Since，则与被请求资源的最后修改时间进行对比，如果一致则返回304和响应报文头，浏览器只需要从缓存中获取信息即可
- 如果真的被修改：那么开始传输响应一个整体，服务器返回：200 OK
- 如果没有被修改：那么只需传输响应header，服务器返回：304 Not Modified
- Etag：服务器响应请求时，通过此字段告诉浏览器当前资源在服务器生成的唯一标识（生成规则由服务器决定）
- If-Match：条件请求，携带上一次请求中资源的ETag，服务器根据这个字段判断文件是否有新的修改
- If-None-Match： 再次请求服务器时，浏览器的请求报文头部会包含此字段，后面的值为在缓存中获取的标识。服务器接收到次报文后发现If-None-Match则与被请求资源的唯一标识进行对比。
- 但是实际应用中由于Etag的计算是使用算法来得出的，而算法会占用服务端计算的资源，所有服务端的资源都是宝贵的，所以就很少使用Etag了

- 浏览器地址栏中写入URL，回车浏览器发现缓存中有这个文件了，不用继续请求了，直接去缓存拿（最快）
- F5就是告诉浏览器，别偷懒，好歹去服务器看看这个文件是否有过期了。于是浏览器就胆胆襟襟的发送一个请求带上If-Modify-since
- Ctrl+F5告诉浏览器，你先把你缓存中的这个文件给我删了，然后再去服务器请求个完整的资源文件下来。于是客户端就完成了强行更新的操作

#### 3.缓存场景
- 对于大部分的场景都可以使用强缓存配合协商缓存解决，但是在一些特殊的地方可能需要选择特殊的缓存策

- 对于某些不需要缓存的资源，可以使用 Cache-control: no-store ，表示该资源不需要缓存
- 对于频繁变动的资源，可以使用 Cache-Control: no-cache 并配合 ETag 使用，表示该资源已被缓存，但是每次都会发送请求询问资源是否更新
- 对于代码文件来说，通常使用 Cache-Control: max-age=31536000 并配合策略缓存使用，然后对文件进行指纹处理，一旦文件名变动就会立刻下载新的文件

#### 4.讲讲304
- 如果客户端发送了一个带条件的 GET 请求且该请求已被允许，而文档的内容(自 上次访问以来或者根据请求的条件)并没有改变，则服务器应当返回这个 304 状态码

#### 5.强缓存、协商缓存什么时候用哪个
- 因为服务器上的资源不是一直固定不变的，大多数情况下它会更新，这个时候如果我们 还访问本地缓存，那么对用户来说，那就相当于资源没有更新，用户看到的还是旧的资 源;所以我们希望服务器上的资源更新了浏览器就请求新的资源，没有更新就使用本地 的缓存，以最大程度的减少因网络请求而产生的资源浪费。

#### 6.缓存总结
- 缓存分为两种:强缓存和协商缓存，根据响应的 header 内容来决定。
```
           获取资源形式          状态码	           发送请求到服务器
强缓存	   从缓存取       200(from cache)	   否，直接从缓存取
协商缓存	  从缓存取	     304(not modified)    是，通过服务器来告知缓存是否可用
```
- 强缓存相关字段有 expires，cache-control。如果 cache-control 与 expires 同时存在的话， cache-control 的优先级高于 expires。
- 协商缓存相关字段有 Last-Modified/If-Modified-Since，Etag/If-None-Match

#### 7.cookie和localSrorage、session、indexDB的区别
```
特性	                cookie	                             localStorage         sessionStorage	indexDB
数据生命周期	  一般由服务器生成，可以设置过期时间	       除非被清理，否则一直存在	页面关闭就清理	   除非被清理，否则一直存在
数据存储大小	              4K	                             5M                           5M	     无限
与服务端通信	  每次都会携带在 header 中，对于请求性能影响	      不参与	                不参与	  不参与
```
- 从上表可以看到，cookie 已经不建议用于存储。如果没有大量数据存储需求的话，可以使用 localStorage和 sessionStorage 。对于不怎么改变的数据尽量使用 localStorage 存储，否则可以用 sessionStorage 存储。

对于 cookie，我们还需要注意安全性
```
 属性	               作用
value	      如果用于保存用户登录态，应该将该值加密，不能使用明文的用户标识
http-only     不能通过 JS访问 Cookie，减少 XSS攻击
secure	      只能在协议为 HTTPS 的请求中携带
same-site     规定浏览器不能在跨域请求中携带 Cookie，减少 CSRF 攻击
```

### 跨域
- 因为浏览器出于安全考虑，有同源策略。也就是说，如果协议、域名或者端口有一个不同就是跨域，Ajax请求会失败。

我们可以通过以下几种常用方法解决跨域的问题

#### JSONP
- JSONP 的原理很简单，就是利用 <script>标签没有跨域限制的漏洞。通过 <script>标签指向一个需要访问的地址并提供一个回调函数来接收数据当需要通讯时
```
<script src="http://domain/api?param1=a&param2=b&callback=jsonp"></script>
<script>
    function jsonp(data) {
    	console.log(data)
	}
</script>    
```
JSONP 使用简单且兼容性不错，但是只限于 get 请求
- 在开发中可能会遇到多个 JSONP 请求的回调函数名是相同的，这时候就需要自己封装一个 JSONP，以下是简单实现
```
function jsonp(url, jsonpCallback, success) {
  let script = document.createElement("script");
  script.src = url;
  script.async = true;
  script.type = "text/javascript";
  window[jsonpCallback] = function(data) {
    success && success(data);
  };
  document.body.appendChild(script);
}
jsonp(
  "http://xxx",
  "callback",
  function(value) {
    console.log(value);
  }
);
```
	
#### CORS
- CORS需要浏览器和后端同时支持。IE 8 和 9 需要通过 XDomainRequest 来实现。
- 浏览器会自动进行 CORS 通信，实现CORS通信的关键是后端。只要后端实现了 CORS，就实现了跨域。
- 服务端设置 Access-Control-Allow-Origin 就可以开启 CORS。 该属性表示哪些域名可以访问资源，如果设置通配符则表示所有网站都可以访问资源。

#### document.domain
- 该方式只能用于二级域名相同的情况下，比如 a.test.com 和 b.test.com 适用于该方式。
- 只需要给页面添加 document.domain = 'test.com' 表示二级域名都相同就可以实现跨域

#### postMessage
- 这种方式通常用于获取嵌入页面中的第三方页面数据。一个页面发送消息，另一个页面判断来源并接收消息
```
// 发送消息端
window.parent.postMessage('message', 'http://test.com');
// 接收消息端
var mc = new MessageChannel();
mc.addEventListener('message', (event) => {
    var origin = event.origin || event.originalEvent.origin;
    if (origin === 'http://test.com') {
        console.log('验证通过')
    }
});
```

### 网页验证码是干嘛的，是为了解决什么安全问题

   ```
    （1）区分用户是计算机还是人的公共全自动程序。可以防止恶意破解密码、刷票、论坛灌水
    （2）有效防止黑客对某一个特定注册用户用特定程序暴力破解方式进行不断的登陆尝试
   ```  

### 扫描二维码登录网页是什么原理，前后两个事件是如何联系的
   ```
    核心过程应该是：浏览器获得一个临时 id，通过长连接等待客户端扫描带有此 id 的二维码后，
    从长连接中获得客户端上报给 server的帐号信息进行展示。并在客户端点击确认后，
    获得服务器授信的令牌，进行随后的信息交互过程。在超时、网络断开、其他设备上登录后，
    此前获得的令牌或丢失、或失效，对授权过程形成有效的安全防护。

    我的理解：
    二维码登录网页的基本原理是，用户进入登录网页后，服务器生成一个 uid 来标识一个用户。
    对应的二维码对应了一个对应 uid 的链接，任何能够识别二维码的应用都可以获得这个链接，
    但是它们没有办法和对应登录的服务器响应。比如微信的二维码登录，只有用微信识这个二维码才有效。
    当微信客户端打开这个链接时，对应的登录服务器就获得了用户的相关信息。这个时候登录网页
    根据先前的长连接获取到服务器传过来的用户信息进行显示。然后提前预加载一些登录后可能用到的信息。
    当客户端点击确认授权登陆后，服务器生成一个权限令牌给网页，网页之后使用这个令牌进行信息的交互过程。
    由于整个授权的过程都是在手机端进行的，因此能够很好的防止 PC 上泛滥的病毒。并且在超时、
    网络断开、其他设备上登录后，此前获得的令牌或丢失、或失效，对授权过程能够形成有效的安全防护。
   ```

### SGML、HTML、XML 和 XHTML 的区别

   ```
   SGML 是标准通用标记语言，是一种定义电子文档结构和描述其内容的国际标准语言，是所有电子文档标记语言的起源。
   
   HTML 是超文本标记语言，主要是用于规定怎么显示网页。
   
   XML 是可扩展标记语言是未来网页语言的发展方向，XML 和 HTML 的最大区别就在于 
   XML 的标签是可以自己创建的，数量无限多，而 HTML 的标签都是固定的而且数量有限。
   
   XHTML 也是现在基本上所有网页都在用的标记语言，他其实和 HTML 没什么本质的区别，标签都一样，
   用法也都一样，就是比 HTML 更严格，比如标签必须都用小写，标签都必须有闭合标签等。
   ```

xhtml和html有什么区别：
```
一个是功能上的差别：
主要是XHTML可兼容各大浏览器、手机以及PDA，并且浏览器也能快速正确地编译网页

另外是书写习惯的差别：
XHTML 元素必须被正确地嵌套，闭合，区分大小写，文档必须拥有根元素
```

### DHTML 是什么

   ```
    DHTML 将 HTML、JavaScript、DOM 以及 CSS 组合在一起，用于创造动态性更强的网页。
    通过 JavaScript 和 HTML DOM，能够动态地改变 HTML 元素的样式。

    DHTML 实现了网页从 Web 服务器下载后无需再经过服务的处理，而在浏览器中直接动态地更新网页的内容、
    排版样式和动画的功能。例如，当鼠标指针移到文章段落中时，段落能够变成蓝色，
    或者当鼠标指针移到一个超级链接上时，会自动生成一个下拉式子链接目录等。

    包括：
    （1）动态内容（Dynamic Content）：动态地更新网页内容，可“动态”地插入、修改或删除网页的元件，如文字、图像、标记等。
    （2）动态排版样式（Dynamic Style Sheets）：W3C 的 CSS 样式表提供了设定 HTML 标记的字体大小、
        字形、样式、粗细、文字颜色、行高度、加底线或加中间横线、缩排、与边缘距离、靠左右或置中、
        背景图片或颜色等排版功能，而“动态排版样式”即可以“动态”地改变排版样式。
   ```

### DOCTYPE、标准模式与兼容模式、DTD

Doctype作用? 严格模式与混杂模式如何区分？它们有何意义?
```
<!DOCTYPE> 声明位于文档中的最前面，处于 <html> 标签之前。
告知浏览器的解析器， 用什么文档类型规范来解析这个文档

严格模式的排版和 JS 运作模式是以该浏览器支持的最高标准运行

在混杂模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。
DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现
```

#### DOCTYPE 的作用是什么
   
   ```
   <!DOCTYPE>  声明一般位于文档的第一行，它的作用主要是告诉浏览器以什么样的模式来解析文档。一般指定了之后会
   以标准模式来进行文档解析，否则就以兼容模式进行解析。在标准模式下，浏览器的解析规则都是按照最新的标准进行解析的。
   而在兼容模式下，浏览器会以向后兼容的方式来模拟老式浏览器的行为，以保证一些老的网站的正确访问。

   在 html5 之后不再需要指定 DTD 文档，因为 html5 以前的 html 文档都是基于 SGML 的，所以需要通过
   指定 DTD 来定义文档中允许的属性以及一些规则。而 html5 不再基于 SGML 了，所以不再需要使用 DTD。
   ```

   ```
   IE5.5 引入了文档模式的概念，而这个概念是通过使用文档类型（DOCTYPE）切换实现的。

   <!DOCTYPE>声明位于 HTML 文档中的第一行，处于 <html> 标签之前。告知浏览器的解析器用什么文档标准解析这个文档。

   DOCTYPE 不存在或格式不正确会导致文档以兼容模式呈现。
   ```

#### 标准模式与兼容模式各有什么区别
   ``` 
   标准模式的渲染方式和 JS 引擎的解析方式都是以该浏览器支持的最高标准运行。
   在兼容模式中，页面以宽松的向后兼容的方式显示，模拟老式浏览器的行为以防止站点无法工作。
   ```
   
#### DTD
   ```
   DTD（ Document Type Definition 文档类型定义）是一组机器可读的规则，它们定义 XML 或 HTML 的特定版本中
   所有允许元素及它们的属性和层次关系的定义。在解析网页时，浏览器将使用这些规则检查页面的有效性并且采取相应的措施。
   
   DTD 是对 HTML 文档的声明，还会影响浏览器的渲染模式（工作模式）。
   ```

#### HTML5 为什么只需要写 `<!DOCTYPE HTML>`，而不需要引入 DTD
   ```
   HTML5 不基于 SGML，因此不需要对 DTD 进行引用，但是需要 DOCTYPE 来规范浏览器的行为（让浏览器按照它们应该的方式来运行）。
   
   而 HTML4.01 基于 SGML ，所以需要对 DTD 进行引用，才能告知浏览器文档所使用的文档类型。
   ```

### 页面导入样式时，使用 link 和 @import 有什么区别

   ```
   （1）从属关系区别。 @import 是 CSS 提供的语法规则，只有导入样式表的作用；
   link 是 HTML 提供的标签，不仅可以加载 CSS 文件，还可以定义 RSS、rel 连接属性、引入网站图标等。
   （2）加载顺序区别。加载页面时，link 标签引入的 CSS 被同时加载；@import 引入的 CSS 将在页面加载完毕后被加载。
   （3）兼容性区别。@import 是 CSS2.1 才有的语法，故只可在 IE5+ 才能识别；
   link 标签作为 HTML 元素，不存在兼容性问题。
   （4）DOM 可控性区别。可以通过 JS 操作 DOM ，插入 link 标签来改变样式；
   由于 DOM 方法是基于文档的，无法使用 @import 的方式插入样式。
   ```
   
```
link是HTML方式， @import是CSS方式
link最大限度支持并行下载，@import过多嵌套导致串行下载，出现FOUC(文档样式短暂失效)
link可以通过rel="alternate stylesheet"指定候选样式
浏览器对link支持早于@import，可以使用@import对老浏览器隐藏样式
@import必须在样式规则之前，可以在css文件中引用其他文件
总体来说：link优于@import
```

#### link标签定义
   ```
   link 标签定义文档与外部资源的关系。
   link 元素是空元素，它仅包含属性。 此元素只能存在于 head 部分，不过它可出现任何次数。
   link 标签中的 rel 属性定义了当前文档与被链接文档之间的关系。常见的 stylesheet 指的是定义一个外部加载的样式表。
   ```

### head标签中必不可少的是

   ```
    <head> 标签用于定义文档的头部，它是所有头部元素的容器。<head> 中的元素可以引用脚本、指示浏览器在哪里找到样式表、提供
    元信息等等。

    文档的头部描述了文档的各种属性和信息，包括文档的标题、在 Web 中的位置以及和其他文档的关系等。绝大多数文档头部包含的数
    据都不会真正作为内容显示给读者。

    下面这些标签可用在 head 部分：<base>, <link>, <meta>, <script>, <style>, 以及 <title>。

    <title> 定义文档的标题，它是 head 部分中唯一必需的元素。
   ``` 

#### 常用的meta标签
   ```
    <meta> 元素可提供有关页面的元信息（meta-information），比如针对搜索引擎和更新频度的描述和关键词。
    <meta> 标签位于文档的头部，不包含任何内容。<meta> 标签的属性定义了与文档相关联的名称/值对。

    <!DOCTYPE html>  H5标准声明，使用 HTML5 doctype，不区分大小写
    <head lang=”en”> 标准的 lang 属性写法
    <meta charset=’utf-8′>    声明文档使用的字符编码
    <meta http-equiv=”X-UA-Compatible” content=”IE=edge,chrome=1″/>   优先使用 IE 最新版本和 Chrome
    <meta name=”description” content=”不超过150个字符”/>       页面描述
    <meta name=”keywords” content=””/>      页面关键词者
    <meta name=”author” content=”name, email@gmail.com”/>    网页作者
    <meta name=”robots” content=”index,follow”/>      搜索引擎抓取
    <meta name=”viewport” content=”initial-scale=1, maximum-scale=3, minimum-scale=1, user-scalable=no”> 为移动设备添加 viewport
    <meta name=”apple-mobile-web-app-title” content=”标题”> iOS 设备 begin
    <meta name=”apple-mobile-web-app-capable” content=”yes”/>  添加到主屏后的标题（iOS 6 新增）
    是否启用 WebApp 全屏模式，删除苹果默认的工具栏和菜单栏
    <meta name=”apple-itunes-app” content=”app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL”>
    添加智能 App 广告条 Smart App Banner（iOS 6+ Safari）
    <meta name=”apple-mobile-web-app-status-bar-style” content=”black”/>
    <meta name=”format-detection” content=”telphone=no, email=no”/>  设置苹果工具栏颜色
    <meta name=”renderer” content=”webkit”>  启用360浏览器的极速模式(webkit)
    <meta http-equiv=”X-UA-Compatible” content=”IE=edge”>     避免IE使用兼容模式
    <meta http-equiv=”Cache-Control” content=”no-siteapp” />    不让百度转码
    <meta name=”HandheldFriendly” content=”true”>     针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓
    <meta name=”MobileOptimized” content=”320″>   微软的老式浏览器
    <meta name=”screen-orientation” content=”portrait”>   uc强制竖屏
    <meta name=”x5-orientation” content=”portrait”>    QQ强制竖屏
    <meta name=”full-screen” content=”yes”>              UC强制全屏
    <meta name=”x5-fullscreen” content=”true”>       QQ强制全屏
    <meta name=”browsermode” content=”application”>   UC应用模式
    <meta name=”x5-page-mode” content=”app”>    QQ应用模式
    <meta name=”msapplication-tap-highlight” content=”no”>    windows phone 点击无高光
    设置页面不缓存
    <meta http-equiv=”pragma” content=”no-cache”>
    <meta http-equiv=”cache-control” content=”no-cache”>
    <meta http-equiv=”expires” content=”0″>
   ```

#### viewport
```
 <meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no" />
    // width    设置viewport宽度，为一个正整数，或字符串‘device-width’
    // device-width  设备宽度
    // height   设置viewport高度，一般设置了宽度，会自动解析出高度，可以不用设置
    // initial-scale    默认缩放比例（初始缩放比例），为一个数字，可以带小数
    // minimum-scale    允许用户最小缩放比例，为一个数字，可以带小数
    // maximum-scale    允许用户最大缩放比例，为一个数字，可以带小数
    // user-scalable    是否允许手动缩放
```

```
<meta name="viewport" content="width=500, initial-scale=1">
```
- width：页面宽度，可以取值具体的数字，也可以是 device-width，表示跟设备宽度相等。
- height：页面高度，可以取值具体的数字，也可以是 device-height，表示跟设备高度相等。
- initial-scale：初始缩放比例。
- minimum-scale：最小缩放比例。
- maximum-scale：最大缩放比例。
- user-scalable：是否允许用户缩放。

#### 延伸提问：怎样处理移动端 1px 被渲染成 2px 问题
```
局部处理：
meta标签中的 viewport属性 ，initial-scale 设置为 1
rem按照设计稿标准走，外加利用transfrome 的scale(0.5) 缩小一倍即可；

全局处理：
mate标签中的 viewport属性 ，initial-scale 设置为 0.5
rem 按照设计稿标准走即可
```

### 用于预格式化文本的标签是
   ```
    预格式化就是保留文字在源码中的格式，最后显示出来样式与源码中的样式一致，所见即所得。

    <pre> 定义预格式文本，保持文本原有的格式
   ```

### iframe有哪些缺点
   ```
    iframe 元素会创建包含另外一个文档的内联框架（即行内框架）。

    主要缺点有：
    （1）iframe 会阻塞主页面的 onload 事件。window 的 onload 事件需要
        在所有 iframe 加载完毕后（包含里面的元素）才会触发。在 Safari 和 Chrome 里，
        通过 JavaScript 动态设置 iframe 的 src 可以避免这种阻塞情况。
    （2） 搜索引擎的检索程序无法解读这种页面，不利于网页的 SEO 。
    （3） iframe 和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。
    （4） 浏览器的后退按钮失效。
    （5） 小型的移动设备无法完全显示框架。
   ```

- iframe会阻塞主页面的Onload事件；
- 搜索引擎的检索程序无法解读这种页面，不利于SEO;
- iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。
- 使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
- 动态给iframe添加src属性值，这样可以绕开以上两个问题

### label的作用是什么？是怎么用的
   ```
    label 标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。

    <label for="Name">Number:</label>
    <input type=“text“ name="Name" id="Name"/>
   ```

### html5的form的自动完成功能是什么
   ```
    autocomplete 属性规定输入字段是否应该启用自动完成功能。
    默认为启用，设置为 autocomplete=off 可以关闭该功能。

    自动完成允许浏览器预测对字段的输入。当用户在字段开始键入时，
    浏览器基于之前键入过的值，应该显示出在字段中填写的选项。

    autocomplete 属性适用于 <form>，以及下面的 <input> 类型：text, search, 
    url, telephone, email, password, datepickers, range 以及 color。
   ```

### title与h1的区别
   ```
    title 属性没有明确意义只表示是个标题，
    h1 则表示层次明确的标题，对页面信息的抓取也有很大的影响。
   ```

### b与strong的区别、i与em的区别
   ```
    从页面显示效果来看，被 <b> 和 <strong> 包围的文字将会被加粗，
    而被 <i> 和 <em> 包围的文字将以斜体的形式呈现。

    但是 <b> <i> 是自然样式标签，分别表示无意义的加粗，无意义的斜体，
    表现样式为 { font-weight: bolder}，仅仅表示「这里应该用粗体显示」
    或者「这里应该用斜体显示」，此两个标签在 HTML4.01 中并不被推荐使用。

    而 <em> 和 <strong> 是语义样式标签。 
    <em> 表示一般的强调文本，而 <strong> 表示比 <em> 语义更强的强调文本。
    
    使用阅读设备阅读网页时：<strong> 会重读，而 <b> 是展示强调内容。
   ``` 

### img的title和alt有什么区别
   ```
    title 通常当鼠标滑动到元素上的时候显示

    alt 是 <img> 的特有属性，是图片内容的等价描述，用于图片无法加载时显示、读屏器阅读图片。
    可提图片高可访问性，除了纯装饰图片外都必须设置有意义的值，搜索引擎会重点分析。
   ```

```
alt(alt text):为不能显示图像、窗体或applets的用户代理（UA），alt属性用来指定替换文字。
替换文字的语言由lang属性指定。(在IE浏览器下会在没有title时把alt当成 tool tip显示)

title(tool tip):该属性为设置该属性的元素提供建议性的信息
```

### Canvas和SVG有什么区别
   ```
    Canvas 是一种通过 JavaScript 来绘制 2D 图形的方法。Canvas 是逐像素来进行渲染的，
    因此当我们对 Canvas 进行缩放时，会出现锯齿或者失真的情况。
    
    SVG 是一种使用 XML 描述 2D 图形的语言。SVG 基于 XML，这意味着 SVG DOM 中的
    每个元素都是可用的。我们可以为某个元素附加 JavaScript 事件监听函数。
    并且 SVG 保存的是图形的绘制方法，因此当 SVG 图形缩放时并不会失真。
   ```

```
svg绘制出来的每一个图形的元素都是独立的DOM节点，能够方便的绑定事件或用来修改。
canvas输出的是一整幅画布

svg输出的图形是矢量图形，后期可以修改参数来自由放大缩小，不会失真和锯齿。
而canvas输出标量画布，就像一张图片一样，放大会失真或者锯齿
```

### src与href的区别

```
src用于替换当前元素，href用于在当前文档和引用资源之间确立联系。
src是source的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；
在请求src资源时会将其指向的资源下载并应用到文档内，例如js脚本，img图片和frame等元素
<script src ="js.js"></script> 当浏览器解析到该元素时，会暂停其他资源的下载和处理，
直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源
嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部

href是Hypertext Reference的缩写，指向网络资源所在位置，建立和当前元素（锚点）
或当前文档（链接）之间的链接，如果我们在文档中添加
<link href="common.css" rel="stylesheet"/>那么浏览器会识别该文档为css文件，
就会并行下载资源并且不会停止对当前文档的处理。
这也是为什么建议使用link方式来加载css，而不是使用@import方式
```

- src用于替换当前元素，href用于在当前文档和引用资源之间确立联系。
- src是source的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将其指向的资源下载并应用到文档内，例如js脚本，img图片和frame等元素
```
<script src =”js.js”></script>
```

```
当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将
该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于
将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部
而不是头部
```
- href是Hypertext Reference的缩写，指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，如果我们在文档中添加
```
<link href=”common.css” rel=”stylesheet”/>
```
```
那么浏览器会识别该文档为css文件，就会并行下载资源并且不会
停止对当前文档的处理。这也是为什么建议使用link方式来加载css，
而不是使用@import方式。
```

### disabled和readonly的区别
   ```
    disabled 指当 input 元素加载时禁用此元素。input 内容不会随着表单提交。
     
    readonly 规定输入字段为只读。input 内容会随着表单提交。

    无论设置 readonly 还是 disabled，通过 js 脚本都能更改 input 的 value
   ```  

### attribute和property的区别
   ```
    attribute 是 dom 元素在文档中作为 html 标签拥有的属性；
    property 就是 dom 元素在 js 中作为对象拥有的属性。
    对于 html 的标准属性来说，attribute 和 property 是同步的，是会自动更新的，
    但是对于自定义的属性来说，他们是不同步的。
   ```

### css reset和normalize.css有什么区别

   ```
    css reset 是最早的一种解决浏览器间样式不兼容问题的方案，它的基本思想是
    将浏览器的所有样式都重置掉，从而达到所有浏览器样式保持一致的效果。
    但是使用这种方法，可能会带来一些性能上的问题，并且对于一些元素的
    不必要的样式的重置，其实反而会造成画蛇添足的效果。

    后面出现一种更好的解决浏览器间样式不兼容的方法，就是 normalize.css ，
    它的思想是尽量的保留浏览器自带的样式，通过在原有的样式的基础上进行调整，
    来保持各个浏览器间的样式表现一致。相对与 css reset，
    normalize.css 的方法保留了有价值的默认值，并且修复了一些浏览器的 bug，
    而且使用 normalize.css 不会造成元素复杂的继承链。
   ```
   
   ```
    为什么会有 CSS Reset 的存在呢？那是因为早期的浏览器支持和理解的 CSS 规范不同，
    导致渲染页面时效果不一致，会出现很多兼容性问题。

    reset 的目的，是将所有的浏览器的自带样式重置掉，这样更易于保持各浏览器渲染的一致性。

    normalize 的理念则是尽量保留浏览器的默认样式，不进行太多的重置，
    而尽力让这些样式保持一致并尽可能与现代标准相符合。

    1.Normalize.css 保护了有价值的默认值
    Reset 通过为几乎所有的元素施加默认样式，强行使得元素有相同的视觉效果。 
    相比之下，Normalize.css 保持了许多默认的浏览器样式。 这就意味着
    你不用再为所有公共的排版元素重新设置样式。当一个元素在不同的浏览器中有不同的默认值时，
    Normalize.css 会力求让这些样式保持一致并尽可能与现代标准相符合。

    2.Normalize.css 修复了浏览器的 bug
    它修复了常见的桌面端和移动端浏览器的 bug。这往往超出了 Reset 所能做到的范畴。
    关于这一点，Normalize.css 修复的问题包含了 HTML5 元素的显示设置、预格式化文字的 font-size 问题、
    在 IE9 中 SVG 的溢出、许多出现在各浏览器和操作系统中的与表单相关的 bug。

    3.Normalize.css 没有复杂的继承链
    使用 Reset 最让人困扰的地方莫过于在浏览器调试工具中大段大段的继承链。
    在 Normalize.css 中就不会有这样的问题，因为在我们的准则中对多选择器的使用时非常谨慎的，
    我们仅会有目的地对目标元素设置样式。

    4.Normalize.css 是模块化的
    这个项目已经被拆分为多个相关却又独立的部分，这使得你能够很容易也很清楚地知道
    哪些元素被设置了特定的值。因此这能让你自己选择性地移除掉某些永远不会用到部分（比如表单的一般化）。

    5.Normalize.css 拥有详细的文档
    Normalize.css 的代码基于详细而全面的跨浏览器研究与测试。这个文件中拥有详细的代码说明
    并在 Github Wiki 中有进一步的说明。这意味着你可以找到每一行代码具体完成了什么工作、
    为什么要写这句代码、浏览器之间的差异，并且你可以更容易地进行自己的测试。
   ```

### div+css的布局较table布局有什么优点

```
改版的时候更方便，只要改css文件。
页面加载速度更快、结构化清晰、页面显示简洁。
表现与结构相分离。
易于优化（seo）搜索引擎更友好，排名更容易靠前。
```

### http

#### http的几种请求方法用途

```
GET方法：发送一个请求来取得服务器上的某一资源

POST方法：向URL指定的资源提交数据或附加新的数据

PUT方法：跟POST方法很像，也是向服务器提交数据。但是，它们之间有不同。PUT指定了资源在服务器上的位置，而POST没有

HEAD方法：只请求页面的首部

DELETE方法：删除服务器上的某资源

OPTIONS方法：它用于获取当前URL所支持的方法。如果请求成功，会有一个Allow的头包含类似“GET,POST”这样的信息

TRACE方法：TRACE方法被用于激发一个远程的，应用层的请求消息回路

CONNECT方法：把请求连接转换到透明的TCP/IP通道
```

#### http状态码及其含义

```
1XX：信息状态码
  100 Continue 继续，一般在发送post请求时，已发送了http header之后服务端将返回此信息，
  表示确认，之后发送具体参数信息
  101	Switching Protocols	切换协议。服务器根据客户端的请求切换协议。
  只能切换到更高级的协议，例如，切换到HTTP的新版本协议
  
2XX：成功状态码
  200 OK 正常返回信息
  201 Created 请求成功并且服务器创建了新的资源
  202 Accepted 服务器已接受请求，但尚未处理
  203	Non-Authoritative Information	非授权信息。请求成功。
  但返回的meta信息不在原始的服务器，而是一个副本
  204	No Content	无内容。服务器成功处理，但未返回内容。
  在未更新网页的情况下，可确保浏览器继续显示当前文档
  205	Reset Content	重置内容。服务器处理成功，
  用户终端（例如：浏览器）应重置文档视图。可通过此返回码清除浏览器的表单域
  206	Partial Content	部分内容。服务器成功处理了部分GET请求

3XX：重定向
  300	Multiple Choices	多种选择。请求的资源可包括多个位置，
  相应可返回一个资源特征与地址的列表用于用户终端（例如：浏览器）选择
  301 Moved Permanently 请求的网页已永久移动到新位置。
  302 Found 临时性重定向。
  303 See Other 临时性重定向，且总是使用 GET 请求新的 URI。
  304 Not Modified 自从上次请求后，请求的网页未修改过。
  305	Use Proxy	使用代理。所请求的资源必须通过代理访问
  306	Unused	已经被废弃的HTTP状态码
  307	Temporary Redirect	临时重定向。与302类似。使用GET请求重定向

4XX：客户端错误
  400 Bad Request 服务器无法理解请求的格式，客户端不应当尝试再次使用相同的内容发起请求。
  401 Unauthorized 请求未授权。
  402	Payment Required	保留，将来使用
  403 Forbidden 禁止访问。
  404 Not Found 找不到如何与 URI 相匹配的资源。
  405	Method Not Allowed	客户端请求中的方法被禁止
  406	Not Acceptable	服务器无法根据客户端请求的内容特性完成请求
  407	Proxy Authentication Required	请求要求代理的身份认证，与401类似
  408	Request Time-out	服务器等待客户端发送的请求时间过长，超时
  409	Conflict	服务器完成客户端的PUT请求是可能返回此代码，服务器处理请求时发生了冲突
  410	Gone	客户端请求的资源已经不存在。410不同于404，如果资源以前有现在被永久删除了
  可使用410代码，网站设计人员可通过301代码指定资源的新位置
  411	Length Required	服务器无法处理客户端发送的不带Content-Length的请求信息
  412	Precondition Failed	客户端请求信息的先决条件错误
  413	Request Entity Too Large	由于请求的实体过大，服务器无法处理，因此拒绝请求。
  为防止客户端的连续请求，服务器可能会关闭连接。如果只是服务器暂时无法处理，则会包含一个Retry-After的响应信息
  414	Request-URI Too Large	请求的URI过长（URI通常为网址），服务器无法处理
  415	Unsupported Media Type	服务器无法处理请求附带的媒体格式
  416	Requested range not satisfiable	客户端请求的范围无效
  417	Expectation Failed	服务器无法满足Expect的请求头信息

5XX: 服务器错误
  500 Internal Server Error 最常见的服务器端错误。
  501	Not Implemented	服务器不支持请求的功能，无法完成请求
  502	Bad Gateway	充当网关或代理的服务器，从远端服务器接收到了一个无效的请求
  503 Service Unavailable 服务器端暂时无法处理请求（可能是过载或维护）。
  504	Gateway Time-out	充当网关或代理的服务器，未及时从远端服务器获取请求
  505	HTTP Version not supported	服务器不支持请求的HTTP协议的版本，无法完成处理
```

#### html规范中为什么要求引用资源不加协议头http或者https

   ```
    如果用户当前访问的页面是通过 HTTPS 协议来浏览的，那么网页中的资源也只能
    通过 HTTPS 协议来引用，否则浏览器会出现警告信息，不同浏览器警告信息展现形式不同。

    为了解决这个问题，我们可以省略 URL 的协议声明，省略后浏览器照样可以正常引用相应的资源，
    这项解决方案称为protocol-relative URL，暂且可译作协议相对 URL。

    如果使用协议相对 URL，无论是使用 HTTPS，还是 HTTP 访问页面，浏览器都会
    以相同的协议请求页面中的资源，避免弹出类似的警告信息，同时还可以节省5字节的数据量。
   ```

#### HTTP request报文结构是怎样的

```
1.首行是Request-Line包括：请求方法，请求URI，协议版本，CRLF(Carriage-Return Line-Feed的缩写，意思是回车换行)
2.首行之后是若干行请求头，包括general-header，request-header或者entity-header，每个一行以CRLF结束
3.请求头和消息实体之间有一个CRLF分隔
4.根据实际请求需要可能包含一个消息实体 一个请求报文例子如下：
GET /Protocols/rfc2616/rfc2616-sec5.html HTTP/1.1
Host: www.w3.org
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.153 Safari/537.36
Referer: https://www.google.com.hk/
Accept-Encoding: gzip,deflate,sdch
Accept-Language: zh-CN,zh;q=0.8,en;q=0.6
Cookie: authorstyle=yes
If-None-Match: "2cc8-3e3073913b100"
If-Modified-Since: Wed, 01 Sep 2004 13:24:52 GMT

name=qiu&age=6
```

#### HTTP response报文结构是怎样的

```
1.首行是状态行包括：HTTP版本，状态码，状态描述，后面跟一个CRLF
2.首行之后是若干行响应头，包括：通用头部，响应头部，实体头部
3.响应头部和响应实体之间用一个CRLF空行分隔
4.最后是一个可能的消息实体 响应报文例子如下：
HTTP/1.1 200 OK
Date: Tue, 08 Jul 2014 05:28:43 GMT
Server: Apache/2
Last-Modified: Wed, 01 Sep 2004 13:24:52 GMT
ETag: "40d7-3e3073913b100"
Accept-Ranges: bytes
Content-Length: 16599
Cache-Control: max-age=21600
Expires: Tue, 08 Jul 2014 11:28:43 GMT
P3P: policyref="http://www.w3.org/2001/05/P3P/p3p.xml"
Content-Type: text/html; charset=iso-8859-1

{"name": "qiu", "age": 6}
```

### 对web标准 可用性、可访问性的理解

   ```
    可用性（Usability）：产品是否容易上手，用户能否完成任务，效率如何，
    以及这过程中用户的主观感受可好，是从用户的角度来看产品的质量。
    可用性好意味着产品质量高，是企业的核心竞争力

    可访问性（Accessibility）：Web 内容对于残障用户的可阅读和可理解性
    
    可维护性（Maintainability）：一般包含两个层次，
    一是当系统出现问题时，快速定位并解决问题的成本，成本低则可维护性好。
    二是代码是否容易被人理解，是否容易修改和增强功能。
   ```

### WEB标准以及W3C标准是什么
```
标签闭合、标签小写、不乱嵌套、使用外链css和js、结构行为表现的分离
```

### web开发中会话跟踪的方法有哪些

```
cookie
session
url重写
隐藏input
ip地址
```

### IE各版本和Chrome可以并行下载多少个资源

   ```
    （1）  IE6 2 个并发
    （2）  iE7 升级之后的 6 个并发，之后版本也是 6 个
    （3）  Firefox，chrome 也是6个
   ```

### Chrome中的Waterfall
详细资料可以参考：
   [《前端性能之 Chrome 的 Waterfall》](https://blog.csdn.net/carian_violet/article/details/84954360)
   [《教你读懂网络请求的瀑布图》](https://blog.csdn.net/csdn_girl/article/details/54911632)

### webSocket如何兼容低版本浏览器

   ```
    Adobe Flash Socket 、
    ActiveX HTMLFile (IE) 、
    基于 multipart 编码发送 XHR 、
    基于长轮询的 XHR
   ```

### Flash、Ajax各自的优缺点，在使用中如何取舍

   ```
    Flash：
    （1） Flash 适合处理多媒体、矢量图形、访问机器
    （2） 对 CSS、处理文本上不足，不容易被搜索

    Ajax：
    （1） Ajax 对 CSS、文本支持很好，支持搜索
    （2） 多媒体、矢量图形、机器访问不足

    共同点：
    （1） 与服务器的无刷新传递消息
    （2） 可以检测用户离线和在线状态
    （3） 操作 DOM
   ```

### git fetch和git pull的区别

```
git pull：相当于是从远程获取最新版本并merge到本地
git fetch：相当于是从远程获取最新版本到本地，不会自动merge
```

### 为什么利用多个域名来存储网站资源会更有效

```
CDN缓存更方便
突破浏览器并发限制
节约cookie带宽
节约主域名的连接数，优化页面响应速度
防止不必要的安全问题
```

### 页面可见性（Page Visibility API）可以有哪些用途

   ```
    这个新的 API 的意义在于，通过监听网页的可见性，可以预判网页的卸载，
    还可以用来节省资源，减缓电能的消耗。比如，一旦用户不看网页，下面这些网页行为都是可以暂停的。

    （1）对服务器的轮询
    （2）网页动画
    （3）正在播放的音频或视频
   ```

### 从用户刷新网页开始，一次js请求一般情况下有哪些地方会有缓存处理

```
dns缓存，cdn缓存，浏览器缓存，服务器缓存
```

### 在html5中，哪个方法用于获得用户的当前位置

   ```
    getCurrentPosition()
   ```

### 渐进增强和优雅降级的定义

   ```
    渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对
             高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

    优雅降级：一开始就根据高版本浏览器构建完整的功能，然后再针对低版本浏览器进行兼容。
   ```

```
渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后
再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

优雅降级：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

区别：优雅降级是从复杂的现状开始，并试图减少用户体验的供给，
而渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，
以适应未来环境的需要。降级（功能衰减）意味着往回看；
而渐进增强则意味着朝前看，同时保证其根基处于安全地带
```

### 主流浏览器内核私有属性css前缀

   ```
    mozilla 内核 （firefox,flock 等）    -moz
    webkit  内核 （safari,chrome 等）   -webkit
    opera   内核 （opera 浏览器）        -o
    trident 内核 （ie 浏览器）           -ms
   ```

### 知道的网页制作会用到的图片格式有哪些

```
png-8、png-24、jpeg、gif、svg
但是上面的那些都不是面试官想要的最后答案。面试官希望听到是Webp,Apng。（是否有关注新技术，新鲜事物）

Webp：WebP格式，谷歌（google）开发的一种旨在加快图片加载速度的图片格式。
图片压缩体积大约只有JPEG的2/3，并能节省大量的服务器带宽资源和数据空间。
Facebook Ebay等知名网站已经开始测试并使用WebP格式。

在质量相同的情况下，WebP格式图像的体积要比JPEG格式图像小40%。

Apng：全称是“Animated Portable Network Graphics”, 是PNG的位图动画扩展，
可以实现png格式的动态图片效果。04年诞生，但一直得不到各大浏览器厂商的支持，
直到日前得到 iOS safari 8的支持，有望代替GIF成为下一代动态图标准
```

### 文档的不同注释方式

   ```
    HTML 的注释方法 <!--注释内容--> 
    
    CSS 的��释方法 /*注释内容*/ 
    
    JavaScript 的注释方法 /* 多行注释方式 */ //单行注释方式
   ```

### 实现不使用border画出1px高的线，在不同浏览器的标准模式与怪异模式下都能保持一致的效果

   ```html
     <div style="height:1px;overflow:hidden;background:red"></div>
   ```

### 如何在页面上实现一个圆形的可点击区域

   ```
（1）纯 html 实现，使用 <area> 来给 <img> 图像标记热点区域的方式，<map> 标签用来
    定义一个客户端图像映射，<area> 标签用来定义图像映射中的区域，area 元素永远嵌套
    在 map 元素内部，我们可以将 area 区域设置为圆形，从而实现可点击的圆形区域。

（2）纯 css 实现，使用 border-radius ，当 border-radius 的长度等于
    宽高相等的元素值的一半时，即可实现一个圆形的点击区域。

（3）纯 js 实现，判断一个点在不在圆上的简单算法，通过监听文档的点击事件，
    获取每次点击时鼠标的位置，判断该位置是否在我们规定的圆形区域内。
   ```

```
svg
border-radius
纯js实现 需要求一个点在不在圆上简单算法、获取鼠标坐标等等
```

### HTML5 drag api
- dragstart:事件主体是被拖放元素，在开始拖放被拖放元素时触发，。
- darg:事件主体是被拖放元素，在正在拖放被拖放元素时触发。
- dragenter:事件主体是目标元素，在被拖放元素进入某元素时触发。
- dragover:事件主体是目标元素，在被拖放在某元素内移动时触发。
- dragleave:事件主体是目标元素，在被拖放元素移出目标元素是触发。
- drop:事件主体是目标元素，在目标元素完全接受被拖放元素时触发。
- dragend:事件主体是被拖放元素，在整个拖放操作结束时触发

### 拖拽有哪些知识点
- 可以通过给标签设置draggable属性来实现元素的拖拽，img和a标签默认是可以拖拽的
- 拖拽者身上的三个事件：ondragstart、ondrag、ondragend
- 拖拽要放到的元素：ondragenter、ondragover、ondragleave、ondrap


### web worker
```
在 HTML 页面中，如果在执行脚本时，页面的状态是不可相应的，
直到脚本执行完成后， 页面才变成可相应。web worker 是运行在
后台的 js，独立于其他脚本，不会影响页面你 的性能。并且通过 
postMessage 将结果回传到主线程。这样在进行复杂操作的时候，
就不会阻塞主线程了
```

如何创建 web worker:
- 检测浏览器对于 web worker 的支持性
- 创建 web worker 文件(js，回传函数等)
- 创建 web worker 对象

### 用一个div模拟textarea的实现
- 给 div 添加 contenteditable=true 即可

### 资源预加载prefetch/preload
```
都是告知浏览器提前加载文件(图片、视频、js、css等)，
但执行上是有区别的。
```

- prefetch：其利用浏览器空闲时间来下载或预取用户在不久的将来可能访问的文档。<link href="/js/xx.js" rel="prefetch">
- preload : 可以指明哪些资源是在页面加载完成后即刻需要的，浏览器在主渲染机制介入前就进行预加载，这一机制使得资源可以更早的得到加载并可用，且更不易阻塞页面的初步渲染，进而提升性能。 <link href="/js/xxx.js" rel="preload" as="script">需要 as 指定资源类型目前可用的属性类型有如下：
```
audio: 音频文件。
document: 一个将要被嵌入到<frame>或<iframe>内部的HTML文档。
embed: 一个将要被嵌入到<embed>元素内部的资源。
fetch: 那些将要通过fetch和XHR请求来获取的资源，比如一个ArrayBuffer或JSON文件。
font: 字体文件。
image: 图片文件。
object: 一个将会被嵌入到<embed>元素内的文件。
script: JavaScript文件。
style: 样式表。
track: WebVTT文件。
worker: 一个JavaScript的web worker或shared worker。
video: 视频文件。
```

### 如何解决a标签点击后hover事件失效的问题
改变a标签css属性的排列顺序
只需要记住LoVe HAte原则就可以了(爱恨原则)：
```
link→visited→hover→active
```
比如下面错误的代码顺序：
```
a:hover{
  color: green;
  text-decoration: none;
}
a:visited{ /* visited在hover后面，这样的话hover事件就失效了 */
  color: red;
  text-decoration: none;
}
```
正确的做法是将两个事件的位置调整一下。

注意各个阶段的含义：
- a:link：未访问时的样式，一般省略成a
- a:visited：已经访问后的样式
- a:hover：鼠标移上去时的样式
- a:active：鼠标按下时的样式

### 点击一个input依次触发的事件
```
const text = document.getElementById('text');
text.onclick = function (e) {
  console.log('onclick')
}
text.onfocus = function (e) {
  console.log('onfocus')
}
text.onmousedown = function (e) {
  console.log('onmousedown')
}
text.onmouseenter = function (e) {
  console.log('onmouseenter')
}
```
答案：
```
'onmouseenter'
'onmousedown'
'onfocus'
'onclick'
```

### 有写过原生的自定义事件吗
- 创建自定义事件
原生自定义事件有三种写法：
  - 1.使用Event
```
let myEvent = new Event('event_name');
```
  - 2.使用customEvent （可以传参数）
```
let myEvent = new CustomEvent('event_name', {
	detail: {
		// 将需要传递的参数放到这里
		// 可以在监听的回调函数中获取到：event.detail
	}
})
```
  - 3.使用document.createEvent('CustomEvent')和initCustomEvent()
```let myEvent = document.createEvent('CustomEvent');// 注意这里是为'CustomEvent'
myEvent.initEvent(
	// 1. event_name: 事件名称
	// 2. canBubble: 是否冒泡
	// 3. cancelable: 是否可以取消默认行为
)
```
    - createEvent：创建一个事件
    - initEvent：初始化一个事件
可以看到，initEvent可以指定3个参数。
（有些文章中会说还有第四个参数detail，但是我查看了W3C上
并没有这个参数，而且实践了一下也没有效果）

- 事件的监听
```
自定义事件的监听其实和普通事件的一样，
使用addEventListener来监听：
```
```
button.addEventListener('event_name', function (e) {})
```

- 事件的触发
```
触发自定义事件使用dispatchEvent(myEvent)。
注意，这里的参数是要自定义事件的对象(也就是myEvent)，
而不是自定义事件的名称('myEvent')
```
案例
来看个案例吧：
```
// 1.
// let myEvent = new Event('myEvent');
// 2.
// let myEvent = new CustomEvent('myEvent', {
//   detail: {
//     name: 'lindaidai'
//   }
// })
// 3.
let myEvent = document.createEvent('CustomEvent');
myEvent.initEvent('myEvent', true, true)

let btn = document.getElementsByTagName('button')[0]
btn.addEventListener('myEvent', function (e) {
  console.log(e)
  console.log(e.detail)
})
setTimeout(() => {
  btn.dispatchEvent(myEvent)
}, 2000)
```

### addEventListener和attachEvent的区别
- 前者是标准浏览器中的用法，后者IE8以下
- addEventListener可有冒泡，可有捕获；attachEvent只有冒泡，没有捕获。
- 前者事件名不带on，后者带on
- 前者回调函数中的this指向当前元素，后者指向window

### addEventListener函数的第三个参数
- 第三个参数涉及到冒泡和捕获，是true时为捕获，是false则为冒泡。

- 或者是一个对象{passive: true}，针对的是Safari浏览器，禁止/开启使用滚动的时候要用到。

### DOM事件流是什么
事件发生时会在元素节点之间按照特定的顺序传播，
这个传播过程就叫做DOM事件流。

- DOM事件流分为三个阶段：
  - 捕获阶段：事件从window发出，自上而下向目标节点传播的阶段
  - 目标阶段：真正的目标阶段正在处理事件的阶段
  - 冒泡阶段：事件从目标节点自下而上向window传播的阶段

(注意：JS代码只能执行捕获或者冒泡其中一个阶段，要么是捕获要么是冒泡)

### 冒泡和捕获的具体过程
- 冒泡指的是：当给某个目标元素绑定了事件之后，这个事件会依次在它的父级元素中被触发(当然前提是这个父级元素也有这个同名称的事件，比如子元素和父元素都绑定了click事件就触发父元素的click)。（非常好记，你就想想水底有一个泡泡从下面往上传的，所以是冒泡）

- 捕获则是从上层向下层传递，与冒泡相反。

来看看这个例子：
```
<!-- 会依次执行 button li ul -->
<ul onclick="alert('ul')">
  <li onclick="alert('li')">
    <button onclick="alert('button')">点击</button>
  </li>
</ul>
<script>
  window.addEventListener('click', function (e) {
    alert('window')
  })
  document.addEventListener('click', function (e) {
    alert('document')
  })
</script>
```
- 冒泡结果：button > li > ul > document > window
- 捕获结果：window > document > ul > li > button

### 如何阻止冒泡和默认事件(兼容写法)
阻止冒泡：
```
function stopBubble (e) { // 阻止冒泡
  if (e && e.stopPropagation) {
    e.stopPropagation();
  } else {
    // 兼容 IE
    window.event.cancelBubble = true;
  }
}
function stopDefault (e) { // 阻止默认事件
  if (e && e.preventDefault) {
    e.preventDefault();
  } else {
    // 兼容 IE
    window.event.returnValue = false;
    return false;
  }
}
```

### 所有的事件都有冒泡吗
并不是所有的事件都有冒泡的，例如以下事件就没有：
- onblur
- onfocus
- onmouseenter
- onmouseleave

### 关于一些兼容性
- event的兼容性
  - 其它浏览器window.event
  - 火狐下没有window.event，所以用传入的参数ev代替
  - 最终写法：var oEvent = ev || window.event

- 事件源的兼容性
  - 其它浏览器event.target
  - IE下为event.srcElement
  - 最终写法：var target = event.target || event.srcElement

- 阻止事件冒泡
  - 其它浏览器event.stopPropagation()
  - IE下为window.event.cancelBubble = true

- 阻止默认事件
  - 其它浏览器e.preventDefault()
  - IE下为window.event.returnValue = false

### offset、scroll、client的区别
client:
- oEvent.clientX是指鼠标到可视区左边框的距离。
- oEvent.clientY是指鼠标到可视区上边框的距离。
- clientWidth是指可视区的宽度。
- clientHeight是指可视区的高度。
- clientLeft获取左边框的宽度。
- clientTop获取上边框的宽度。

offset:
- offsetWidth是指div的宽度（包括div的边框）
- offsetHeight是指div的高度（包括div的边框）
- offsetLeft是指div到整个页面左边框的距离（不包括div的边框）
- offsetTop是指div到整个页面上边框的距离（不包括div的边框）

scroll:
- scrollTop是指可视区顶部边框与整个页面上部边框的看不到的区域。
- scrollLeft是指可视区左边边框与整个页面左边边框的看不到的区域。
- scrollWidth是指左边看不到的区域加可视区加右边看不到的区域即整个页面的宽度（包括边框）
- scrollHeight是指上边看不到的区域加可视区加右边看不到的区域即整个页面的高度（包括边框）

### target="_blank"有哪些问题
存在问题：
- 安全隐患：新打开的窗口可以通过window.opener获取到来源页面的window对象即使跨域也可以。某些属性的访问被拦截，是因为跨域安全策略的限制。 但是，比如修改window.opener.location的值，指向另外一个地址，这样新窗口有可能会把原来的网页地址改了并进行页面伪装来欺骗用户。
- 新打开的窗口与原页面窗口共用一个进程，若是新页面有性能不好的代码也会影响原页面

解决方案：
- 尽量不用target="_blank"
- 如果一定要用，需要加上rel="noopener"或者rel="noreferrer"。这样新窗口的window.openner就是null了，而且会让新窗口运行在独立的进程里，不会拖累原来页面的进程。(不过，有些浏览器对性能做了优化，即使不加这个属性，新窗口也会在独立进程打开。不过为了安全考虑，还是加上吧。)

### children以及childNodes的区别
- children和只获取该节点下的所有element节点
- childNodes不仅仅获取element节点还会获取元素标签中的空白节点
- firstElementChild只获取该节点下的第一个element节点
- firstChild会获取空白节点


### 前端安全模块

#### 代码注入XSS
- 跨网站指令码（英语：Cross-site scripting，通常简称为：XSS）是一种网站应用程式的安全漏洞攻击，是代码注入的一种。它允许恶意使用者将程式码注入到网页上，其他使用者在观看网页时就会受到影响。这类攻击通常包含了 HTML 以及使用者端脚本语言
- XSS 分为三种：反射型，存储型和 DOM-based

#### 如何攻击
- XSS 通过修改 HTML节点或者执行 JS代码来攻击网站。
- 例如通过 URL 获取某些参数
```
<!-- http://www.domain.com?name=<script>alert(1)</script> -->
<div>{{name}}</div>    
```
- 上述 URL 输入可能会将 HTML 改为 <div><script>alert(1)</script></div> ，这样页面中就凭空多了一段可执行脚本。这种攻击类型是反射型攻击，也可以说是 DOM-based 攻击

#### 如何防御
- 最普遍的做法是转义输入输出的内容，对于引号，尖括号，斜杠进行转义
```
function escape(str) {
	str = str.replace(/&/g, "&amp;");
	str = str.replace(/</g, "&lt;");
	str = str.replace(/>/g, "&gt;");
	str = str.replace(/"/g, "&quto;");
	str = str.replace(/'/g, "&##39;");
	str = str.replace(/`/g, "&##96;");
    str = str.replace(/\//g, "&##x2F;");
    return str
}
```
通过转义可以将攻击代码 <script>alert(1)</script> 变成
```
// -> &lt;script&gt;alert(1)&lt;&##x2F;script&gt;
escape('<script>alert(1)</script>')
```
- 对于显示富文本来说，不能通过上面的办法来转义所有字符，因为这样会把需要的格式也过滤掉。这种情况通常采用白名单过滤的办法，当然也可以通过黑名单过滤，但是考虑到需要过滤的标签和标签属性实在太多，更加推荐使用白名单的方式
```
var xss = require("xss");
var html = xss('<h1 id="title">XSS Demo</h1><script>alert("xss");</script>');
// -> <h1>XSS Demo</h1>&lt;script&gt;alert("xss");&lt;/script&gt;
console.log(html);
```
- 以上示例使用了 js-xss来实现。可以看到在输出中保留了 h1 标签且过滤了 script 标签

#### cookie如何防范XSS攻击
- XSS(跨站脚本攻击)是指攻击者在返回的 HTML 中嵌入 javascript 脚本，为了减轻这些 攻击，需要在 HTTP 头部配上，set-cookie

- httpOnly 这个属性可以防止 XSS,它会禁止 javascript 脚本来访问 cookie
- secure- 这个属性告诉浏览器仅在请求为 https 的时候发送 cookie

#### 跨站请求伪造CSRF
- CSRF 就是利用用户的登录态发起恶意请求
- CSRF（Cross-site request forgery） 跨站请求伪造，是一种常见的攻击方式。是指 A 网站正常登陆后，cookie 正常保存登录信息，其他网站 B 通过某种方式调用 A 网站接口进行操作，A 的接口会在请求时会自动带上 cookie。

- 同源策略可以通过 html 标签加载资源，而且同源策略不阻止接口请求而是拦截请求结果，CSRF 恰恰占了这两个便宜。
- 对于 GET 请求，直接放到 <img> 就能神不知鬼不觉地请求跨域接口。
- 对于 POST 请求，很多例子都使用 form 提交：
```
<form action="<nowiki>http://bank.com/transfer.do</nowiki>" method="POST">
  <input type="hidden" name="acct" value="MARIA" />
  <input type="hidden" name="amount" value="100000" />
  <input type="submit" value="View my pictures" />
</form>
```
- 浏览器同源策略不能作为防范 CSRF 的方法 浏览器允许这么做，归根到底就是因为你无法用 js 直接操作获得的结果。

如何攻击
- 假设网站中有一个通过 Get 请求提交用户评论的接口，那么攻击者就可以在钓鱼网站中加入一个图片，图片的地址就是评论接口
```
<img src="http://www.domain.com/xxx?comment='attack'"/>
```

如何防御
- Get 请求不对数据进行修改
- 不让第三方网站访问到用户 Cookie
- 阻止第三方网站请求接口
- 请求时附带验证信息，比如验证码或者 token

#### CSRF怎么获取用户的登录态
- 攻击全称不需要获取cookie，只是在危险的网站欺骗用户去点击已登录的网站链接，利用已登录的网站的自动发送cookie达到目的。因为http请求都会带着请求目标域下的cookie的，向同一个服务器发请求时会带上浏览器保存的对于那个服务器的cookie，而不管你从哪个网站向目标网站发请求

#### cookie通常是不能跨域访问的，那问什么会有csrf攻击
疑问：
- csrf说用户访问了A网站，然后又访问恶意网站B, B中也发送请求到A，携带A站的cookie，这样就构成了csrf。 可是cookie好像是不支持跨域的吧？

回答
- 浏览器会依据加载的域名附带上对应域名cookie，又不是发送b站的cookie。
- 就是如果用户在a站登录了生成了授权的cookie 之类的，然后访问b站，b站故意构造请求a站的请求，如删除操作之类的，用script，img或者iframe之类的加载a站着个地址，浏览器会附带上a站此登录用户的授权cookie信息，这样就构成crsf，会删除掉当前用户的数据

总结
- XSS攻击: 注入恶意代码
  - cookie 设置 httpOnly
  - 转义页面上的输入内容和输出内容
- CSRF: 跨站请求伪造，防护:
  - get不修改数据
  - 不被第三方网站访问到用户的 cookie
  - 设置白名单，不被第三方网站请求
  - 请求校验

#### 浏览器同源策略SOP
#### 1.同源
先解释何为同源：协议、域名、端口都一样，就是同源。
```
             url                 	   同源
https://niconico.com(opens new window)	   基准
https://niconico.com/spirit	            o
https://sub.niconico.com/spirit	            x
http://niconico.com/spirit	            x
https://niconico.com:8080/spirit	    x
```

#### 2.限制
- 你之所以会遇到 跨域问题，正是因为 SOP 的各种限制。但是具体来说限制了什么呢？
- 如果你说 SOP 就是“限制非同源资源的获取”，这不对，最简单的例子是引用图片、css、js 文件等资源的时候就允许跨域。
- 如果你说 SOP 就是“禁止跨域请求”，这也不对，本质上 SOP 并不是禁止跨域请求，而是在请求后拦截了请求的回应。

其实表面上 SOP 分两种情况：
- 可以正常引用 iframe、图片等各种资源，但是限制对其内容进行操作
- 直接限制 ajax 请求，准确来说是限制操作 ajax 响应结果，这会引起后面说到的 CSRF

- 但是，本质上这两条是一样的：总之，对于非同源的资源，浏览器可以“直接使用”，但是程序员和用户不可以对这些数据进行操作，杜绝某些居心不良的行为。这就是现代安全浏览器对用户的保护之一。

下面是 3 个在实际应用中会遇到的例子：
- 使用 ajax 请求其他跨域 API，最常见的情况，前端新手噩梦
- iframe 与父页面交流（如 DOM 或变量的获取），出现率比较低，而且解决方法也好懂
- 对跨域图片（例如来源于 <img> ）进行操作，在 canvas 操作图片的时候会遇到这个问题

如果没有了 SOP：
- iframe 里的机密信息被肆意读取
- 更加肆意地进行 CSRF
- 接口被第三方滥用

#### 3.绕过跨域
- SOP 虽然让用户更安全，同时也会对程序员带来一定程度的麻烦，因为有时候业务上就是有跨域的需求。绕过跨域的方案由于篇幅所限，并且网上也很多相关文章，所以不在这里展开解决跨域的方案，只给出几个关键词：

对于 ajax
- 使用 JSONP
- 后端进行 CORS 配置
- 后端反向代理
- 使用 WebSocket

对于 iframe
- 使用 location.hash 或 window.name 进行信息交流
- 使用 postMessage

#### 4.浏览器同源策略与ajax
- 对于 ajax 请求，在获得数据之后你能肆意进行 js 操作。这时候虽然同源策略会阻止响应，但依然会发出请求。因为执行响应拦截的是浏览器而不是后端程序。事实上你的请求已经发到服务器并返回了结果，但是迫于安全策略，浏览器不允许你继续进行 js 操作，所以报出你熟悉的 blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.。

- 所以再强调一次，同源策略不能作为防范 CSRF 的方法。

- 不过可以防范 CSRF 的例外还是有的，浏览器并不是让所有请求都发送成功，上述情况仅限于简单请求，相关知识会在下面 CORS 一节详细解释。

#### 跨域资源共享CORS
- 跨域是浏览器限制，跨域资源共享（Cross-origin resource sharing）也是服务器与浏览器协调的结果。

- 如果服务器设置了 CORS 相关配置，在返回浏览器的请求头会加上 Access-Control-Allow-Origin，浏览器看到这个字段的值与当前的源匹配，就会解锁跨域限制。
```
HTTP/1.1 200 OK
Date: Sun, 24 Apr 2016 12:43:39 GMT
Server: Apache
Access-Control-Allow-Origin: http://www.acceptmeplease.com
Keep-Alive: timeout=2, max=100
Connection: Keep-Alive
Content-Type: application/xml
Content-Length: 423
```
对于 CORS，请求分两种。

#### 1.简单请求
- 请求方法使用 GET、POST 或 HEAD
- Content-Type 设为 application/x-www-form-urlencoded、multipart/form-data 或 text/plain

- 符合上面两个条件的都为 CORS 简单请求。简单请求都会直接发到服务器，会造成 CSRF。

#### 2.预检请求
- 不符合简单请求要求的请求都需要先发送预检请求（Preflight Request）。浏览器会在真正请求前发送 OPTION 方法的请求向服务器询问当前源是否符合 CORS 目标，验证通过后才会发送正式请求。

- 例如使用 application/json 传参的 POST 请求就是非简单请求，会在预检中被拦截。

- 再例如使用 PUT 方法请求，也会发送预检请求。

- 上面提到的可以防范 CSRF 的例外，就是指预检请求。即使跨域成功请求预检，但真正请求并不能发出去，这就保证了 CSRF 无法成功。

#### 3.CORS与cookie
- 与同域不同，用于跨域的 CORS 请求默认不发送 Cookie 和 HTTP 认证信息，前后端都要在配置中设定请求时带上 cookie。
- 这就是为什么在进行 CORS 请求时 axios 需要设置 withCredentials: true。

下面是 node.js 的后台 koa 框架的 CORS 设置：
```
/**
 * CORS middleware
 *
 * @param {Object} [options]
 *  - {String|Function(ctx)} origin `Access-Control-Allow-Origin`, default is request Origin header
 *  - {String|Array} allowMethods `Access-Control-Allow-Methods`, default is 'GET,HEAD,PUT,POST,DELETE,PATCH'
 *  - {String|Array} exposeHeaders `Access-Control-Expose-Headers`
 *  - {String|Array} allowHeaders `Access-Control-Allow-Headers`
 *  - {String|Number} maxAge `Access-Control-Max-Age` in seconds
 *  - {Boolean} credentials `Access-Control-Allow-Credentials`
 *  - {Boolean} keepHeadersOnError Add set headers to `err.header` if an error is thrown
 * @return {Function} cors middleware
 * @api public
 */
```
- 顺带一提，Access-Control-Allow-Credentials 设为 true 时，Access-Control-Allow-Origin 强制不能设为 *，为了安全，也是挺麻烦

#### 密码安全
加盐
- 对于密码存储来说，必然是不能明文存储在数据库中的，否则一旦数据库泄露，会对用户造成很大的损失。并且不建议只对密码单纯通过加密算法加密，因为存在彩虹表的关系

- 通常需要对密码加盐，然后进行几次不同加密算法的加密
```
// 加盐也就是给原密码添加字符串，增加原密码长度
sha256(sha1(md5(salt + password + salt)))
```
- 但是加盐并不能阻止别人盗取账号，只能确保即使数据库泄露，也不会暴露用户的真实密码。一旦攻击者得到了用户的账号，可以通过暴力破解的方式破解密码。对于这种情况，通常使用验证码增加延时或者限制尝试次数的方式。并且一旦用户输入了错误的密码，也不能直接提示用户输错密码，而应该提示账号或密码错误

前端加密
- 虽然前端加密对于安全防护来说意义不大，但是在遇到中间人攻击的情况下，可以避免明文密码被第三方获取


### 性能优化相关
#### 性能优化方式
#### 1.DNS预解析
- DNS 解析也是需要时间的，可以通过预解析的方式来预先获得域名所对应的 IP
```
<link rel="dns-prefetch" href="//blog.poetries.top">
```

#### 2.缓存
- 缓存对于前端性能优化来说是个很重要的点，良好的缓存策略可以降低资源的重复加载提高网页的整体加载速度
- 通常浏览器缓存策略分为两种：强缓存和协商缓存

强缓存
- 实现强缓存可以通过两种响应头实现：Expires和 Cache-Control 。强缓存表示在缓存期间不需要请求，state code为 200
```
Expires: Wed, 22 Oct 2018 08:41:00 GMT
```
- Expires 是 HTTP / 1.0 的产物，表示资源会在 Wed, 22 Oct 2018 08:41:00 GMT 后过期，需要再次请求。并且 Expires 受限于本地时间，如果修改了本地时间，可能会造成缓存失效
```
Cache-control: max-age=30
```
- Cache-Control 出现于 HTTP / 1.1，优先级高于 Expires 。该属性表示资源会在 30 秒后过期，需要再次请求

协商缓存
- 如果缓存过期了，我们就可以使用协商缓存来解决问题。协商缓存需要请求，如果缓存有效会返回 304
- 协商缓存需要客户端和服务端共同实现，和强缓存一样，也有两种实现方式

Last-Modified 和 If-Modified-Since
- Last-Modified 表示本地文件最后修改日期，If-Modified-Since 会将 Last-Modified的值发送给服务器，询问服务器在该日期后资源是否有更新，有更新的话就会将新的资源发送回来
- 但是如果在本地打开缓存文件，就会造成 Last-Modified 被修改，所以在 HTTP / 1.1 出现了 ETag

ETag 和 If-None-Match
- ETag 类似于文件指纹，If-None-Match 会将当前 ETag 发送给服务器，询问该资源 ETag 是否变动，有变动的话就将新的资源发送回来。并且 ETag 优先级比 Last-Modified 高

选择合适的缓存策略
- 对于大部分的场景都可以使用强缓存配合协商缓存解决，但是在一些特殊的地方可能需要选择特殊的缓存策略

- 对于某些不需要缓存的资源，可以使用 Cache-control: no-store ，表示该资源不需要缓存
- 对于频繁变动的资源，可以使用 Cache-Control: no-cache 并配合 ETag 使用，表示该资源已被缓存，但是每次都会发送请求询问资源是否更新。
- 对于代码文件来说，通常使用 Cache-Control: max-age=31536000 并配合策略缓存使用，然后对文件进行指纹处理，一旦文件名变动就会立刻下载新的文件

#### 3.使用HTTP/2.0
- 因为浏览器会有并发请求限制，在 HTTP / 1.1 时代，每个请求都需要建立和断开，消耗了好几个 RTT 时间，并且由于 TCP 慢启动的原因，加载体积大的文件会需要更多的时间
- 在 HTTP / 2.0 中引入了多路复用，能够让多个请求使用同一个 TCP 链接，极大的加快了网页的加载速度。并且还支持 Header 压缩，进一步的减少了请求的数据大小

#### 4.预加载
在开发中，可能会遇到这样的情况。有些资源不需要马上用到，但是希望尽早获取，这时候就可以使用预加载
预加载其实是声明式的 fetch ，强制浏览器请求资源，并且不会阻塞 onload 事件，可以使用以下代码开启预加载
<link rel="preload" href="http://example.com">
预加载可以一定程度上降低首屏的加载时间，因为可以将一些不影响首屏但重要的文件延后加载，唯一缺点就是兼容性不好

#1.5 预渲染
可以通过预渲染将下载的文件预先在后台渲染，可以使用以下代码开启预渲染

<link rel="prerender" href="http://poetries.com">
预渲染虽然可以提高页面的加载速度，但是要确保该页面百分百会被用户在之后打开，否则就白白浪费资源去渲染
#1.6 懒执行与懒加载
懒执行

懒执行就是将某些逻辑延迟到使用时再计算。该技术可以用于首屏优化，对于某些耗时逻辑并不需要在首屏就使用的，就可以使用懒执行。懒执行需要唤醒，一般可以通过定时器或者事件的调用来唤醒
懒加载

懒加载就是将不关键的资源延后加载
懒加载的原理就是只加载自定义区域（通常是可视区域，但也可以是即将进入可视区域）内需要加载的东西。对于图片来说，先设置图片标签的 src 属性为一张占位图，将真实的图片资源放入一个自定义属性中，当进入自定义区域时，就将自定义属性替换为 src 属性，这样图片就会去下载资源，实现了图片懒加载

懒加载不仅可以用于图片，也可以使用在别的资源上。比如进入可视区域才开始播放视频等
#1.7 文件优化
图片优化

对于如何优化图片，有 2 个思路

减少像素点
减少每个像素点能够显示的颜色
图片加载优化

不用图片。很多时候会使用到很多修饰类图片，其实这类修饰图片完全可以用 CSS 去代替。
对于移动端来说，屏幕宽度就那么点，完全没有必要去加载原图浪费带宽。一般图片都用 CDN 加载，可以计算出适配屏幕的宽度，然后去请求相应裁剪好的图片
小图使用 base64格式
将多个图标文件整合到一张图片中（雪碧图）
选择正确的图片格式：
对于能够显示 WebP 格式的浏览器尽量使用 WebP 格式。因为 WebP 格式具有更好的图像数据压缩算法，能带来更小的图片体积，而且拥有肉眼识别无差异的图像质量，缺点就是兼容性并不好
小图使用 PNG，其实对于大部分图标这类图片，完全可以使用 SVG 代替
照片使用 JPEG
其他文件优化

CSS文件放在 head 中
服务端开启文件压缩功能
将 script 标签放在 body 底部，因为 JS 文件执行会阻塞渲染。当然也可以把 script 标签放在任意位置然后加上 defer ，表示该文件会并行下载，但是会放到 HTML 解析完成后顺序执行。对于没有任何依赖的 JS文件可以加上 async ，表示加载和渲染后续文档元素的过程将和 JS 文件的加载与执行并行无序进行。 执行 JS代码过长会卡住渲染，对于需要很多时间计算的代码
可以考虑使用 Webworker。Webworker可以让我们另开一个线程执行脚本而不影响渲染。
CDN

静态资源尽量使用 CDN 加载，由于浏览器对于单个域名有并发请求上限，可以考虑使用多个 CDN 域名。对于 CDN 加载静态资源需要注意 CDN 域名要与主站不同，否则每次请求都会带上主站的 Cookie

#1.8 其他
使用 Webpack 优化项目

对于 Webpack4，打包项目使用 production 模式，这样会自动开启代码压缩
使用 ES6 模块来开启 tree shaking，这个技术可以移除没有使用的代码
优化图片，对于小图可以使用 base64 的方式写入文件中
按照路由拆分代码，实现按需加载
给打包出来的文件名添加哈希，实现浏览器缓存文件
监控

对于代码运行错误，通常的办法是使用 window.onerror 拦截报错。该方法能拦截到大部分的详细报错信息，但是也有例外

对于跨域的代码运行错误会显示 Script error. 对于这种情况我们需要给 script 标签添加 crossorigin 属性
对于某些浏览器可能不会显示调用栈信息，这种情况可以通过 arguments.callee.caller 来做栈递归
对于异步代码来说，可以使用 catch 的方式捕获错误。比如 Promise 可以直接使用 catch 函数，async await 可以使用 try catch
但是要注意线上运行的代码都是压缩过的，需要在打包时生成 sourceMap 文件便于 debug。
对于捕获的错误需要上传给服务器，通常可以通过 img 标签的 src发起一个请求
#
2 首屏渲染优化
css / js 分割，使首屏依赖的文件体积最小，内联首屏关键 css / js；
非关键性的文件尽可能的 异步加载和懒加载，避免阻塞首页渲染；
使用dns-prefetch / preconnect / prefetch / preload等浏览器提供的资源提示，加快文件传输；
谨慎控制好 Web字体，一个大字体包足够让你功亏一篑
控制字体包的加载时机；
如果使用的字体有限，那尽可能只将使用的文字单独打包，能有效减少体积； 合理利用 Localstorage / server-worker 等存储方式进行 数据与资源缓存
分清轻重缓急
重要的元素优先渲染；
视窗内的元素优先渲染
服务端渲染(SSR):
减少首屏需要的数据量，剔除冗余数据和请求；
控制好缓存，对数据/页面进行合理的缓存；
页面的请求使用流的形式进行传递；
优化用户感知
利用一些动画 过渡效果，能有效减少用户对卡顿的感知；
尽可能利用 骨架屏(Placeholder) / Loading 等减少用户对白屏的感知；
动画帧数尽量保证在 30帧 以上，低帧数、卡顿的动画宁愿不要；
js 执行时间避免超过 100ms，超过的话就需要做
寻找可 缓存 的点
任务的 分割异步 或 web worker 执行
移动端的性能优化

首屏加载和按需加载，懒加载
资源预加载
图片压缩处理，使用base64内嵌图片
合理缓存dom对象
使用touchstart代替click（click 300毫秒的延迟）
利用transform:translateZ(0)，开启硬件GUP加速
不滥用web字体，不滥用float（布局计算消耗性能），减少font-size声明
使用viewport固定屏幕渲染，加速页面渲染内容
尽量使用事件代理，避免直接事件绑定
#
3 页面基础优化
引入位置: css 文件<head>中引入， js 文件<body>底部引入
影响首屏的，优先级很高的 js 也可以头部引入，甚至内联
减少请求 (http 1.0 - 1.1)，合并请求，正确设置 http 缓存
减少文件体积
删除多余代码:
tree-shaking
UglifyJs
code-spliting
混淆 / 压缩代码，开启 gzip 压缩；
多份编译文件按条件引入
针对现代浏览器直接给 ES6 文件，只针对低端浏览器引用编译后的 ES5 文件
可以利用<script type="module"> / <script type="module">进行条件引入用
动态 polyfill，只针对不支持的浏览器引入 polyfill；
图片优化:
根据业务场景，与UI探讨选择 合适质量，合适尺寸；
根据需求和平台，选择 合适格式，例如非透明时可用 jpg；非苹果端，使用 webp；
小图片合成 雪碧图，低于 5K 的图片可以转换成 base64 内嵌
合适场景下，使用 iconfont 或者 svg；
使用缓存
浏览器缓存: 通过设置请求的过期时间，合理运用浏览器缓存；
CDN缓存: 静态文件合理使用 CDN 缓存技术
HTML 放于自己的服务器上；
打包后的图片 / js / css 等资源上传到 CDN 上，文件带上 hash 值；
由于浏览器对单个域名请求的限制，可以将资源放在多个不同域的 CDN 上，可以绕开该限制；
服务器缓存: 将不变的数据、页面缓存到 内存 或 远程存储(redis等) 上
数据缓存: 通过各种存储将不常变的数据进行缓存，缩短数据的获取时间
#
4 性能优化方向
前端性能优化分为两个方向，一是工程化方向，另一个是细节方向

#4.1 工程化方向
客户端Gzip离线包，服务器资源Gzip压缩。
JS瘦身，Tree shaking，ES Module，动态Import，动态Polyfill
图片加载优化，Webp，考虑兼容性，可以提前加载一张图片，嗅探是否支持Webp
服务端渲染，客户端预渲染
CDN静态资源
Webpack Dll，通用优先打包抽离，利用浏览器缓存
骨架图
数据预取，包括接口数据，和加载详情页图片
Webpack本身提供的优化，Base64，资源压缩，Tree shaking，拆包chunk
减少重定向
#4.2 细节方向
图片，图片占位，图片懒加载。 雪碧图
使用 prefetch / preload 预加载等新特性
Preload 来告诉浏览器预先请求当前页需要的资源，从而提高这些资源的请求优先级。比如，对于那些本来请求优先级较低的关键请求，我们可以通过设置 Preload 来提升这些请求的优先级
Prefetch 来告诉浏览器用户将来可能在其他页面（非本页面）可能使用到的资源，那么浏览器会在空闲时，就去预先加载这些资源放在 http 缓存内，最常见的 dns-prefetch。比如，当我们在浏览A页面，如果会通过A页面中的链接跳转到B页面，而B页面中我们有些资源希望尽早提前加载，那么我们就可以在A页面里添加这些资源 Prefetch ，那么当浏览器空闲时，就会去加载这些资源
所以，对于那些可能在当前页面使用到的资源可以利用 Preload，而对一些可能在将来的某些页面中被使用的资源可以利用 Prefetch。如果从加载优先级上看，Preload 会提升请求优先级；而Prefetch会把资源的优先级放在最低，当浏览器空闲时才去预加载
服务器合理设置缓存策略
async（加载完当前js立即执行）/ defer(所有资源加载完之后执行js)
减少Dom的操作，减少重排重绘
从客户端层面，首屏减少和客户端交互，合并接口请求
数据缓存
首页不加载不可视组件
防止渲染抖动，控制时序
减少组件层级
优先使用Flex布局
#
5 长列表优化
#vue-virtual-scroll-list优化长列表
虚拟列表的实现原理：只渲染可视区的 dom 节点，其余不可见的数据卷起来，只会渲染可视区域的 dom 节点，提高渲染性能及流畅性，优点是支持海量数据的渲染；

github地址：https://github.com/tangbc/vue-virtual-scroll-list

#Object.freeze优化长列表
Object.freeze()方法可以冻结一个对象。一个被冻结的对象再也不能被修改；冻结了一个对象则不能向这个对象添加新的属性，不能删除已有属性，不能修改该对象已有属性的可枚举性、可配置性、可写性，以及不能修改已有属性的值。
对于data()或vuex中冻结的对象，vue不会做getter和setter的转换。因此对于一个不变的、大数据量的数组或Object数据来说，使用Object.freeze()可以有效地提升性能。
#
6 卡顿问题解决
CSS动画效率比JS高，css可以用GPU加速，3d加速。如果非要用JS动画，可以用requestAnimationFrame
批量进行DOM操作，固定图片容器大小，避免屏幕抖动
减少重绘重排
节流和防抖
减少临时大对象产生，利用对象缓存，主要是减少内存碎片
异步操作，IntersectionObserver，PostMessage，RequestIdleCallback
#
7 编码优化
编码优化，指的就是 在代码编写时的，通过一些 最佳实践，提升代码的执行性能。通常这并不会带来非常大的收益，但这属于 程序猿的自我修养，而且这也是面试中经常被问到的一个方面，考察自我管理与细节的处理。

数据读取:

通过作用域链 / 原型链 读取变量或方法时，需要更多的耗时，且越长越慢
对象嵌套越深，读取值也越慢；
最佳实践
尽量在局部作用域中进行 变量缓存；
避免嵌套过深的数据结构，数据扁平化 有利于数据的读取和维护
循环: 循环通常是编码性能的关键点；

代码的性能问题会再循环中被指数倍放大
最佳实践
尽可能 减少循环次数
减少遍历的数据量；
完成目的后马上结束循环
避免在循环中执行大量的运算，避免重复计算，相同的执行结果应该使用缓存；
js 中使用 倒序循环 会略微提升性能；
尽量避免使用 for-in 循环，因为它会枚举原型对象，耗时大于普通循环；
条件流程性能: Map / Object > switch > if-else

// 使用 if-else
if(type === 1) {

} else if (type === 2) {

} else if (type === 3) {

}

// 使用 switch
switch (type) {
	case 1:
		break;4
	case 2:
		break;
	case 3:
		break;
    default:
        break;
}

// 使用 Map
const map = new Map([
	[1, () => {}],
	[2, () => {}],
	[3, () => {}],
])
map.get(type)()

// 使用 Objext
const obj = {
	1: () => {},
	2: () => {},
	3: () => {},
}
obj[type]()
减少 cookie 体积: 能有效减少每次请求的体积和响应时间；

去除不必要的 cookie；
压缩 cookie 大小；
设置 domain 与 过期时间；
dom 优化:

减少访问 dom 的次数，如需多次，将 dom 缓存于变量中；
减少重绘与回流:
多次操作合并为一次；
减少对计算属性的访问
例如 offsetTop， getComputedStyle 等
因为浏览器需要获取最新准确的值，因此必须立即进行重排，这样会破坏了浏览器的队列整合，尽量将值进行缓存使用；
大量操作时，可将 dom 脱离文档流或者隐藏，待操作完成后再重新恢复；
使用DocumentFragment / cloneNode / replaceChild进行操作；
使用事件委托，避免大量的事件绑定；
css 优化:

层级扁平，避免过于多层级的选择器嵌套；
特定的选择器 好过一层一层查找: .xxx-child-text{} - 优于 .xxx .child .text{}
减少使用通配符与属性选择器；
减少不必要的多余属性；
使用 动画属性实现动画，动画时脱离文档流，开启硬件加速，优先使用 css 动画；
使用 <link> 替代原生 @import；
html 优化:

减少 dom 数量，避免不必要的节点或嵌套
避免<img src="" />空标签，能减少服务器压力，因为 src 为空时，浏览器仍然会发起请求
IE 向页面所在的目录发送请求；
Safari、Chrome、Firefox 向页面本身发送请求；
Opera 不执行任何操作。
图片提前 指定宽高 或者 脱离文档流，能有效减少因图片加载导致的页面回流；
语义化标签 有利于 SEO 与浏览器的解析时间；
减少使用 table 进行布局，避免使用<br />与<hr />
#
8 如何根据chrome的timing优化
#8.1 性能优化API
Performance。performance.now()与new Date()区别，它是高精度的，且是相对时间，相对于页面加载的那一刻。但是不一定适合单页面场景
window.addEventListener("load", ""); window.addEventListener("domContentLoaded", "");
Img的onload事件，监听首屏内的图片是否加载完成，判断首屏事件
RequestFrameAnmation 和 RequestIdleCallback
IntersectionObserver、MutationObserver，PostMessage
Web Worker，耗时任务放在里面执行
#8.2 检测工具
Chrome Dev Tools
Page Speed
Jspref
#8.3 前端指标
image-20210307184052955

window.onload = function(){
    setTimeout(function(){
        let t = performance.timing
        console.log('DNS查询耗时 ：' + (t.domainLookupEnd - t.domainLookupStart).toFixed(0))
        console.log('TCP链接耗时 ：' + (t.connectEnd - t.connectStart).toFixed(0))
        console.log('request请求耗时 ：' + (t.responseEnd - t.responseStart).toFixed(0))
        console.log('解析dom树耗时 ：' + (t.domComplete - t.domInteractive).toFixed(0))
        console.log('白屏时间 ：' + (t.responseStart - t.navigationStart).toFixed(0))
        console.log('domready时间 ：' + (t.domContentLoadedEventEnd - t.navigationStart).toFixed(0))
        console.log('onload时间 ：' + (t.loadEventEnd - t.navigationStart).toFixed(0))

        if(t = performance.memory){
            console.log('js内存使用占比 ：' + (t.usedJSHeapSize / t.totalJSHeapSize * 100).toFixed(2) + '%')
        }
    })
}
DNS预解析优化

dns解析是很耗时的，因此如果解析域名过多，会让首屏加载变得过慢，可以考虑dns-prefetch优化

DNS Prefetch 应该尽量的放在网页的前面，推荐放在 后面。具体使用方法如下：

<meta http-equiv="x-dns-prefetch-control" content="on">
<link rel="dns-prefetch" href="//www.zhix.net">
<link rel="dns-prefetch" href="//api.share.zhix.net">
<link rel="dns-prefetch" href="//bdimg.share.zhix.net">
request请求耗时

不请求，用cache（最好的方式就是尽量引用公共资源，同时设置缓存，不去重新请求资源，也可以运用PWA的离线缓存技术，可以帮助wep实现离线使用）
前端打包时压缩
服务器上的zip压缩
图片压缩（比如tiny），使用webp等高压缩比格式
把过大的包，拆分成多个较少的包，防止单个资源耗时过大
同一时间针对同一域名下的请求有一定数量限制，超过限制数目的请求会被阻塞。如果资源来自于多个域下，可以增大并行请求和下载速度
延迟、异步、预加载、懒加载
对于非首屏的资源，可以使用 defer 或 async 的方式引入
也可以按需加载，在逻辑中，只有执行到时才做请求
对于多屏页面，滚动时才动态载入图片
解析dom树耗时






