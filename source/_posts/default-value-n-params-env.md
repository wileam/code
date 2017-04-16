title: params default value & params environment & TDZ
date: 2016-07-30 22:27:32
category:
- frontend
tags:
- ES6
---

看 ES6 parameter default value 的时候，发现一些很困惑的现象。

```js
let y = 1;
function foo(x = y, y) {}
foo();
```

结果是 reference error: y is not defined. 因为这里 y 是处在 `TDZ`(Temporal Dead Zone)。

```js
console.log(x); // TDZ
let x;
```

可是为什么呢，明明全局有定义 y 呀，为什么未定义？难道参数默认值有单独的作用域？继续试验：

<!-- more -->

```js
let y = 1;
function foo(x = function(){console.log(y)}, y = 2) {
  x(); // 2
  y = 3;
  x(); // 3
}
foo();
console.log(y); //1
```

```js
let y = 1;
function foo(x = function(){console.log(y)}) {
  let y = 3;
  x(); // 1
}
foo();
```

```js
function foo(x = function(){console.log(y)}) {
  let y = 3;
  x(); // ReferenceError: y is not defined
}
foo();
```

很让人困惑，感觉是存在3个作用域，全局/参数/函数体。参数默认值的函数，可以访问参数中定义的，和参数外定义(outer/global)的变量，不能访问函数体中定义的变量。

于是去找ES标准中的定义，找到了
> 9.2.12 FunctionDeclarationInstantiation
> If the function’s formal parameters do not include any default value initializers then the body declarations are instantiated in the same Environment Record as the parameters. If default value parameter initializers exist, a second Environment Record is created for the body declarations. Formal parameters and functions are initialized as part of FunctionDeclarationInstantiation. All other bindings are initialized during evaluation of the function body.

豁然开朗，果然就是这样。

结论:

如果参数存在默认值，则有三个环境 environment( `environment` in ES6 = `scope` in ES5). Outer environment / parameters environment / function body environment.
parameters environment 可以访问自己和外层，不能访问函数体内的变量。
函数体内可以修改 parameters env 里定义的 formal parameters 的值，不能重新定义（除非用`var`……）。

关于`var`可以看一个更晕的例子:

```js
let y =1;
function foo(x = function(){console.log(y)},y=2) {
  x(); // 2
  var y = 3; // if use let, then throw error: y is already declared, which is much more clear.
  console.log(y); //3
  x(); // 2
}
foo();
console.log(y); //1
```

so，个人建议:
- 参数变量、函数体内变量、全局变量别用一样的名字
- 不要用 var 来定义变量，总是用 `let` 或 `const`

参考资料：
- [TDZ](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/let#Temporal_dead_zone_and_errors_with_let)
- [ES6 Notes: Default values of parameters](http://dmitrysoshnikov.com/ecmascript/es6-notes-default-values-of-parameters/)
