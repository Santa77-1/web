## JavaScript

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

1、原型链继承
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

2.构造函数继承（使用call）
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

3.实例继承
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

4.拷贝继承
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

5.组合继承
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

6.寄生组合继承
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

7.使用extends关键字扩展一个类并继承它的行为（es6）
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




















