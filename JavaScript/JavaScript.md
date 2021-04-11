## JavaScript 面试知识点总结
整理了 JavaScript 面试的部分知识点

### 目录

- [js数据类型](#js数据类型)
  - [js有几种类型的值？你能画一下他们的内存图吗](#js有几种类型的值你能画一下他们的内存图吗)
  - [堆和栈](#堆和栈)
  - [基本数据类型和引用数据类型](#基本数据类型和引用数据类型)
  - [undefined与undeclared区别](#undefined与undeclared区别)
  - [null和undefined区别](#null和undefined区别)
  - [如何获取安全的undefined值](#如何获取安全的undefined值)
  - [Symbol类型的注意点](#Symbol类型的注意点)
  - [js中整数的安全范围是多少](#js中整数的安全范围是多少)

- [js类型判断](#js类型判断)
  - [typeof操作符](#typeof操作符)
    - [typeof NaN的结果是什么](#typeof-NaN的结果是什么)
  - [instanceof](#instanceof)
  - [constructor](#constructor)
  - [Object.prototype.toString.call()](#ObjectprototypetoStringcall)
  - [封装javascript的类型判断函数](#封装javascript的类型判断函数)

- [js类型转换](#js类型转换)
  - [其他值到字符串的转换规则--17. 其他值到字符串的转换规则？](#其他值到字符串的转换规则)
  - [其他值到数字值的转换规则--18. 其他值到数字值的转换规则？](#其他值到数字值的转换规则)
  - [其他值到布尔类型的值的转换规则--19. 其他值到布尔类型的值的转换规则？](#其他值到布尔类型的值的转换规则)
  - [如何将字符串转化为数字，例如'12.3b'--29. 如何将字符串转化为数字，例如 '12.3b'?](#如何将字符串转化为数字例如123b)
  - [什么情况下会发生布尔值的隐式强制类型转换--25. 什么情况下会发生布尔值的隐式强制类型转换？](#什么情况下会发生布尔值的隐式强制类型转换)
  - [Symbol值的强制类型转换--27. Symbol值的强制类型转换？](#Symbol值的强制类型转换)
  - [将浮点数点左边的数每三位添加一个逗号,12000000.11转化为『12,000,000.11』--30. 如何将浮点数点左边的数每三位添加一个逗号，如 12000000.11 转化为『12,000,000.11』?](#将浮点数点左边的数每三位添加一个逗号1200000011转化为1200000011)
  - [解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字,区别--23. 解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字，它们之间的区别是什么？](#解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字区别)

- [js属性](#js属性)
  - [内部属性[[Class]]是什么--4. 内部属性 [[Class]] 是什么？](#内部属性Class是什么)
  - [属性的遍历--141 属性的遍历](#属性的遍历)

- [js操作符](#js操作符)
  - [||和&&操作符的返回值--26. || 和 && 操作符的返回值？](#和操作符的返回值)
  - [==操作符的强制类型转换规则--28. == 操作符的强制类型转换规则？  ](#操作符的强制类型转换规则)
  - [操作符什么时候用于字符串的拼接--24. 操作符什么时候用于字符串的拼接？](#操作符什么时候用于字符串的拼接)
  - [~操作符的作用--22. ~ 操作符的作用？](#操作符的作用)

- [类和对象](#类和对象)
  - [JavaScript如何实现一个类，怎么实例化这个类--115 JavaScript如何实现一个类，怎么实例化这个类](#JavaScript如何实现一个类怎么实例化这个类)
  - [ECMAScript6怎么写class，为什么会出现class这种东西--69. ECMAScript6 怎么写 class，为什么会出现 class 这种东西?  47 ECMAScript6 怎么写class么](#ECMAScript6怎么写class为什么会出现class这种东西)
  - [javascript创建对象的几种方式--21 javascript有哪些方法定义对象  34. javascript 创建对象的几种方式？  34 javascript创建对象的几种方式](#javascript创建对象的几种方式)
  - [如何判断一个对象是否属于某个类--48. 如何判断一个对象是否属于某个类？](#如何判断一个对象是否属于某个类)
  - [如何判断一个对象是否为空对象--159. 如何判断一个对象是否为空对象？](#如何判断一个对象是否为空对象)
  - [怎么判断两个对象相等--79 怎么判断两个对象相等？](#怎么判断两个对象相等)
  - [js有哪些内置对象--5. 介绍 js 有哪些内置对象？  31 介绍js有哪些内置对象 108 介绍JS有哪些内置对象](#js有哪些内置对象)
  - [什么是假值对象--21. 什么是假值对象？](什么是假值对象)
  - [Object.is()与原来的比较操作符“===”、“==”的区别--92. Object.is() 与原来的比较操作符 “===”、“==” 的区别？](#Objectis与原来的比较操作符的区别)
  - [Object.assign()--168. Object.assign()](#Objectassign)
  - [使用Object.defineProperty()来进行数据劫持有什么缺点--110. Object.defineProperty 介绍？  111. 使用 Object.defineProperty() 来进行数据劫持有什么缺点？](#使用ObjectdefineProperty来进行数据劫持有什么缺点)

- [数组和对象](#数组和对象)
  - [如何实现数组的随机排序--33. 如何实现数组的随机排序？](#如何实现数组的随机排序)
  - [快速的让一个数组乱序--65 快速的让一个数组乱序](#快速的让一个数组乱序)
  - [数组去重方法总结--74 数组去重方法总结](#数组去重方法总结)
  - [判断是否是数组--137 判断是否是数组](#判断是否是数组)
  - [如何通过JS判断一个数组--51 如何通过JS判断一个数组](#如何通过JS判断一个数组)
  - [数组的fill方法--76. 数组的 fill 方法？](#数组的fill方法)
  - [数组和对象有哪些原生方法--75. 数组和对象有哪些原生方法，列举一下？](#数组和对象有哪些原生方法)
  - [JS数组和对象的遍历方式，以及几种方式的比较--60 JS 数组和对象的遍历方式，以及几种方式的比较](#JS数组和对象的遍历方式以及几种方式的比较)
  - [JavaScript类数组对象的定义--74. JavaScript 类数组对象的定义？ ](#JavaScript类数组对象的定义)
  - [Array构造函数只有一个参数值时的表现--16. Array 构造函数只有一个参数值时的表现？](#Array构造函数只有一个参数值时的表现)
  - [Array.splice()与Array.splice()的区别--132 Array.splice() 与 Array.splice() 的区别？](#Arraysplice与Arraysplice的区别)
  *- [53. [].forEach.call($$(""),function(a){a.style.outline="1px solid #" (~~(Math.random()(1<<24))).toString(16)}) 能解释一下这段代码的意思吗？](#)
  *- [45. ["1", "2", "3"].map(parseInt) 答案是多少？  37 ["1", "2", "3"].map(parseInt) 答案是多少](#)
  - [map与forEach的区别--53 map与forEach的区别](#map与forEach的区别)
  - [Map和WeakMap结构--132. Map 和 WeakMap 结构？](#Map和WeakMap结构)
  - [Set和WeakSet结构--131. Set 和 WeakSet 结构？](#Set和WeakSet结构)
  *- [{}和[]的valueOf和toString的结果是什么--20. {} 和 [] 的 valueOf 和 toString 的结果是什么？](#{}和[]的valueOf和toString的结果是什么)

- [函数](#函数)
  - [JavaScript中，调用函数有哪几种方式--129 JavaScript 中，调用函数有哪几种方式](#JavaScript中调用函数有哪几种方式)
  - [函数式编程--117. 谈一谈你理解的函数式编程？  54 谈一谈你理解的函数式编程](#函数式编程)
  - [箭头函数与普通函数的区别--55 谈一谈箭头函数与普通函数的区别？](#箭头函数与普通函数的区别)
  - [封装一个函数，参数是定时器的时间，.then执行回调函数--78 封装一个函数，参数是定时器的时间，.then执行回调函数](#封装一个函数参数是定时器的时间then执行回调函数)
  - [函数节流，应用场景和原理--121 什么是函数节流？介绍一下应用场景和原理？](#函数节流应用场景和原理)
  - [isNaN和Number.isNaN函数的区别--15. isNaN 和 Number.isNaN 函数的区别？](#isNaN和NumberisNaN函数的区别)
  - [Javascript全局函数和全局变量--76 Javascript全局函数和全局变量](#Javascript全局函数和全局变量)
  - [什么是闭包，为什么要用它--46. 什么是闭包，为什么要用它？  1 闭包](#什么是闭包，为什么要用它)
  - [使用闭包实现每隔一秒打印--160. 使用闭包实现每隔一秒打印 1,2,3,4](#使用闭包实现每隔一秒打印)
  - [eval是做什么的--39. eval 是做什么的？  35 eval是做什么的](#eval是做什么的)

- [js原型和原型链](#js原型和原型链)
  - [js获取原型的方法](#js获取原型的方法)
  - [Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是](#Javascript中有一个函数执行时对象查找时永远不会去查找原型这个函数是)

- [js继承](#js继承)
  - [Javascript如何实现继承](#Javascript如何实现继承)
  - [原型链继承](#原型链继承)
  - [构造函数继承](#构造函数继承)
  - [实例继承](#实例继承)
  - [拷贝继承](#拷贝继承)
  - [组合继承](#组合继承)
  - [寄生组合继承](#寄生组合继承)
  - [es6使用extends关键字扩展一个类并继承它的行为](#es6使用extends关键字扩展一个类并继承它的行为)
  - [JavaScript继承的几种实现方式](#JavaScript继承的几种实现方式)

- [this对象](#this对象)  38. 谈谈 This 对象的理解。   6 谈谈This对象的理解 101 描述一下this
  - [this指向--56 谈一谈函数中this的指向  136 this指向](#this指向)
  - [.call()和.apply()的区别--73. .call() 和 .apply() 的区别？ ](#call和apply的区别)
  - [手写call、apply及bind函数--97. 手写 call、apply 及 bind 函数](#手写callapply及bind函数)
  - [简单实现Function.bind函数--130 简单实现 Function.bind 函数](#简单实现Functionbind函数)
  - [new操作符具体干了什么呢？如何实现--50. new 操作符具体干了什么呢？如何实现？    8 new操作符具体干了什么呢?](#new操作符具体干了什么呢如何实现)
  - [Javascript的作用域链--37. Javascript 的作用域链？ 2 说说你对作用域链的理解  117 Javascript作用链域](#Javascript的作用域链)
  - [JavaScript中的作用域与变量声明提升--78. JavaScript 中的作用域与变量声明提升？ 113 解释JavaScript中的作用域与变量声明提升  86 谈谈变量提升？](#JavaScript中的作用域与变量声明提升)

- [事件](#事件)
  - [事件是什么？IE与火狐的事件机制有什么区别？如何阻止冒泡--42. 事件是什么？IE 与火狐的事件机制有什么区别？ 如何阻止冒泡？](#事件是什么IE与火狐的事件机制有什么区别如何阻止冒泡)
  - [事件的各个阶段--63 事件的各个阶段](#事件的各个阶段)
  - [事件“捕获”和“冒泡”执行顺序和事件的执行次数--120 介绍事件“捕获”和“冒泡”执行顺序和事件的执行次数](#事件“捕获”和“冒泡”执行顺序和事件的执行次数)
  - [事件代理--4 请解释什么是事件代理](#事件代理)
  - [三种事件模型是什么--43. 三种事件模型是什么？7 事件模型](#三种事件模型是什么)
  - [事件委托--44. 事件委托是什么？](#事件委托)
  - [js的事件循环是什么--95. js 的事件循环是什么？](#js的事件循环是什么)
  - [事件流--96 说说事件流](#事件流)
  - [写一个通用的事件侦听器函数--41. 写一个通用的事件侦听器函数。](#写一个通用的事件侦听器函数)
  - [移动端的点击事件的有延迟，时间是多久，为什么会有？怎么解决这个延时--85. 移动端的点击事件的有延迟，时间是多久，为什么会有？ 怎么解决这个延时？](#移动端的点击事件的有延迟时间是多久为什么会有怎么解决这个延时)

- [浏览器](#浏览器)
  - [从输入URL到看到页面发生的全过程--100 说说从输入URL到看到页面发生的全过程，越详细越好](#从输入URL到看到页面发生的全过程)
  - [浏览器的渲染过程，DOM树和渲染树的区别--111 描述浏览器的渲染过程，DOM树和渲染树的区别](#浏览器的渲染过程DOM树和渲染树的区别)
  - [浏览器的缓存机制--56. 谈一谈浏览器的缓存机制？  81 浏览器缓存  102 说一下浏览器的缓存机制](#浏览器的缓存机制)
  - [Ajax解决浏览器缓存问题--57. Ajax 解决浏览器缓存问题？](#Ajax解决浏览器缓存问题)
  - [常见兼容性问题--22 常见兼容性问题？](#常见兼容性问题)
  - [请求方式](#请求方式)
    - [get和post请求在缓存方面的区别--122. get 和 post 请求在缓存方面的区别](#get和post请求在缓存方面的区别)
    - [get请求传参长度的误区--120. get 请求传参长度的误区](#get请求传参长度的误区)
  - [检测浏览器版本版本有哪些方式--88. 检测浏览器版本版本有哪些方式？  107 检测浏览器版本版本有哪些方式？](#检测浏览器版本版本有哪些方式)
  *- [84. 把 script 标签放在页面的最底部的 body 封闭之前和封闭之后有什么区别？浏览器会如何解析它们？  128 把<script>放在</body>之前和之后有什么区别？浏览器会如何解析它们？](#)
  - [script的位置是否会影响首屏显示时间--112 script 的位置是否会影响首屏显示时间](#script的位置是否会影响首屏显示时间)
  *- [82. 需求：实现一个页面操作不会整页刷新的网站，并且能在浏览器前进、后退时正确响应。给出你的技术实现方案？](#)
  - [如何检测浏览器所支持的最小字体大小--138. 如何检测浏览器所支持的最小字体大小？](#如何检测浏览器所支持的最小字体大小)
  - [开发中常用的几种Content-Type--157. 开发中常用的几种 Content-Type ？](#开发中常用的几种ContentType)
  - [如何判断当前脚本运行在浏览器还是node环境中？（阿里）--83. 如何判断当前脚本运行在浏览器还是 node 环境中？（阿里）](#如何判断当前脚本运行在浏览器还是node环境中阿里)
  - [V8引擎的垃圾回收机制--80. 简单介绍一下 V8 引擎的垃圾回收机制](#V8引擎的垃圾回收机制)
  - [Javascript垃圾回收方法--124 Javascript垃圾回收方法  139 垃圾回收](#Javascript垃圾回收方法)
  - [URL和URI的区别--121. URL 和 URI 的区别？](#URL和URI的区别)
  - [在输入框中如何判断输入的是一个正确的网址--143 在输入框中如何判断输入的是一个正确的网址](#在输入框中如何判断输入的是一个正确的网址)
  - [页面编码和被请求的资源编码如果不一致如何处理--127 页面编码和被请求的资源编码如果不一致如何处理](#页面编码和被请求的资源编码如果不一致如何处理)
  - [加载--138 加载](#加载)
  - [WEB应用从服务器主动推送Data到客户端有那些方式--134 WEB应用从服务器主动推送Data到客户端有那些方式](#WEB应用从服务器主动推送Data到客户端有那些方式)

- [cookie](#cookie)  62. 简单谈一下 cookie ？
  - [如何删除一个cookie--126 如何删除一个cookie](#如何删除一个cookie)
  - [服务器代理转发时，该如何处理cookie--61. 服务器代理转发时，该如何处理 cookie？](#服务器代理转发时该如何处理cookie)
  - [什么是Samesite Cookie属性--105. 什么是 Samesite Cookie 属性？](#什么是Samesite-Cookie属性)

- [面向对象](#面向对象)
  - [什么是面向对象编程及面向过程编程，它们的异同和优缺点--48 什么是面向对象编程及面向过程编程，它们的异同和优缺点 49 面向对象编程思想](#什么是面向对象编程及面向过程编程它们的异同和优缺点)

- [同步和异步](#同步和异步)
  - [同步和异步的区别--58. 同步和异步的区别？   41 同步和异步的区别](#同步和异步的区别)
  - [异步加载JS的方式有哪些--12 异步加载JS的方式有哪些？](#异步加载JS的方式有哪些)
  - [异步编程的实现方式--118. 异步编程的实现方式？ 57 异步编程的实现方式  ](#异步编程的实现方式)
  - [什么是单线程，和异步的关系--87 什么是单线程，和异步的关系](#什么是单线程和异步的关系)
  *- [136. 什么是 Promise 对象，什么是 Promises/A 规范？  23 说说你对promise的了解  99 请手写实现一个promise](#)
  - [手写一个Promise--137. 手写一个 Promise](#手写一个Promise)
  - [defer和async--43 defer和async](#defer和async)

- [模式](#模式)
  - [用过哪些设计模式--18 用过哪些设计模式？](#用过哪些设计模式)
  - [单例模式模式--140. 单例模式模式是什么？](#单例模式模式)
  - [策略模式--141. 策略模式是什么？](#策略模式)
  - [代理模式--142. 代理模式是什么？](#代理模式)
  - [中介者模式--143. 中介者模式是什么？](#中介者模式)
  - [适配器模式--144. 适配器模式是什么？](#适配器模式)
  - [观察者模式和发布订阅模式有什么不同--145. 观察者模式和发布订阅模式有什么不同？](#观察者模式和发布订阅模式有什么不同)
  - [严格模式的限制--44 说说严格模式的限制](#严格模式的限制)
  - [手写一个观察者模式--162. 手写一个观察者模式？](#手写一个观察者模式)

- [模块化](#模块化)
  - [模块化开发怎么做--63. 模块化开发怎么做？  11 模块化开发怎么做？](#模块化开发怎么做)
  - [js的几种模块规范--64. js 的几种模块规范？](#js的几种模块规范)
  - [ES6模块与CommonJS模块、AMD、CMD的差异--66. ES6 模块与 CommonJS 模块、AMD、CMD 的差异。 65. AMD 和 CMD 规范的区别？   27 谈谈你对AMD、CMD的理解  16 说说你对AMD和Commonjs的理解](#ES6模块与CommonJS模块AMDCMD的差异)
  - [JS模块加载器的轮子怎么造，也就是如何实现一个模块加载器--68. JS 模块加载器的轮子怎么造，也就是如何实现一个模块加载器？](#JS模块加载器的轮子怎么造也就是如何实现一个模块加载器)
  - [require模块引入的查找方式--135. require 模块引入的查找方式？](#require模块引入的查找方式)

- [DOM](#DOM)
  - [什么是DOM和BOM--40. 什么是 DOM 和 BOM？](#什么是DOM和BOM)
  - [介绍DOM的发展--118 介绍 DOM 的发展](#介绍DOM的发展)
  - [DOM操作怎样添加、移除、移动、复制、创建和查找节点--71. DOM 操作——怎样添加、移除、移动、复制、创建和查找节点？   怎样添加、移除、移动、复制、创建和查找节点](#DOM操作怎样添加移除移动复制创建和查找节点)
  - [虚拟DOM(Virtual DOM),为什么虚拟DOM比原生DOM快--112. 什么是 虚拟DOM Virtual DOM？为什么 Virtual DOM 比原生 DOM 快？](#虚拟DOMVirtual-DOM为什么虚拟DOM比原生DOM快)
  - [如何比较两个DOM树的差异--113. 如何比较两个 DOM 树的差异？](#如何比较两个DOM树的差异)
  - [介绍DOM0，DOM2，DOM3事件处理方式区别--119 介绍DOM0，DOM2，DOM3事件处理方式区别](#介绍DOM0DOM2DOM3事件处理方式区别)

- [优化](#优化)
  - [项目做过哪些性能优化](#项目做过哪些性能优化)
  - [懒加载 预加载 懒执行](#懒加载-预加载-懒执行)
  - [如何渲染几万条数据并不卡住界面](#如何渲染几万条数据并不卡住界面)
  - [一个列表，假设有100000个数据，这个该怎么办](#一个列表假设有100000个数据这个该怎么办)

- [安全](#安全)
  - [同源](#同源)
    - [JavaScript的同源策略](#JavaScript的同源策略)
    - [浏览器的同源政策](#)
  - [限制](#限制)
  - [跨域](#跨域)
    - [jsonp](#jsonp)
      - [手写一个jsonp](#手写一个jsonp)
    - [postMessage](#postMessage)
    - [CORS](#CORS)
    - [WebSocket](#WebSocket)
    - [proxy代理跨域(最常见)](#proxy代理跨域最常见)
  - [鉴权](#鉴权)
    - [HTTP Basic Authentication](#HTTP-Basic-Authentication)
    - [session-cookie](#sessioncookie)
    - [token验证](#token验证)
    - [OAuth](#OAuth)
  - [常见web安全及防护原理](#常见web安全及防护原理)
  - [什么是XSS攻击？如何防范XSS攻击](#什么是XSS攻击如何防范XSS攻击)
  - [什么是CSRF攻击？如何防范CSRF攻击](#什么是CSRF攻击如何防范CSRF攻击)
  - [SQL注入攻击](#SQL注入攻击)
  - [什么是CSP](#什么是CSP)
  - [什么是点击劫持？如何防范点击劫持](#什么是点击劫持如何防范点击劫持)
  - [哪些操作会造成内存泄漏](#哪些操作会造成内存泄漏)

- [Ajax和axios](#Ajax和axios)
  - [Ajax是什么? 原理？如何创建一个Ajax--55. Ajax 是什么? 如何创建一个 Ajax？  9 Ajax原理](#Ajax是什么原理如何创建一个Ajax)
  - [ajax、axios、fetch区别--105 ajax、axios、fetch区别](#ajaxaxiosfetch区别)

- [概念](#概念)
  - [写JavaScript的基本规范--9. 说几条写 JavaScript 的基本规范？  32 说几条写JavaScript的基本规范  109 说几条写JavaScript的基本规范](#写JavaScript的基本规范)
  - [js的节流与防抖--85 防抖/节流  91. 介绍一下 js 的节流与防抖？](#js的节流与防抖)
  - [js中的深浅拷贝实现--84 深浅拷贝  96. js 中的深浅拷贝实现？](#js中的深浅拷贝实现)
  - [js中的命名规则--166. js 中的命名规则](#js中的命名规则)
  - [对原生Javascript了解程度--58 对原生Javascript了解程度](#对原生Javascript了解程度)
  - [渐进增强和优雅降级--42 渐进增强和优雅降级](#渐进增强和优雅降级)
  - [JavaScript的组成--106 JavaScript的组成](#JavaScript的组成)
  - [如何编写高性能的JavaScript--79. 如何编写高性能的 Javascript ？   110 如何编写高性能的JavaScript](#如何编写高性能的JavaScript)
  - [js语句末尾分号是否可以省略--167. js 语句末尾分号是否可以省略？](#js语句末尾分号是否可以省略)
  - [js延迟加载的方式有哪些--54. js 延迟加载的方式有哪些？  40 js延迟加载的方式有哪些](#js延迟加载的方式有哪些)
  - [使用JS实现获取文件扩展名--90. 使用 JS 实现获取文件扩展名？](#使用JS实现获取文件扩展名)
  - [对web标准、可用性、可访问性的理解--50 对web标准、可用性、可访问性的理解](#对web标准可用性可访问性的理解)
  - [对于JSON的了解--52. 对于 JSON 的了解？  39 JSON 的了解](#对于JSON的了解)
  - [XML和JSON的区别--14 XML和JSON的区别？](#XML和JSON的区别)
  - [JavaScript对象生命周期的理解--97 JavaScript 对象生命周期的理解](#JavaScript对象生命周期的理解)
  - [requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何缓存的？）--67. requireJS 的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何 缓存的？）](#requireJS的核心原理是什么如何动态加载的如何避免多次加载的如何缓存的)
  - [什么是“前端路由”？什么时候适合使用“前端路由”？“前端路由”有哪些优点和缺点--86. 什么是“前端路由”？什么时候适合使用“前端路由”？“前端路由”有哪些优点和缺点？](#什么是前端路由什么时候适合使用前端路由前端路由有哪些优点和缺点)
  - [Polyfill--89. 什么是 Polyfill ？](#Polyfill)
  - [rest参数--128. 什么是 rest 参数？](#rest参数)
  - [Proxy--133. 什么是 Proxy ？](#Proxy)
  - [gulp--61 gulp是什么](#gulp)
  - [web开发中会话跟踪的方法有哪些--29 web开发中会话跟踪的方法有哪些](#web开发中会话跟踪的方法有哪些)
  - [进程间通信的方式--173. 进程间通信的方式？](#进程间通信的方式)
  - [Reflect对象创建目的--134. Reflect 对象创建目的？](#Reflect对象创建目的)

- [ES6](#ES6) 46 谈谈你对ES6的理解
  - [let var const--52 谈一谈let与var的区别  127. let 和 const 的注意点？  64 let var const](#let var const)

- [实现](#实现)
  - [Js动画与CSS动画区别及相应实现--119. Js 动画与 CSS 动画区别及相应实现  59 Js动画与CSS动画区别及相应实现](#Js动画与CSS动画区别及相应实现)
  - [js拖拽功能的实现,对页面某个节点的拖曳如何做？（使用原生JS）--125. js 拖拽功能的实现  75 （设计题）想实现一个对页面某个节点的拖曳？如何做？（使用原生JS）](#js拖拽功能的实现对页面某个节点的拖曳如何做使用原生JS)
  - [使用js实现一个持续的动画效果--77 使用js实现一个持续的动画效果](#使用js实现一个持续的动画效果)
  - [实现点击容器内的图标，图标边框变成border:1px solid red，点击空白处重置--92 实现效果，点击容器内的图标，图标边框变成border 1px solid red，点击空白处重置](#实现点击容器内的图标图标边框变成border1px-solid-red点击空白处重置)
  - [canvas上面随机布着一些黑块，请实现方法，计算canvas上有多少个黑块--98 我现在有一个canvas，上面随机布着一些黑块，请实现方法，计算canvas上有多少个黑块](#canvas上面随机布着一些黑块请实现方法计算canvas上有多少个黑块)
  - [怎么做JS代码Error统计--139. 怎么做 JS 代码 Error 统计？](#怎么做JS代码Error统计)
  - [完成一个Dialog组件，说说你设计的思路？它应该有什么功能--103 现在要你完成一个Dialog组件，说说你设计的思路？它应该有什么功能？](#完成一个Dialog组件说说你设计的思路它应该有什么功能)
  - [js中倒计时的纠偏实现--172. js 中倒计时的纠偏实现？](#js中倒计时的纠偏实现)
  - [函数柯里化的实现--98. 函数柯里化的实现](#函数柯里化的实现)
  - [EventEmitter实现--163. EventEmitter 实现](#EventEmitter实现)
  - [如何查找一篇英文文章中出现频率最高的单词--174. 如何查找一篇英文文章中出现频率最高的单词？](#如何查找一篇英文文章中出现频率最高的单词)
  *- [94 实现Storage，使得该对象为单例，并对localStorage进行封装设置值setItem(key,value)和getItem(key)](#)
  - [获取页面所有的checkbox--67 希望获取到页面中所有的checkbox怎么做？  73 获取页面所有的checkbox](#获取页面所有的checkbox)

- [宏任务和微任务](#宏任务和微任务)
  - [requestAnimationFrame--114. 什么是 requestAnimationFrame ？](#requestAnimationFrame)
  - [为什么使用setTimeout实现setInterval？怎么模拟--126. 为什么使用 setTimeout 实现 setInterval？怎么模拟？](#为什么使用setTimeout实现setInterval怎么模拟)

- [对比](#对比)
  - [addEventListener()和attachEvent()的区别--72 addEventListener()和attachEvent()的区别](#addEventListener和attachEvent的区别)
  - [attribute和property的区别是什么--45 attribute和property的区别是什么](#attribute和property的区别是什么)
  - [caller和callee的区别--104 caller和callee的区别](#caller和callee的区别)
  - [documen.write和innerHTML的区别--70. documen.write 和 innerHTML 的区别？](#documenwrite和innerHTML的区别)
  - [escape,encodeURI,encodeURIComponent区别--93. escape,encodeURI,encodeURIComponent 有什么区别？](#escape,encodeURI,encodeURIComponent区别)
  - [innerHTML与outerHTML的区别--72. innerHTML 与 outerHTML 的区别？](#innerHTML与outerHTML的区别)
  - [Javascript中callee和caller的作用--70 Javascript中callee和caller的作用？](#Javascript中callee和caller的作用)
  - [js代码中的"use strict";是什么意思?使用它区别是什么--47. javascript 代码中的 "use strict"; 是什么意思 ? 使用它区别是什么？ 38 javascript 代码中的"use strict";是什么意思](#js代码中的use-strict是什么意思使用它区别是什么)
  - [mouseover和mouseenter区别--124. mouseover 和 mouseenter 的区别？](#mouseover和mouseenter区别)
  *- [116. offsetWidth/offsetHeight,clientWidth/clientHeight 与 scrollWidth/scrollHeight 的区别？  20 offsetWidth/offsetHeight,clientWidth/clientHeight与scrollWidth/scrollHeight的区别](#)
  - [toPrecision和toFixed和Math.round的区别--101. toPrecision 和 toFixed 和 Math.round 的区别？](#toPrecision和toFixed和Mathround的区别)
  - [Unicode和UTF-8之间的关系--94. Unicode 和 UTF-8 之间的关系？](#Unicode和UTF-8之间的关系)
  - [window.onload和$(document).ready--71 window.onload和$(document).ready](#windowonload和documentready)
  - [区分什么是“客户区坐标”、“页面坐标”、“屏幕坐标”--122 区分什么是“客户区坐标”、“页面坐标”、“屏幕坐标”](#区分什么是客户区坐标页面坐标屏幕坐标)

- [算法](#算法)
  - [常用正则表达式--31. 常用正则表达式  69 正则表达式](#常用正则表达式)
  - [生成随机数的各种方法--32. 生成随机数的各种方法？](#生成随机数的各种方法)
  - [为什么0.1+0.2!=0.3？如何解决这个问题--99. 为什么 0.1+0.2 != 0.3？如何解决这个问题？](#为什么010203如何解决这个问题)
  - [原码、反码和补码的介绍--100. 原码、反码和补码的介绍](#原码反码和补码的介绍)
  - [什么是尾调用，使用尾调用有什么好处--129. 什么是尾调用，使用尾调用有什么好处？](#什么是尾调用使用尾调用有什么好处)
  - [js中不同进制数字的表示方式--12. 在 js 中不同进制数字的表示方式](#js中不同进制数字的表示方式)
  - [Math.ceil和Math.floor--169. Math.ceil 和 Math.floor](#Math.ceil和Math.floor)
  - [[,,,]的长度--77. [,,,] 的长度？](#[,,,]的长度)
  - [js for循环注意点--170. js for 循环注意点](#js-for循环注意点)

- [其他](#其他)
  - [hybrid--89 前端面试之hybrid](#hybrid)
  - [组件化--90 前端面试之组件化](#组件化)
  *- [87. 如何测试前端代码么？ 知道 BDD, TDD, Unit Test 么？ 知道怎么测试你的前端工程么(mocha, sinon, jasmin, qUnit..)？](#)
  - [为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片--142 为什么通常在发送数据埋点请求的时候使用的是 1x1 像素的透明 gif 图片](#为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片)
  - [如何确定页面的可用性时间，什么是Performance API--165. 如何确定页面的可用性时间，什么是 Performance API？](#如何确定页面的可用性时间什么是Performance-API)
  - [event loop--95 说说event loop  ](#event-loop)
  - [Electron--83 尽可能多的说出你对 Electron 的理解](#Electron)
  - [有四个操作会忽略enumerable为false的属性--140 有四个操作会忽略enumerable为false的属性	](#有四个操作会忽略enumerable为false的属性)
  - [164. 一道常被人轻视的前端 JS 面试题](#)
  - [123 解释一下这段代码的意思](#)
  




### js数据类型
```
js基本数据类型：
Undefined、Null、Boolean、Number、String，还有在 ES6 中新增的 Symbol 和 ES10 中新增的 BigInt 类型。
Symbol 代表创建后独一无二且不可变的数据类型，它的出现我认为主要是为了解决可能出现的全局变量冲突的问题。
BigInt 是一种数字类型的数据，它可以表示任意精度格式的整数，使用 BigInt 可以安全地存储和操作大整数，
即使这个数已经超出了 Number 能够表示的安全整数范围。
```

```
js引用数据类型：object、array、function
```

  #### js有几种类型的值
```
js 可以分为两种类型的值，一种是基本数据类型，一种是复杂数据类型。
基本数据类型：undefined、null、boolean、number、string、symbol
复杂数据类型指的是 Object 类型，所有其他的如 Array、Date 
等数据类型都可以理解为 Object 类型的子类。

两种类型间的主要区别是它们的存储位置不同，基本数据类型的值直接保存在栈中，
而复杂数据类型的值保存在堆中，通过使用在栈中保存对应的指针来获取堆中的值。
```

栈：原始数据类型（Undefined、Null、Boolean、Number、String） <br>
堆：引用数据类型（对象、数组和函数）

```
两种类型的区别是：存储位置不同。
原始数据类型直接存储在栈（stack）中的简单数据段，占据空间小、
大小固定，属于被频繁使用数据，所以放入栈中存储。

引用数据类型存储在堆（heap）中的对象，占据空间大、大小不固定。
如果存储在栈中，将会影响程序运行的性能；引用数据类型在栈中存储了指针，
该指针指向堆中该实体的起始地址。当解释器寻找引用值时，
会首先检索其在栈中的地址，取得地址后从堆中获得实体。
```

  #### 堆和栈
```
堆和栈的概念存在于数据结构中和操作系统内存中。

（1）在数据结构中，栈中数据的存取方式为先进后出。而堆是一个优先队列，
是按优先级来进行排序的，优先级可以按照大小来规定。完全二叉树是堆的一种实现方式。
（2）在操作系统中，内存被分为栈区和堆区。

栈区内存由编译器自动分配释放，存放函数的参数值，局部变量的值等。
其操作方式类似于数据结构中的栈。

堆区内存一般由程序员分配释放，若程序员不释放，程序结束时可能由垃圾回收机制回收。
```

  #### undefined与undeclared区别
```
已在作用域中声明但还没有赋值的变量，是 undefined 的。
相反，还没有在作用域中声明过的变量，是 undeclared 的。

对于 undeclared 变量的引用，浏览器会报引用错误，
如 ReferenceError: b is not defined。但是我们可以使用 
typeof 的安全防范机制来避免报错，因为对于 undeclared
（或者 not defined ）变量，typeof 会返回 "undefined"。
```

  #### null和undefined区别
```
首先 Undefined 和 Null 都是基本数据类型，这两个基本数据类型分别都只有一个值，就是 undefined 和 null。

undefined 代表的含义是未定义，null 代表的含义是空对象。一般变量声明了但还没有定义的时候会返回 undefined，null
主要用于赋值给一些可能会返回对象的变量，作为初始化。

undefined 在 js 中不是一个保留字，这意味着我们可以使用 undefined 来作为一个变量名，这样的做法是非常危险的，它
会影响我们对 undefined 值的判断。但是我们可以通过一些方法获得安全的 undefined 值，比如说 void 0。

当我们对两种类型使用 typeof 进行判断的时候，Null 类型化会返回 “object”，这是一个历史遗留的问题。当我们使用双等
号对两种类型的值进行比较时会返回 true，使用三个等号时会返回 false。
```

```
undefined 表示不存在这个值。

undefined :是一个表示"无"的原始值或者说表示"缺少值"，
就是此处应该有一个值，但是还没有定义。当尝试读取时会返回 undefined

例如变量被声明了，但没有赋值时，就等于undefined

null 表示一个对象被定义了，值为“空值”

null : 是一个对象(空对象, 没有任何属性和方法)

例如作为函数的参数，表示该函数的参数不是对象；

在验证null时，一定要使用　=== ，因为 ==无法分别null 和　undefined
```

  #### 如何获取安全的undefined值
```
因为 undefined 是一个标识符，所以可以被当作变量来使用和赋值，
但是这样会影响 undefined 的正常判断。

表达式 void ___ 没有返回值，因此返回结果是 undefined。
void 并不改变表达式的结果，只是让表达式不返回值。

按惯例我们用 void 0 来获得 undefined。
```

  #### Symbol类型的注意点
```
Symbol 函数前不能使用 new 命令，否则会报错。

Symbol 函数可以接受一个字符串作为参数，表示对 Symbol 实例的描述，
主要是为了在控制台显示，或者转为字符串时，比较容易区分。

Symbol 作为属性名，该属性不会出现在 for...in、for...of 循环中，
也不会被 Object.keys()、Object.getOwnPropertyNames()、JSON.stringify() 返回。

Object.getOwnPropertySymbols 方法返回一个数组，
成员是当前对象的所有用作属性名的 Symbol 值。

Symbol.for 接受一个字符串作为参数，然后搜索有没有以该参数作为名称的 Symbol 值。
如果有，就返回这个 Symbol 值，否则就新建并返回一个以该字符串为名称的 Symbol 值。

Symbol.keyFor 方法返回一个已登记的 Symbol 类型值的 key。
```

  #### js中整数的安全范围是多少
```
安全整数指的是，在这个范围内的整数转化为二进制存储的时候不会出现精度丢失，
能够被“安全”呈现的最大整数是 2^53 - 1，即9007199254740991，
在 ES6 中被定义为 Number.MAX_SAFE_INTEGER。
最小整数是-9007199254740991，在 ES6 中被定义为 Number.MIN_SAFE_INTEGER。

如果某次计算的结果得到了一个超过 JavaScript 数值范围的值，
那么这个值会被自动转换为特殊的 Infinity 值。如果某次计算返回了
正或负的 Infinity 值，那么该值将无法参与下一次的计算。
判断一个数是不是有穷的，可以使用 isFinite 函数来判断。
```

### js类型判断

typeof，instanceof，constructor，Object.prototype.toString.call()
```
（1）typeof：
直接在计算机底层基于数据类型的值（二进制）进行检测
typeof null为object原因是对象存在在计算机中，
都是以000开始的二进制存储，所以检测出来的结果是对象
typeof普通对象/数组对象/正则对象/日期对象 都是object
typeof NaN === 'number'
（2）instanceof
检测当前实例是否属于这个类的
底层机制：只要当前类出现在实例的原型上，结果都是true
不能检测基本数据类型
（3）constructor
支持基本类型
constructor可以随便改，也不准
（4）Object.prototype.toString.call([val])
返回当前实例所属类信息

判断 Target 的类型，单单用 typeof 并无法完全满足，这其实并不是 bug，
本质原因是 JS 的万物皆对象的理论。因此要真正完美判断时，我们需要区分对待:
1.基本类型(null): 使用String(null)
2.基本类型(string / number / boolean / undefined / symbol) + function: 直接使用typeof即可
3.其余引用类型(Array / Date / RegExp Error): 调用toString后根据[object XXX]进行判断
很稳的判断封装:
let class2type = {}
'Array Date RegExp Object Error'.split(' ').forEach(e => class2type[ '[object ' + e + ']' ] = e.toLowerCase()) 
function type(obj) {
    if (obj == null) return String(obj)
    return typeof obj === 'object' ? class2type[ Object.prototype.toString.call(obj) ] || 'object' : typeof obj
}
```

  #### typeof操作符
优点：能够快速区分基本数据类型 
缺点：不能将Object、Array和Null区分，都返回object  

（1）对于原始类型来说，除了 null 都可以显示正确的类型
```
Number、String，Undefined、Boolean、Null、
还有在 ES6 中新增的 Symbol 和 ES10 中新增的 BigInt 

typeof 1             // 'number'
typeof '1'           // 'string'
typeof undefined     // 'undefined'
typeof true          // 'boolean'
typeof Symbol()      // 'symbol'
typeof null          // 'object'
PS：为什么null会出现这种情况呢？因为在 JS的最初版本中，
使用的是 32 位系统，为了性能考虑使用低位存储了变量的类型信息，
000 开头代表是对象，然而 null表示为全零，所以将它错误的判断为 object 。
虽然现在的内部类型判断代码已经改变了，但是对于这个Bug却是一直流传下来。
```

（2）typeof 对于对象来说，除了函数都会显示 object，
所以说 typeof 并不能准确判断变量到底是什么类型
```
array、object、function
typeof []             // 'object'
typeof {}             // 'object'
typeof console.log    // 'function'
```

   #### typeof NaN的结果是什么
```
typeof NaN;           // "number"

NaN 意指“不是一个数字”（not a number），NaN 是一个“警戒值”
（sentinel value，有特殊用途的常规值），用于指出数字类型中的错误情况，
即“执行数学运算没有成功，这是失败后返回的结果”。NaN 是一个特殊值，
它和自身不相等，是唯一一个非自反（自反，reflexive，
即 x === x 不成立）的值。而 NaN != NaN为 true。
```

  #### instanceof
```
作用：用于判断实例属于哪个构造函数。
原理：判断实例对象的__proto__属性，和构造函数的prototype属性，
是否为同一个引用（是否指向同一个地址）。instanceof 可以正确的判断对象的类型，
因为内部机制是通过判断对象的原型链中是不是能找到类型的 prototype

优点：能够区分Array、Object和Function，适合用于判断自定义的类实例对象
缺点：Number，Boolean，String基本数据类型不能判断

console.log(2 instanceof Number);                    // false
console.log(true instanceof Boolean);                // false 
console.log('str' instanceof String);                // false  
console.log([] instanceof Array);                    // true
console.log(function(){} instanceof Function);       // true
console.log({} instanceof Object);                   // true    

instanceof 在MDN中的解释：instanceof 运算符用来测试一个对象
在其原型链中是否存在一个构造函数的 prototype 属性。
其意思就是判断对象是否是某一数据类型（如Array）的实例，
请重点关注一下是判断一个对象是否是数据类型的实例。
在这里字面量值，2， true ，'str'不是实例，所以判断值为false
```

```
实现instanceof：
(1)首先获取类型的原型
(2)获得对象的原型
(3)一直循环判断对象的原型是否等于类型的原型，
直到对象原型为 null，因为原型链最终为 null

function instanceof(left, right) {
    // 获得类型的原型
    let prototype = right.prototype
    // 获得对象的原型
    left = left.__proto__
    // 判断对象的类型是否等于类型的原型
    while (true) {
    	if (left === null)
    		return false
    	if (prototype === left)
    		return true
    	left = left.__proto__
    }
}
```

```
注意1：虽然说，实例是由构造函数 new 出来的，但是实例的__proto__属性引用的是
构造函数的prototype。也就是说，实例的__proto__属性与构造函数本身无关。
注意2：在原型链上，原型的上面可能还会有原型，以此类推往上走，继续找__proto__属性。
这条链上如果能找到， instanceof 的返回结果也是 true。

比如说：
foo instance of Foo的结果为true，因为foo.__proto__ === M.prototype为true。
foo instance of Object的结果也为true，为Foo.prototype.__proto__ === Object.prototype为true。
但我们不能轻易的说：foo 一定是 由Object创建的实例`。这句话是错误的。我们来看下一个问题就明白了。

问题：已知A继承了B，B继承了C。怎么判断 a 是由A直接生成的实例，
还是B直接生成的实例呢？还是C直接生成的实例呢？
分析：这就要用到原型的constructor属性了。
foo.__proto__.constructor === M的结果为true，但是 foo.__proto__.constructor === Object的结果为false。
所以，用 consturctor判断就比用 instanceof判断，更为严谨。
```

  #### constructor
```
console.log((2).constructor === Number);                  // true
console.log((true).constructor === Boolean);              // true
console.log(('str').constructor === String);              // true
console.log(([]).constructor === Array);                  // true
console.log((function() {}).constructor === Function);    // true
console.log(({}).constructor === Object);                 // true

坑：如果创建一个对象，更改它的原型，constructor就会变得不可靠了
function Fn(){};
Fn.prototype=new Array();
var f=new Fn();
console.log(f.constructor===Fn);    // false
console.log(f.constructor===Array); // true 
```

  #### Object.prototype.toString.call()
```
使用 Object 对象的原型方法 toString ，使用 call 
进行狸猫换太子，借用Object的 toString 方法

优点：精准判断数据类型
缺点：写法繁琐不容易记，推荐进行封装后使用

var a = Object.prototype.toString;
console.log(a.call(2));               // [object Number]
console.log(a.call(true));            // [object Boolean]
console.log(a.call('str'));           // [object String]
console.log(a.call([]));              // [object Array]
console.log(a.call(function(){}));    // [object Function]
console.log(a.call({}));              // [object Object]
console.log(a.call(undefined));       // [object Undefined]
console.log(a.call(null));            // [object Null]
```

  #### 封装javascript的类型判断函数
```js
function getType(value) {
  // 判断数据是 null 的情况
  if (value === null) {
    return value + "";
  }

  // 判断数据是引用类型的情况
  if (typeof value === "object") {
    let valueClass = Object.prototype.toString.call(value),
      type = valueClass.split(" ")[1].split("");

    type.pop();

    return type.join("").toLowerCase();
  } else {
    // 判断数据是基本数据类型的情况和函数的情况
    return typeof value;
  }
}
```

- [js类型转换](#js类型转换)
  - [其他值到字符串的转换规则--17. 其他值到字符串的转换规则？](#其他值到字符串的转换规则)
  - [其他值到数字值的转换规则--18. 其他值到数字值的转换规则？](#其他值到数字值的转换规则)
  - [其他值到布尔类型的值的转换规则--19. 其他值到布尔类型的值的转换规则？](#其他值到布尔类型的值的转换规则)
  - [如何将字符串转化为数字，例如'12.3b'--29. 如何将字符串转化为数字，例如 '12.3b'?](#如何将字符串转化为数字例如123b)
  - [什么情况下会发生布尔值的隐式强制类型转换--25. 什么情况下会发生布尔值的隐式强制类型转换？](#什么情况下会发生布尔值的隐式强制类型转换)
  - [Symbol值的强制类型转换--27. Symbol值的强制类型转换？](#Symbol值的强制类型转换)
  - [将浮点数点左边的数每三位添加一个逗号,12000000.11转化为『12,000,000.11』--30. 如何将浮点数点左边的数每三位添加一个逗号，如 12000000.11 转化为『12,000,000.11』?](#将浮点数点左边的数每三位添加一个逗号1200000011转化为1200000011)
  - [解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字,区别--23. 解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字，它们之间的区别是什么？](#解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字区别)

- [js属性](#js属性)
  - [内部属性[[Class]]是什么--4. 内部属性 [[Class]] 是什么？](#内部属性Class是什么)
  - [属性的遍历--141 属性的遍历](#属性的遍历)

- [js操作符](#js操作符)
  - [||和&&操作符的返回值--26. || 和 && 操作符的返回值？](#和操作符的返回值)
  - [==操作符的强制类型转换规则--28. == 操作符的强制类型转换规则？  ](#操作符的强制类型转换规则)
  - [操作符什么时候用于字符串的拼接--24. 操作符什么时候用于字符串的拼接？](#操作符什么时候用于字符串的拼接)
  - [~操作符的作用--22. ~ 操作符的作用？](#操作符的作用)

- [类和对象](#类和对象)
  - [JavaScript如何实现一个类，怎么实例化这个类--115 JavaScript如何实现一个类，怎么实例化这个类](#JavaScript如何实现一个类怎么实例化这个类)
  - [ECMAScript6怎么写class，为什么会出现class这种东西--69. ECMAScript6 怎么写 class，为什么会出现 class 这种东西?  47 ECMAScript6 怎么写class么](#ECMAScript6怎么写class为什么会出现class这种东西)
  - [javascript创建对象的几种方式--21 javascript有哪些方法定义对象  34. javascript 创建对象的几种方式？  34 javascript创建对象的几种方式](#javascript创建对象的几种方式)
  - [如何判断一个对象是否属于某个类--48. 如何判断一个对象是否属于某个类？](#如何判断一个对象是否属于某个类)
  - [如何判断一个对象是否为空对象--159. 如何判断一个对象是否为空对象？](#如何判断一个对象是否为空对象)
  - [怎么判断两个对象相等--79 怎么判断两个对象相等？](#怎么判断两个对象相等)
  - [js有哪些内置对象--5. 介绍 js 有哪些内置对象？  31 介绍js有哪些内置对象 108 介绍JS有哪些内置对象](#js有哪些内置对象)
  - [什么是假值对象--21. 什么是假值对象？](什么是假值对象)
  - [Object.is()与原来的比较操作符“===”、“==”的区别--92. Object.is() 与原来的比较操作符 “===”、“==” 的区别？](#Objectis与原来的比较操作符的区别)
  - [Object.assign()--168. Object.assign()](#Objectassign)
  - [使用Object.defineProperty()来进行数据劫持有什么缺点--110. Object.defineProperty 介绍？  111. 使用 Object.defineProperty() 来进行数据劫持有什么缺点？](#使用ObjectdefineProperty来进行数据劫持有什么缺点)

- [数组和对象](#数组和对象)
  - [如何实现数组的随机排序--33. 如何实现数组的随机排序？](#如何实现数组的随机排序)
  - [快速的让一个数组乱序--65 快速的让一个数组乱序](#快速的让一个数组乱序)
  - [数组去重方法总结--74 数组去重方法总结](#数组去重方法总结)
  - [判断是否是数组--137 判断是否是数组](#判断是否是数组)
  - [如何通过JS判断一个数组--51 如何通过JS判断一个数组](#如何通过JS判断一个数组)
  - [数组的fill方法--76. 数组的 fill 方法？](#数组的fill方法)
  - [数组和对象有哪些原生方法--75. 数组和对象有哪些原生方法，列举一下？](#数组和对象有哪些原生方法)
  - [JS数组和对象的遍历方式，以及几种方式的比较--60 JS 数组和对象的遍历方式，以及几种方式的比较](#JS数组和对象的遍历方式以及几种方式的比较)
  - [JavaScript类数组对象的定义--74. JavaScript 类数组对象的定义？ ](#JavaScript类数组对象的定义)
  - [Array构造函数只有一个参数值时的表现--16. Array 构造函数只有一个参数值时的表现？](#Array构造函数只有一个参数值时的表现)
  - [Array.splice()与Array.splice()的区别--132 Array.splice() 与 Array.splice() 的区别？](#Arraysplice与Arraysplice的区别)
  *- [53. [].forEach.call($$(""),function(a){a.style.outline="1px solid #" (~~(Math.random()(1<<24))).toString(16)}) 能解释一下这段代码的意思吗？](#)
  *- [45. ["1", "2", "3"].map(parseInt) 答案是多少？  37 ["1", "2", "3"].map(parseInt) 答案是多少](#)
  - [map与forEach的区别--53 map与forEach的区别](#map与forEach的区别)
  - [Map和WeakMap结构--132. Map 和 WeakMap 结构？](#Map和WeakMap结构)
  - [Set和WeakSet结构--131. Set 和 WeakSet 结构？](#Set和WeakSet结构)
  *- [{}和[]的valueOf和toString的结果是什么--20. {} 和 [] 的 valueOf 和 toString 的结果是什么？](#{}和[]的valueOf和toString的结果是什么)

- [函数](#函数)
  - [JavaScript中，调用函数有哪几种方式--129 JavaScript 中，调用函数有哪几种方式](#JavaScript中调用函数有哪几种方式)
  - [函数式编程--117. 谈一谈你理解的函数式编程？  54 谈一谈你理解的函数式编程](#函数式编程)
  - [箭头函数与普通函数的区别--55 谈一谈箭头函数与普通函数的区别？](#箭头函数与普通函数的区别)
  - [封装一个函数，参数是定时器的时间，.then执行回调函数--78 封装一个函数，参数是定时器的时间，.then执行回调函数](#封装一个函数参数是定时器的时间then执行回调函数)
  - [函数节流，应用场景和原理--121 什么是函数节流？介绍一下应用场景和原理？](#函数节流应用场景和原理)
  - [isNaN和Number.isNaN函数的区别--15. isNaN 和 Number.isNaN 函数的区别？](#isNaN和NumberisNaN函数的区别)
  - [Javascript全局函数和全局变量--76 Javascript全局函数和全局变量](#Javascript全局函数和全局变量)
  - [什么是闭包，为什么要用它--46. 什么是闭包，为什么要用它？  1 闭包](#什么是闭包，为什么要用它)
  - [使用闭包实现每隔一秒打印--160. 使用闭包实现每隔一秒打印 1,2,3,4](#使用闭包实现每隔一秒打印)
  - [eval是做什么的--39. eval 是做什么的？  35 eval是做什么的](#eval是做什么的)


### js原型和原型链
```
原型：在 js 中我们是使用构造函数来新建一个对象的，
每一个构造函数的内部都有一个 prototype 属性值，
这个属性值是一个对象，这个对象包含了可以由该构造函数的
所有实例共享的属性和方法。当我们使用构造函数新建一个对象后，
在这个对象的内部将包含一个指针，这个指针指向构造函数的
prototype 属性对应的值，在 ES5 中这个指针被称为对象的原型（prototype）。

一般来说我们是不应该能够获取到这个值的，但是现在浏览器中
都实现了 __proto__ 属性来让我们访问这个属性，但是我们最好
不要使用这个属性，因为它不是规范中规定的。
ES5 中新增了一个 Object.getPrototypeOf() 方法，
我们可以通过这个方法来获取对象的原型。

原型链：当我们访问一个对象的属性时，如果这个对象内部不存在这个属性，
那么它就会去它的原型对象里找这个属性，这个原型对象又会有自己的原型，
于是就这样一直找下去，也就是原型链的概念。

原型链的尽头一般来说都是 Object.prototype ，所以这就是
我们新建的对象为什么能够使用 toString() 等方法的原因。

特点：
JavaScript 对象是通过引用来传递的，我们创建的每个新对象实体中并没有一份
属于自己的原型副本。当我们修改原型时，与之相关的对象也会继承这一改变。

关系：instance.constructor.prototype = instance.__proto__
```

  #### js获取原型的方法
```
p.__proto__
p.constructor.prototype
Object.getPrototypeOf(p)
```

  #### Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是
```
hasOwnProperty

所有继承了 Object 的对象都会继承到 hasOwnProperty 方法。
这个方法可以用来检测一个对象是否含有特定的自身属性，
和in 运算符不同，该方法会忽略掉那些从原型链上继承到的属性。
```

### js继承
```
javascript继承的7种方法：
(1)原型链继承：将父类的实例作为子类的原型。
(2)构造函数继承（使用call）：使用父类的构造函数来增强子类实例，
等于是复制父类的实例属性给子类。
(3)实例继承：为父类实例添加新特性，作为子类实例返回。
(4)拷贝继承：把父类实例对象上的方法拷贝到子类的原型上。
(5)组合继承：通过调用父类构造函数，继承父类的属性并保留传参的优点，
然后通过将父类实例作为子类原型，实现函数复用。
(6)寄生组合继承：通过寄生方式，砍掉父类的实例属性，这样，
在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，
避免的组合继承的缺点。
(7)使用extends关键字扩展一个类并继承它的行为（es6）。
```

```
我了解的 js 中实现继承的几种方式有：
（1）第一种是以原型链的方式来实现继承，但是这种实现方式存在的缺点是，
在包含有引用类型的数据时，会被所有的实例对象所共享，
容易造成修改的混乱。还有就是在创建子类型的时候不能向超类型传递参数。

（2）第二种方式是使用借用构造函数的方式，这种方式是通过在
子类型的函数中调用超类型的构造函数来实现的，这一种方法解决了
不能向超类型传递参数的缺点，但是它存在的一个问题就是无法实现
函数方法的复用，并且超类型原型定义的方法子类型也没有办法访问到。

（3）第三种方式是组合继承，组合继承是将原型链和借用构造函数
组合起来使用的一种方式。通过借用构造函数的方式来实现类型的属性
的继承，通过将子类型的原型设置为超类型的实例来实现方法的继承。
这种方式解决了上面的两种模式单独使用时的问题，但是由于我们
是以超类型的实例来作为子类型的原型，所以调用了两次超类的
构造函数，造成了子类型的原型中多了很多不必要的属性。

（4）第四种方式是原型式继承，原型式继承的主要思路就是基于
已有的对象来创建新的对象，实现的原理是，向函数中传入一个对象，
然后返回一个以这个对象为原型的对象。这种继承的思路主要不是
为了实现创造一种新的类型，只是对某个对象实现一种简单继承，
ES5 中定义的 Object.create() 方法就是原型式继承的实现。
缺点与原型链方式相同。

（5）第五种方式是寄生式继承，寄生式继承的思路是创建一个
用于封装继承过程的函数，通过传入一个对象，然后复制一个对象的副本，
然后对象进行扩展，最后返回这个对象。这个扩展的过程就可以理解是一种继承。
这种继承的优点就是对一个简单对象实现继承，如果这个对象
不是我们的自定义类型时。缺点是没有办法实现函数的复用。

（6）第六种方式是寄生式组合继承，组合继承的缺点就是使用
超类型的实例做为子类型的原型，导致添加了不必要的原型属性。
寄生式组合继承的方式是使用超类型的原型的副本来作为
子类型的原型，这样就避免了创建不必要的属性。
```

js继承实现方式：既然要实现继承，那么首先我们得有一个父类，代码如下：
```
// 定义一个动物类
function Animal (name) {
  // 属性
  this.name = name || 'Animal';
  // 实例方法
  this.sleep = function(){
    console.log(this.name + '正在睡觉！');
  }
}
// 原型方法
Animal.prototype.eat = function(food) {
  console.log(this.name + '正在吃：' + food);
};
```

  #### 原型链继承
```
核心：将父类的实例作为子类的原型
function Cat() {
}
Cat.prototype = new Animal();
Cat.prototype.name = 'cat';

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.eat('fish');    //cat正在吃fish
cat.sleep();    //cat正在睡觉。。。
console.log(cat instanceof Animal); //true
console.log(cat instanceof Cat);    //true

特点：
1.纯粹的继承关系，实例是子类的实例，也是父类的实例
2.父类新增方法属性，子类都能访问到
3.简单易于实现
缺点：
1.可以在Cat构造函数中，为Cat实例增加实例属性。如果要新增原型属性和方法，则必须放在Cat.prototype = new Animal();这样的语句之后执行。
2.无法实现多继承
3.来自原型对象的引用属性是所有实例共享的
4.创建子类的实例时，无法向父类构造函数传参
```

  #### 构造函数继承
```
使用call
核心：使用父类的构造函数来增强子类实例，
等于是复制父类的实例属性给子类（没用到原型）

function Cat2(name) {
    Animal.call(this);
    this.name = name || 'Tom';
}
// Test Code
var cat2 = new Cat2();
console.log(cat2.name); //Tom
cat2.sleep()    //Tom正在睡觉。。。
console.log(cat2 instanceof Cat2); //true
console.log(cat2 instanceof Animal); //false

特点：
1.解决了1中，子类实例共享父类引用属性的问题
2.创建子类实例时，可以向父类传递参数
3.可以实现多继承（call多个父类对象）
缺点：
1.实例并不是父类的实例，只是子类的实例
2.只能继承父类的实例属性和方法，不能继承原型属性/方法
3.无法实现函数复用，每个子类都有父类实例函数的副本，影响性能
```

  #### 实例继承
```
核心：为父类实例添加新特性，作为子类实例返回
function Cat3(name) {
    var instance = new Animal();
    instance.name = name || 'Tom';
    return instance;
}

// Test Code
var cat3 = new Cat3();
console.log(cat3.name);
cat3.sleep();
cat3.eat('meat');
console.log(cat3 instanceof Cat3); //false
console.log(cat3 instanceof Animal); //true

特点：
1.不限制调用方式，不管是 new 子类() 还是 子类()，
返回的对象具有相同的效果
缺点：
1.实例是父类的实例，不是子类的实例
2.不支持多继承
```

  #### 拷贝继承
```
function Cat(name) {
    var animal = new Animal();
    for (var p in animal) {
        Cat.prototype[p] = animal[p];
    }
    Cat.prototype.name = name || 'Tom';
}

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.sleep();
cat.eat('bread');
console.log(cat instanceof Cat); //true
console.log(cat instanceof Animal); //false

特点：
支持多继承
缺点：
1.效率较低，占用内存高
2.无法获取父类不可枚举的方法（不可枚举方法，不能使用for-in访问到）
```

  #### 组合继承
```
核心：通过调用父类构造函数，继承父类的属性并保留传参的优点，
然后通过将父类实例作为子类原型，实现函数复用。

function Cat(name) {
    Animal.call(this);
    this.name = name || "Tom";
}
Cat.prototype = new Animal();
Cat.prototype.constructor = Cat;

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.sleep();
cat.eat('bread');
console.log(cat instanceof Cat); //true
console.log(cat instanceof Animal); //true

特点：
1.弥补了方式二的缺陷，可以继承实例属性/方法，也可以继承原型属性/方法
2.即是子类的实例，也是父类的实例
3.不存在引用属性共享问题
4.可传参
5.函数可复用
缺点：
1.调用了两次父构造函数，生成了两份实例
（子类实例将子类原型上的那份屏蔽掉了），消耗内存较少
```

  #### 寄生组合继承
```
核心：通过寄生方式，砍掉父类的实例属性，这样，在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，避免的组合继承的缺点。
function Cat(name) {
    Animal.call(this);
    this.name = name || "Tom";
}
(function () {
    // 创建一个没有实例方法的类
    var Super = function () {
    }
    Super.prototype = Animal.prototype;
    // 将实例作为子类的原型
    Cat.prototype = new Super();
})();
// 修复构造函数
Cat.prototype.constructor = Cat;

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.sleep();
cat.eat('bread');
console.log(cat instanceof Cat); //true
console.log(cat instanceof Animal); //true

特点：
堪称完美
缺点：
1.实现较为复杂
```

   #### 寄生式组合继承的实现
```js
function Person(name) {
  this.name = name;
}

Person.prototype.sayName = function() {
  console.log("My name is " + this.name + ".");
};

function Student(name, grade) {
  Person.call(this, name);
  this.grade = grade;
}

Student.prototype = Object.create(Person.prototype);
Student.prototype.constructor = Student;

Student.prototype.sayMyGrade = function() {
  console.log("My grade is " + this.grade + ".");
};
```

  #### es6使用extends关键字扩展一个类并继承它的行为
```
首先使用es6语法把代码简化如下：
class Animal2 {
    constructor (name, food) {
        this.name = name || "Animal";
        this.food = food;
        this.sleep = () => console.log(this.name + '正在睡觉。。。');
    }
    eat(){
        // console.log(this.name + '正在吃' + this.food);
        return this.name + '正在吃' + this.food;
    }
}

然后让Reptile类继承Animal2

class Reptile extends Animal2 {
    constructor (name, food, habit){
        super(name, food);
        this.habit = habit;
    }
    printHabit() {
        console.log(this.habit);
    }
}

// Test Code
let cat = new Reptile('cat', 'fish', 'sleep');
cat.printHabit(); //sleep
console.log(cat.eat()); //cat正在吃fish
console.log(cat instanceof Reptile); //true
console.log(cat instanceof Animal2); //true
```

- [this对象](#this对象)  38. 谈谈 This 对象的理解。   6 谈谈This对象的理解 101 描述一下this
  - [this指向--56 谈一谈函数中this的指向  136 this指向](#this指向)
  - [.call()和.apply()的区别--73. .call() 和 .apply() 的区别？ ](#call和apply的区别)
  - [手写call、apply及bind函数--97. 手写 call、apply 及 bind 函数](#手写callapply及bind函数)
  - [简单实现Function.bind函数--130 简单实现 Function.bind 函数](#简单实现Functionbind函数)
  - [new操作符具体干了什么呢？如何实现--50. new 操作符具体干了什么呢？如何实现？    8 new操作符具体干了什么呢?](#new操作符具体干了什么呢如何实现)
  - [Javascript的作用域链--37. Javascript 的作用域链？ 2 说说你对作用域链的理解  117 Javascript作用链域](#Javascript的作用域链)
  - [JavaScript中的作用域与变量声明提升--78. JavaScript 中的作用域与变量声明提升？ 113 解释JavaScript中的作用域与变量声明提升  86 谈谈变量提升？](#JavaScript中的作用域与变量声明提升)

- [事件](#事件)
  - [事件是什么？IE与火狐的事件机制有什么区别？如何阻止冒泡--42. 事件是什么？IE 与火狐的事件机制有什么区别？ 如何阻止冒泡？](#事件是什么IE与火狐的事件机制有什么区别如何阻止冒泡)
  - [事件的各个阶段--63 事件的各个阶段](#事件的各个阶段)
  - [事件“捕获”和“冒泡”执行顺序和事件的执行次数--120 介绍事件“捕获”和“冒泡”执行顺序和事件的执行次数](#事件“捕获”和“冒泡”执行顺序和事件的执行次数)
  - [事件代理--4 请解释什么是事件代理](#事件代理)
  - [三种事件模型是什么--43. 三种事件模型是什么？7 事件模型](#三种事件模型是什么)
  - [事件委托--44. 事件委托是什么？](#事件委托)
  - [js的事件循环是什么--95. js 的事件循环是什么？](#js的事件循环是什么)
  - [事件流--96 说说事件流](#事件流)
  - [写一个通用的事件侦听器函数--41. 写一个通用的事件侦听器函数。](#写一个通用的事件侦听器函数)
  - [移动端的点击事件的有延迟，时间是多久，为什么会有？怎么解决这个延时--85. 移动端的点击事件的有延迟，时间是多久，为什么会有？ 怎么解决这个延时？](#移动端的点击事件的有延迟时间是多久为什么会有怎么解决这个延时)

- [浏览器](#浏览器)
  - [从输入URL到看到页面发生的全过程--100 说说从输入URL到看到页面发生的全过程，越详细越好](#从输入URL到看到页面发生的全过程)
  - [浏览器的渲染过程，DOM树和渲染树的区别--111 描述浏览器的渲染过程，DOM树和渲染树的区别](#浏览器的渲染过程DOM树和渲染树的区别)
  - [浏览器的缓存机制--56. 谈一谈浏览器的缓存机制？  81 浏览器缓存  102 说一下浏览器的缓存机制](#浏览器的缓存机制)
  - [Ajax解决浏览器缓存问题--57. Ajax 解决浏览器缓存问题？](#Ajax解决浏览器缓存问题)
  - [常见兼容性问题--22 常见兼容性问题？](#常见兼容性问题)
  - [请求方式](#请求方式)
    - [get和post请求在缓存方面的区别--122. get 和 post 请求在缓存方面的区别](#get和post请求在缓存方面的区别)
    - [get请求传参长度的误区--120. get 请求传参长度的误区](#get请求传参长度的误区)
  - [检测浏览器版本版本有哪些方式--88. 检测浏览器版本版本有哪些方式？  107 检测浏览器版本版本有哪些方式？](#检测浏览器版本版本有哪些方式)
  *- [84. 把 script 标签放在页面的最底部的 body 封闭之前和封闭之后有什么区别？浏览器会如何解析它们？  128 把<script>放在</body>之前和之后有什么区别？浏览器会如何解析它们？](#)
  - [script的位置是否会影响首屏显示时间--112 script 的位置是否会影响首屏显示时间](#script的位置是否会影响首屏显示时间)
  *- [82. 需求：实现一个页面操作不会整页刷新的网站，并且能在浏览器前进、后退时正确响应。给出你的技术实现方案？](#)
  - [如何检测浏览器所支持的最小字体大小--138. 如何检测浏览器所支持的最小字体大小？](#如何检测浏览器所支持的最小字体大小)
  - [开发中常用的几种Content-Type--157. 开发中常用的几种 Content-Type ？](#开发中常用的几种ContentType)
  - [如何判断当前脚本运行在浏览器还是node环境中？（阿里）--83. 如何判断当前脚本运行在浏览器还是 node 环境中？（阿里）](#如何判断当前脚本运行在浏览器还是node环境中阿里)
  - [V8引擎的垃圾回收机制--80. 简单介绍一下 V8 引擎的垃圾回收机制](#V8引擎的垃圾回收机制)
  - [Javascript垃圾回收方法--124 Javascript垃圾回收方法  139 垃圾回收](#Javascript垃圾回收方法)
  - [URL和URI的区别--121. URL 和 URI 的区别？](#URL和URI的区别)
  - [在输入框中如何判断输入的是一个正确的网址--143 在输入框中如何判断输入的是一个正确的网址](#在输入框中如何判断输入的是一个正确的网址)
  - [页面编码和被请求的资源编码如果不一致如何处理--127 页面编码和被请求的资源编码如果不一致如何处理](#页面编码和被请求的资源编码如果不一致如何处理)
  - [加载--138 加载](#加载)
  - [WEB应用从服务器主动推送Data到客户端有那些方式--134 WEB应用从服务器主动推送Data到客户端有那些方式](#WEB应用从服务器主动推送Data到客户端有那些方式)

- [cookie](#cookie)  62. 简单谈一下 cookie ？
  - [如何删除一个cookie--126 如何删除一个cookie](#如何删除一个cookie)
  - [服务器代理转发时，该如何处理cookie--61. 服务器代理转发时，该如何处理 cookie？](#服务器代理转发时该如何处理cookie)
  - [什么是Samesite Cookie属性--105. 什么是 Samesite Cookie 属性？](#什么是Samesite-Cookie属性)

- [面向对象](#面向对象)
  - [什么是面向对象编程及面向过程编程，它们的异同和优缺点--48 什么是面向对象编程及面向过程编程，它们的异同和优缺点 49 面向对象编程思想](#什么是面向对象编程及面向过程编程它们的异同和优缺点)

- [同步和异步](#同步和异步)
  - [同步和异步的区别--58. 同步和异步的区别？   41 同步和异步的区别](#同步和异步的区别)
  - [异步加载JS的方式有哪些--12 异步加载JS的方式有哪些？](#异步加载JS的方式有哪些)
  - [异步编程的实现方式--118. 异步编程的实现方式？ 57 异步编程的实现方式  ](#异步编程的实现方式)
  - [什么是单线程，和异步的关系--87 什么是单线程，和异步的关系](#什么是单线程和异步的关系)
  *- [136. 什么是 Promise 对象，什么是 Promises/A 规范？  23 说说你对promise的了解  99 请手写实现一个promise](#)
  - [手写一个Promise--137. 手写一个 Promise](#手写一个Promise)
  - [defer和async--43 defer和async](#defer和async)

- [模式](#模式)
  - [用过哪些设计模式--18 用过哪些设计模式？](#用过哪些设计模式)
  - [单例模式模式--140. 单例模式模式是什么？](#单例模式模式)
  - [策略模式--141. 策略模式是什么？](#策略模式)
  - [代理模式--142. 代理模式是什么？](#代理模式)
  - [中介者模式--143. 中介者模式是什么？](#中介者模式)
  - [适配器模式--144. 适配器模式是什么？](#适配器模式)
  - [观察者模式和发布订阅模式有什么不同--145. 观察者模式和发布订阅模式有什么不同？](#观察者模式和发布订阅模式有什么不同)
  - [严格模式的限制--44 说说严格模式的限制](#严格模式的限制)
  - [手写一个观察者模式--162. 手写一个观察者模式？](#手写一个观察者模式)

- [模块化](#模块化)
  - [模块化开发怎么做--63. 模块化开发怎么做？  11 模块化开发怎么做？](#模块化开发怎么做)
  - [js的几种模块规范--64. js 的几种模块规范？](#js的几种模块规范)
  - [ES6模块与CommonJS模块、AMD、CMD的差异--66. ES6 模块与 CommonJS 模块、AMD、CMD 的差异。 65. AMD 和 CMD 规范的区别？   27 谈谈你对AMD、CMD的理解  16 说说你对AMD和Commonjs的理解](#ES6模块与CommonJS模块AMDCMD的差异)
  - [JS模块加载器的轮子怎么造，也就是如何实现一个模块加载器--68. JS 模块加载器的轮子怎么造，也就是如何实现一个模块加载器？](#JS模块加载器的轮子怎么造也就是如何实现一个模块加载器)
  - [require模块引入的查找方式--135. require 模块引入的查找方式？](#require模块引入的查找方式)

- [DOM](#DOM)
  - [什么是DOM和BOM--40. 什么是 DOM 和 BOM？](#什么是DOM和BOM)
  - [介绍DOM的发展--118 介绍 DOM 的发展](#介绍DOM的发展)
  - [DOM操作怎样添加、移除、移动、复制、创建和查找节点--71. DOM 操作——怎样添加、移除、移动、复制、创建和查找节点？   怎样添加、移除、移动、复制、创建和查找节点](#DOM操作怎样添加移除移动复制创建和查找节点)
  - [虚拟DOM(Virtual DOM),为什么虚拟DOM比原生DOM快--112. 什么是 虚拟DOM Virtual DOM？为什么 Virtual DOM 比原生 DOM 快？](#虚拟DOMVirtual-DOM为什么虚拟DOM比原生DOM快)
  - [如何比较两个DOM树的差异--113. 如何比较两个 DOM 树的差异？](#如何比较两个DOM树的差异)
  - [介绍DOM0，DOM2，DOM3事件处理方式区别--119 介绍DOM0，DOM2，DOM3事件处理方式区别](#介绍DOM0DOM2DOM3事件处理方式区别)



### 优化

  #### 项目做过哪些性能优化
```
减少 HTTP 请求数
减少 DNS 查询
使用 CDN
避免重定向
图片懒加载
减少 DOM 元素数量
减少DOM 操作
使用外部 JavaScript 和 CSS
压缩 JavaScript 、 CSS 、字体、图片等
优化 CSS Sprite
使用 iconfont
字体裁剪
多域名分发划分内容到不同域名
尽量减少 iframe 使用
避免图片 src 为空
把样式表放在link 中
把JavaScript放在页面底部
```

  #### 懒加载 预加载 懒执行
```
懒加载也叫延迟加载，指的是在长网页中延迟加载图片的时机，
当用户需要访问时，再去加载，这样可以提高网站的首屏加载速度，
提升用户的体验，并且可以减少服务器的压力。它适用于图片很多，
页面很长的电商网站的场景。懒加载的实现原理是，将页面上的图片
的 src 属性设置为空字符串，将图片的真实路径保存在一个自定义属性中，
当页面滚动的时候，进行判断，如果图片进入页面可视区域内，
则从自定义属性中取出真实路径赋值给图片的 src 属性，
以此来实现图片的延迟加载。懒加载不仅可以用于图片，
也可以使用在别的资源上。比如进入可视区域才开始播放视频等等。

预加载指的是将所需的资源提前请求加载到本地，这样后面在需要
用到时就直接从缓存取资源。通过预加载能够减少用户的等待时间，
提高用户的体验。我了解的预加载的最常用的方式是使用 js 中的 
image 对象，通过为 image 对象来设置 scr 属性，来实现图片的预加载。

这两种方式都是提高网页性能的方式，两者主要区别是一个是提前加载，
一个是迟缓甚至不加载。懒加载对服务器前端有一定的缓解压力作用，
预加载则会增加服务器前端压力。

懒执行就是将某些逻辑延迟到使用时再计算。该技术可以用于首屏优化，
对于某些耗时逻辑并不需要在首屏就使用的，就可以使用懒执行。
懒执行需要唤醒，一般可以通过定时器或者事件的调用来唤醒懒加载
```

```
预加载：提前加载图片，当用户需要查看时可直接从本地缓存中渲染。

懒加载：懒加载的主要目的是作为服务器前端的优化，
减少请求数或延迟请求数。

两种技术的本质：两者的行为是相反的，一个是提前加载，
一个是迟缓甚至不加载。 懒加载对服务器前端有一定的
缓解压力作用，预加载则会增加服务器前端压力。
```

懒加载实现：
```
图片懒加载
// <img src="default.png" data-src="https://xxxx/real.png">
function isVisible(el) {
  const position = el.getBoundingClientRect()
  const windowHeight = document.documentElement.clientHeight
  // 顶部边缘可见
  const topVisible = position.top > 0 && position.top < windowHeight;
  // 底部边缘可见
  const bottomVisible = position.bottom < windowHeight && position.bottom > 0;
  return topVisible || bottomVisible;
}

function imageLazyLoad() {
  const images = document.querySelectorAll('img')
  for (let img of images) {
    const realSrc = img.dataset.src
    if (!realSrc) continue
    if (isVisible(img)) {
      img.src = realSrc
      img.dataset.src = ''
    }
  }
}

// 测试
window.addEventListener('load', imageLazyLoad)
window.addEventListener('scroll', imageLazyLoad)
// or
window.addEventListener('scroll', throttle(imageLazyLoad, 1000))
```

  #### 如何渲染几万条数据并不卡住界面
```
这道题考察了如何在不卡住页面的情况下渲染数据，也就是说不能
一次性将几万条都渲染出来，而应该一次渲染部分 DOM，
那么就可以通过 requestAnimationFrame 来每 16 ms 刷新一次

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <ul>控件</ul>
  <script>
    setTimeout(() => {
      // 插入十万条数据
      const total = 100000
      // 一次插入 20 条，如果觉得性能不好就减少
      const once = 20
      // 渲染数据总共需要几次
      const loopCount = total / once
      let countOfRender = 0
      let ul = document.querySelector("ul");
      function add() {
        // 优化性能，插入不会造成回流
        const fragment = document.createDocumentFragment();
        for (let i = 0; i < once; i++) {
          const li = document.createElement("li");
          li.innerText = Math.floor(Math.random() * total);
          fragment.appendChild(li);
        }
        ul.appendChild(fragment);
        countOfRender += 1;
        loop();
      }
      function loop() {
        if (countOfRender < loopCount) {
          window.requestAnimationFrame(add);
        }
      }
      loop();
    }, 0);
  </script>
</body>
</html>
```

  #### 一个列表，假设有100000个数据，这个该怎么办
```
我们需要思考的问题：该处理是否必须同步完成？数据是否必须按顺序完成？

解决办法：
（1）将数据分页，利用分页的原理，每次服务器端只返回
一定数目的数据，浏览器每次只对一部分进行加载。

（2）使用懒加载的方法，每次加载一部分数据，其余数据当需要使用时再去加载。

（3）使用数组分块技术，基本思路是为要处理的项目创建一个队列，
然后设置定时器每过一段时间取出一部分数据，然后再使用定时器
取出下一个要处理的项目进行处理，接着再设置另一个定时器。
```


### 安全

  #### 同源
同源策略是一种安全协议
```
我对浏览器的同源政策的理解是，一个域下的 js 脚本在未经允许的情况下，
不能够访问另一个域的内容。这里的同源的指的是两个域的
协议、域名、端口号必须相同，否则则不属于同一个域。

同源政策主要限制了三个方面：
第一个是当前域下的 js 脚本不能够访问其他域下的 cookie、localStorage 和 indexDB。
第二个是当前域下的 js 脚本不能够操作访问操作其他域下的 DOM。
第三个是当前域下 ajax 无法发送跨域请求。

同源政策的目的主要是为了保证用户的信息安全，防止某个文档或脚本从
多个不同源装载。
它只是对 js 脚本的一种限制，并不是对浏览器的限制，
对于一般的 img、或者script 脚本请求都不会有跨域的限制，
这是因为这些操作都不会通过响应结果来进行可能出现安全问题的操作。
```

```
举例说明：比如一个黑客程序，他利用Iframe把真正的银行登录页面
嵌到他的页面上，当你使用真实的用户名，密码登录时，他的页面就
可以通过Javascript读取到你的表单中input中的内容，
这样用户名，密码就轻松到手了。

缺点：
现在网站的JS都会进行压缩，一些文件用了严格模式，而另一些没有。
这时这些本来是严格模式的文件，被 merge后，这个串就到了文件的中间，
不仅没有指示严格模式，反而在压缩后浪费了字节
```

   #### 浏览器的同源政策
```
我对浏览器的同源政策的理解是，一个域下的 js 脚本在未经允许
的情况下，不能够访问另一个域的内容。这里的同源的指的是两个域
的协议、域名、端口号必须相同，否则则不属于同一个域。

同源政策主要限制了三个方面：
第一个是当前域下的 js 脚本不能够访问其他域下的 cookie、localStorage 和 indexDB。

第二个是当前域下的 js 脚本不能够操作访问操作其他域下的 DOM。

第三个是当前域下 ajax 无法发送跨域请求。

同源政策的目的主要是为了保证用户的信息安全，它只是对 js 脚本的
一种限制，并不是对浏览器的限制，对于一般的 img、或者script 脚本请求
都不会有跨域的限制，这是因为这些操作都不会通过响应结果来进行
可能出现安全问题的操作。
```

  #### 限制
为什么会产生跨域？
```
你之所以会遇到跨域问题，正是因为 SOP 的各种限制。
本质上 SOP 并不是禁止跨域请求，而是在请求后拦截了请求的回应。

其实表面上 SOP 分两种情况：
可以正常引用 iframe、图片等各种资源，但是限制对其内容进行操作
直接限制 ajax 请求，准确来说是限制操作 ajax 响应结果，这会引起 CSRF
但是，本质上这两条是一样的：总之，对于非同源的资源，
浏览器可以“直接使用”，但是程序员和用户不可以对这些数据进行操作，
杜绝某些居心不良的行为。这就是现代安全浏览器对用户的保护之一。

下面是 3 个在实际应用中会遇到的例子：
使用 ajax 请求其他跨域 API，最常见的情况
iframe 与父页面交流（如 DOM 或变量的获取），出现率比较低
对跨域图片（例如来源于 <img> ）进行操作，
在 canvas 操作图片的时候会遇到这个问题

如果没有了 SOP：
iframe 里的机密信息被肆意读取
更加肆意地进行 CSRF
接口被第三方滥用
```

  #### 跨域
因为浏览器出于安全考虑，有同源策略。也就是说，
如果协议、域名或者端口有一个不同就是跨域
```
1. 通过 jsonp 跨域
2. document.domain + iframe 跨域
3. location.hash + iframe
4. window.name + iframe 跨域
5 .postMessage 跨域
6. 跨域资源共享（CORS)
7. nginx 代理跨域
8. nodejs 中间件代理跨域
9. WebSocket 协议跨域
```

```
解决跨域的方法我们可以根据我们想要实现的目的来划分。

首先我们如果只是想要实现主域名下的不同子域名的跨域操作，
我们可以使用设置 document.domain 来解决。
（1）将 document.domain 设置为主域名，来实现相同子域名的跨域操作，
这个时候主域名下的 cookie 就能够被子域名所访问。
同时如果文档中含有主域名相同，子域名不同的 iframe 的话，
我们也可以对这个 iframe 进行操作。

如果是想要解决不同跨域窗口间的通信问题，比如说一个页面
想要和页面的中的不同源的 iframe 进行通信的问题，我们可以使用 
location.hash 或者 window.name 或者 postMessage 来解决。
（2）使用 location.hash 的方法，我们可以在主页面动态的修改 
iframe 窗口的 hash 值，然后在 iframe 窗口里实现监听函数
来实现这样一个单向的通信。因为在 iframe 是没有办法访问到
不同源的父级窗口的，所以我们不能直接修改父级窗口的 hash 值
来实现通信，我们可以在 iframe 中再加入一个 iframe ，
这个 iframe 的内容是和父级页面同源的，所以我们可以使用
window.parent.parent 来修改最顶级页面的 src，以此来实现双向通信。

（3）使用 window.name 的方法，主要是基于同一个窗口中设置了 
window.name 后不同源的页面也可以访问，所以不同源的子页面
可以首先在 window.name 中写入数据，然后跳转到一个和父级同源的页面。
这个时候父级页面就可以访问同源的子页面中 window.name 
中的数据了，这种方式的好处是可以传输的数据量大。

（4）使用 postMessage 来解决的方法，这是一个 h5 中新增的
一个 api。通过它我们可以实现多窗口间的信息传递，通过获取到
指定窗口的引用，然后调用 postMessage 来发送信息，
在窗口中我们通过对 message 信息的监听来接收信息，
以此来实现不同源间的信息交换。

如果是像解决 ajax 无法提交跨域请求的问题，我们可以使用 jsonp、
cors、websocket 协议、服务器代理来解决问题。
（5）使用 jsonp 来实现跨域请求，它的主要原理是通过动态构建 
script  标签来实现跨域请求，因为浏览器对 script 标签的
引入没有跨域的访问限制 。通过在请求的 url 后指定一个回调函数，
然后服务器在返回数据的时候，构建一个 json 数据的包装，
这个包装就是回调函数，然后返回给前端，前端接收到数据后，
因为请求的是脚本文件，所以会直接执行，这样我们先前定义好的
回调函数就可以被调用，从而实现了跨域请求的处理。
这种方式只能用于 get 请求。

（6）使用 CORS 的方式，CORS 是一个 W3C 标准，全称是"跨域资源共享"。
CORS 需要浏览器和服务器同时支持。目前，所有浏览器都支持该功能，
因此我们只需要在服务器端配置就行。浏览器将 CORS 请求分成两类：
简单请求和非简单请求。对于简单请求，浏览器直接发出 CORS 请求。
具体来说，就是会在头信息之中，增加一个 Origin 字段。Origin 
字段用来说明本次请求来自哪个源。服务器根据这个值，决定是否同意这次请求。
对于如果 Origin 指定的源，不在许可范围内，服务器会返回一个正常的 HTTP 回应。
浏览器发现，这个回应的头信息没有包含 Access-Control-Allow-Origin 字段，
就知道出错了，从而抛出一个错误，ajax 不会收到响应信息。
如果成功的话会包含一些以 Access-Control- 开头的字段。
非简单请求，浏览器会先发出一次预检请求，来判断该域名是否
在服务器的白名单中，如果收到肯定回复后才会发起请求。

（7）使用 websocket 协议，这个协议没有同源限制。

（8）使用服务器来代理跨域的访问请求，就是有跨域的请求操作时
发送请求给后端，让后端代为请求，然后最后将获取的结果发返回。
```

   #### jsonp
在CORS和postMessage以前，我们一直都是通过JSONP来做跨域通信的。
```
JSONP的原理：通过<script>标签的异步加载来实现的。
比如说，实际开发中，我们发现，
head标签里，可以通过<script>标签的src，里面放url，
加载很多在线的插件。这就是用到了JSONP。
JSONP 使用简单且兼容性不错，但是只限于 get 请求。
在开发中可能会遇到多个 JSONP 请求的回调函数名是相同的，
这时候就需要自己封装一个 JSONP

JSONP的实现：
比如说，客户端这样写：
    <script src="http://www.smyhvae.com/?data=name&callback=myjsonp"></script>

上面的src中，data=name是get请求的参数，myjsonp是和后台约定好的函数名。 服务器端这样写：
  myjsonp({
      data: {}
  })
于是，本地要求创建一个myjsonp 的全局函数，才能将返回的数据执行出来。
实际开发中，前端的JSONP是这样实现的：
<script>
    var util = {};
    //定义方法：动态创建 script 标签
    /**
     * [function 在页面中注入js脚本]
     * @param  {[type]} url     [description]
     * @param  {[type]} charset [description]
     * @return {[type]}         [description]
     */
    util.createScript = function (url, charset) {
        var script = document.createElement('script');
        script.setAttribute('type', 'text/javascript');
        charset && script.setAttribute('charset', charset);
        script.setAttribute('src', url);
        script.async = true;
        return script;
    };

    /**
     * [function 处理jsonp]
     * @param  {[type]} url      [description]
     * @param  {[type]} onsucess [description]
     * @param  {[type]} onerror  [description]
     * @param  {[type]} charset  [description]
     * @return {[type]}          [description]
     */
    util.jsonp = function (url, onsuccess, onerror, charset) {
        var callbackName = util.getName('tt_player'); //事先约定好的 函数名
        window[callbackName] = function () {      //根据回调名称注册一个全局的函数
            if (onsuccess && util.isFunction(onsuccess)) {
                onsuccess(arguments[0]);
            }
        };
        var script = util.createScript(url + '&callback=' + callbackName, charset);   //动态创建一个script标签
        script.onload = script.onreadystatechange = function () {   //监听加载成功的事件，获取数据
            if (!script.readyState || /loaded|complete/.test(script.readyState)) {
                script.onload = script.onreadystatechange = null;
                // 移除该script的 DOM 对象
                if (script.parentNode) {
                    script.parentNode.removeChild(script);
                }
                // 删除函数或变量
                window[callbackName] = null;  //最后不要忘了删除
            }
        };
        script.onerror = function () {
            if (onerror && util.isFunction(onerror)) {
                onerror();
            }
        };
        document.getElementsByTagName('head')[0].appendChild(script); //往html中增加这个标签，目的是把请求发送出去
    };
</script>
```

   #### 手写一个jsonp
```js
function jsonp(url, params, callback) {
  // 判断是否含有参数
  let queryString = url.indexOf("?") === "-1" ? "?" : "&";

  // 添加参数
  for (var k in params) {
    if (params.hasOwnProperty(k)) {
      queryString += k + "=" + params[k] + "&";
    }
  }

  // 处理回调函数名
  let random = Math.random()
      .toString()
      .replace(".", ""),
    callbackName = "myJsonp" + random;

  // 添加回调函数
  queryString += "callback=" + callbackName;

  // 构建请求
  let scriptNode = document.createElement("script");
  scriptNode.src = url + queryString;

  window[callbackName] = function() {
    // 调用回调函数
    callback(...arguments);

    // 删除这个引入的脚本
    document.getElementsByTagName("head")[0].removeChild(scriptNode);
  };

  // 发起请求
  document.getElementsByTagName("head")[0].appendChild(scriptNode);
}
```

   #### postMessage
H5中新增的postMessage()方法，可以用来做跨域通信。
```
场景：窗口 A (http:A.com)向跨域的窗口 B (http:B.com)发送信息。步骤如下
在A窗口中操作如下：向B窗口发送数据：
	// 窗口A(http:A.com)向跨域的窗口B(http:B.com)发送信息
 	Bwindow.postMessage('data', 'http://B.com'); //这里强调的是B窗口里的window对象
2. 在B窗口中操作如下：
    // 在窗口B中监听 message 事件
    Awindow.addEventListener('message', function (event) {   //这里强调的是A窗口里的window对象
        console.log(event.origin);  //获取 ：url。这里指：http://A.com
        console.log(event.source);  //获取：A window对象
        console.log(event.data);    //获取传过来的数据
    }, false);
```

   #### CORS
```
CORS：不受同源策略的限制，支持跨域。一种新的通信协议标准。
可以理解成是：同时支持同源和跨域的Ajax。
CORS为什么支持跨域的通信？
跨域时，浏览器会拦截Ajax请求，并在http头中加Origin。

浏览器会自动进行 CORS 通信，实现 CORS 通信的关键是后端。
只要后端实现了 CORS，就实现了跨域。服务端设置 
Access-Control-Allow-Origin 就可以开启 CORS。 
该属性表示哪些域名可以访问资源，如果设置通配符则表示所有网站
都可以访问资源。 虽然设置 CORS和前端没什么关系，但是通过这种方式
解决跨域问题的话，会在发送请求时出现两种情况，分别为简单请求和复杂请求。

简单请求：
以 Ajax 为例，当满足以下条件时，会触发简单请求
1.使用下列方法之一：GET、HEAD、POST
2.Content-Type 的值仅限于下列三者之一：text/plain、
multipart/form-data、application/x-www-form-urlencoded

请求中的任意 XMLHttpRequestUpload 对象均没有注册任何事件监听器； 
XMLHttpRequestUpload 对象可以使用XMLHttpRequest.upload 属性访问

复杂请求：
对于复杂请求来说，首先会发起一个预检请求，该请求是 option 方法的，
通过该请求来知道服务端是否允许跨域请求。
对于预检请求来说，如果你使用过 Node 来设置 CORS 的话，可能会遇到过这么一个坑。

以下以 express框架举例
app.use((req, res, next) => {
  res.header('Access-Control-Allow-Origin', '*')
  res.header('Access-Control-Allow-Methods', 'PUT, GET, POST, DELETE, OPTIONS')
  res.header(
    'Access-Control-Allow-Headers',
    'Origin, X-Requested-With, Content-Type, Accept, Authorization, Access-Control-Allow-Credentials'
  )
  next()
})
该请求会验证你的 Authorization 字段，没有的话就会报错。
当前端发起了复杂请求后，你会发现就算你代码是正确的，
返回结果也永远是报错的。因为预检请求也会进入回调中，
也会触发 next 方法，因为预检请求并不包含 Authorization 字段，
所以服务端会报错。
想解决这个问题很简单，只需要在回调中过滤 option 方法即可

res.statusCode = 204
res.setHeader('Content-Length', '0')
res.end()

  if (req.method == "OPTIONS") {
    res.send(200);
  }
  else {
    next();
  }
  
项目实例：
解决方式是给服务器设置允许跨域的字段，一般需要设置如下几个字段，
以express框架来说，设置允许cros跨域响应头：
app.all("*" , function(req,res,next){
	res.header('Access-Control-Allow-Origin' , "*")  
	res.header('Access-Control-Allow-Headers' , 'Content-Type,Content-length,Authorization,Accept,X-Requested-With,yourHeaderFeild');  
	res.header('Access-Control-Allow-Methods' , 'PUT,POST,GEt,DELETE,OPTIONS');  
	if(req.method == 'OPTIONS'){    
		res.send(200)  
	}  else{    
		next()  
	}
})
上述代码中设置细则如下：  
Access-Control-Allow-Origin：设置允许cros跨域的网址
Access-Control-Allow-Headers：设置允许cros跨域的请求头部
Access-Control-Allow-Methods：设置允许cros跨域的请求方式
```

   #### WebSocket
```
WebSocket不受同源策略的限制，支持跨域
用法如下：
    var ws = new WebSocket('wss://echo.websocket.org'); //创建WebSocket的对象。参数可以是 ws 或 wss，后者表示加密。

    //把请求发出去
    ws.onopen = function (evt) {
        console.log('Connection open ...');
        ws.send('Hello WebSockets!');
    };

    //对方发消息过来时，我接收
    ws.onmessage = function (evt) {
        console.log('Received Message: ', evt.data);
        ws.close();
    };

    //关闭连接
    ws.onclose = function (evt) {
        console.log('Connection closed.');
    };
```

```
由于 http 存在一个明显的弊端（消息只能有客户端推送到服务器端，
而服务器端不能主动推送到客户端），导致如果服务器如果有连续的变化，
这时只能使用轮询，而轮询效率过低，并不适合。于是 WebSocket被发明出来

相比与 http 具有以下优点：
支持双向通信，实时性更强；

可以发送文本，也可以二进制文件；

协议标识符是 ws，加密后是 wss ；

较少的控制开销。连接创建后，ws客户端、服务端进行数据交换时，
协议控制的数据包头部较小。在不包含头部的情况下，服务端到
客户端的包头只有2~10字节（取决于数据包长度），客户端到
服务端的的话，需要加上额外的4字节的掩码。而HTTP协议每次
通信都需要携带完整的头部；

支持扩展。ws协议定义了扩展，用户可以扩展协议，
或者实现自定义的子协议。（比如支持自定义压缩算法等）

无跨域问题。

实现比较简单，服务端库如 socket.io、ws，
可以很好的帮助我们入门。而客户端也只需要参照 api 实现即可
```

   #### proxy代理跨域(最常见)
```
使用vue开发的时候，可以使用vue脚手架自带的http-proxy代理程序进行跨域。
步骤：
1.在vue脚手架中新增配置文件vue.config.js文件，添加一个新的配置项，如下：
module.exports = {	
	devServer:{		
		proxy:{			
			'/api':{				
				target:'http://localhost:3000/'//自己的服务器端口3000							
				changeOrigin:true //打开跨域			
			}		
		}	
	}
}
上述代码中设置了一个接口/api，这个接口作为自己的服务器的代理服务器，
即访问这个接口就如访问http://localhost:3000
然后我们需要将这个/api作为我们提交数据的默认地址，
即在vue项目的mian.js文件中设置如下代码，此处以axios为例：
axios.defalts.baseURL = "/api"
```

  #### 鉴权
什么是鉴权：
```
鉴权（authentication）是指验证用户是否拥有访问系统的权利。
传统的鉴权是通过密码来验证的。这种方式的前提是，
每个获得密码的用户都已经被授权。在建立用户时，就为此用户分配一个密码，
用户的密码可以由管理员指定，也可以由用户自行申请。
这种方式的弱点十分明显：一旦密码被偷或用户遗失密码，
情况就会十分麻烦，需要管理员对用户密码进行重新修改，
而修改密码之前还要人工验证用户的合法身份。

为了克服这种鉴权方式的缺点，需要一个更加可靠的鉴权方式。
目前的主流鉴权方式是利用认证授权来验证数字签名的正确与否。

逻辑上，授权发生在鉴权之后，而实际上，这两者常常是一个过程。
```

常用的鉴权有四种：
```
1、HTTP Basic Authentication
2、session-cookie
3、Token验证
4、OAuth(开放授权)
```

鉴权分类：
```
用户鉴权，网络对用户进行鉴权，防止非法用户占用网络资源。
网络鉴权，用户对网络进行鉴权，防止用户接入了非法的网络，被骗取关键信息。
这种双向的认证机制，就是AKA
（Authentication and Key Agreement，鉴权和密钥协商）鉴权。

除了AKA鉴权，也可以使用其它鉴权方式。在IMS AKA鉴权广泛实施之前，
或在特定的条件下（例如通过固定网络ADSL连接方式接入IMS），
可以使用HTTP摘要鉴权等其他鉴权方式。

3G UMTS（Universal Mobile Telecommunication System，通用移动通讯系统）、
EPS（Evolved Packet System，演进的分组系统）、
IMS（IP Multimedia Subsystem，IP多媒体子系统）
网络都采用了AKA双向鉴权机制，鉴权原理也大致相同。
而2G网络，只有用户鉴权，无网络鉴权。
```

```
鉴权时机：
移动网络对鉴权时机的要求为：
2G、3G网络中，鉴权发生在开机、呼叫、位置更新以及在补充业务的
激活、去活、登记或删除操作之前。
2G网络中，运营商都是启用的“按比例鉴权”方案。
3G网络中，用户首次接入网络必须鉴权，此后启用“按比例鉴权”方案。
IMS网络中，网络可以通过注册或重注册过程，在任何时候对用户进行鉴权。
```

   #### HTTP Basic Authentication
```
这种授权方式是浏览器遵守http协议实现的基本授权方式,
HTTP协议进行通信的过程中，
HTTP协议定义了基本认证认证允许HTTP服务器对
客户端进行用户身份证的方法。

认证过程：
1．客户端向服务器请求数据，请求的内容可能是一个网页
或者是一个ajax异步请求，
此时，假设客户端尚未被验证，则客户端提供如下请求至服务器:
Get /index.html HTTP/1.0
Host:www.google.com

2． 服务器向客户端发送验证请求代码401,
（WWW-Authenticate: Basic realm=”google.com”这句话是关键，
如果没有客户端不会弹出用户名和密码输入界面）服务器返回的数据大抵如下：
HTTP/1.0 401 Unauthorised
Server: SokEvo/1.0
WWW-Authenticate: Basic realm=”google.com”
Content-Type: text/html
Content-Length: xxx

3． 当符合http1.0或1.1规范的客户端（如IE，FIREFOX）收到401返回值时，
将自动弹出一个登录窗口，要求用户输入用户名和密码。

4． 用户输入用户名和密码后，将用户名及密码以BASE64加密方式加密，
并将密文放入前一条请求信息中，则客户端发送的第一条请求信息
则变成如下内容：
Get /index.html HTTP/1.0
Host:www.google.com
Authorization: Basic d2FuZzp3YW5n

注：d2FuZzp3YW5n表示加密后的用户名及密码（用户名：密码 然后通过base64加密，
加密过程是浏览器默认的行为，不需要我们人为加密，我们只需要输入用户名密码即可）

5． 服务器收到上述请求信息后，将Authorization字段后的用户信息
取出、解密，将解密后的用户名及密码与用户数据库进行比较验证，
如用户名及密码正确，服务器则根据请求，将所请求资源发送给客户端。

效果：
客户端未未认证的时候，会弹出用户名密码输入框，
这个时候请求时属于pending状态，
这个时候其实服务当用户输入用户名密码的时候客户端
会再次发送带Authentication头的请求。
```

   #### session-cookie
```
HTTP Cookie（也叫Web Cookie或浏览器Cookie）是服务器发送到
用户浏览器并保存在本地的一小块数据，它会在浏览器下次向
同一服务器再发起请求时被携带并发送到服务器上。通常，
它用于告知服务端两个请求是否来自同一浏览器，如保持用户的登录状态。
Cookie使基于无状态的HTTP协议记录稳定的状态信息成为了可能。

Cookie主要用于以下三个方面：
会话状态管理（如用户登录状态、购物车、游戏分数或其它需要记录的信息）
个性化设置（如用户自定义设置、主题等）
浏览器行为跟踪（如跟踪分析用户行为等）

认证过程：
1.服务器在接受客户端首次访问时在服务器端创建seesion，然后
保存seesion(我们可以将seesion保存在内存中，也可以保存在redis中，
推荐使用后者)，然后给这个session生成一个唯一的标识字符串,
然后在响应头中种下这个唯一标识字符串。

2.签名。这一步只是对sid进行加密处理，
3.服务端会根据这个secret密钥进行解密。（非必需步骤）

3.浏览器中收到请求响应的时候会解析响应头，然后将sid保存在本地cookie中，
浏览器在下次http请求的请求头中会带上该域名下的cookie信息。

4.服务器在接受客户端请求时会去解析请求头cookie中的sid，然后根据这个sid
去找服务器端保存的该客户端的session，然后判断该请求是否合法。

5.一旦用户登出，服务端和客户端同时销毁该会话在后续请求中，
6.服务器会根据数据库验证会话id，如果验证通过，则继续处理；
```

   #### token验证
```
认证过程：
1.用户输入登陆凭据；
2.服务器验证凭据是否正确，然后返回一个经过签名的token；
3.客户端负责存储token，可以存在localstorage，或者cookie中
4.对服务器的请求带上这个token；
5.服务器对JWT进行解码，如果token有效，则处理该请求；
6.一旦用户登出，客户端销毁token。

cookie与token性能对比：cookie与token看上去很像，但是有区别
1.sessionid 他只是一个唯一标识的字符串，服务端是根据这个字符串，
来查询在服务器端保持的seesion，这里面才保存着用户的登陆状态。
但是token本身就是一种登陆成功凭证，他是在登陆成功后根据某种规则生成的
一种信息凭证，他里面本身就保存着用户的登陆状态。
服务器端只需要根据定义的规则校验这个token是否合法就行。

2.session-cookie是需要cookie配合的，居然要cookie，
3.那么在http代理客户端的选择上就是只有浏览器了，
因为只有浏览器才会去解析请求响应头里面的cookie,
然后每次请求再默认带上该域名下的cookie。
但是我们知道http代理客户端不只有浏览器，还有原生APP等等，
这个时候cookie是不起作用的，或者浏览器端是可以禁止cookie的，
但是token就不一样，他是登陆请求在登陆成功后再请求响应体中返回的信息，
客户端在收到响应的时候，可以把他存在本地的cookie,storage，
或者内存中，然后再下一次请求的请求头重带上这个token就行了。
简单点来说cookie-session机制他限制了客户端的类型，
而token验证机制丰富了客户端类型。

3.时效性。session-cookie的sessionid实在登陆的时候生成的
而且在登出事时一直不变的，在一定程度上安全就会低，
而token是可以在一段时间内动态改变的。

4.可扩展性。token验证本身是比较灵活的，一是token的解决方案
有许多，常用的是JWT，二来我们可以基于token验证机制，
专门做一个鉴权服务，用它向多个服务的请求进行统一鉴权。
```

   #### OAuth
```
(开放授权)
OAUTH协议为用户资源的授权提供了一个安全的、开放而又简易的标准。
与以往的授权方式不同之处是OAUTH的授权不会使第三方触及到用户的
帐号信息（如用户名与密码），即第三方无需使用用户的用户名与密码
就可以申请获得该用户资源的授权，因此OAUTH是安全的。同时，
任何第三方都可以使用OAUTH认证服务，任何服务提供商都
可以实现自身的OAUTH认证服务，因而OAUTH是开放的。

我们常见的提供OAuth认证服务的厂商有支付宝，QQ，微信。

OAuth协议又有1.0和2.0两个版本。相比较1.0版，
2.0版整个授权验证流程更简单更安全，
也是目前最主要的用户身份验证和授权方式。

典型案例：
如果一个用户拥有两项服务：一项服务是图片在线存储服务A，
另一个是图片在线打印服务B。由于服务A与服务B是由两家不同
的服务提供商提供的，所以用户在这两家服务提供商的网站上
各自注册了用户，假设这两个用户名各不相同，密码也各不相同。

当用户要使用服务B打印存储在服务A上的图片时，用户该如何处理？
方法一：用户可能先将待打印的图片从服务A上下载下来并上传到
服务B上打印，这种方式安全但处理比较繁琐，效率低下；

方法二：用户将在服务A上注册的用户名与密码提供给服务B，
服务B使用用户的帐号再去服务A处下载待打印的图片，
这种方式效率是提高了，但是安全性大大降低了，
服务B可以使用用户的用户名与密码去服务A上查看甚至篡改用户的资源。

方法三：当服务B（打印服务）要访问用户的服务A（图片服务）时，
通过OAUTH机制，服务B向服务A请求未经用户授权的RequestToken后，
服务A将引导用户在服务A的网站上登录，并询问用户是否将
图片服务授权给服务B。用户同意后，服务B就可以访问用户
在服务A上的图片服务。整个过程服务B没有触及到用户在服务A的帐号信息。

OAuth相关术语：
在认证和授权的过程中涉及的三方包括：
(1)服务提供方（ServiceProvider），用户使用服务提供方来
存储受保护的资源，如照片，视频，联系人列表。
(2)用户（User），存放在服务提供方的受保护的资源的拥有者
(3)客户端（Consumer），要访问服务提供方资源的第三方应用，
通常是网站，如提供照片打印服务的网站
也可以是桌面或移动应用程序。在认证过程之前，
客户端要向服务提供者申请客户端标识。

OAuth相关的三个URL：
RequestToken URL:获取未授权的RequestToken服务地址；
UserAuthorization URL:获取用户授权的RequestToken服务地址；
AccessToken URL:用授权的RequestToken换取AccessToken的服务地址。

OAuth认证和授权过程：
(1)客户端（第三方软件）向OAUTH服务提供商请求未授权的RequestToken。
即向RequestToken URL发起请求；
(2)OAUTH服务提供商同意使用者的请求，并向其颁发未经用户授权
的oauth_token与对应的oauth_token_secret，并返回给使用者；
(3)使用者向OAUTH服务提供商请求用户授权的RequestToken。
即向UserAuthorization URL发起请求并在请求中携带
上一步服务提供商颁发的未授权的token与其密钥；
(4)OAUTH服务提供商通过网页要求用户登录并引导用户完成授权；
(5)RequestToken授权后，使用者将向AccessToken URL发起请求，
将上步授权的RequestToken换取成AccessToken。
请求的参数见上图，这个比第一步多了一个参数就是RequestToken；
(6)OAUTH服务提供商同意使用者的请求，并向其颁发AccessToken
与对应的密钥，并返回给使用者；
(7)使用者以后就可以使用上步返回的AccessToken访问用户授权的资源。

简单整理就三个步骤：
1.获取未授权的RequestToken
2.获取用户授权的RequestToken
3.用授权的RequestToken换取AccessToken
```

  #### 哪些操作会造成内存泄漏
```
第一种情况是我们由于使用未声明的变量，而意外的创建了一个全局变量，
而使这个变量一直留在内存中无法被回收。

第二种情况是我们设置了 setInterval 定时器，而忘记取消它，
如果循环函数有对外部变量的引用的话，那么这个变量会被
一直留在内存中，而无法被回收。

第三种情况是我们获取一个 DOM 元素的引用，而后面这个元素被删除，
由于我们一直保留了对这个元素的引用，所以它也无法被回收。

第四种情况是不合理的使用闭包，从而导致某些变量一直被留在内存当中。
```

```
1.意外的全局变量
2.被遗忘的计时器或回调函数
3.脱离 DOM 的引用
4.闭包
```

```
JavaScript 内存泄露指对象在不需要使用它时仍然存在，
导致占用的内存不能使用或回收

未使用 var 声明的全局变量
闭包函数(Closures)

循环引用(两个对象相互引用)

控制台日志(console.log)

移除存在绑定事件的DOM元素(IE)

setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏

垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。
如果一个对象的引用数量为 0（没有其他对象引用过该对象），
或对该对象的惟一引用是循环的，那么该对象的内存即可回收

内存泄漏指任何对象在您不再拥有或需要它之后仍然存在
setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏
闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）
```

  #### 常见web安全及防护原理
```
sql注入原理：
就是通过把SQL命令插入到Web表单递交或输入域名或页面请求的
查询字符串，最终达到欺骗服务器执行恶意的SQL命令

总的来说有以下几点：
永远不要信任用户的输入，要对用户的输入进行校验，
可以通过正则表达式，或限制长度，对单引号和双"-"进行转换等
永远不要使用动态拼装SQL，可以使用参数化的SQL或者
直接使用存储过程进行数据查询存取，永远不要使用
管理员权限的数据库连接，为每个应用使用单独的权限有限的数据库连接
不要把机密信息明文存放，请加密或者hash掉密码和敏感的信息

XSS原理及防范：
Xss(cross-site scripting)攻击指的是攻击者往Web页面里
插入恶意html标签或者javascript代码。比如：
攻击者在论坛中放一个看似安全的链接，骗取用户点击后，
窃取cookie中的用户私密信息；或者攻击者在论坛中加
一个恶意表单，当用户提交表单的时候，却把信息传送到
攻击者的服务器中，而不是用户原本以为的信任站点

XSS防范方法：
首先代码里对用户输入的地方和变量都需要仔细检查长度和对”<”,”>”,”;”,”’”等
字符做过滤；其次任何内容写到页面之前都必须加以encode，
避免不小心把html tag 弄出来。这一个层面做好，至少可以堵住超过一半的XSS 攻击

XSS与CSRF有什么区别吗？
XSS是获取信息，不需要提前知道其他用户页面的代码和数据包。
CSRF是代替用户完成指定的动作，需要知道其他用户页面的代码和
数据包。要完成一次CSRF攻击，受害者必须依次完成两个步骤

登录受信任网站A，并在本地生成Cookie

在不登出A的情况下，访问危险网站B

CSRF的防御：
服务端的CSRF方式方法很多样，但总的思想都是一致的，
就是在客户端页面增加伪随机数通过验证码的方法
```

  #### 什么是XSS攻击？如何防范XSS攻击
```
XSS 攻击指的是跨站脚本攻击，是一种代码注入攻击。
攻击者通过在网站注入恶意脚本，使之在用户的浏览器上运行，
从而盗取用户的信息如 cookie 等。

XSS 的本质是因为网站没有对恶意代码进行过滤，与正常的代码
混合在一起了，浏览器没有办法分辨哪些脚本是可信的，
从而导致了恶意代码的执行。

XSS 一般分为存储型、反射型和 DOM 型。

存储型指的是恶意代码提交到了网站的数据库中，当用户请求数据
的时候，服务器将其拼接为 HTML 后返回给了用户，
从而导致了恶意代码的执行。

反射型指的是攻击者构建了特殊的 URL，当服务器接收到请求后，
从 URL 中获取数据，拼接到 HTML 后返回，从而导致了恶意代码的执行。

DOM 型指的是攻击者构建了特殊的 URL，用户打开网站后，
js 脚本从 URL 中获取数据，从而导致了恶意代码的执行。

XSS 攻击的预防可以从两个方面入手，一个是恶意代码提交的时候，
一个是浏览器执行恶意代码的时候。

对于第一个方面，如果我们对存入数据库的数据都进行的转义处理，
但是一个数据可能在多个地方使用，有的地方可能不需要转义，
由于我们没有办法判断数据最后的使用场景，
所以直接在输入端进行恶意代码的处理，其实是不太可靠的。

因此我们可以从浏览器的执行来进行预防，一种是使用纯前端的方式，
不用服务器端拼接后返回。另一种是对需要插入到 HTML 中的代码
做好充分的转义。对于 DOM 型的攻击，主要是前端脚本的不可靠而造成的，
我们对于数据获取渲染和字符串拼接的时候应该对可能出现的恶意代码情况进行判断。

还有一些方式，比如使用 CSP ，CSP 的本质是建立一个白名单，
告诉浏览器哪些外部资源可以加载和执行，从而防止恶意代码的注入攻击。

还可以对一些敏感信息进行保护，比如 cookie 使用 http-only ，
使得脚本无法获取。也可以使用验证码，避免脚本伪装成用户执行一些操作。
```

  #### 什么是CSRF攻击？如何防范CSRF攻击
```
CSRF 攻击指的是跨站请求伪造攻击，攻击者诱导用户进入一个
第三方网站，然后该网站向被攻击网站发送跨站请求。
如果用户在被攻击网站中保存了登录状态，那么攻击者就
可以利用这个登录状态，绕过后台的用户验证，
冒充用户向服务器执行一些操作。

CSRF 攻击的本质是利用了 cookie 会在同源请求中携带
发送给服务器的特点，以此来实现用户的冒充。

一般的 CSRF 攻击类型有三种：
第一种是 GET 类型的 CSRF 攻击，比如在网站中的一个 img 标签
里构建一个请求，当用户打开这个网站的时候就会自动发起提交。

第二种是 POST 类型的 CSRF 攻击，比如说构建一个表单，
然后隐藏它，当用户进入页面时，自动提交这个表单。

第三种是链接类型的 CSRF 攻击，比如说在 a 标签的 href 
属性里构建一个请求，然后诱导用户去点击。

CSRF 可以用下面几种方法来防护：
第一种是同源检测的方法，服务器根据 http 请求头中 origin 或者 
referer 信息来判断请求是否为允许访问的站点，从而对请求进行过滤。
当 origin 或者 referer 信息都不存在的时候，直接阻止。
这种方式的缺点是有些情况下 referer 可以被伪造。还有就是我们这种
方法同时把搜索引擎的链接也给屏蔽了，所以一般网站会允许搜索引擎
的页面请求，但是相应的页面请求这种请求方式也可能被攻击者给利用。

第二种方法是使用 CSRF Token 来进行验证，服务器向用户返回一个
随机数 Token ，当网站再次发起请求时，在请求参数中加入服务器端
返回的 token ，然后服务器对这个 token 进行验证。这种方法解决了
使用 cookie 单一验证方式时，可能会被冒用的问题，但是这种方法
存在一个缺点就是，我们需要给网站中的所有请求都添加上这个 token，
操作比较繁琐。还有一个问题是一般不会只有一台网站服务器，
如果我们的请求经过负载平衡转移到了其他的服务器，但是这个服务器
的 session 中没有保留这个 token 的话，就没有办法验证了。
这种情况我们可以通过改变 token 的构建方式来解决。

第三种方式使用双重 Cookie 验证的办法，服务器在用户访问网站页面时，
向请求域名注入一个Cookie，内容为随机字符串，然后当用户再次向服务器
发送请求的时候，从 cookie 中取出这个字符串，添加到 URL 参数中，
然后服务器通过对 cookie 中的数据和参数中的数据进行比较，来进行验证。
使用这种方式是利用了攻击者只能利用 cookie，但是不能访问获取 cookie 
的特点。并且这种方法比 CSRF Token 的方法更加方便，并且不涉及到
分布式访问的问题。这种方法的缺点是如果网站存在 XSS 漏洞的，
那么这种方式会失效。同时这种方式不能做到子域名的隔离。

第四种方式是使用在设置 cookie 属性的时候设置 Samesite ，限制 cookie 
不能作为被第三方使用，从而可以避免被攻击者利用。Samesite 一共有
两种模式，一种是严格模式，在严格模式下 cookie 在任何情况下都不可能
作为第三方 Cookie 使用，在宽松模式下，cookie 可以被请求是 GET 请求，
且会发生页面跳转的请求所使用。
```

  #### SQL注入攻击
```
SQL 注入攻击指的是攻击者在 HTTP 请求中注入恶意的 SQL 代码，
服务器使用参数构建数据库 SQL 命令时，恶意 SQL 被一起构造，
破坏原有 SQL 结构，并在数据库中执行，
达到编写程序时意料之外结果的攻击行为。
```

  #### 什么是CSP
```
CSP 指的是内容安全策略，它的本质是建立一个白名单，
告诉浏览器哪些外部资源可以加载和执行。我们只需要配置
规则，如何拦截由浏览器自己来实现。

通常有两种方式来开启 CSP，一种是设置 HTTP 首部中的 
Content-Security-Policy，一种是设置 meta 标签的方式 
<metahttp-equiv="Content-Security-Policy">
```

  #### 什么是点击劫持？如何防范点击劫持
```
点击劫持是一种视觉欺骗的攻击手段，攻击者将需要攻击的网站通过
iframe 嵌套的方式嵌入自己的网页中，
并将 iframe 设置为透明，在页面中透出一个按钮诱导用户点击。

我们可以在 http 相应头中设置 X-FRAME-OPTIONS 来防御用 
iframe 嵌套的点击劫持攻击。通过不同的值，
可以规定页面在特定的一些情况才能作为 iframe 来使用。
```




- [Ajax和axios](#Ajax和axios)
  - [Ajax是什么? 原理？如何创建一个Ajax--55. Ajax 是什么? 如何创建一个 Ajax？  9 Ajax原理](#Ajax是什么原理如何创建一个Ajax)
  - [ajax、axios、fetch区别--105 ajax、axios、fetch区别](#ajaxaxiosfetch区别)

- [概念](#概念)
  - [写JavaScript的基本规范--9. 说几条写 JavaScript 的基本规范？  32 说几条写JavaScript的基本规范  109 说几条写JavaScript的基本规范](#写JavaScript的基本规范)
  - [js的节流与防抖--85 防抖/节流  91. 介绍一下 js 的节流与防抖？](#js的节流与防抖)
  - [js中的深浅拷贝实现--84 深浅拷贝  96. js 中的深浅拷贝实现？](#js中的深浅拷贝实现)
  - [js中的命名规则--166. js 中的命名规则](#js中的命名规则)
  - [对原生Javascript了解程度--58 对原生Javascript了解程度](#对原生Javascript了解程度)
  - [渐进增强和优雅降级--42 渐进增强和优雅降级](#渐进增强和优雅降级)
  - [JavaScript的组成--106 JavaScript的组成](#JavaScript的组成)
  - [如何编写高性能的JavaScript--79. 如何编写高性能的 Javascript ？   110 如何编写高性能的JavaScript](#如何编写高性能的JavaScript)
  - [js语句末尾分号是否可以省略--167. js 语句末尾分号是否可以省略？](#js语句末尾分号是否可以省略)
  - [js延迟加载的方式有哪些--54. js 延迟加载的方式有哪些？  40 js延迟加载的方式有哪些](#js延迟加载的方式有哪些)
  - [使用JS实现获取文件扩展名--90. 使用 JS 实现获取文件扩展名？](#使用JS实现获取文件扩展名)
  - [对web标准、可用性、可访问性的理解--50 对web标准、可用性、可访问性的理解](#对web标准可用性可访问性的理解)
  - [对于JSON的了解--52. 对于 JSON 的了解？  39 JSON 的了解](#对于JSON的了解)
  - [XML和JSON的区别--14 XML和JSON的区别？](#XML和JSON的区别)
  - [JavaScript对象生命周期的理解--97 JavaScript 对象生命周期的理解](#JavaScript对象生命周期的理解)
  - [requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何缓存的？）--67. requireJS 的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何 缓存的？）](#requireJS的核心原理是什么如何动态加载的如何避免多次加载的如何缓存的)
  - [什么是“前端路由”？什么时候适合使用“前端路由”？“前端路由”有哪些优点和缺点--86. 什么是“前端路由”？什么时候适合使用“前端路由”？“前端路由”有哪些优点和缺点？](#什么是前端路由什么时候适合使用前端路由前端路由有哪些优点和缺点)
  - [Polyfill--89. 什么是 Polyfill ？](#Polyfill)
  - [rest参数--128. 什么是 rest 参数？](#rest参数)
  - [Proxy--133. 什么是 Proxy ？](#Proxy)
  - [gulp--61 gulp是什么](#gulp)
  - [web开发中会话跟踪的方法有哪些--29 web开发中会话跟踪的方法有哪些](#web开发中会话跟踪的方法有哪些)
  - [进程间通信的方式--173. 进程间通信的方式？](#进程间通信的方式)
  - [Reflect对象创建目的--134. Reflect 对象创建目的？](#Reflect对象创建目的)

- [ES6](#ES6) 46 谈谈你对ES6的理解
  - [let var const--52 谈一谈let与var的区别  127. let 和 const 的注意点？  64 let var const](#let var const)

- [实现](#实现)
  - [Js动画与CSS动画区别及相应实现--119. Js 动画与 CSS 动画区别及相应实现  59 Js动画与CSS动画区别及相应实现](#Js动画与CSS动画区别及相应实现)
  - [js拖拽功能的实现,对页面某个节点的拖曳如何做？（使用原生JS）--125. js 拖拽功能的实现  75 （设计题）想实现一个对页面某个节点的拖曳？如何做？（使用原生JS）](#js拖拽功能的实现对页面某个节点的拖曳如何做使用原生JS)
  - [使用js实现一个持续的动画效果--77 使用js实现一个持续的动画效果](#使用js实现一个持续的动画效果)
  - [实现点击容器内的图标，图标边框变成border:1px solid red，点击空白处重置--92 实现效果，点击容器内的图标，图标边框变成border 1px solid red，点击空白处重置](#实现点击容器内的图标图标边框变成border1px-solid-red点击空白处重置)
  - [canvas上面随机布着一些黑块，请实现方法，计算canvas上有多少个黑块--98 我现在有一个canvas，上面随机布着一些黑块，请实现方法，计算canvas上有多少个黑块](#canvas上面随机布着一些黑块请实现方法计算canvas上有多少个黑块)
  - [怎么做JS代码Error统计--139. 怎么做 JS 代码 Error 统计？](#怎么做JS代码Error统计)
  - [完成一个Dialog组件，说说你设计的思路？它应该有什么功能--103 现在要你完成一个Dialog组件，说说你设计的思路？它应该有什么功能？](#完成一个Dialog组件说说你设计的思路它应该有什么功能)
  - [js中倒计时的纠偏实现--172. js 中倒计时的纠偏实现？](#js中倒计时的纠偏实现)
  - [函数柯里化的实现--98. 函数柯里化的实现](#函数柯里化的实现)
  - [EventEmitter实现--163. EventEmitter 实现](#EventEmitter实现)
  - [如何查找一篇英文文章中出现频率最高的单词--174. 如何查找一篇英文文章中出现频率最高的单词？](#如何查找一篇英文文章中出现频率最高的单词)
  *- [94 实现Storage，使得该对象为单例，并对localStorage进行封装设置值setItem(key,value)和getItem(key)](#)
  - [获取页面所有的checkbox--67 希望获取到页面中所有的checkbox怎么做？  73 获取页面所有的checkbox](#获取页面所有的checkbox)

- [宏任务和微任务](#宏任务和微任务)
  - [requestAnimationFrame--114. 什么是 requestAnimationFrame ？](#requestAnimationFrame)
  - [为什么使用setTimeout实现setInterval？怎么模拟--126. 为什么使用 setTimeout 实现 setInterval？怎么模拟？](#为什么使用setTimeout实现setInterval怎么模拟)

- [对比](#对比)
  - [addEventListener()和attachEvent()的区别--72 addEventListener()和attachEvent()的区别](#addEventListener和attachEvent的区别)
  - [attribute和property的区别是什么--45 attribute和property的区别是什么](#attribute和property的区别是什么)
  - [caller和callee的区别--104 caller和callee的区别](#caller和callee的区别)
  - [documen.write和innerHTML的区别--70. documen.write 和 innerHTML 的区别？](#documenwrite和innerHTML的区别)
  - [escape,encodeURI,encodeURIComponent区别--93. escape,encodeURI,encodeURIComponent 有什么区别？](#escape,encodeURI,encodeURIComponent区别)
  - [innerHTML与outerHTML的区别--72. innerHTML 与 outerHTML 的区别？](#innerHTML与outerHTML的区别)
  - [Javascript中callee和caller的作用--70 Javascript中callee和caller的作用？](#Javascript中callee和caller的作用)
  - [js代码中的"use strict";是什么意思?使用它区别是什么--47. javascript 代码中的 "use strict"; 是什么意思 ? 使用它区别是什么？ 38 javascript 代码中的"use strict";是什么意思](#js代码中的use-strict是什么意思使用它区别是什么)
  - [mouseover和mouseenter区别--124. mouseover 和 mouseenter 的区别？](#mouseover和mouseenter区别)
  *- [116. offsetWidth/offsetHeight,clientWidth/clientHeight 与 scrollWidth/scrollHeight 的区别？  20 offsetWidth/offsetHeight,clientWidth/clientHeight与scrollWidth/scrollHeight的区别](#)
  - [toPrecision和toFixed和Math.round的区别--101. toPrecision 和 toFixed 和 Math.round 的区别？](#toPrecision和toFixed和Mathround的区别)
  - [Unicode和UTF-8之间的关系--94. Unicode 和 UTF-8 之间的关系？](#Unicode和UTF-8之间的关系)
  - [window.onload和$(document).ready--71 window.onload和$(document).ready](#windowonload和documentready)
  - [区分什么是“客户区坐标”、“页面坐标”、“屏幕坐标”--122 区分什么是“客户区坐标”、“页面坐标”、“屏幕坐标”](#区分什么是客户区坐标页面坐标屏幕坐标)

- [算法](#算法)
  - [常用正则表达式--31. 常用正则表达式  69 正则表达式](#常用正则表达式)
  - [生成随机数的各种方法--32. 生成随机数的各种方法？](#生成随机数的各种方法)
  - [为什么0.1+0.2!=0.3？如何解决这个问题--99. 为什么 0.1+0.2 != 0.3？如何解决这个问题？](#为什么010203如何解决这个问题)
  - [原码、反码和补码的介绍--100. 原码、反码和补码的介绍](#原码反码和补码的介绍)
  - [什么是尾调用，使用尾调用有什么好处--129. 什么是尾调用，使用尾调用有什么好处？](#什么是尾调用使用尾调用有什么好处)
  - [js中不同进制数字的表示方式--12. 在 js 中不同进制数字的表示方式](#js中不同进制数字的表示方式)
  - [Math.ceil和Math.floor--169. Math.ceil 和 Math.floor](#Math.ceil和Math.floor)
  - [[,,,]的长度--77. [,,,] 的长度？](#[,,,]的长度)
  - [js for循环注意点--170. js for 循环注意点](#js-for循环注意点)

- [其他](#其他)
  - [hybrid--89 前端面试之hybrid](#hybrid)
  - [组件化--90 前端面试之组件化](#组件化)
  *- [87. 如何测试前端代码么？ 知道 BDD, TDD, Unit Test 么？ 知道怎么测试你的前端工程么(mocha, sinon, jasmin, qUnit..)？](#)
  - [为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片--142 为什么通常在发送数据埋点请求的时候使用的是 1x1 像素的透明 gif 图片](#为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片)
  - [如何确定页面的可用性时间，什么是Performance API--165. 如何确定页面的可用性时间，什么是 Performance API？](#如何确定页面的可用性时间什么是Performance-API)
  - [event loop--95 说说event loop  ](#event-loop)
  - [Electron--83 尽可能多的说出你对 Electron 的理解](#Electron)
  - [有四个操作会忽略enumerable为false的属性--140 有四个操作会忽略enumerable为false的属性	](#有四个操作会忽略enumerable为false的属性)
  - [164. 一道常被人轻视的前端 JS 面试题](#)
  - [123 解释一下这段代码的意思](#)




	概念
	
	webpack
	115. 谈谈你对 webpack 的看法   15 谈谈你对webpack的看法

	node
	26 Node的应用场景

	jQuery
	24 你觉得jQuery源码有哪些写的好的地方
	88 是否用过 jQuery 的 Deferred

	算法

	安全

	优化

	DOM

	模块化

	模式

	同步和异步

	面向对象

	Cookie 

	浏览器

·	事件

·	This

·	js继承

·	js原型和原型链  

·	函数

·	数组

·	操作符

·	js数据类型  

o	js类型判断

o	js类型转换
	
·	类和对象

·	属性

·	字符串










