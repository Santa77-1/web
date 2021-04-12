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





### VUE

  #### vue的生命周期函数
```
beforeCreate:
在实例初始化之后，数据观测 (data observer) 和 event/watcher 
事件配置之前被调用。

在new一个vue实例后，只有一些默认的生命周期钩子和默认事件，其他的东西
都还没创建。在beforeCreate生命周期执行的时候，data和methods中的
数据都还没有初始化。不能在这个阶段使用data中的数据和methods中的方法

created:
在实例创建完成后被立即调用。在这一步，实例已完成以下的配置：
数据观测 (data observer)，property 和方法的运算，watch/event 事件回调。
然而，挂载阶段还没开始，\$el property 目前尚不可用。

data 和 methods都已经被初始化好了，如果要调用 methods 中的方法，
或者操作 data 中的数据，最早可以在这个阶段中操作

beforeMount:
在挂载开始之前被调用：相关的 render 函数首次被调用。

执行到这个钩子的时候，在内存中已经编译好了模板了，
但是还没有挂载到页面中，此时，页面还是旧的

mounted:
实例被挂载后调用，这时 el 被新创建的 vm.\$el 替换了。
如果根实例挂载到了一个文档内的元素上，
当 mounted 被调用时 vm.\$el 也在文档内。

执行到这个钩子的时候，就表示Vue实例已经初始化完成了。此时组件
脱离了创建阶段，进入到了运行阶段。如果我们想要通过插件操作
页面上的DOM节点，最早可以在这个阶段中进行

beforeUpdate:
当执行这个钩子时，页面中的显示的数据还是旧的，
data中的数据是更新后的， 页面还没有和最新的数据保持同步

updated:
页面显示的数据和data中的数据已经保持同步了，都是最新的

beforeDestroy:
Vue实例从运行阶段进入到了销毁阶段，这个时候上所有的 data 和 
methods，指令，过滤器……都是处于可用状态，还没有真正被销毁

destroyed:
这个时候上所有的 data 和 methods，指令，过滤器……
都是处于不可用状态，组件已经被销毁了。

activated:
被 `keep-alive` 缓存的组件激活时调用。

deactivated:
被 `keep-alive` 缓存的组件停用时调用。
```

```
init：
1.initLifecycle/Event，往vm上挂载各种属性
2.callHook: beforeCreated: 实例刚创建
3.initInjection/initState: 初始化注入和 data 响应性
4.created: 创建完成，属性已经绑定， 但还未生成真实dom`
5.进行元素的挂载： $el / vm.$mount()
6.是否有template: 解析成 render function
    *.vue文件: vue-loader会将<template>编译成render function
7.beforeMount: 模板编译/挂载之前
8.执行render function，生成真实的dom，并替换到dom tree中
9.mounted: 组件已挂载

update：
1.执行diff算法，比对改变是否需要触发UI更新
2.flushScheduleQueue
3.watcher.before: 触发beforeUpdate钩子 - watcher.run(): 
  执行watcher中的 notify，通知所有依赖项更新UI
4.触发updated钩子: 组件已更新
5.actived / deactivated(keep-alive): 不销毁，缓存，组件激活与失活
6.destroy
  beforeDestroy: 销毁开始
  销毁自身且递归销毁子组件以及事件监听
    remove(): 删除节点
    watcher.teardown(): 清空依赖
    vm.$off(): 解绑监听
  destroyed: 完成后触发钩子
  
  
Vue2和Vue3对比：
Vue2	                  Vue3
beforeCreate	          setup(替代)
created	                setup(替代)
beforeMount	            onBeforeMount
mounted	                onMounted
beforeUpdate           	onBeforeUpdate
updated	                nUpdated
beforeDestroy	          onBeforeUnmount
destroyed	              onUnmounted
errorCaptured          	onErrorCaptured
-	                      onRenderTracked
-	                      onRenderTriggered


