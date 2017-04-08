# ES6 的学习，代码中有详细注释
#### 生命不息，奋斗不止，通过学习支撑奋斗的资本

##### 我写代码喜欢加足量的注释

##### 一是为了自己检查代码，调试bug时方便

##### 二是为了后期的维护

##### ...foo

- 不定参数，所有传递进来的其它参数都被放到一个数组中，赋值给变量foo

两种es6转es5的工具: 1.Babel 2.Traceur

#### ...

- 对象的浅复制
  - 还可以在原有的基础上覆盖以及扩展对象的属性

```javascript
const obj = { a: 1, b: 2}
const obj2 = { ...obj } // => { a: 1, b: 2 }
// ----------------------------
const obj = { a: 1, b: 2}
const obj2 = { ...obj, b: 3, c: 4} // => { a: 1, b: 3, c: 4 }，覆盖了 b，新增了 c
```

let和const命令 (不存在变量提升)



const实际上保证的，并不是变量的值不得改动，而是变量指向的那个内存地址不得改动。



对于简单类型的数据（数值、字符串、布尔值），值就保存在变量指向的那个内存地址，因此等同于常量。

但对于复合类型的数据（主要是对象和数组），变量指向的内存地址，保存的只是一个指针，const只能保证这个指针是固定的，至于它指向的数据结构（可以改变数据）是不是可变的，就完全不能控制了。

使用const声明变量或者其他复合类型时，只会保证地址不会发生变化，但是是可以给这个复合数据添加属性和值的，这就很危险了



但是改变地址指向是不允许的，可以使用Object.freeze() 方法将对象冻结 



顶层对象的属性与全局变量挂钩，被认为是JavaScript语言最大的设计败笔之一



浏览器和Web Worker中 self 等同于 window   Node里面木有window



从数组和对象中提取值，对变量进行赋值，这被称为解构，
解构需要等号右边是可遍历的结构，比如数组，事实上，只要某种数据结构具有Iterator接口，都可以采用数组形式的解构赋值



解构的*默认值*生效需要对应的那个数组成员是undefined的，比如**null**就不行了



六种方式的声明变量： function var  let const class import 



解构赋值，等号右边的值不是对象时，就先将其转为对象，undefined和null是无法转为对象的，所以当等号右边的值是它们时会报错





Promise对象，用来传递异步操作的消息http://www.jianshu.com/p/063f7e490e9a



- 字符串遍历

```javascript
for (let codePoint of 'foo') {
  	console.log(codePoint)
}
// "f"
// "o"
// "o"
```



- Iterator 接口(遍历器)

- 标签模板

  - “标签模板”的一个重要应用，就是过滤HTML字符串，防止用户输入恶意内容。
  - 标签模板的另一个应用，就是多语言转换（国际化处理）。

- 解构

  > ```
  > const { printName } = logger
  > ```
  >
  > 等于
  >
  > ```
  > const printName = logger.printName;
  > ```

- 箭头函数

  > h => h(app);
  >
  > (function(h){
  >
  > ​	return h(app);
  >
  > })

  - 将h作为createElement的别名是一个通用惯例

数组的扩展

- 数组的api
  - `entries()`、`keys()`、`values()`、`find()`和`findIndex()`会将空位处理成`undefined`