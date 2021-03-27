## JavaScript 面试知识点总结
整理了 JavaScript 面试的部分知识点

### 目录

- [js数据类型](#js数据类型)
  - [js有几种类型的值](#js有几种类型的值)
  - [堆和栈](#堆和栈)
- [js类型判断](#js类型判断)
  - [typeof操作符](#typeof操作符)
  - [instanceof](#instanceof)
  - [constructor](#constructor)
  - [Object.prototype.toString.call()](#Object.prototype.toString.call())
- [js原型和原型链](#js原型和原型链)
  - [js获取原型的方法](#js获取原型的方法)
- [js继承](#js继承)
  - [原型链继承](#原型链继承)
  - [构造函数继承](#构造函数继承)
  - [实例继承](#实例继承)
  - [拷贝继承](#拷贝继承)
  - [组合继承](#组合继承)
  - [寄生组合继承](#寄生组合继承)
  - [es6使用extends关键字扩展一个类并继承它的行为](#es6使用extends关键字扩展一个类并继承它的行为)
- [安全](#安全)
  - [同源](#同源)
  - [限制](#限制)
  - [跨域](#跨域)
    - [jsonp](#jsonp) 
  - [鉴权](#鉴权)


#### js数据类型

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

##### js有几种类型的值

```
js 可以分为两种类型的值，一种是基本数据类型，一种是复杂数据类型。
基本数据类型：undefined、null、boolean、number、string、symbol
复杂数据类型指的是 Object 类型，所有其他的如 Array、Date 等数据类型都可以理解为 Object 类型的子类。

两种类型间的主要区别是它们的存储位置不同，基本数据类型的值直接保存在栈中，
而复杂数据类型的值保存在堆中，通过使用在栈中保存对应的指针来获取堆中的值。
```

栈：原始数据类型（Undefined、Null、Boolean、Number、String） <br>
堆：引用数据类型（对象、数组和函数）

```
两种类型的区别是：存储位置不同。
原始数据类型直接存储在栈（stack）中的简单数据段，占据空间小、大小固定，属于被频繁使用数据，所以放入栈中存储。

引用数据类型存储在堆（heap）中的对象，占据空间大、大小不固定。如果存储在栈中，将会影响程序运行的性能；
引用数据类型在栈中存储了指针，该指针指向堆中该实体的起始地址。当解释器寻找引用值时，
会首先检索其在栈中的地址，取得地址后从堆中获得实体。
```

#### 堆和栈

```
堆和栈的概念存在于数据结构中和操作系统内存中。

（1）在数据结构中，栈中数据的存取方式为先进后出。而堆是一个优先队列，是按优先级来进行排序的，
优先级可以按照大小来规定。完全二叉树是堆的一种实现方式。
（2）在操作系统中，内存被分为栈区和堆区。

栈区内存由编译器自动分配释放，存放函数的参数值，局部变量的值等。其操作方式类似于数据结构中的栈。
堆区内存一般由程序员分配释放，若程序员不释放，程序结束时可能由垃圾回收机制回收。
```

### js类型判断
typeof，instanceof，constructor，Object.prototype.toString.call()

```
（1）typeof：
直接在计算机底层基于数据类型的值（二进制）进行检测
typeof null为object原因是对象存在在计算机中，都是以000开始的二进制存储，所以检测出来的结果是对象
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
优点：能够快速区分基本数据类型 缺点：不能将Object、Array和Null区分，都返回object  

（1）对于原始类型来说，除了 null 都可以显示正确的类型
```
Number、String，Undefined、Boolean、Null、还有在 ES6 中新增的 Symbol 和 ES10 中新增的 BigInt 
typeof 1             // 'number'
typeof '1'           // 'string'
typeof undefined     // 'undefined'
typeof true          // 'boolean'
typeof Symbol()      // 'symbol'
typeof null          // 'object'
PS：为什么null会出现这种情况呢？因为在 JS的最初版本中，使用的是 32 位系统，为了
性能考虑使用低位存储了变量的类型信息，000 开头代表是对象，然而 null表示为全零，
所以将它错误的判断为 object 。虽然现在的内部类型判断代码已经改变了，但是对于这个Bug却是一直流传下来。
```

（2）typeof 对于对象来说，除了函数都会显示 object，所以说 typeof 并不能准确判断变量到底是什么类型
```
array、object、function
typeof []             // 'object'
typeof {}             // 'object'
typeof console.log    // 'function'
```

（3）typeof NaN
```
typeof NaN;           // "number"

NaN 意指“不是一个数字”（not a number），NaN 是一个“警戒值”（sentinel value，有特殊用途的常规值），
用于指出数字类型中的错误情况，即“执行数学运算没有成功，这是失败后返回的结果”。
NaN 是一个特殊值，它和自身不相等，是唯一一个非自反（自反，reflexive，即 x === x 不成立）的值。而 NaN != NaN为 true。
```

#### instanceof
```
作用：用于判断实例属于哪个构造函数。
原理：判断实例对象的__proto__属性，和构造函数的prototype属性，是否为同一个引用（是否指向同一个地址）。
instanceof 可以正确的判断对象的类型，因为内部机制是通过判断对象的原型链中是不是能找到类型的 prototype

优点：能够区分Array、Object和Function，适合用于判断自定义的类实例对象
缺点：Number，Boolean，String基本数据类型不能判断

console.log(2 instanceof Number);                    // false
console.log(true instanceof Boolean);                // false 
console.log('str' instanceof String);                // false  
console.log([] instanceof Array);                    // true
console.log(function(){} instanceof Function);       // true
console.log({} instanceof Object);                   // true    

instanceof 在MDN中的解释：instanceof 运算符用来测试一个对象在其原型链中是否存在一个
构造函数的 prototype 属性。其意思就是判断对象是否是某一数据类型（如Array）的实例，
请重点关注一下是判断一个对象是否是数据类型的实例。在这里字面量值，2， true ，'str'不是实例，所以判断值为false
```

```
实现instanceof：
(1)首先获取类型的原型
(2)获得对象的原型
(3)一直循环判断对象的原型是否等于类型的原型，直到对象原型为 null，因为原型链最终为 null
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

问题：已知A继承了B，B继承了C。怎么判断 a 是由A直接生成的实例，还是B直接生成的实例呢？还是C直接生成的实例呢？
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
使用 Object 对象的原型方法 toString ，使用 call 进行狸猫换太子，借用Object的 toString 方法

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

### js原型和原型链

```
原型：在 js 中我们是使用构造函数来新建一个对象的，每一个构造函数的内部都有一个 prototype 属性值，
这个属性值是一个对象，这个对象包含了可以由该构造函数的所有实例共享的属性和方法。
当我们使用构造函数新建一个对象后，在这个对象的内部将包含一个指针，这个指针指向
构造函数的 prototype 属性对应的值，在 ES5 中这个指针被称为对象的原型（prototype）。

一般来说我们是不应该能够获取到这个值的，但是现在浏览器中都实现了 __proto__ 属性
来让我们访问这个属性，但是我们最好不要使用这个属性，因为它不是规范中规定的。
ES5 中新增了一个 Object.getPrototypeOf() 方法，我们可以通过这个方法来获取对象的原型。

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

### js继承

```
javascript继承的7种方法：
1.原型链继承：将父类的实例作为子类的原型。
2.构造函数继承（使用call）：使用父类的构造函数来增强子类实例，等于是复制父类的实例属性给子类。
3.实例继承：为父类实例添加新特性，作为子类实例返回。
4.拷贝继承：把父类实例对象上的方法拷贝到子类的原型上。
5.组合继承：通过调用父类构造函数，继承父类的属性并保留传参的优点，然后通过将父类实例作为子类原型，实现函数复用。
6.寄生组合继承：通过寄生方式，砍掉父类的实例属性，这样，在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，避免的组合继承的缺点。
7.使用extends关键字扩展一个类并继承它的行为（es6）。
```

```
我了解的 js 中实现继承的几种方式有：
（1）第一种是以原型链的方式来实现继承，但是这种实现方式存在的缺点是，在包含有引用类型的数据时，
会被所有的实例对象所共享，容易造成修改的混乱。还有就是在创建子类型的时候不能向超类型传递参数。

（2）第二种方式是使用借用构造函数的方式，这种方式是通过在子类型的函数中调用超类型的构造函数
来实现的，这一种方法解决了不能向超类型传递参数的缺点，但是它存在的一个问题就是
无法实现函数方法的复用，并且超类型原型定义的方法子类型也没有办法访问到。

（3）第三种方式是组合继承，组合继承是将原型链和借用构造函数组合起来使用的一种方式。
通过借用构造函数的方式来实现类型的属性的继承，通过将子类型的原型设置为超类型的实例来实现方法的继承。
这种方式解决了上面的两种模式单独使用时的问题，但是由于我们是以超类型的实例来作为子类型的原型，
所以调用了两次超类的构造函数，造成了子类型的原型中多了很多不必要的属性。

（4）第四种方式是原型式继承，原型式继承的主要思路就是基于已有的对象来创建新的对象，实现的原理是，
向函数中传入一个对象，然后返回一个以这个对象为原型的对象。这种继承的思路主要不是为了实现创造一种新的类型，
只是对某个对象实现一种简单继承，ES5 中定义的 Object.create() 方法就是原型式继承的实现。缺点与原型链方式相同。

（5）第五种方式是寄生式继承，寄生式继承的思路是创建一个用于封装继承过程的函数，通过传入一个对象，
然后复制一个对象的副本，然后对象进行扩展，最后返回这个对象。这个扩展的过程就可以理解是一种继承。
这种继承的优点就是对一个简单对象实现继承，如果这个对象不是我们的自定义类型时。缺点是没有办法实现函数的复用。

（6）第六种方式是寄生式组合继承，组合继承的缺点就是使用超类型的实例做为子类型的原型，导致添加了不必要的原型属性。
寄生式组合继承的方式是使用超类型的原型的副本来作为子类型的原型，这样就避免了创建不必要的属性。
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

#### 构造函数继承（使用call）
```
核心：使用父类的构造函数来增强子类实例，等于是复制父类的实例属性给子类（没用到原型）
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
1.不限制调用方式，不管是 new 子类() 还是 子类()，返回的对象具有相同的效果
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
核心：通过调用父类构造函数，继承父类的属性并保留传参的优点，然后通过将父类实例作为子类原型，实现函数复用。
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
1.调用了两次父构造函数，生成了两份实例（子类实例将子类原型上的那份屏蔽掉了），消耗内存较少
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
### 安全

#### 同源

同源策略是一种安全协议
```
我对浏览器的同源政策的理解是，一个域下的 js 脚本在未经允许的情况下，不能够访问另一个域的内容。
这里的同源的指的是两个域的协议、域名、端口号必须相同，否则则不属于同一个域。

同源政策主要限制了三个方面：
第一个是当前域下的 js 脚本不能够访问其他域下的 cookie、localStorage 和 indexDB。
第二个是当前域下的 js 脚本不能够操作访问操作其他域下的 DOM。
第三个是当前域下 ajax 无法发送跨域请求。

同源政策的目的主要是为了保证用户的信息安全，防止某个文档或脚本从多个不同源装载。
它只是对 js 脚本的一种限制，并不是对浏览器的限制，对于一般的 img、或者script 脚本请求
都不会有跨域的限制，这是因为这些操作都不会通过响应结果来进行可能出现安全问题的操作。
```

```
举例说明：比如一个黑客程序，他利用Iframe把真正的银行登录页面嵌到他的页面上，当你使用真实的用户名，
密码登录时，他的页面就可以通过Javascript读取到你的表单中input中的内容，这样用户名，密码就轻松到手了。

缺点：
现在网站的JS都会进行压缩，一些文件用了严格模式，而另一些没有。这时这些本来是严格模式的文件，
被 merge后，这个串就到了文件的中间，不仅没有指示严格模式，反而在压缩后浪费了字节
```

#### 限制

为什么会产生跨域？
```
你之所以会遇到跨域问题，正是因为 SOP 的各种限制。
本质上 SOP 并不是禁止跨域请求，而是在请求后拦截了请求的回应。

其实表面上 SOP 分两种情况：
可以正常引用 iframe、图片等各种资源，但是限制对其内容进行操作
直接限制 ajax 请求，准确来说是限制操作 ajax 响应结果，这会引起 CSRF
但是，本质上这两条是一样的：总之，对于非同源的资源，浏览器可以“直接使用”，但是程序员和用户
不可以对这些数据进行操作，杜绝某些居心不良的行为。这就是现代安全浏览器对用户的保护之一。

下面是 3 个在实际应用中会遇到的例子：
使用 ajax 请求其他跨域 API，最常见的情况
iframe 与父页面交流（如 DOM 或变量的获取），出现率比较低
对跨域图片（例如来源于 <img> ）进行操作，在 canvas 操作图片的时候会遇到这个问题

如果没有了 SOP：
iframe 里的机密信息被肆意读取
更加肆意地进行 CSRF
接口被第三方滥用
```

#### 跨域

因为浏览器出于安全考虑，有同源策略。也就是说，如果协议、域名或者端口有一个不同就是跨域
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

首先我们如果只是想要实现主域名下的不同子域名的跨域操作，我们可以使用设置 document.domain 来解决。
（1）将 document.domain 设置为主域名，来实现相同子域名的跨域操作，
这个时候主域名下的 cookie 就能够被子域名所访问。同时如果文档中含有主域名相同，
子域名不同的 iframe 的话，我们也可以对这个 iframe 进行操作。

如果是想要解决不同跨域窗口间的通信问题，比如说一个页面想要和页面的中的不同源的 iframe 
进行通信的问题，我们可以使用 location.hash 或者 window.name 或者 postMessage 来解决。
（2）使用 location.hash 的方法，我们可以在主页面动态的修改 iframe 窗口的 hash 值，
然后在 iframe 窗口里实现监听函数来实现这样一个单向的通信。因为在 iframe 是没有办法访问
到不同源的父级窗口的，所以我们不能直接修改父级窗口的 hash 值来实现通信，我们可以在 
iframe 中再加入一个 iframe ，这个 iframe 的内容是和父级页面同源的，所以我们可以使用
window.parent.parent 来修改最顶级页面的 src，以此来实现双向通信。
（3）使用 window.name 的方法，主要是基于同一个窗口中设置了 window.name 后不同源的页面也可以
访问，所以不同源的子页面可以首先在 window.name 中写入数据，然后跳转到一个和父级同源的页面。
这个时候父级页面就可以访问同源的子页面中 window.name 中的数据了，这种方式的好处是可以传输的数据量大。
（4）使用 postMessage 来解决的方法，这是一个 h5 中新增的一个 api。通过它我们可以
实现多窗口间的信息传递，通过获取到指定窗口的引用，然后调用 postMessage 来发送信息，
在窗口中我们通过对 message 信息的监听来接收信息，以此来实现不同源间的信息交换。

如果是像解决 ajax 无法提交跨域请求的问题，我们可以使用 jsonp、cors、websocket 协议、服务器代理来解决问题。
（5）使用 jsonp 来实现跨域请求，它的主要原理是通过动态构建 script  标签来实现跨域请求，
因为浏览器对 script 标签的引入没有跨域的访问限制 。通过在请求的 url 后指定一个回调函数，
然后服务器在返回数据的时候，构建一个 json 数据的包装，这个包装就是回调函数，
然后返回给前端，前端接收到数据后，因为请求的是脚本文件，所以会直接执行，
这样我们先前定义好的回调函数就可以被调用，从而实现了跨域请求的处理。这种方式只能用于 get 请求。
（6）使用 CORS 的方式，CORS 是一个 W3C 标准，全称是"跨域资源共享"。CORS 需要
浏览器和服务器同时支持。目前，所有浏览器都支持该功能，因此我们只需要在服务器端配置就行。
浏览器将 CORS 请求分成两类：简单请求和非简单请求。对于简单请求，浏览器直接发出 CORS 请求。
具体来说，就是会在头信息之中，增加一个 Origin 字段。Origin 字段用来说明本次请求来自哪个源。
服务器根据这个值，决定是否同意这次请求。对于如果 Origin 指定的源，不在许可范围内，
服务器会返回一个正常的 HTTP 回应。浏览器发现，这个回应的头信息没有包含 Access-Control-Allow-Origin 字段，
就知道出错了，从而抛出一个错误，ajax 不会收到响应信息。如果成功的话会包含一些以 Access-Control- 开头的字段。
非简单请求，浏览器会先发出一次预检请求，来判断该域名是否在服务器的白名单中，如果收到肯定回复后才会发起请求。
（7）使用 websocket 协议，这个协议没有同源限制。
（8）使用服务器来代理跨域的访问请求，就是有跨域的请求操作时发送请求给后端，让后端代为请求，然后最后将获取的结果发返回。
```

#### jsonp
在CORS和postMessage以前，我们一直都是通过JSONP来做跨域通信的。
```
JSONP的原理：通过<script>标签的异步加载来实现的。比如说，实际开发中，我们发现，
head标签里，可以通过<script>标签的src，里面放url，加载很多在线的插件。这就是用到了JSONP。
JSONP 使用简单且兼容性不错，但是只限于 get 请求。
在开发中可能会遇到多个 JSONP 请求的回调函数名是相同的，这时候就需要自己封装一个 JSONP

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

（5）H5中新增的postMessage()方法，可以用来做跨域通信。
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

（6）CORS
```
CORS：不受同源策略的限制，支持跨域。一种新的通信协议标准。可以理解成是：同时支持同源和跨域的Ajax。
CORS为什么支持跨域的通信？
跨域时，浏览器会拦截Ajax请求，并在http头中加Origin。

浏览器会自动进行 CORS 通信，实现 CORS 通信的关键是后端。只要后端实现了 CORS，就实现了跨域。
服务端设置 Access-Control-Allow-Origin 就可以开启 CORS。 该属性表示哪些域名可以访问资源，
如果设置通配符则表示所有网站都可以访问资源。 虽然设置 CORS和前端没什么关系，但是通过
这种方式解决跨域问题的话，会在发送请求时出现两种情况，分别为简单请求和复杂请求。

简单请求：
以 Ajax 为例，当满足以下条件时，会触发简单请求
1.使用下列方法之一：GET、HEAD、POST
2.Content-Type 的值仅限于下列三者之一：text/plain、multipart/form-data、application/x-www-form-urlencoded
请求中的任意 XMLHttpRequestUpload 对象均没有注册任何事件监听器； 
XMLHttpRequestUpload 对象可以使用XMLHttpRequest.upload 属性访问

复杂请求：
对于复杂请求来说，首先会发起一个预检请求，该请求是 option 方法的，通过该请求来知道服务端是否允许跨域请求。
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
当前端发起了复杂请求后，你会发现就算你代码是正确的，返回结果也永远是报错的。因为预检请求也会
进入回调中，也会触发 next 方法，因为预检请求并不包含 Authorization 字段，所以服务端会报错。
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
```

（9）WebSocket
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

#### 鉴权

什么是鉴权：
```
鉴权（authentication）是指验证用户是否拥有访问系统的权利。传统的鉴权是通过密码来验证的。
这种方式的前提是，每个获得密码的用户都已经被授权。在建立用户时，就为此用户分配一个密码，
用户的密码可以由管理员指定，也可以由用户自行申请。这种方式的弱点十分明显：一旦密码被偷或用户遗失密码，
情况就会十分麻烦，需要管理员对用户密码进行重新修改，而修改密码之前还要人工验证用户的合法身份。

为了克服这种鉴权方式的缺点，需要一个更加可靠的鉴权方式。目前的主流鉴权方式是利用认证授权来验证数字签名的正确与否。

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
这种双向的认证机制，就是AKA（Authentication and Key Agreement，鉴权和密钥协商）鉴权。

除了AKA鉴权，也可以使用其它鉴权方式。在IMS AKA鉴权广泛实施之前，或在特定的条件下
（例如通过固定网络ADSL连接方式接入IMS），可以使用HTTP摘要鉴权等其他鉴权方式。

3G UMTS（Universal Mobile Telecommunication System，通用移动通讯系统）、
EPS（Evolved Packet System，演进的分组系统）、IMS（IP Multimedia Subsystem，IP多媒体子系统）
网络都采用了AKA双向鉴权机制，鉴权原理也大致相同。而2G网络，只有用户鉴权，无网络鉴权。
```

```
鉴权时机：
移动网络对鉴权时机的要求为：
2G、3G网络中，鉴权发生在开机、呼叫、位置更新以及在补充业务的激活、去活、登记或删除操作之前。
2G网络中，运营商都是启用的“按比例鉴权”方案。
3G网络中，用户首次接入网络必须鉴权，此后启用“按比例鉴权”方案。
IMS网络中，网络可以通过注册或重注册过程，在任何时候对用户进行鉴权。
```

HTTP Basic Authentication
```
这种授权方式是浏览器遵守http协议实现的基本授权方式,HTTP协议进行通信的过程中，
HTTP协议定义了基本认证认证允许HTTP服务器对客户端进行用户身份证的方法。

认证过程：
1．客户端向服务器请求数据，请求的内容可能是一个网页或者是一个ajax异步请求，
此时，假设客户端尚未被验证，则客户端提供如下请求至服务器:
Get /index.html HTTP/1.0
Host:www.google.com

2． 服务器向客户端发送验证请求代码401,（WWW-Authenticate: Basic realm=”google.com”这句话是关键，
如果没有客户端不会弹出用户名和密码输入界面）服务器返回的数据大抵如下：
HTTP/1.0 401 Unauthorised
Server: SokEvo/1.0
WWW-Authenticate: Basic realm=”google.com”
Content-Type: text/html
Content-Length: xxx

3． 当符合http1.0或1.1规范的客户端（如IE，FIREFOX）收到401返回值时，
将自动弹出一个登录窗口，要求用户输入用户名和密码。

4． 用户输入用户名和密码后，将用户名及密码以BASE64加密方式加密，
并将密文放入前一条请求信息中，则客户端发送的第一条请求信息则变成如下内容：
Get /index.html HTTP/1.0
Host:www.google.com
Authorization: Basic d2FuZzp3YW5n

注：d2FuZzp3YW5n表示加密后的用户名及密码（用户名：密码 然后通过base64加密，
加密过程是浏览器默认的行为，不需要我们人为加密，我们只需要输入用户名密码即可）

5． 服务器收到上述请求信息后，将Authorization字段后的用户信息取出、解密，将解密后的
用户名及密码与用户数据库进行比较验证，如用户名及密码正确，服务器则根据请求，将所请求资源发送给客户端。

效果：
客户端未未认证的时候，会弹出用户名密码输入框，这个时候请求时属于pending状态，
这个时候其实服务当用户输入用户名密码的时候客户端会再次发送带Authentication头的请求。
```

session-cookie
```
HTTP Cookie（也叫Web Cookie或浏览器Cookie）是服务器发送到用户浏览器并保存在本地的一小块数据，
它会在浏览器下次向同一服务器再发起请求时被携带并发送到服务器上。通常，它用于告知服务端两个请求
是否来自同一浏览器，如保持用户的登录状态。Cookie使基于无状态的HTTP协议记录稳定的状态信息成为了可能。

Cookie主要用于以下三个方面：
会话状态管理（如用户登录状态、购物车、游戏分数或其它需要记录的信息）
个性化设置（如用户自定义设置、主题等）
浏览器行为跟踪（如跟踪分析用户行为等）

认证过程：
1.服务器在接受客户端首次访问时在服务器端创建seesion，然后保存seesion(我们可以将seesion
保存在内存中，也可以保存在redis中，推荐使用后者)，然后给这个session生成一个
唯一的标识字符串,然后在响应头中种下这个唯一标识字符串。

2.签名。这一步只是对sid进行加密处理，服务端会根据这个secret密钥进行解密。（非必需步骤）

3.浏览器中收到请求响应的时候会解析响应头，然后将sid保存在本地cookie中，
浏览器在下次http请求的请求头中会带上该域名下的cookie信息。

4.服务器在接受客户端请求时会去解析请求头cookie中的sid，然后根据这个sid
去找服务器端保存的该客户端的session，然后判断该请求是否合法。

5.一旦用户登出，服务端和客户端同时销毁该会话在后续请求中，服务器会根据数据库验证会话id，如果验证通过，则继续处理；
```

Token验证
```
认证过程：
1.用户输入登陆凭据；
2.服务器验证凭据是否正确，然后返回一个经过签名的token；
3.客户端负责存储token，可以存在localstorage，或者cookie中
4.对服务器的请求带上这个token；
5.服务器对JWT进行解码，如果token有效，则处理该请求；
6.一旦用户登出，客户端销毁token。

cookie与token性能对比：cookie与token看上去很像，但是有区别
1.sessionid 他只是一个唯一标识的字符串，服务端是根据这个字符串，来查询在服务器端保持的seesion，
这里面才保存着用户的登陆状态。但是token本身就是一种登陆成功凭证，他是在登陆成功后根据某种规则生成的
一种信息凭证，他里面本身就保存着用户的登陆状态。服务器端只需要根据定义的规则校验这个token是否合法就行。

2.session-cookie是需要cookie配合的，居然要cookie，那么在http代理客户端的选择上就是只有浏览器了，
因为只有浏览器才会去解析请求响应头里面的cookie,然后每次请求再默认带上该域名下的cookie。
但是我们知道http代理客户端不只有浏览器，还有原生APP等等，这个时候cookie是不起作用的，
或者浏览器端是可以禁止cookie的，但是token就不一样，他是登陆请求在登陆成功后再请求响应体中返回的信息，
客户端在收到响应的时候，可以把他存在本地的cookie,storage，或者内存中，
然后再下一次请求的请求头重带上这个token就行了。简单点来说
cookie-session机制他限制了客户端的类型，而token验证机制丰富了客户端类型。

3.时效性。session-cookie的sessionid实在登陆的时候生成的而且在登出事时一直不变的，
在一定程度上安全就会低，而token是可以在一段时间内动态改变的。

4.可扩展性。token验证本身是比较灵活的，一是token的解决方案有许多，常用的是JWT，
二来我们可以基于token验证机制，专门做一个鉴权服务，用它向多个服务的请求进行统一鉴权。
```

OAuth(开放授权)
```
OAUTH协议为用户资源的授权提供了一个安全的、开放而又简易的标准。与以往的授权方式不同之处
是OAUTH的授权不会使第三方触及到用户的帐号信息（如用户名与密码），即第三方无需使用
用户的用户名与密码就可以申请获得该用户资源的授权，因此OAUTH是安全的。同时，
任何第三方都可以使用OAUTH认证服务，任何服务提供商都可以实现自身的OAUTH认证服务，因而OAUTH是开放的。

我们常见的提供OAuth认证服务的厂商有支付宝，QQ，微信。

OAuth协议又有1.0和2.0两个版本。相比较1.0版，2.0版整个授权验证流程更简单更安全，
也是目前最主要的用户身份验证和授权方式。

典型案例：
如果一个用户拥有两项服务：一项服务是图片在线存储服务A，另一个是图片在线打印服务B。
由于服务A与服务B是由两家不同的服务提供商提供的，所以用户在这两家服务提供商的网站上
各自注册了用户，假设这两个用户名各不相同，密码也各不相同。

当用户要使用服务B打印存储在服务A上的图片时，用户该如何处理？
方法一：用户可能先将待打印的图片从服务A上下载下来并上传到服务B上打印，
这种方式安全但处理比较繁琐，效率低下；

方法二：用户将在服务A上注册的用户名与密码提供给服务B，服务B使用用户的帐号
再去服务A处下载待打印的图片，这种方式效率是提高了，但是安全性大大降低了，
服务B可以使用用户的用户名与密码去服务A上查看甚至篡改用户的资源。

方法三：当服务B（打印服务）要访问用户的服务A（图片服务）时，通过OAUTH机制，
服务B向服务A请求未经用户授权的RequestToken后，服务A将引导用户在服务A的网站上登录，
并询问用户是否将图片服务授权给服务B。用户同意后，服务B就可以访问用户
在服务A上的图片服务。整个过程服务B没有触及到用户在服务A的帐号信息。

OAuth相关术语：
在认证和授权的过程中涉及的三方包括：
1.服务提供方（ServiceProvider），用户使用服务提供方来存储受保护的资源，如照片，视频，联系人列表。
2.用户（User），存放在服务提供方的受保护的资源的拥有者
3.客户端（Consumer），要访问服务提供方资源的第三方应用，通常是网站，如提供照片打印服务的网站
也可以是桌面或移动应用程序。在认证过程之前，客户端要向服务提供者申请客户端标识。

OAuth相关的三个URL：
RequestToken URL:获取未授权的RequestToken服务地址；
UserAuthorization URL:获取用户授权的RequestToken服务地址；
AccessToken URL:用授权的RequestToken换取AccessToken的服务地址。

OAuth认证和授权过程：
1.客户端（第三方软件）向OAUTH服务提供商请求未授权的RequestToken。即向RequestToken URL发起请求；
2.OAUTH服务提供商同意使用者的请求，并向其颁发未经用户授权的oauth_token与
对应的oauth_token_secret，并返回给使用者；
3.使用者向OAUTH服务提供商请求用户授权的RequestToken。即向UserAuthorization URL发起请求
并在请求中携带上一步服务提供商颁发的未授权的token与其密钥；
4.OAUTH服务提供商通过网页要求用户登录并引导用户完成授权；
5.RequestToken授权后，使用者将向AccessToken URL发起请求，将上步授权的RequestToken换取成AccessToken。
请求的参数见上图，这个比第一步多了一个参数就是RequestToken；
6.OAUTH服务提供商同意使用者的请求，并向其颁发AccessToken与对应的密钥，并返回给使用者；
7.使用者以后就可以使用上步返回的AccessToken访问用户授权的资源。

简单整理就三个步骤：
1.获取未授权的RequestToken
2.获取用户授权的RequestToken
3.用授权的RequestToken换取AccessToken
```