上面是vue的声明周期的简单梳理，
接下来我们直接以代码的形式来完成vue的初始化：
new Vue({})

// 初始化Vue实例
function _init() {
	 // 挂载属性
    initLifeCycle(vm) 
    // 初始化事件系统，钩子函数等
    initEvent(vm) 
    // 编译slot、vnode
    initRender(vm) 
    // 触发钩子
    callHook(vm, 'beforeCreate')
    // 添加inject功能
    initInjection(vm)
    // 完成数据响应性 props/data/watch/computed/methods
    initState(vm)
    // 添加 provide 功能
    initProvide(vm)
    // 触发钩子
    callHook(vm, 'created')
		
	 // 挂载节点
    if (vm.$options.el) {
        vm.$mount(vm.$options.el)
    }
}

// 挂载节点实现
function mountComponent(vm) {
	 // 获取 render function
    if (!this.options.render) {
        // template to render
        // Vue.compile = compileToFunctions
        let { render } = compileToFunctions() 
        this.options.render = render
    }
    // 触发钩子
    callHook('beforeMounte')
    // 初始化观察者
    // render 渲染 vdom， 
    vdom = vm.render()
    // update: 根据 diff 出的 patchs 挂载成真实的 dom 
    vm._update(vdom)
    // 触发钩子  
    callHook(vm, 'mounted')
}

// 更新节点实现
funtion queueWatcher(watcher) {
	nextTick(flushScheduleQueue)
}

// 清空队列
function flushScheduleQueue() {
	 // 遍历队列中所有修改
    for(){
	    // beforeUpdate
        watcher.before()
         
        // 依赖局部更新节点
        watcher.update() 
        callHook('updated')
    }
}

// 销毁实例实现
Vue.prototype.$destory = function() {
	 // 触发钩子
    callHook(vm, 'beforeDestory')
    // 自身及子节点
    remove() 
    // 删除依赖
    watcher.teardown() 
    // 删除监听
    vm.$off() 
    // 触发钩子
    callHook(vm, 'destoryed')
}
```

  #### Vue中父子组件生命周期执行顺序
```
在单一组件中，钩子的执行顺序是
beforeCreate-> created -> mounted->... ->destroyed
```

父子组件生命周期执行顺序：

加载渲染过程
  ```txt
  父beforeCreate->父created->父beforeMount->子beforeCreate->子created->子beforeMount->子mounted->父mounted
  ```

更新过程
  ```txt
  父beforeUpdate->子beforeUpdate->子updated->父updated
  ```

销毁过程
  ```txt
  父beforeDestroy->子beforeDestroy->子destroyed->父destroyed
  ```

常用钩子简易版
  ```txt
  父create->子created->子mounted->父mounted
  ```

  #### vue双向数据绑定原理
```
vue 通过使用双向数据绑定，来实现了 View 和 Model 的同步更新。
vue 的双向数据绑定主要是通过使用数据劫持和发布订阅者模式来实现的。

首先我们通过 Object.defineProperty() 方法来对 Model 数据各个
属性添加访问器属性，以此来实现数据的劫持，因此当 Model 中的数据
发生变化的时候，我们可以通过配置的 setter 和 getter 方法来
实现对 View 层数据更新的通知。

数据在 html 模板中一共有两种绑定情况，一种是使用 v-model 来对 
value 值进行绑定，一种是作为文本绑定，在对模板引擎进行解析的过程中。

如果遇到元素节点，并且属性值包含 v-model 的话，我们就从 Model 中
去获取 v-model 所对应的属性的值，并赋值给元素的 value 值。
然后给这个元素设置一个监听事件，当 View 中元素的数据发生变化
的时候触发该事件，通知 Model 中的对应的属性的值进行更新。

