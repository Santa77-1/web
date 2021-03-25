## HTML 面试知识点总结

整理了 HTML 面试的部分知识点

### 目录

- [HTML5有哪些新特性、移除了哪些元素？](#html5有哪些新特性、移除了哪些元素)
- [HTML5元素分类](#html5元素分类)
- [行内元素、块级元素、空元素的区别？](#行内元素、块级元素、空元素的区别？)

#### html5有哪些新特性、移除了哪些元素？

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

#### 行内元素、块级元素、空元素的区别？

   ```
   HTML4 中，元素被分成两大类: inline （内联元素）与 block（块级元素）。
   
   一个行内元素只占据它对应标签的边框所包含的空间。
   常见的行内元素有 a b span img strong sub sup button input label select textarea
   
   块级元素占据其父元素（容器）的整个宽度，因此创建了一个“块”。
   常见的块级元素有  div ul ol li dl dt dd h1 h2 h3 h4 h5 h6 p 
   
   （1） 格式上，默认情况下，行内元素不会以新行开始，而块级元素会新起一行。
   （2） 内容上，默认情况下，行内元素只能包含文本和其他行内元素。而块级元素可以包含行内元素和其他块级元素。
   （3） 行内元素与块级元素属性的不同，主要是盒模型属性上：行内元素设置 width 无效，height 无效
        （可以设置 line-height），设置 margin 和 padding 的上下不会对其他元素产生影响。
   
   空元素：<br> <hr> <img> <input> <link> <meta>
   行内元素不可以设置宽高，不独占一行
   块级元素可以设置宽高，独占一行
   ```





