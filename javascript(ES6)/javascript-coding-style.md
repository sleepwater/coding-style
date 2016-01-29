# Javascript(ES6) Coding Style

## 目录

* [命名](#命名)
* [缩进/空格](#缩进/空格)
* [分号](#分号)
* [字符串](#字符串)
* [ES6](#ES6)
* [参考](#参考)

## 命名

* 文件夹

使用小写，多个单词使用中划线分割。

``` javascript
utils
root-view
```

* 文件

使用小写，多个单词使用中划线分割。

``` javascript
main.js
layout-view.js
```

* 变量

使用前缀小写的驼峰式命名。

``` javascript
let groupName = 'Default Group';
```

* 常量

全部大写，多个单词使用下划线分割。

``` javascript
const API = 'http://localhost';
const API_PORT = '9000';
```

* 方法名

使用前缀小写的驼峰式命名。

``` javascript
function drawChart() {
    // coding here
}
```

对于私有方法，采用下划线为前缀的命名方式。

``` javascript
// 对外的方法
function drawChart() {
    // coding here
}

// 内部调用的方法
function _prepareData() {
    // coding here
}
```

> 其实JavaScript不存在私有属性或私有方法的概念，这里的“私有”指的是不想被外部引用，以下划线为前缀只是作为一个“约定”：
> 
> * 所有不想被外部调用的方法都使用下划线为前缀的命名方式。
> 
> 
> * 不在作用域之外调用内部方法。

* 类名

使用前缀大写的驼峰式命名。

``` javascript
class Person {
    constructor() {
        // coding here
    }
}
```

## 缩进/空格

> 圆点表示空格。

* 缩进使用4个空格。**不要使用tab字符。**

``` javascript
function test() {
∙∙∙∙// coding here
}
```

* 大括号所包含的代码块之前需要保留一个空格。
* 定义多个参数时，逗号之后需要保留一个空格。
* 关键字之后需要保留一个空格，如if，for，while等。
* 运算符两边需要各保留一个空格，如=，===，>等。
* 函数名与小括号之间不需要保留空格。
* 小括号内部两侧不需要保留空格。

``` javascript
function test(a,∙b)∙{
∙∙∙∙if·(a∙>∙1)∙{
		console.log(a);  
	}∙else {
  		console.log(b);
	}
}
```

# 分号

**请不要忘记加分号**

``` javascript
let message = 'Please do not forget semicolons';
```

> 其实加还是不加，并不是个硬性指标，只是代码风格而已，就好比缩进是用空格还是tab一样，只要项目内统一，不混着用就行了。
> 
> 不加分号的开源项目：[Vue](https://github.com/vuejs/vue)，[Bootstrap](https://github.com/twbs/bootstrap)

# 字符串

* 使用单引号定义字符串。

``` javascript
const single = 'single';
const double = 'double';
```

* 字符串过长，换行拼接时使用加号。

``` javascript
let template = '<div class="book">' + 
    '<span>I am a book.</span>' +
    '</div>';
```

> 在ES6里可使用反引号（``）来定义换行的字符串，并可嵌入变量，多用于定义模板。

``` javascript
let message = 'I am a book.';
let template = `
	<div class="book">
		<span>${message}</span>
	</div>
`;
```

# ES6

* let和const

使用let代替var来定义块级作用域的变量，使用const来定义常量。

``` javascript
const printNumber = function() {
    for (let i = 0; i < 5; i++) {
        console.log(i);
    }
}
```

* 箭头函数。

匿名函数使用箭头函数来定义，尤其是回调函数。如果只有一个返回变量，则不加括号，其余情况需加括号。

``` javascript
promise.then(result => {
  	let {
  		name,
        age
	} = result;
  	
  	return {
  		name,
        age
	};
}).then((name, age) => {
	console.log(name, age);
}).then(() => {
    console.log('Finish');
});
```

* 解构赋值（destructuring）

## 参考

* [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript/blob/master/README.md)
* [jsCode](http://jscode.org/)
* [ECMAScript 6 入门](http://es6.ruanyifeng.com/)
* [Learn ES2015](https://babeljs.io/docs/learn-es2015/)