如果遇到了绑定的文本节点，我们使用 Model 中对应的属性的值来
替换这个文本。对于文本节点的更新，我们使用了发布订阅者模式，
属性作为一个主题，我们为这个节点设置一个订阅者对象，将这个订阅者对象
加入这个属性主题的订阅者列表中。当 Model 层数据发生改变的时候，
Model 作为发布者向主题发出通知，主题收到通知再向它的所有订阅者推送，
订阅者收到通知后更改自己的数据。
```

  #### vuex
```
Vuex 集中式存储管理应用的所有组件的状态，
并以相应的规则保证状态以可预测的方式发生变化

核心概念：
state: 状态中心
mutations: 更改状态
actions: 异步更改状态
getters: 获取状态
modules: 将state分成多个modules，便于管理

1.状态 - state
state保存应用状态

export default new Vuex.Store({ state: { counter:0 },})

2.状态变更 - mutations
mutations用于修改状态，store.js

export default new Vuex.Store({
    mutations:
    {
      add(state) {
        state.counter++
      }
    }
  })
  
3.派生状态 - getters
从state派生出新状态，类似计算属性

export default new Vuex.Store({
    getters:
    {
      doubleCounter(state) { // 计算剩余数量 return state.counter * 2;
      }
    }
  })
  
4.动作 - actions
加业务逻辑，类似于controller

