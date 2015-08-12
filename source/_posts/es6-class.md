title: ES6 Class一瞥
date: 2015-04-05 22:27:32
category:
tags:
- ES6
- Javascript
---

## Class
ES6的`class`提供了一个简洁的语法糖来实现之前通过原型链来实现的Class的功能。

## 可用性

截止目前（2015-04-05)，Class目前还基本没有浏览器支持，除了Firefox39最新版已经实现了。具体的支持情况可以在这里看到：[ECMAScript compatibility table](http://kangax.github.io/compat-table/es6/)

可以通过[Traceur](https://github.com/google/traceur-compiler)来试验Class的功能。

<!-- more -->

## Class语法

### ES6

```js
class Person {
    constructor(name,age) {
        this.name = name,
        this.age = age
    }
    sayHi() {
        console.log('Hi, my name is '+ this.name);
    }
}

var ray = new Person('ray',21);
ray.sayHi(); //'Hi, my name is ray'
```

### 以前的方式
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.sayHi = function() {
    console.log('Hi, my name is '+ this.name);
}

var ray = new Person('ray', 21);
ray.sayHi(); //'Hi, my name is ray'
```

## Class实现继承

继承是通过`extends`关键字和`super`实现的。

```js
//inheritance
class Female extends Person {
    constructor(name, age) {
        super(name, age);
    }

    sayHi() {
        // call Person.sayHi()
        super.sayHi();

        // add a new log
        console.log('meow');
    }
}

var joanna = new Female('joanna', 26);
joanna.sayHi();
//'Hi, my name is joanna'
//'meow'
```

ES5的写法
```
var Female = function (name, age) {
    Person.call(name, age);
    this.name  = name;
    this.age = age;
};
Female.prototype = Object.create(Person.prototype);
Female.prototype.sayHi = function() {
    Person.prototype.sayHi.call(this);
    console.log('meow');
}

var joanna = new Female('joanna', 26);
joanna.sayHi();
//'Hi, my name is joanna'
//'meow'
```

## 参考资料
- [ECMAScript compatibility table](http://kangax.github.io/compat-table/es6/)
- [ECMAScript 6 support in Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla)
- [An introduction to ES6 classes](http://javascriptplayground.com/blog/2014/07/introduction-to-es6-classes-tutorial/)
- [Traceur - Getting Started](https://github.com/google/traceur-compiler/wiki/Getting-Started)


## 后记
啊我为什么会写ES6 Class呢，因为好玩呗 ~~其实这是一篇命题作文~~ (逃