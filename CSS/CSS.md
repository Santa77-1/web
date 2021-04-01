## CSS 面试知识点总结
整理了 CSS 面试的部分知识点

### 目录

- [水平垂直居中](#水平垂直居中)
- [css选择符](#css选择符)
- [css优先级算法](#css优先级算法)
- [盒模型](#盒模型)
- [BFC](#BFC)
- [margin重叠](#margin重叠)
- [优化](#优化)
  - [css优化、提高性能的方法](#css优化提高性能的方法)



- [布局](#布局)
  - [65.⼏种常⻅的 CSS 布局](#)
    - [BFC。 .27.对 BFC 规范（块级格式化上下⽂：block formatting context）的理解？
13 对BFC规范的理解？	 	 5 如何创建块级格式化上下⽂(block formatting context),BFC有什
么⽤](#)
    - [13.请解释⼀下 CSS3 的 Flex box（弹性盒布局模型），以及适⽤场景？ 66 请解释⼀下
CSS3 的 Flexbox（弹性盒布局模型）以及适⽤场景](#)
    - [28 ⼏种常⻅的CSS布局](#)
      - [流体布局](#)
      - [圣杯布局](#)
      - [双⻜翼布局](#)
    - [36 ⾃适应布局](#)
		
  - [实现](#实现)
    - [99.css 实现上下固定中间⾃适应布局？](#)
    - [100.css 两栏布局的实现？](#)
    - [101.css 三栏布局的实现？](#)
    - [24 列出你所知道可以改变⻚⾯布局的属性](#)
    - [16.CSS 多列等⾼如何实现 ？ 68 请写出多种等⾼布局](#)

  - [移动端](#移动端)
    - [32.移动端的布局⽤过媒体查询吗？](#)
    - [64.使⽤ rem 布局的优缺点？](#)

- [盒模型＊](#)
  - [71.内联盒模型基本概念](#)

- [选择符](#)
  - [css选择符		 56 CSS选择符有哪些？哪些属性可以继承](#)
  - [css优先级算法． 12 CSS优先级算法如何计算？](#)
  - [23 CSS不同选择器的权重(CSS层叠的规则)](#)

- [定位](#)
  - [⽔平垂直居中 9.如何居中 div？ 51 两种以上⽅式实现已知或者未知宽度的垂直⽔平居中](#)
  - [45 ⽔平居中的⽅法](#)
  - [46 垂直居中的⽅法](#)
  - [41 如何垂直居中⼀个浮动元素？](#)
  - [58 如何居中div？如何居中⼀个浮动元素？如何让绝对定位的div居中](#)
  - [40 css中可以让⽂字在垂直和⽔平⽅向上重叠的两个属性是什么？](#)
  - [23.绝对定位元素与⾮绝对定位元素的百分⽐计算的区别](#)
  - [83.⽆依赖绝对定位是什么？](#)
	 
- [优化](#)
  - [css优化、提⾼性能的⽅法 70 CSS优化、提⾼性能的⽅法有哪些](#)
  - [25 CSS在性能优化⽅⾯的实践](#)

- [实现](#)
  - [103.实现⼀个三⻆形](#)
  - [14.⽤纯 CSS 创建⼀个三⻆形的原理是什么？ 59 ⽤纯CSS创建⼀个三⻆形的原理是什么](#)
  - [102.实现⼀个宽⾼⾃适应的正⽅形](#)
  - [104.⼀个⾃适应矩形，⽔平垂直居中，且宽⾼⽐为 2:1](#)
  - [15.⼀个满屏品字布局如何设计?	 60 ⼀个满屏 品 字布局 如何设计?](#)
  - [66.画⼀条 0.5px 的线](#)
  - [37 请⽤CSS写⼀个简单的幻灯⽚效果⻚⾯](#)
  - [49.让⻚⾯⾥的字体变清晰，变细⽤ CSS 怎么做？．		 87 让⻚⾯⾥的字体变清晰，变细⽤
CSS怎么做？（IOS⼿机浏览器字体⻮轮设置）](#)
  - [50 左边宽度固定，右边⾃适应](#)
  - [57.有⼀个⾼度⾃适应的 div，⾥⾯有两个 div，⼀个⾼度 100px，希望另⼀个填满剩下的⾼
度。90 ⼀个⾼度⾃适应的div，⾥⾯有两个div，⼀个⾼度100px，希望另⼀个填满剩下的⾼度](#)
  - [54.如果需要⼿动写动画，你认为最⼩时间间隔是多久，为什么？（阿⾥）21 如果需要⼿动写
动画，你认为最⼩时间间隔是多久，为什么？（阿⾥）](#)
  - [49 说⼀说css3的animation](#)
  - [26 CSS3动画（简单动画的实现，如旋转等）](#)
  - [52 如何实现⼩于12px的字体效果](#)

- [浮动](#)
  - [29.请解释⼀下为什么需要清除浮动？清除浮动的⽅式](#)
  - [30.使⽤ clear 属性清除浮动的原理？](#)
  - [31.zoom:1 的清除浮动原理?](#)
  - [7 清除浮动的⼏种⽅式，各⾃的优缺点](#)
  - [14 谈谈浮动和清除浮动](#)
  - [69 浮动元素引起的问题](#)
  - [86 设置元素浮动后，该元素的 display 值会如何变化](#)

- [浏览器](#)
  - [35.浏览器是怎样解析 CSS 选择器的？ 71 浏览器是怎样解析CSS选择器的](#)
  - [59.浏览器如何判断是否⽀持 webp 格式图⽚](#)
  - [17.经常遇到的浏览器的兼容性有哪些？原因，解决⽅法是什么，常⽤ hack 的技巧？](#)
  - [53 css hack原理及常⽤hack](#)
  - [67 经常遇到的浏览器的JS兼容性有哪些？解决⽅法是什么](#)
  - [36.在⽹⻚中应该使⽤奇数还是偶数的字体？为什么呢？ 19 在⽹⻚中的应该使⽤奇数还是偶
数的字体？为什么呢？ 72 在⽹⻚中的应该使⽤奇数还是偶数的字体](#)
  - [21.CSS ⾥的 visibility 属性有个 collapse 属性值是⼲嘛⽤的？在不同浏览器下以后什么区别？](#)
  - [47.如何修改 chrome 记住密码后⾃动填充表单的⻩⾊背景？82 如何修改Chrome记住密码后
⾃动填充表单的⻩⾊背景	](#)
  - [48.怎么让 Chrome ⽀持⼩于 12px 的⽂字？](#)
  - [63 iOS safari 如何阻⽌“橡⽪筋效果”](#)

- [标签、属性](#)
  - [84.absolute 与 overflow 的关系？](#)
  - [41.absolute 的 containingblock（包含块）计算⽅式跟正常流有什么不同](#)
  - [39.简单说⼀下 css3 的 all 属性](#)
  - [78.border 的特殊性？](#)
  - [85.clip 裁剪是什么？](#)
  - [10.display 有哪些值？说明他们的作⽤。 10 display有哪些值？说明他们的作⽤](#)
  - [2 display: none;与visibility: hidden;的区别](#)
  - [25.'display'、'position'和'float'的相互关系？ 6 display、float、position的关系](#)
  - [16 display:inline-block 什么时候不会显示间隙？(携程)](#)
  - [89 display:inline-block 什么时候会显示间隙](#)
  - [91.font-weight 的特殊性？](#)
  - [50.font-style 属性中 italic 和 oblique 的区别？](#)
  - [88 font-style 属性 oblique 是什么意思	 ](#)
  - [42.对于 hasLayout 的理解？](#)
  - [55.如何让去除 inline-block 元素间间距？](#)
  - [52.layout viewport、visual viewport 和 ideal viewport 的区别？](#)
  - [93.letter-spacing 与字符间距？](#)
  - [18·li与 li 之间有看不⻅的空⽩间隔是什么原因引起的？有什么解决办法？ 61 li与li之间有看不
⻅的空⽩间隔是什么原因引起的？有什么解决办法](#)
  - [84 你对 line-height 是如何理解的](#)
  - [80.line-height 的特殊性？](#)
  - [85 line-height 三种赋值⽅式有何区别？（带单位、纯数字、百分⽐）](#)
  - [3 link与@import的区别](#)
  - [37.margin 和 padding 分别适合什么场景使⽤？73 margin和padding分别适合什么场景使⽤](#)
  - [76.margin:auto 的填充规则？](#)
  - [77.margin ⽆效的情形](#)
  - [70.min-width/max-width 和 min-height/max-height 属性间的覆盖规则？](#)
  - [82.overflow 的特殊性？](#)
  - [56.overflow:scroll 时不能平滑滚动的问题怎么处理？](#)
  - [11.position 的值 relative 和 absolute 定位原点是？ 15 position的值， relative和absolute定
位原点是](#)
  - [53.position:fixed;在 android 下⽆效怎么处理？](#)
  - [86.relative 的特殊性？](#)
  - [67.transition 和 animation 的区别](#)
  - [61.style 标签写在 body 后与 body 前有什么区别？](#)
  - [92.text-indent 的特殊性？](#)
  - [81.vertical-align 的特殊性？](#)
  - [22.width:auto 和 width:100\x 的区别](#)
  - [95.white-space 与换⾏和空格的控制？](#)
  - [94.word-spacing 与单词间距？](#)
  - [79.什么是基线和 x-height？](#)

- [样式](#)
  - [初始化](#)
    - [19.为什么要初始化 CSS 样式？	 8 为什么要初始化CSS样式? 62 为什么要初始化
CSS样式](#)
    - [40.为什么不建议使⽤统配符初始化 css 样式。](#)
  - [38.抽离样式模块怎么写，说出思路，有⽆实践经验？[阿⾥航旅的⾯试题]。74 抽离样式模块
怎么写，说出思路](#)
  - [45.什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的 IE？（待深⼊了
解）77 什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE](#)
  - [46.视差滚动效果，如何给每⻚做不同的动画？（回到顶部，向下滑动要再次出现，和只出现
⼀次分别怎么做？） 78 什么是视差滚动效果，如何给每⻚做不同的动画](#)
  - [43.元素竖向的百分⽐设定是相对于容器的⾼度吗？](#)
  - [51.设备像素、css 像素、设备独⽴像素、dpr、ppi 之间的区别？](#)
  - [44.全屏滚动的原理是什么？⽤到了 CSS 的哪些属性？（待深⼊实践）76 全屏滚动的原理是
什么？ ⽤到了CSS的那些属性](#)
  - [105.你知道 CSS 中不同属性设置为百分⽐\x 时对应的计算基准？](#)
  - [69.为什么 height:100\x 会⽆效？](#)
  - [75 元素竖向的百分⽐设定是相对于容器的⾼度吗](#)
  - [18 ⾏内元素float:left后是否变为块级元素？](#)
  - [42 px和em的区别](#)
  - [39 rgba()和opacity的透明效果有什么不同？64 rgba() 和 opacity 的透明效果有什么不同](#)

- [伪类](#)
  - [4.伪类与伪元素的区别 34 伪类和伪元素的区别 80 伪元素和伪类的区别和作⽤．](#)
  - [7.关于伪类 LVHA 的解释?](#)
  - [3.::before 和:after 中双冒号和单冒号有什么区别？解释⼀下这 2 个伪元素的作⽤。20 ::before 
和 :after中双冒号和单冒号 有什么区别？解释⼀下这2个伪元素的作⽤ 81 ::before 和 :after 中双冒
号和单冒号有什么区别](#)
  - [79 a标签上四个伪类的执⾏顺序是怎么样的](#)

- [概念](#)
  - [层叠](#)
    - [87.什么是层叠上下⽂？](#)
    - [88.什么是层叠⽔平？](#)
    - [89.元素的层叠顺序？](#) 	 
    - [90.层叠准则？](#)

  - [替换元素](#)
    - [73.替换元素是什么？](#)
    - [74.替换元素的计算规则？](#)
    - [75.content 与替换元素的关系？](#)
    - [44 知道css有个content属性吗？有什么作⽤？有什么应⽤？](#)
    - [65 css 属性 content 有什么作⽤](#)
  - [28.IFC 是什么？](#)
  - [20.包含块是什么，对于包含块的理解?](#)
  - [68.⾸选最⼩宽度是什么？](#)
  - [72.幽灵空⽩节点是什么？](#)
  - [60. Cookie 隔离是什么？（或者说：请求资源的时候不要让它带 cookie 怎么做）](#)

- [其他](#)
  - [12..CSS3 有哪些新特性？（根据项⽬回答） 9 css3有哪些新特性](#)
    - [8.CSS3 新增伪类有那些？ 57 CSS3新增伪类有那些](#)
  - [5.CSS 中哪些属性可以继承？ 54 CSS有哪些继承属性 56 CSS选择符有哪些？哪些属性可
以继承](#)
  - [22 CSS合并⽅法](#)
  - [63.阐述⼀下 CSSSprites,雪碧图 1 css sprite是什么,有什么优缺点](#)
  - [62.什么是 CSS 预处理器/后处理器？](#)
    - [33.使⽤ CSS 预处理器吗？喜欢哪个？](#)
  - [margin重叠 38 什么是外边距重叠？重叠的结果是什么？](#)
  - [55 外边距折叠(collapsing margins)](#)
  - [隐藏](#)
    - [96.隐藏元素的 background-image 到底加不加载？](#)
    - [97.如何实现单⾏／多⾏⽂本溢出的省略（...）？](#)
    - [98.常⻅的元素隐藏⽅式？](#)
    - [63 请列举⼏种隐藏元素的⽅法](#)
  - [图⽚](#)
    - [58.png、jpg、gif 这些图⽚格式解释⼀下，分别什么时候⽤。有没有了解过 webp？](#)
    - [24.简单介绍使⽤图⽚ base64 编码的优点和缺点。27 base64的原理及优缺点 35 
base64的使⽤](#)
    - [83 ⽹站图⽚⽂件，如何点击下载？⽽⾮点击预览](#)
    - [17 PNG\GIF\JPG的区别及如何选](#)
  - [48 重绘和回流（重排）是什么，如何避免？](#)
  - [4 什么是FOUC?如何避免](#)
  - [47 如何使⽤CSS实现硬件加速？](#)
  - [32 ⾃定义字体的使⽤场景](#)
  - [33 如何美化CheckBox](#)
  - [43 Sass、LESS是什么？⼤家为什么要使⽤他们？](#)
  - [29 stylus/sass/less区别](#)
  - [30 postcss的作用](#)



#### margin重叠

```
margin重叠指的是在垂直方向上，两个相邻元素的margin发生重叠的情况。

一般来说可以分为四种情形：
（1）第一种是相邻兄弟元素的marin-bottom和margin-top的值发生重叠。这种情况下我们可以通过设置其中一个元素为BFC来解决。
（2）第二种是父元素的margin-top和子元素的margin-top发生重叠。它们发生重叠是因为它们是相邻的，所以
我们可以通过这一点来解决这个问题。我们可以为父元素设置border-top、padding-top值来分隔它们，
当然我们也可以将父元素设置为BFC来解决。
（3）第三种是高度为auto的父元素的margin-bottom和子元素的margin-bottom发生重叠。
它们发生重叠一个是因为它们相邻，一个是因为父元素的高度不固定。因此我们可以
为父元素设置border-bottom、padding-bottom来分隔它们，也可以为父元素设置一个高度，
max-height和min-height也能解决这个问题。当然将父元素设置为BFC是最简单的方法。
（4）第四种情况，是没有内容的元素，自身的margin-top和margin-bottom发生的重叠。
我们可以通过为其设置border、padding或者高度来解决这个问题。
```

```
块级元素的上外边距（margin-top）与下外边距（margin-bottom）有时会合并为单个外边距，这样的现象称为“margin合并”。
产生折叠的必备条件：margin必须是邻接的!

而根据w3c规范，两个margin是邻接的必须满足以下条件：
•必须是处于常规文档流（非float和绝对定位）的块级盒子，并且处于同一个BFC当中。
•没有线盒，没有空隙，没有padding和border将他们分隔开
•都属于垂直方向上相邻的外边距，可以是下面任意一种情况
•元素的margin-top与其第一个常规文档流的子元素的margin-top
•元素的margin-bottom与其下一个常规文档流的兄弟元素的margin-top
•height为auto的元素的margin-bottom与其最后一个常规文档流的子元素的margin-bottom
•高度为0并且最小高度也为0，不包含常规文档流的子元素，并且自身没有建立新的BFC的元素的margin-top和margin-bottom


margin合并的3种场景：
（1）相邻兄弟元素margin合并。
解决办法：
•设置块状格式化上下文元素（BFC）

（2）父级和第一个/最后一个子元素的margin合并。
解决办法：
对于margin-top合并，可以进行如下操作（满足一个条件即可）：
•父元素设置为块状格式化上下文元素；
•父元素设置border-top值；
•父元素设置padding-top值；
•父元素和第一个子元素之间添加内联元素进行分隔。

对于margin-bottom合并，可以进行如下操作（满足一个条件即可）：
•父元素设置为块状格式化上下文元素；
•父元素设置border-bottom值；
•父元素设置padding-bottom值；
•父元素和最后一个子元素之间添加内联元素进行分隔；
•父元素设置height、min-height或max-height。

（3）空块级元素的margin合并。
解决办法：
•设置垂直方向的border；
•设置垂直方向的padding；
•里面添加内联元素（直接Space键空格是没用的）；
•设置height或者min-height。
```

### 优化

#### css优化、提高性能的方法

```
加载性能：
（1）css压缩：将写好的css进行打包压缩，可以减少很多的体积。
（2）css单一样式：当需要下边距和左边距的时候，很多时候选择:margin:top 0 bottom 0;
但margin-bottom:bottom;margin-left:left;执行的效率更高。
（3）减少使用@import,而建议使用link，因为后者在页面加载时一起加载，前者是等待页面加载完成之后再进行加载。

选择器性能：
（1）关键选择器（key selector）。选择器的最后面的部分为关键选择器（即用来匹配目标元素的部分）。
CSS选择符是从右到左进行匹配的。当使用后代选择器的时候，浏览器会遍历所有子元素来确定是否是指定的元素等等；
（2）如果规则拥有ID选择器作为其关键选择器，则不要为规则增加标签。
过滤掉无关的规则（这样样式系统就不会浪费时间去匹配它们了）。
（3）避免使用通配规则，如*{}计算次数惊人！只对需要用到的元素进行选择。
（4）尽量少的去对标签进行选择，而是用class。
（5）尽量少的去使用后代选择器，降低选择器的权重值。后代选择器的开销是最高的，
尽量将选择器的深度降到最低，最高不要超过三层，更多的使用类来关联每一个标签元素。
（6）了解哪些属性是可以通过继承而来的，然后避免对这些属性重复指定规则。

渲染性能：
（1）慎重使用高性能属性：浮动、定位。
（2）尽量减少页面重排、重绘。
（3）去除空规则：｛｝。空规则的产生原因一般来说是为了预留样式。去除这些空规则无疑能减少css文档体积。
（4）属性值为0时，不加单位。
（5）属性值为浮动小数0.**，可以省略小数点之前的0。
（6）标准化各种浏览器前缀：带浏览器前缀的在前。标准属性在后。
（7）不使用@import前缀，它会影响css的加载速度。
（8）选择器优化嵌套，尽量避免层级过深。
（9）css雪碧图，同一页面相近部分的小图标，方便使用，减少页面的请求次数，
但是同时图片本身会变大，使用时，优劣考虑清楚，再使用。
（10）正确使用display的属性，由于display的作用，某些样式组合会无效，徒增样式体积的同时也影响解析性能。
（11）不滥用web字体。对于中文网站来说WebFonts可能很陌生，国外却很流行。
web fonts通常体积庞大，而且一些浏览器在下载web fonts时会阻塞页面渲染损伤性能。

可维护性、健壮性：
（1）将具有相同属性的样式抽离出来，整合并通过class在页面中进行使用，提高css的可维护性。
（2）样式与内容分离：将css代码定义到外部css中。
```

CSS在性能优化方面的实践：
```
css压缩与合并、Gzip压缩
css文件放在head里、不要用@import
尽量用缩写、避免用滤镜、合理使用选择器
```

```
多个css合并，尽量减少HTTP请求
将css文件放在页面最上面
移除空的css规则
避免使用CSS表达式
选择器优化嵌套，尽量避免层级过深
充分利用css继承属性，减少代码量
抽象提取公共样式，减少代码量
属性值为0时，不加单位
属性值为小于1的小数时，省略小数点前面的0
css雪碧图
```





## 布局

65.⼏种常⻅的 CSS 布局
  ### 65.⼏种常⻅的 CSS 布局

   #### BFC
```
BFC指的是块级格式化上下文，一个元素形成了BFC之后，那么它内部元素产生的布局不会影响到外部元素，
外部元素的布局也不会影响到BFC中的内部元素。一个BFC就像是一个隔离区域，和其他区域互不影响。

一般来说根元素是一个BFC区域，浮动和绝对定位的元素也会形成BFC，display属性的值为inline-block、
flex这些属性时也会创建BFC。还有就是元素的overflow的值不为visible时都会创建BFC。

创建BFC（触发BFC）:
（1）根元素或包含根元素的元素
（2）浮动元素float＝left|right或inherit（≠none）
（3）绝对定位元素position＝absolute或fixed
（4）display＝inline-block|flex|inline-flex|table-cell或table-caption
（5）overflow＝hidden|auto或scroll(≠visible)

开发中的应用：
阻止margin重叠
可以包含浮动元素 —— 清除内部浮动(清除浮动的原理是两个 div都位于同一个 BFC 区域之中)
自适应两栏布局
可以阻止元素被浮动元素覆盖
```

```
BFC布局与普通文档流布局区别：
普通文档流布局:
浮动的元素是不会被父级计算高度
非浮动元素会覆盖浮动元素的位置
margin会传递给父级元素
两个相邻元素上下的margin会重叠

BFC布局规则:
浮动的元素会被父级计算高度(父级元素触发了BFC)
非浮动元素不会覆盖浮动元素的位置(非浮动元素触发了BFC)
margin不会传递给父级(父级触发BFC)
属于同一个BFC的两个相邻元素上下margin会重叠
```

```
块格式化上下文（Block Formatting Context，BFC）是Web页面的可视化CSS渲染的一部分，
是布局过程中生成块级盒子的区域，也是浮动元素与其他元素的交互限定区域。

通俗来讲
•BFC是一个独立的布局环境，可以理解为一个容器，在这个容器中按照一定规则进行物品摆放，并且不会影响其它环境中的物品。
•如果一个元素符合触发BFC的条件，则BFC中的元素布局不受外部影响。
```

   #### Flexbox弹性盒布局
```
flex布局是CSS3新增的一种布局方式，我们可以通过将一个元素的display属性值
设置为flex从而使它成为一个flex容器，它的所有子元素都会成为它的项目。

一个容器默认有两条轴，一个是水平的主轴，一个是与主轴垂直的交叉轴。
我们可以使用flex-direction来指定主轴的方向。我们可以使用justify-content来
指定元素在主轴上的排列方式，使用align-items来指定元素在交叉轴上的排列方式。
还可以使用flex-wrap来规定当一行排列不下时的换行方式。

对于容器中的项目，我们可以使用order属性来指定项目的排列顺序，
还可以使用flex-grow来指定当排列空间有剩余的时候，项目的放大比例。
还可以使用flex-shrink来指定当排列空间不足时，项目的缩小比例。
```

```
Flex是FlexibleBox的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。

任何一个容器都可以指定为Flex布局。行内元素也可以使用Flex布局。注意，
设为Flex布局以后，子元素的float、clear和vertical-align属性将失效。

采用Flex布局的元素，称为Flex容器（flex container），简称"容器"。
它的所有子元素自动成为容器成员，称为Flex项目（flex item），简称"项目"。

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis），项目默认沿主轴排列。

以下6个属性设置在容器上。
（1）flex-direction属性决定主轴的方向（即项目的排列方向）。
（2）flex-wrap属性定义，如果一条轴线排不下，如何换行。
（3）flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
（4）justify-content属性定义了项目在主轴上的对齐方式。
（5）align-items属性定义项目在交叉轴上如何对齐。
（6）align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

以下6个属性设置在项目上。
（1）order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
（2）flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
（3）flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
（4）flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间。浏览器根据这个属性，
计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
（5）flex属性是flex-grow，flex-shrink和flex-basis的简写，默认值为0 1 auto。
（6）align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。
默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
```

   #### 流体布局
```
流体布局通俗的讲就像水上偏流的“盒子”一样，哪有缝隙往哪里流动，前提是缝隙放的下“盒子”的宽度，
流体布局可以铺满屏幕

实现：
.left {
	float: left;
	width: 100px;
	height: 200px;
	background: red;
}
.right {
	float: right;
	width: 200px;
	height: 200px;
	background: blue;
}
.main {
	margin-left: 120px;
	margin-right: 220px;
	height: 200px;
	background: green;
}
<div class="container">
    <div class="left"></div>
    <div class="right"></div>
    <div class="main"></div>
</div>
```

   #### 圣杯布局
```
要求：三列布局；中间主体内容前置，且宽度自适应；两边内容定宽
好处：重要的内容放在文档流前面可以优先渲染
原理：利用相对定位、浮动、负边距布局，而不添加额外标签

实现：
  .container {
      padding-left: 150px;
      padding-right: 190px;
  }
  .main {
      float: left;
      width: 100%;
  }
  .left {
      float: left;
      width: 190px;
      margin-left: -100%;
      position: relative;
      left: -150px;
  }
  .right {
      float: left;
      width: 190px;
      margin-left: -190px;
      position: relative;
      right: -190px;
  }
<div class="container">
	<div class="main"></div>
	<div class="left"></div>
	<div class="right"></div>
</div>
```

   #### 双⻜翼布局
```
双飞翼布局：对圣杯布局（使用相对定位，对以后布局有局限性）的改进，消除相对定位布局
原理：主体元素上设置左右边距，预留两翼位置。左右两栏使用浮动和负边距归位，消除相对定位。

实现：
.container {
    /*padding-left:150px;*/
    /*padding-right:190px;*/
}
.main-wrap {
    width: 100%;
    float: left;
}
.main {
    margin-left: 150px;
    margin-right: 190px;
}
.left {
    float: left;
    width: 150px;
    margin-left: -100%;
    /*position: relative;*/
    /*left:-150px;*/
}
.right {
    float: left;
    width: 190px;
    margin-left: -190px;
    /*position:relative;*/
    /*right:-190px;*/
}
<div class="content">
    <div class="main"></div>
</div>
<div class="left"></div>
<div class="right"></div>
```
    - [36 ⾃适应布局](#)
   #### ⾃适应布局
```
左侧浮动或者绝对定位，然后右侧margin撑开
使用<div>包含，然后靠负margin形成bfc
使用flex
```

  ### 实现

   #### css实现上下固定中间自适应布局

```css
利用绝对定位实现body {
  padding: 0;
  margin: 0;
}

.header {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100px;
  background: red;
}

.container {
  position: absolute;
  top: 100px;
  bottom: 100px;
  width: 100%;
  background: green;
}

.footer {
  position: absolute;
  bottom: 0;
  height: 100px;
  width: 100%;
  background: red;
}

利用flex布局实现html,
body {
  height: 100%;
}

body {
  display: flex;
  padding: 0;
  margin: 0;
  flex-direction: column;
}

.header {
  height: 100px;
  background: red;
}

.container {
  flex-grow: 1;
  background: green;
}

.footer {
  height: 100px;
  background: red;
}
```

   #### css两栏布局的实现
```
两栏布局一般指的是页面中一共两栏，左边固定，右边自适应的布局，一共有四种实现的方式。

以左边宽度固定为 200px 为例

（1）利用浮动，将左边元素宽度设置为 200px，并且设置向左浮动。将右边元素的 
margin-left 设置为 200px，宽度设置为 auto（默认为 auto，撑满整个父元素）。

（2）第二种是利用flex布局，将左边元素的放大和缩小比例设置为 0，基础大小设置为200px。
     将右边的元素的放大比例设置为 1，缩小比例设置为 1，基础大小设置为 auto。

（3）第三种是利用绝对定位布局的方式，将父级元素设置相对定位。左边元素设置为 
absolute定位，并且宽度设置为200px。将右边元素的 margin-left 的值设置为200px。

（4）第四种还是利用绝对定位的方式，将父级元素设置为相对定位。左边元素宽度
设置为 200px，右边元素设置为绝对定位，左边定位为 200px，其余方向定位为 0。
```

```css
/*（1）利用浮动，将左边元素宽度设置为200px，并且设置向左浮动。将右边元素
的margin-left设置为200px，宽度设置为auto（默认为auto，撑满整个父元素）。*/

.outer {
  height: 100px;
}

.left {
  float: left;

  height: 100px;
  width: 200px;

  background: tomato;
}

.right {
  margin-left: 200px;

  width: auto;
  height: 100px;

  background: gold;
}

/*（2）第二种是利用flex布局，将左边元素的放大和缩小比例设置为0，基础大小设置
为200px。将右边的元素的放大比例设置为1，缩小比例设置为1，基础大小设置为auto。*/

.outer {
  display: flex;

  height: 100px;
}

.left {
  flex-shrink: 0;
  flex-grow: 0;
  flex-basis: 200px;

  background: tomato;
}

.right {
  flex: auto;
  /*11auto*/

  background: gold;
}

/*（3）第三种是利用绝对定位布局的方式，将父级元素设置相对定位。左边元素设置为
absolute定位，并且宽度设置为200px。将右边元素的margin-left的值设置为200px。*/
.outer {
  position: relative;

  height: 100px;
}

.left {
  position: absolute;

  width: 200px;
  height: 100px;

  background: tomato;
}

.right {
  margin-left: 200px;
  height: 100px;

  background: gold;
}

/*（4）第四种还是利用绝对定位的方式，将父级元素设置为相对定位。左边元素宽度
设置为200px，右边元素设置为绝对定位，左边定位为200px，其余方向定位为0。*/
.outer {
  position: relative;

  height: 100px;
}

.left {
  width: 200px;
  height: 100px;

  background: tomato;
}

.right {
  position: absolute;

  top: 0;
  right: 0;
  bottom: 0;
  left: 200px;

  background: gold;
}
```

   #### css三栏布局的实现
```
三栏布局一般指的是页面中一共有三栏，左右两栏宽度固定，中间自适应的布局，一共有五种实现方式。

这里以左边宽度固定为100px，右边宽度固定为200px为例。

（1）利用绝对定位的方式，左右两栏设置为绝对定位，中间设置对应方向大小的margin的值。

（2）利用flex布局的方式，左右两栏的放大和缩小比例都设置为0，
     基础大小设置为固定的大小，中间一栏设置为auto。

（3）利用浮动的方式，左右两栏设置固定大小，并设置对应方向的浮动。
中间一栏设置左右两个方向的margin值，注意这种方式，中间一栏必须放到最后。

（4）圣杯布局，利用浮动和负边距来实现。父级元素设置左右的padding，三列均设置向左浮动，
    中间一列放在最前面，宽度设置为父级元素的宽度，因此后面两列都被挤到了下一行，
    通过设置margin负值将其移动到上一行，再利用相对定位，定位到两边。
    圣杯布局中间列的宽度不能小于两边任意列的宽度，而双飞翼布局则不存在这个问题。

（5）双飞翼布局，双飞翼布局相对于圣杯布局来说，左右位置的保留是通过中间列的margin值
来实现的，而不是通过父元素的padding来实现的。本质上来说，也是通过浮动和外边距负值来实现的。
```

```css
/*（1）利用绝对定位的方式，左右两栏设置为绝对定位，中间设置对应方向大小的margin的值。*/
.outer {
  position: relative;
  height: 100px;
}

.left {
  position: absolute;

  width: 100px;
  height: 100px;
  background: tomato;
}

.right {
  position: absolute;
  top: 0;
  right: 0;

  width: 200px;
  height: 100px;
  background: gold;
}

.center {
  margin-left: 100px;
  margin-right: 200px;
  height: 100px;
  background: lightgreen;
}

/*（2）利用flex布局的方式，左右两栏的放大和缩小比例都设置为0，
基础大小设置为固定的大小，中间一栏设置为auto*/
.outer {
  display: flex;
  height: 100px;
}

.left {
  flex: 00100px;
  background: tomato;
}

.right {
  flex: 00200px;
  background: gold;
}

.center {
  flex: auto;
  background: lightgreen;
}

/*（3）利用浮动的方式，左右两栏设置固定大小，并设置对应方向的浮动。
中间一栏设置左右两个方向的margin值，注意这种方式，中间一栏必须放到最后。*/
.outer {
  height: 100px;
}

.left {
  float: left;
  width: 100px;
  height: 100px;
  background: tomato;
}

.right {
  float: right;
  width: 200px;
  height: 100px;
  background: gold;
}

.center {
  height: 100px;
  margin-left: 100px;
  margin-right: 200px;
  background: lightgreen;
}

/*（4）圣杯布局，利用浮动和负边距来实现。父级元素设置左右的 padding，三列均设置向左浮动，
中间一列放在最前面，宽度设置为父级元素的宽度，因此后面两列都被挤到了下一行，
通过设置 margin 负值将其移动到上一行，再利用相对定位，定位到两边。*/
.outer {
  height: 100px;
  padding-left: 100px;
  padding-right: 200px;
}

.left {
  position: relative;
  left: -100px;

  float: left;
  margin-left: -100%;

  width: 100px;
  height: 100px;
  background: tomato;
}

.right {
  position: relative;
  left: 200px;

  float: right;
  margin-left: -200px;

  width: 200px;
  height: 100px;
  background: gold;
}

.center {
  float: left;

  width: 100%;
  height: 100px;
  background: lightgreen;
}

/*（5）双飞翼布局，双飞翼布局相对于圣杯布局来说，左右位置的保留是通过中间列的 
margin 值来实现的，而不是通过父元素的 padding 来实现的。
本质上来说，也是通过浮动和外边距负值来实现的。*/

.outer {
  height: 100px;
}

.left {
  float: left;
  margin-left: -100%;

  width: 100px;
  height: 100px;
  background: tomato;
}

.right {
  float: left;
  margin-left: -200px;

  width: 200px;
  height: 100px;
  background: gold;
}

.wrapper {
  float: left;

  width: 100%;
  height: 100px;
  background: lightgreen;
}

.center {
  margin-left: 100px;
  margin-right: 200px;
  height: 100px;
}
```

   #### 列出你所知道可以改变⻚⾯布局的属性
```
position、display、float、width、height、margin、padding、top、left、right
```

   #### css多列等⾼如何实现
```
（1）利用padding-bottom|margin-bottom正负值相抵，不会影响页面布局的特点。
设置父容器设置超出隐藏（overflow:hidden），这样父容器的高度就还是它
里面的列没有设定padding-bottom时的高度，当它里面的任一列高度增加了，
则父容器的高度被撑到里面最高那列的高度，
其他比这列矮的列会用它们的padding-bottom补偿这部分高度差。

（2）利用table-cell所有单元格高度都相等的特性，来实现多列等高。

（3）利用flex布局中项目align-items属性默认为stretch，
如果项目未设置高度或设为auto，将占满整个容器的高度的特性，来实现多列等高。
```

```
在列的父元素上使用这个背景图进行Y轴的铺放，从而实现一种等高列的假像
模仿表格布局等高列效果：兼容性不好，在ie6-7无法正常运行
css3 flexbox 布局： .container{display: flex; align-items: stretch;
```

  ### 移动端

   #### 移动端的布局⽤过媒体查询吗
```
假设你现在正用一台显示设备来阅读这篇文章，同时你也想把它投影到屏幕上，
或者打印出来，而显示设备、屏幕投影和打印等这些媒介都有自己的特点，
CSS就是为文档提供在不同媒介上展示的适配方法

当媒体查询为真时，相关的样式表或样式规则会按照正常的级联规被应用。
当媒体查询返回假，标签上带有媒体查询的样式表仍将被下载（只不过不会被应用）。

包含了一个媒体类型和至少一个使用宽度、高度和颜色等媒体属性来限制样式表范围的表达式。
CSS3加入的媒体查询使得无需修改内容便可以使样式应用于某些特定的设备范围。
```

   #### 使⽤rem布局的优缺点
```
优点：
在屏幕分辨率千差万别的时代，只要将rem与屏幕分辨率关联起来就可以实现页面的整体缩放，
使得在设备上的展现都统一起来了。而且现在浏览器基本都已经支持rem了，兼容性也非常的好。

缺点：
（1）在奇葩的dpr设备上表现效果不太好，比如一些华为的高端机型用rem布局会出现错乱。
（2）使用iframe引用也会出现问题。
（3）rem在多屏幕尺寸适配上与当前两大平台的设计哲学不一致。
    即大屏的出现到底是为了看得又大又清楚，还是为了看的更多的问题。
```

## 盒模型

```
（1）有两种盒子模型：IE盒模型（border-box）、W3C标准盒模型（content-box）
（2）盒模型：分为内容（content）、填充（padding）、边界（margin）、边框（border）四个部分

IE盒模型和W3C标准盒模型的区别：
（1）W3C标准盒模型：属性width，height只包含内容content，不包含border和padding
（2）IE盒模型：属性width，height包含content、border和padding，指的是content+padding+border。

在ie8+浏览器中使用哪个盒模型可以由box-sizing（CSS新增的属性）控制，默认值为content-box，即标准盒模型；
如果将box-sizing设为border-box则用的是IE盒模型。如果在ie6，7，8中DOCTYPE缺失会将盒子模型解释为IE盒子模型。
若在页面中声明了DOCTYPE类型，所有的浏览器都会把盒模型解释为W3C盒模型。
```

```
盒模型都是由四个部分组成的，分别是margin、border、padding和content。
标准盒模型和IE盒模型的区别在于设置width和height时，所对应的范围不同。标准盒模型的width和height属性的范围
只包含了content，而IE盒模型的width和height属性的范围包含了border、padding和content。
一般来说，我们可以通过修改元素的box-sizing属性来改变元素的盒模型。

box-sizing 常用的属性有哪些？分别有什么作用
box-sizing: content-box; 默认的标准(W3C)盒模型元素效果
box-sizing: border-box; 触发怪异(IE)盒模型元素的效果
box-sizing: inherit; 继承父元素 box-sizing 属性的值
```

```
CSS如何设置这两种模型：
/* 设置当前盒子为 标准盒模型（默认） */
box-sizing: content-box;
/* 设置当前盒子为 IE盒模型 */
box-sizing: border-box;
备注：盒子默认为标准盒模型。

JS如何设置、获取盒模型对应的宽和高：
（1）方式一：通过DOM节点的 style 样式获取
element.style.width/height;
缺点：通过这种方式，只能获取行内样式，不能获取内嵌的样式和外链的样式。
这种方式有局限性，但应该了解。

（2）方式二（通用型）
window.getComputedStyle(element).width/height;
方式二能兼容 Chrome、火狐。是通用型方式。

（3）方式三（IE独有的）
element.currentStyle.width/height;
和方式二相同，但这种方式只有IE独有。获取到的即时运行完之后的宽高（三种css样式都可以获取）。

（4）方式四
element.getBoundingClientRect().width/height;
此 api 的作用是：获取一个元素的绝对位置。绝对位置是视窗 viewport 左上角的绝对位置。
此 api 可以拿到四个属性：left、top、width、height。
```

  ### 内联盒模型基本概念
```
（1）内容区域（content area）。内容区域指一种围绕文字看不见的盒子，
其大小仅受字符本身特性控制，本质上是一个字符盒子（character box）；
但是有些元素，如图片这样的替换元素，其内容显然不是文字，
不存在字符盒子之类的，因此，对于这些元素，内容区域可以看成元素自身。

（2）内联盒子（inline box）。“内联盒子”不会让内容成块显示，而是排成一行，
这里的“内联盒子”实际指的就是元素的“外在盒子”，用来决定元素是内联还是块级。
该盒子又可以细分为“内联盒子”和“匿名内联盒子”两类。

（3）行框盒子（line box），每一行就是一个“行框盒子”（实线框标注），
每个“行框盒子”又是由一个一个“内联盒子”组成的。

（4）包含块（containing box），由一行一行的“行框盒子”组成。
```

## 选择符

  ### css选择符
```
（1）id选择器（#myid）
（2）类选择器（.myclassname）
（3）标签选择器（div,h1,p）
（4）后代选择器（h1 p）
（5）相邻后代选择器（子）选择器（ul>li）
（6）兄弟选择器（li~a）
（7）相邻兄弟选择器（li+a）
（8）属性选择器（a[rel="external"]）
（9）伪类选择器（a:hover,li:nth-child）
（10）伪元素选择器（::before、::after）
（11）通配符选择器（*）
```

  ### css优先级算法
```
判断优先级时，首先我们会判断一条属性声明是否有权重，也就是是否在声明后面加上了!important。一条声明如果加上了权重，
那么它的优先级就是最高的，前提是它之后不再出现相同权重的声明。如果权重相同，我们则需要去比较匹配规则的特殊性。

一条匹配规则一般由多个选择器组成，一条规则的特殊性由组成它的选择器的特殊性累加而成。选择器的特殊性可以分为四个等级，
第一个等级是行内样式，为1000，第二个等级是id选择器，为0100，第三个等级是类选择器、伪类选择器和属性选择器，为0010，
第四个等级是元素选择器和伪元素选择器，为0001。规则中每出现一个选择器，就将它的特殊性进行叠加，这个叠加只限于对应的
等级的叠加，不会产生进位。选择器特殊性值的比较是从左向右排序的，也就是说以1开头的特殊性值比所有以0开头的特殊性值要大。
比如说特殊性值为1000的的规则优先级就要比特殊性值为0999的规则高。如果两个规则的特殊性值相等的时候，那么就会根据
它们引入的顺序，后出现的规则的优先级最高。
```

```
CSS的优先级是根据样式声明的特殊性值来判断的。

选择器的特殊性值分为四个等级，如下：
（1）标签内选择符x,0,0,0
（2）ID选择符0,x,0,0
（3）class选择符/属性选择符/伪类选择符	0,0,x,0
（4）元素和伪元素选择符0,0,0,x

计算方法：
（1）每个等级的初始值为0
（2）每个等级的叠加为选择器出现的次数相加
（3）不可进位，比如0,99,99,99
（4）依次表示为：0,0,0,0
（5）每个等级计数之间没关联
（6）等级判断从左向右，如果某一位数值相同，则判断下一位数值
（7）如果两个优先级相同，则最后出现的优先级高，!important也适用
（8）通配符选择器的特殊性值为：0,0,0,0
（9）继承样式优先级最低，通配符样式优先级高于继承样式
（10）!important（权重），它没有特殊性值，但它的优先级是最高的，为了方便记忆，可以认为它的特殊性值为1,0,0,0,0。

计算实例：
（1）#demo a{color: orange;}/*特殊性值：0,1,0,1*/
（2）div#demo a{color: red;}/*特殊性值：0,1,0,2*/

注意：
（1）样式应用时，css会先查看规则的权重（!important），加了权重的优先级最高，当权重相同的时候，会比较规则的特殊性。
（2）特殊性值越大的声明优先级越高。
（3）相同特殊性值的声明，根据样式引入的顺序，后声明的规则优先级高（距离元素出现最近的）
 (4) 部分浏览器由于字节溢出问题出现的进位表现不做考虑

优先级就近原则，同权重情况下样式定义最近者为准
载入样式以最后载入的定位为准
优先级为: !important > id > class > tag; !important 比 内联优先级高
```

  ### CSS不同选择器的权重(CSS层叠的规则)
```
！important规则最重要，大于其它规则
行内样式规则，加1000
对于选择器中给定的各个ID属性值，加100
对于选择器中给定的各个类属性、属性选择器或者伪类选择器，加10
对于选择其中给定的各个元素标签选择器，加1
如果权值一样，则按照样式规则的先后顺序来应用，顺序靠后的覆盖靠前的规则

以下是权重的规则：标签的权重为1，class的权重为10，id的权重为100，以下例子是演示各种定义的权重值：
/*权重为1*/
div{
}
/*权重为10*/
.class1{
}
/*权重为100*/
#id1{
}
/*权重为100+1=101*/
#id1 div{
}
/*权重为10+1=11*/
.class1 div{
}
/*权重为10+10+1=21*/
.class1 .class2 div{
}

如果权重相同，则最后定义的样式会起作用，但是应该避免这种情况出现
```

## 定位

  ### 水平垂直居中
```
一般常见的几种居中的方法有：

对于宽高固定的元素
（1）我们可以利用margin:0 auto来实现元素的水平居中。
（2）利用绝对定位，设置四个方向的值都为0，并将margin设置为auto，由于宽高固定，因此对应方向实现平分，
     可以实现水平和垂直方向上的居中。
（3）利用绝对定位，先将元素的左上角通过top:50%和left:50%定位到页面的中心，
     然后再通过margin负值来调整元素的中心点到页面的中心。
（4）利用绝对定位，先将元素的左上角通过top:50%和left:50%定位到页面的中心，
     然后再通过translate来调整元素的中心点到页面的中心。
（5）使用flex布局，通过align-items:center和justify-content:center设置容器的垂直和
     水平方向上为居中对齐，然后它的子元素也可以实现垂直和水平的居中。

对于宽高不定的元素，上面的后面两种方法，可以实现元素的垂直和水平的居中。
```

水平居中：给 div 设置一个宽度，然后添加 margin:0 auto 属性
```css
div {
  width: 200px;
  margin: 0 auto;
}
```
水平居中，利用 text-align:center 实现
```css
.container {
  background: rgba(0, 0, 0, 0.5);
  text-align: center;
  font-size: 0;
}
.box {
  display: inline-block;
  width: 500px;
  height: 400px;
  background-color: pink;
}
```
让绝对定位的 div 居中
```css
div {
  position: absolute;
  width: 300px;
  height: 300px;
  margin: auto;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background-color: pink; /*方便看效果*/
}
```
水平垂直居中一
```css
/*确定容器的宽高宽500高300的层设置层的外边距div{*/
position: absolute;/*绝对定位*/
width: 500px;
height: 300px;
top: 50%;
left: 50%;
margin: -150px00-250px;/*外边距为自身宽高的一半*/
background-color: pink;/*方便看效果*/
}
```
水平垂直居中二
```css
/*未知容器的宽高，利用`transform`属性*/
div {
  position: absolute; /*相对定位或绝对定位均可*/
  width: 500px;
  height: 300px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: pink; /*方便看效果*/
}
```
水平垂直居中三
```css
/*利用flex布局实际使用时应考虑兼容性*/
.container {
  display: flex;
  align-items: center; /*垂直居中*/
  justify-content: center; /*水平居中*/
}
.containerdiv {
  width: 100px;
  height: 100px;
  background-color: pink; /*方便看效果*/
}
```
水平垂直居中四
```css
/*利用text-align:center和vertical-align:middle属性*/
.container {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  text-align: center;
  font-size: 0;
  white-space: nowrap;
  overflow: auto;
}
.container::after {
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
}
.box {
  display: inline-block;
  width: 500px;
  height: 400px;
  background-color: pink;
  white-space: normal;
  vertical-align: middle;
}
```

  ### ⽔平居中的⽅法
```
元素为行内元素，设置父元素text-align:center
如果元素宽度固定，可以设置左右margin为auto;
绝对定位和移动: absolute + transform
使用flex-box布局，指定justify-content属性为center
display设置为tabel-ceil
```

  ### 垂直居中的⽅法
```
将显示方式设置为表格，display:table-cell,同时设置vertial-align：middle
使用flex布局，设置为align-item：center
绝对定位中设置bottom:0,top:0,并设置margin:auto
绝对定位中固定高度时设置top:50%，margin-top值为高度一半的负值
文本垂直居中设置line-height为height值

如果是单行文本, line-height 设置成和 height 值
.vertical {
    height: 100px;
    line-height: 100px;
  }
  
已知高度的块级子元素，采用绝对定位和负边距
.container {
  position: relative;
}
.vertical {
  height: 300px;  /*子元素高度*/
  position: absolute;
  top:50%;  /*父元素高度50%*/
  margin-top: -150px; /*自身高度一半*/
}

未知高度的块级父子元素居中，模拟表格布局
缺点：IE67不兼容，父级 overflow：hidden 失效
.container {
    display: table;
  }
  .content {
    display: table-cell;
    vertical-align: middle;
  }

新增 inline-block 兄弟元素，设置 vertical-align
	缺点：需要增加额外标签，IE67不兼容
.container {
  height: 100%;/*定义父级高度，作为参考*/
}
.extra .vertical{
  display: inline-block;  /*行内块显示*/
  vertical-align: middle; /*垂直居中*/
}
.extra {
  height: 100%; /*设置新增元素高度为100%*/
}

绝对定位配合 CSS3 位移
.vertical {
  position: absolute;
  top:50%;  /*父元素高度50%*/
  transform:translateY(-50%, -50%);
}

CSS3弹性盒模型
.container {
  display:flex;
  justify-content: center; /*子元素水平居中*/
  align-items: center; /*子元素垂直居中*/
}
```

  - [41 如何垂直居中⼀个浮动元素？](#)
  ### 


  - [58 如何居中div？如何居中⼀个浮动元素？如何让绝对定位的div居中](#)
  ### 


  - [40 css中可以让⽂字在垂直和⽔平⽅向上重叠的两个属性是什么？](#)
  ### 


  - [23.绝对定位元素与⾮绝对定位元素的百分⽐计算的区别](#)
  ### 


  - [83.⽆依赖绝对定位是什么？](#)
  ### 


	 
	 
	 
## 优化

  - [css优化、提⾼性能的⽅法 70 CSS优化、提⾼性能的⽅法有哪些](#)
  ### 
  
  
  - [25 CSS在性能优化⽅⾯的实践](#)



## 实现

  - [103.实现⼀个三⻆形](#)
  ### 
  
  
  
  - [14.⽤纯 CSS 创建⼀个三⻆形的原理是什么？ 59 ⽤纯CSS创建⼀个三⻆形的原理是什么](#)
  - [102.实现⼀个宽⾼⾃适应的正⽅形](#)
  - [104.⼀个⾃适应矩形，⽔平垂直居中，且宽⾼⽐为 2:1](#)
  - [15.⼀个满屏品字布局如何设计?	 60 ⼀个满屏 品 字布局 如何设计?](#)
  - [66.画⼀条 0.5px 的线](#)
  - [37 请⽤CSS写⼀个简单的幻灯⽚效果⻚⾯](#)
  - [49.让⻚⾯⾥的字体变清晰，变细⽤ CSS 怎么做？．		 87 让⻚⾯⾥的字体变清晰，变细⽤
CSS怎么做？（IOS⼿机浏览器字体⻮轮设置）](#)
  - [50 左边宽度固定，右边⾃适应](#)
  - [57.有⼀个⾼度⾃适应的 div，⾥⾯有两个 div，⼀个⾼度 100px，希望另⼀个填满剩下的⾼
度。90 ⼀个⾼度⾃适应的div，⾥⾯有两个div，⼀个⾼度100px，希望另⼀个填满剩下的⾼度](#)
  - [54.如果需要⼿动写动画，你认为最⼩时间间隔是多久，为什么？（阿⾥）21 如果需要⼿动写
动画，你认为最⼩时间间隔是多久，为什么？（阿⾥）](#)
  - [49 说⼀说css3的animation](#)
  - [26 CSS3动画（简单动画的实现，如旋转等）](#)
  - [52 如何实现⼩于12px的字体效果](#)




## 浮动

  - [29.请解释⼀下为什么需要清除浮动？清除浮动的⽅式](#)
  ### 
  
  
  - [30.使⽤ clear 属性清除浮动的原理？](#)
  - [31.zoom:1 的清除浮动原理?](#)
  - [7 清除浮动的⼏种⽅式，各⾃的优缺点](#)
  - [14 谈谈浮动和清除浮动](#)
  - [69 浮动元素引起的问题](#)
  - [86 设置元素浮动后，该元素的 display 值会如何变化](#)



## 浏览器

  - [35.浏览器是怎样解析 CSS 选择器的？ 71 浏览器是怎样解析CSS选择器的](#)
  ### 
  
  
  - [59.浏览器如何判断是否⽀持 webp 格式图⽚](#)
  - [17.经常遇到的浏览器的兼容性有哪些？原因，解决⽅法是什么，常⽤ hack 的技巧？](#)
  - [53 css hack原理及常⽤hack](#)
  - [67 经常遇到的浏览器的JS兼容性有哪些？解决⽅法是什么](#)
  - [36.在⽹⻚中应该使⽤奇数还是偶数的字体？为什么呢？ 19 在⽹⻚中的应该使⽤奇数还是偶
数的字体？为什么呢？ 72 在⽹⻚中的应该使⽤奇数还是偶数的字体](#)
  - [21.CSS ⾥的 visibility 属性有个 collapse 属性值是⼲嘛⽤的？在不同浏览器下以后什么区别？](#)
  - [47.如何修改 chrome 记住密码后⾃动填充表单的⻩⾊背景？82 如何修改Chrome记住密码后
⾃动填充表单的⻩⾊背景	](#)
  - [48.怎么让 Chrome ⽀持⼩于 12px 的⽂字？](#)
  - [63 iOS safari 如何阻⽌“橡⽪筋效果”](#)



## 标签、属性

  - [84.absolute 与 overflow 的关系？](#)
  ### 
  
  
  - [41.absolute 的 containingblock（包含块）计算⽅式跟正常流有什么不同](#)
  - [39.简单说⼀下 css3 的 all 属性](#)
  - [78.border 的特殊性？](#)
  - [85.clip 裁剪是什么？](#)
  - [10.display 有哪些值？说明他们的作⽤。 10 display有哪些值？说明他们的作⽤](#)
  - [2 display: none;与visibility: hidden;的区别](#)
  - [25.'display'、'position'和'float'的相互关系？ 6 display、float、position的关系](#)
  - [16 display:inline-block 什么时候不会显示间隙？(携程)](#)
  - [89 display:inline-block 什么时候会显示间隙](#)
  - [91.font-weight 的特殊性？](#)
  - [50.font-style 属性中 italic 和 oblique 的区别？](#)
  - [88 font-style 属性 oblique 是什么意思	 ](#)
  - [42.对于 hasLayout 的理解？](#)
  - [55.如何让去除 inline-block 元素间间距？](#)
  - [52.layout viewport、visual viewport 和 ideal viewport 的区别？](#)
  - [93.letter-spacing 与字符间距？](#)
  - [18·li与 li 之间有看不⻅的空⽩间隔是什么原因引起的？有什么解决办法？ 61 li与li之间有看不
⻅的空⽩间隔是什么原因引起的？有什么解决办法](#)
  - [84 你对 line-height 是如何理解的](#)
  - [80.line-height 的特殊性？](#)
  - [85 line-height 三种赋值⽅式有何区别？（带单位、纯数字、百分⽐）](#)
  - [3 link与@import的区别](#)
  - [37.margin 和 padding 分别适合什么场景使⽤？73 margin和padding分别适合什么场景使⽤](#)
  - [76.margin:auto 的填充规则？](#)
  - [77.margin ⽆效的情形](#)
  - [70.min-width/max-width 和 min-height/max-height 属性间的覆盖规则？](#)
  - [82.overflow 的特殊性？](#)
  - [56.overflow:scroll 时不能平滑滚动的问题怎么处理？](#)
  - [11.position 的值 relative 和 absolute 定位原点是？ 15 position的值， relative和absolute定
位原点是](#)
  - [53.position:fixed;在 android 下⽆效怎么处理？](#)
  - [86.relative 的特殊性？](#)
  - [67.transition 和 animation 的区别](#)
  - [61.style 标签写在 body 后与 body 前有什么区别？](#)
  - [92.text-indent 的特殊性？](#)
  - [81.vertical-align 的特殊性？](#)
  - [22.width:auto 和 width:100\x 的区别](#)
  - [95.white-space 与换⾏和空格的控制？](#)
  - [94.word-spacing 与单词间距？](#)
  - [79.什么是基线和 x-height？](#)
css哪些属性可以继承](#)


## 样式

  - [初始化](#)
  ### 
  
    - [19.为什么要初始化 CSS 样式？	 8 为什么要初始化CSS样式? 62 为什么要初始化
CSS样式](#)
   #### 
   
   
    - [40.为什么不建议使⽤统配符初始化 css 样式。](#)
  - [38.抽离样式模块怎么写，说出思路，有⽆实践经验？[阿⾥航旅的⾯试题]。74 抽离样式模块
怎么写，说出思路](#)
  - [45.什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的 IE？（待深⼊了
解）77 什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE](#)
  - [46.视差滚动效果，如何给每⻚做不同的动画？（回到顶部，向下滑动要再次出现，和只出现
⼀次分别怎么做？） 78 什么是视差滚动效果，如何给每⻚做不同的动画](#)
  - [43.元素竖向的百分⽐设定是相对于容器的⾼度吗？](#)
  - [51.设备像素、css 像素、设备独⽴像素、dpr、ppi 之间的区别？](#)
  - [44.全屏滚动的原理是什么？⽤到了 CSS 的哪些属性？（待深⼊实践）76 全屏滚动的原理是
什么？ ⽤到了CSS的那些属性](#)
  - [105.你知道 CSS 中不同属性设置为百分⽐\x 时对应的计算基准？](#)
  - [69.为什么 height:100\x 会⽆效？](#)
  - [75 元素竖向的百分⽐设定是相对于容器的⾼度吗](#)
  - [18 ⾏内元素float:left后是否变为块级元素？](#)
  - [42 px和em的区别](#)
  - [39 rgba()和opacity的透明效果有什么不同？64 rgba() 和 opacity 的透明效果有什么不同](#)



## 伪类
  - [4.伪类与伪元素的区别 34 伪类和伪元素的区别 80 伪元素和伪类的区别和作⽤．](#)
  - [7.关于伪类 LVHA 的解释?](#)
  - [3.::before 和:after 中双冒号和单冒号有什么区别？解释⼀下这 2 个伪元素的作⽤。20 ::before 
和 :after中双冒号和单冒号 有什么区别？解释⼀下这2个伪元素的作⽤ 81 ::before 和 :after 中双冒
号和单冒号有什么区别](#)
  - [79 a标签上四个伪类的执⾏顺序是怎么样的](#)



## 概念

  - [层叠](#)
  ### 
  
  
    - [87.什么是层叠上下⽂？](#)
   #### 
   
   
    - [88.什么是层叠⽔平？](#)
    - [89.元素的层叠顺序？](#) 	 
    - [90.层叠准则？](#)

  - [替换元素](#)
    - [73.替换元素是什么？](#)
    - [74.替换元素的计算规则？](#)
    - [75.content 与替换元素的关系？](#)
    - [44 知道css有个content属性吗？有什么作⽤？有什么应⽤？](#)
    - [65 css 属性 content 有什么作⽤](#)
  - [28.IFC 是什么？](#)
  - [20.包含块是什么，对于包含块的理解?](#)
  - [68.⾸选最⼩宽度是什么？](#)
  - [72.幽灵空⽩节点是什么？](#)
  - [60. Cookie 隔离是什么？（或者说：请求资源的时候不要让它带 cookie 怎么做）](#)



## 其他

  - [12..CSS3 有哪些新特性？（根据项⽬回答） 9 css3有哪些新特性](#)
  ### 
  
    - [8.CSS3 新增伪类有那些？ 57 CSS3新增伪类有那些](#)
   #### 
   
   
  - [5.CSS 中哪些属性可以继承？ 54 CSS有哪些继承属性 56 CSS选择符有哪些？哪些属性可
以继承](#)
  - [22 CSS合并⽅法](#)
  - [63.阐述⼀下 CSSSprites,雪碧图 1 css sprite是什么,有什么优缺点](#)
  - [62.什么是 CSS 预处理器/后处理器？](#)
    - [33.使⽤ CSS 预处理器吗？喜欢哪个？](#)
  - [margin重叠 38 什么是外边距重叠？重叠的结果是什么？](#)
  - [55 外边距折叠(collapsing margins)](#)
  - [隐藏](#)
    - [96.隐藏元素的 background-image 到底加不加载？](#)
    - [97.如何实现单⾏／多⾏⽂本溢出的省略（...）？](#)
    - [98.常⻅的元素隐藏⽅式？](#)
    - [63 请列举⼏种隐藏元素的⽅法](#)
  - [图⽚](#)
    - [58.png、jpg、gif 这些图⽚格式解释⼀下，分别什么时候⽤。有没有了解过 webp？](#)
    - [24.简单介绍使⽤图⽚ base64 编码的优点和缺点。27 base64的原理及优缺点 35 
base64的使⽤](#)
    - [83 ⽹站图⽚⽂件，如何点击下载？⽽⾮点击预览](#)
    - [17 PNG\GIF\JPG的区别及如何选](#)
  - [48 重绘和回流（重排）是什么，如何避免？](#)
  - [4 什么是FOUC?如何避免](#)
  - [47 如何使⽤CSS实现硬件加速？](#)
  - [32 ⾃定义字体的使⽤场景](#)
  - [33 如何美化CheckBox](#)
  - [43 Sass、LESS是什么？⼤家为什么要使⽤他们？](#)
  - [29 stylus/sass/less区别](#)
  - [30 postcss的作用](#)

