export default new Vuex.Store({
    actions:
    {
      add({
        commit
      }) {
        setTimeout(() = >{}
      }
    })
测试代码:

<p @click="$store.commit('add')">counter: {{$store.state.counter}}</p>
<p @click="$store.dispatch('add')">async counter: {{$store.state.counter}}</p>
<p>double:{{$store.getters.doubleCounter}}</p>

vuex原理解析
(1)实现一个插件:声明Store类，挂载$store
(2)Store具体实现:
  创建响应式的state，保存mutations、actions和getters
  实现commit根据用户传入type执行对应mutation
  实现dispatch根据用户传入type执行对应action，同时传递上下文
  实现getters，按照getters定义对state做派生
  
// 目标1：实现Store类，管理state（响应式的），commit方法和dispatch方法
// 目标2：封装一个插件，使用更容易使用
let Vue;

class Store {
  constructor(options) {
    // 定义响应式的state
    // this.$store.state.xx
    // 借鸡生蛋
    this._vm = new Vue({
      data: {
        $$state: options.state
      }
    })
    
    this._mutations = options.mutations
    this._actions = options.actions

    // 绑定this指向
    this.commit = this.commit.bind(this)
    this.dispatch = this.dispatch.bind(this)
  }

  // 只读
  get state() {
    return this._vm._data.$$state
  }

  set state(val) {
    console.error('不能直接赋值呀，请换别的方式！！天王盖地虎！！');
    
  }
  
  // 实现commit方法，可以修改state
  commit(type, payload) {
    // 拿出mutations中的处理函数执行它
    const entry = this._mutations[type]
    if (!entry) {
      console.error('未知mutaion类型');
      return
    }

    entry(this.state, payload)
  }

  dispatch(type, payload) {
    const entry = this._actions[type]

    if (!entry) {
      console.error('未知action类型');
      return
    }

    // 上下文可以传递当前store实例进去即可
    entry(this, payload)
  }
}

function install(_Vue){
  Vue = _Vue

  // 混入store实例
  Vue.mixin({
    beforeCreate() {
      if (this.$options.store) {
        Vue.prototype.$store = this.$options.store
      }
    }
  })
}

// { Store, install }相当于Vuex
// 它必须实现install方法
export default { Store, install }
```

  #### MVVM和MVC的区别
```
MVC: MVC是应用最广泛的软件架构之一,一般MVC分为:
Model(模型),View(视图),Controller(控制器)。 这主要是
基于分层的目的,让彼此的职责分开.View一般用过Controller来
和Model进行联系。Controller是Model和View的协调者,
View和Model不直接联系。基本都是单向联系。

1. View传送指令到Controller。
2. Controller完成业务逻辑后改变Model状态。
3. Model将新的数据发送至View,用户得到反馈。

MVVM: MVVM是把MVC中的Controller改变成了ViewModel。

View的变化会自动更新到ViewModel,ViewModel的变化
也会自动同步到View上显示,通过数据来显示视图层。

MVVM和MVC的区别:
  MVC中Controller演变成MVVM中的ViewModel
  MVVM通过数据来显示视图层而不是节点操作
  MVVM主要解决了MVC中大量的dom操作使页面渲染性能降低,
  加载速度变慢,影响用户体验
```

  #### vue的优点
```
轻量级框架
简单易学
双向数据绑定
组件化
视图，数据，结构分离
虚拟 DOM
运行速度更快
```

  #### vue的响应式原理
```
数据发生变化后，会重新对页面渲染，这就是 Vue 响应式

想完成这个过程，我们需要：
  侦测数据的变化
  收集视图依赖了哪些数据
  数据变化时，自动“通知”需要更新的视图部分，并进行更新

对应专业俗语分别是：
数据劫持 / 数据代理
依赖收集
发布订阅模式
```

```
Vue 的响应式原理是核心是通过 ES5 的保护对象的 Object.defindeProperty 
中的访问器属性中的 get 和 set 方法，data 中声明的属性都被添加了
访问器属性，当读取 data 中的数据时自动调用 get 方法，当修改 data 
中的数据时，自动调用 set 方法，检测到数据的变化，会通知观察者 Wacher，
观察者 Wacher自动触发重新render 当前组件（子组件不会重新渲染）,
生成新的虚拟 DOM 树，Vue 框架会遍历并对比新虚拟 DOM 树和
旧虚拟 DOM 树中每个节点的差别，并记录下来，最后，加载操作，
将所有记录的不同点，局部修改到真实 DOM树上。

1.虚拟DOM (Virtaul DOM): 用 js 对象模拟的，保存当前视图内所有 
  DOM 节点对象基本描述属性和节点间关系的树结构。用 js 对象，
  描述每个节点，及其父子关系，形成虚拟 DOM 对象树结构。
2.因为只要在 data 中声明的基本数据类型的数据，基本不存在
  数据不响应问题，所以重点介绍数组和对象在vue中的数据响应问题，
  vue可以检测对象属性的修改，但无法监听数组的所有变动及
  对象的新增和删除，只能使用数组变异方法及$set方法。

总结：Vue 采用数据劫持结合发布—订阅模式的方法，通过
Object.defineProperty() 来劫持各个属性的 setter，getter，
在数据变动时发布消息给订阅者，触发相应的监听回调。

1.Observer 遍历数据对象，给所有属性加上 setter 和 getter，监听数据的变化
2.compile 解析模板指令，将模板中的变量替换成数据，
  然后初始化渲染页面视图，并将每个指令对应的节点绑定更新函数，
  添加监听数据的订阅者，一旦数据有变动，收到通知，更新视图
  
  Watcher 订阅者是 Observer 和 Compile 之间通信的桥梁，主要做的事情

1.在自身实例化时往属性订阅器 (dep) 里面添加自己
2.待属性变动 dep.notice() 通知时，调用自身的 update() 方法，
  并触发 Compile 中绑定的回调
  
Object.defineProperty()，那么它的用法是什么，以及优缺点是什么呢？
  1.可以检测对象中数据发生的修改
  2.对于复杂的对象，层级很深的话，是不友好的，需要经行深度监听，
    这样子就需要递归到底，这也是它的缺点。
  3.对于一个对象中，如果你新增加属性，删除属性，
    **Object.defineProperty()**是不能观测到的，那么应该如何解决呢？
    可以通过Vue.set()和Vue.delete()来实现。
// 模拟 Vue 中的 data 选项 
let data = {
    msg: 'hello'
}
// 模拟 Vue 的实例 
let vm = {}
// 数据劫持:当访问或者设置 vm 中的成员的时候，做一些干预操作
Object.defineProperty(vm, 'msg', {
  // 可枚举(可遍历)
  enumerable: true,
  // 可配置(可以使用 delete 删除，可以通过 defineProperty 重新定义) 
  configurable: true,
  // 当获取值的时候执行 
  get () {
    console.log('get: ', data.msg)
    return data.msg 
  },
  // 当设置值的时候执行 
  set (newValue) {
    console.log('set: ', newValue) 
    if (newValue === data.msg) {
      return
    }
    data.msg = newValue
    // 数据更改，更新 DOM 的值 
    document.querySelector('#app').textContent = data.msg
  } 
})

// 测试
vm.msg = 'Hello World' 
console.log(vm.msg)

Vue3.x响应式数据原理：
Vue3.x改用Proxy替代Object.defineProperty。因为Proxy可以
直接监听对象和数组的变化，并且有多达13种拦截方法。
并且作为新标准将受到浏览器厂商重点持续的性能优化。

Proxy只会代理对象的第一层，那么Vue3又是怎样处理这个问题的呢？
判断当前Reflect.get的返回值是否为Object，如果是则
再通过reactive方法做代理， 这样就实现了深度观测。

监测数组的时候可能触发多次get/set，那么如何防止触发多次呢？
我们可以判断key是否为当前被代理对象target自身属性，也可以判断
旧值与新值是否相等，只有满足以上两个条件之一时，才有可能执行trigger

// 模拟 Vue 中的 data 选项 
let data = {
  msg: 'hello',
  count: 0 
}
// 模拟 Vue 实例
let vm = new Proxy(data, {
  // 当访问 vm 的成员会执行
  get (target, key) {
    console.log('get, key: ', key, target[key])
    return target[key]
  },
  // 当设置 vm 的成员会执行
  set (target, key, newValue) {
    console.log('set, key: ', key, newValue)
    if (target[key] === newValue) {
      return
    }
    target[key] = newValue
    document.querySelector('#app').textContent = target[key]
  }
})

// 测试
vm.msg = 'Hello World'
console.log(vm.msg)

Proxy 相比于 defineProperty 的优势
数组变化也能监听到
不需要深度遍历监听

Proxy 是 ES6 中新增的功能，可以用来自定义对象中的操作

let p = new Proxy(target, handler);
// `target` 代表需要添加代理的对象
// `handler` 用来自定义对象中的操作
// 可以很方便的使用 Proxy 来实现一个数据绑定和监听

let onWatch = (obj, setBind, getLogger) => {
  let handler = {
    get(target, property, receiver) {
      getLogger(target, property)
      return Reflect.get(target, property, receiver);
    },
    set(target, property, value, receiver) {
      setBind(value);
      return Reflect.set(target, property, value);
    }
  };
  return new Proxy(obj, handler);
};

let obj = { a: 1 }
let value
let p = onWatch(obj, (v) => {
  value = v
}, (target, property) => {
  console.log(`Get '${property}' = ${target[property]}`);
})
p.a = 2 // bind `value` to `2`
p.a // -> Get 'a' = 2

总结：
Vue
  记录传入的选项，设置 $data/$el
  把 data 的成员注入到 Vue 实例
  负责调用 Observer 实现数据响应式处理(数据劫持)
  负责调用 Compiler 编译指令/插值表达式等
Observer
  数据劫持
    负责把 data 中的成员转换成 getter/setter
    负责把多层属性转换成 getter/setter
    如果给属性赋值为新对象，把新对象的成员设置为 getter/setter
    添加 Dep 和 Watcher 的依赖关系
    数据变化发送通知
Compiler
  负责编译模板，解析指令/插值表达式
  负责页面的首次渲染过程
  当数据变化后重新渲染
Dep
  收集依赖，添加订阅者(watcher)
  通知所有订阅者
Watcher
  自身实例化的时候往dep对象中添加自己
  当数据变化dep通知所有的 Watcher 实例更新视图
```

  #### 发布订阅模式和观察者模式
```
1. 发布/订阅模式
  发布/订阅模式
    订阅者
    发布者
    信号中心
我们假定，存在一个"信号中心"，某个任务执行完成，就向信号中心
"发布"(publish)一个信 号，其他任务可以向信号中心"订阅"(subscribe)
这个信号，从而知道什么时候自己可以开始执行。
这就叫做"发布/订阅模式"(publish-subscribe pattern)

Vue 的自定义事件：
let vm = new Vue()
vm.$on('dataChange', () => { console.log('dataChange')})
vm.$on('dataChange', () => { 
  console.log('dataChange1')
}) 
vm.$emit('dataChange')

兄弟组件通信过程：
// eventBus.js
// 事件中心
let eventHub = new Vue()

// ComponentA.vue
// 发布者
addTodo: function () {
  // 发布消息(事件)
  eventHub.$emit('add-todo', { text: this.newTodoText }) 
  this.newTodoText = ''
}
// ComponentB.vue
// 订阅者
created: function () {
  // 订阅消息(事件)
  eventHub.$on('add-todo', this.addTodo)
}

模拟 Vue 自定义事件的实现：
class EventEmitter {
  constructor(){
    // { eventType: [ handler1, handler2 ] }
    this.subs = {}
  }
  // 订阅通知
  $on(eventType, fn) {
    this.subs[eventType] = this.subs[eventType] || []
    this.subs[eventType].push(fn)
  }
  // 发布通知
  $emit(eventType) {
    if(this.subs[eventType]) {
      this.subs[eventType].forEach(v=>v())
    }
  }
}

// 测试
var bus = new EventEmitter()

// 注册事件
bus.$on('click', function () {
  console.log('click')
})

bus.$on('click', function () {
  console.log('click1')
})

// 触发事件 
bus.$emit('click')

2. 观察者模式
  观察者(订阅者) -- Watcher
    update():当事件发生时，具体要做的事情
  目标(发布者) -- Dep
    subs 数组:存储所有的观察者
    addSub():添加观察者
    notify():当事件发生，调用所有观察者的 update() 方法
  没有事件中心
// 目标(发布者) 
// Dependency
class Dep {
  constructor () {
    // 存储所有的观察者
    this.subs = []
  }
  // 添加观察者
  addSub (sub) {
    if (sub && sub.update) {
      this.subs.push(sub)
    }
  }
  // 通知所有观察者
  notify () {
    this.subs.forEach(sub => sub.update())
  }
}

// 观察者(订阅者)
class Watcher {
  update () {
    console.log('update')
  }
}

// 测试
let dep = new Dep()
let watcher = new Watcher()
dep.addSub(watcher) 
dep.notify()

3. 总结
1.观察者模式是由具体目标调度，比如当事件触发，Dep 就会去调用
观察者的方法，所以观察者模 式的订阅者与发布者之间是存在依赖的
2.发布/订阅模式由统一调度中心调用，因此发布者和订阅者不需要知道对方的存在

```

  #### Object.defineProperty 介绍
```
Object.defineProperty 函数一共有三个参数，第一个参数是需要
定义属性的对象，第二个参数是需要定义的属性，第三个是该属性描述符。

一个属性的描述符有一下属性，分别是：
value 属性的值，
writable 属性是否可写，
enumerable 属性是否可枚举，
configurable 属性是否可配置修改。
get属性 当访问该属性时，会调用此函数
set属性 当属性值被修改时，会调用此函数。
```

  #### 使用 Object.defineProperty() 来进行数据劫持有什么缺点
```
有一些对属性的操作，使用这种方法无法拦截，比如说通过下标方式修改数组数据或者给对象新增属性，vue 内部通过重写函数解决了这个问题。

在 Vue3.0 中已经不使用这种方式了，而是通过使用 Proxy 对对象进行代理，从而实现数据劫持。使用 Proxy 的好处是它可以完美的监听到任何方式的数据改变，唯一的缺点是兼容性的问题，因为这是 ES6 的语法。
```







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



















