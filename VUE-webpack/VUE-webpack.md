## 框架面试知识点总结
整理了 VUE、React、jQuery、webpack、 Bootstrap面试的部分知识点

### 目录
- [VUE](#VUE)
  - [vue 的生命周期函数](#vue-的生命周期函数)  7 生命周期
  - [Vue中父子组件生命周期执行顺序](#vue中父子组件生命周期执行顺序)
  - [vue 双向数据绑定原理](#vue-双向数据绑定原理)
  - [vuex](#vuex) 9 vuex
  - [MVVM 和 MVC的区别](#mvvm-和-mvc的区别)
  - [vue 的优点](#vue-的优点)
  - [vue 的响应式原理](#vue-的响应式原理)  1 Vue 响应式原理
  - [发布订阅模式和观察者模式](#发布订阅模式和观察者模式) 2 发布订阅模式和观察者模式
  - [Object.defineProperty 介绍](#objectdefineproperty-介绍)
  - [使用 Object.defineProperty() 来进行数据劫持有什么缺点](#使用-objectdefineproperty-来进行数据劫持有什么缺点)
  - [v-if 和 v-show 的区别](#v-if-和-v-show-的区别)
  - [为什么 vue 组件中的 data 必须是函数](#为什么-vue-组件中的-data-必须是函数)
  - [vue 的 activated 和 deactivated 钩子函数](#vue-的-activated-和-deactivated-钩子函数)
  - [nextTick 用法](#nexttick-用法)  6 nextTick
  - [vue中key属性的作用](#vue中key属性的作用)
  - [Vue中key属性用index为什么不行](#vue中key属性用index为什么不行)
  - [Vue的路由模式](#vue的路由模式)  8 vue-router
  - [vue中\$router和\$route的区别](#vue中router和route的区别)
  - [](#) 10 vue3带来的新特性/亮点
  - [](#) 4 VDOM：三个 part
  - [](#) 3 为什么使用 Virtual DOM
  - [](#) 11 Compositon api
  - [Vue diff算法详解](#vue-diff算法详解)
  - [移动端适配的方法](#移动端适配的方法)
  - [rem 原理](#rem-原理)
  - [rem 和 em 的区别](#rem-和-em-的区别)
  - [移动端 300ms 延迟的原因以及解决方案](#移动端-300ms-延迟的原因以及解决方案)
  - [](#)  5 vue 和 react技术选型
  - [Vue 和 React 数据驱动的区别](#vue-和-react-数据驱动的区别)


- [React](#React)
  - [React生命周期](#React生命周期)  1 React生命周期
  - [](#)  23 组件之间通信
  - [](#)  4. 组件的渲染顺序
  - [](#)  8 React组件和渲染更新过程
  - [](#)  1. React 都做过哪些优化
  - [](#)  13 React有哪些优化性能的手段
  - [](#)  9 diff算法是怎么运作
  - [](#)  24 React router
  - [](#)  18 redux 中间件
  - [](#)  14 Redux实现原理解析
  - [](#)  17 聊聊 Redux 和 Vuex 的设计思想
  - [](#)  19 redux数据管理
  - [](#)  3. React Fiber是什么
  - [](#)  2 React Fiber架构
  - [](#)  5 React Fiber架构总结
  - [](#)  7 React事务机制
  - [](#)  2. 浏览器一帧都会干些什么以及requestIdleCallback的启示
  - [](#)  3 createElement过程
  - [](#)  5 setState
  - [](#)  6 setState原理分析
  - [](#)  4 调和阶段 setState内部干了什么
  - [](#)  22 如何避免ajax数据请求重新获取
  - [](#)  12 为什么 React 元素有一个 $$typeof 属性
  - [](#)  10 合成事件原理
  - [](#)  16 react hooks，它带来了那些便利
  - [](#)  15 connect组件原理分析
  - [](#)  11 JSX语法糖本质
  - [](#)  20 受控组件和非受控组件
  - [](#)  21 SSR原理


- [jQuery](#jQuery)
  - [](#)  2 jQuery 的实现原理
  - [](#)  12 针对 jQuery 的优化方法
  - [](#)  17 jQuery对象的特点
  - [](#)  1 你觉得jQuery或zepto源码有哪些写的好的地方
  - [](#)  11 jQuery 一个对象可以同时绑定多个事件，这是如何实现的
  - [](#)  5 jQuery 的属性拷贝(extend)的实现原理是什么，如何实现深拷贝
  - [](#)  6 jQuery 的队列是如何实现的
  - [](#)  10 jQuery 中如何将数组转化为 JSON 字符串，然后再转化回来
  - [](#)  9 jQuery 通过哪个方法和 Sizzle 选择器结合的
  - [](#)  3 jQuery.fn 的 init 方法返回的 this 指的是什么对象
  - [](#)  4 jQuery.extend 与 jQuery.fn.extend 的区别
  - [](#)  7 jQuery 中的 bind(), live(), delegate(), on()的区别
  - [](#)  8 是否知道自定义事件
  - [](#)  14 jQuery UI 如何自定义组件
  - [](#)  15 jQuery 与 jQuery UI、jQuery Mobile 区别
  - [](#)  13 jQuery 的 slideUp 动画，当鼠标快速连续触发, 动画会滞后反复执行，该如何处理呢
  - [](#)  16 jQuery 和 Zepto 的区别？ 各自的使用场景


- [微信小程序](#微信小程序)
  - [](#)  5 微信小程序与vue区别
  - [](#)  1 微信小程序有几个文件
  - [](#)  2 微信小程序怎样跟事件传值
  - [](#)  3 小程序的 wxss 和 css 有哪些不一样的地方？
  - [](#)  4 小程序关联微信公众号如何确定用户的唯一性


- [webpack相关](#webpack相关)
  - [](#)  1 打包体积 优化思路
  - [](#)  2 打包效率
  - [](#)  3 Loader
  - [](#)  4 说一下webpack的一些plugin，怎么使用webpack对项目进行优化


- [Bootstrap](#Bootstrap)
  - [](#)  1 什么是Bootstrap？以及为什么要使用Bootstrap？
  - [](#)  2 使用Bootstrap时，要声明的文档类型是什么？以及为什么要这样声明？
  - [](#)  3 什么是Bootstrap网格系统
  - [](#)  4 Bootstrap 网格系统（Grid System）的工作原理
  - [](#)  5 对于各类尺寸的设备，Bootstrap设置的class前缀分别是什么
  - [](#)  6 Bootstrap 网格系统列与列之间的间隙宽度是多少
  - [](#)  7 如果需要在一个标题的旁边创建副标题，可以怎样操作
  - [](#)  8 用Bootstrap，如何设置文字的对齐方式？
  - [](#)  9 Bootstrap如何设置响应式表格？
  - [](#)  10 使用Bootstrap创建垂直表单的基本步骤？
  - [](#)  11 使用Bootstrap创建水平表单的基本步骤？
  - [](#)  12 使用Bootstrap如何创建表单控件的帮助文本？
  - [](#)  13 使用Bootstrap激活或禁用按钮要如何操作？
  - [](#)  14 Bootstrap有哪些关于的class？
  - [](#)  15 Bootstrap中有关元素浮动及清除浮动的class？
  - [](#)  16 除了屏幕阅读器外，其他设备上隐藏元素的class？
  - [](#)  17 Bootstrap如何制作下拉菜单？
  - [](#)  18 Bootstrap如何制作按钮组？以及水平按钮组和垂直按钮组的优先级？
  - [](#)  19 Bootstrap如何设置按钮的下拉菜单？
  - [](#)  20 Bootstrap中的输入框组如何制作？
  - [](#)  21 Bootstrap中的导航都有哪些？
  - [](#)  22 Bootstrap中设置分页的class？
  - [](#)  23 Bootstrap中显示标签的class？
  - [](#)  24 Bootstrap中如何制作徽章？
  - [](#)  25 Bootstrap中超大屏幕的作用是什么？






