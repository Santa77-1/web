## HTML 面试知识点总结

整理了 HTML 面试的部分知识点

### 目录

- [html5新特性、移除了哪些元素？](#html5新特性-移除了哪些元素)
- [html5元素分类](#html5元素分类)
- [行内元素、块级元素、空元素](#行内元素-块级元素-空元素)
- [语义化](#语义化)
- [前端性能优化](#前端性能优化)

#### html5新特性 移除了哪些元素

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

#### html5元素分类

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

#### 语义化

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
   
### 前端性能优化












