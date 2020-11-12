#入门篇

#### 1.JavaScript 和 Java 的关系

虽然是两种不同的语言，但是彼此之间还是存在关系。**JavaScript的基本语法和对象体系，是模仿Java而设计的**，有很大的相似性，所以JavaScript也从一开始的LiveScript改名为JavaScript，原意是很像Java的脚本语言。

JavaScript与Java的区别：JavaScript的**函数**是一种**独立的数据类型**、JavaScript采用基于原型对象（**prototype**）的继承链。

#### 2.JavaScript和ECMAScript

JavaScript的组成部分：ECMAScript、DOM、BOM

2015年已经发布了ECMAScript6，简称ES6

ECMAScript和JavaScript的关系是：ECMAScript用来标准化JavaScript的基本语法结构。**前者是后者的规格，后者是前者的一种实现。**

#### 3.var、let和const

var：函数作用域。

let、const：ES6新增，块级作用域，所声明的变量只在它所在的代码块内有效。

- 基本用法：掌握在**for循环中var和let的区别**（`images`文件夹）

- let不存在变量提升（hoisting），使用let声明的变量一定要声明之后才能使用，不然就会报错。

- 暂时性死区（`TDZ:temporal dead zone`）：①如果在区块中存在let和const命令，它们所声明的变量就“绑定”在这个区域，不再受外部的影响。②如果在区块中存在let和const命令，这个区块对这些命令声明的变量从一开始就形成了封闭作用域，凡是在声明之前使用就会报错。③总之，在代码块内，在let命令声明变量之前，该变量是不可用的。（3种说法理解）**暂时性死区意味着typeof不再是一个百分百安全的操作**。因为暂时性死区的作用，使用let声明的变量在还没有声明完成之前使用就会报错。**总之，暂时性死区的本质就是，只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量。**

- 不允许重复声明：不允许在相同的作用域内，重复声明同一个变量

  ```
  function foo(){
    let a = 10;
    //错误 var a = 20; 
    //错误 let a = 1；
  }
  ```

  因此不能在函数内部声明参数

  ```
  function foo(f){
    let f；
  }
  foo();  //错误
  ```

#### 4.基本语法

- JavaScript区分大小写，`A`和`a`是两个不同的变量

- 变量提升（hoisting）：JavaScript引擎的工作方式是，先解析代码，**获取所有被声明的变量**，然后再一行行地运行。这样会使**所有变量的声明语句被提升到代码的头部**。

- 作用域：函数作用域，块级作用域。

- 条件语句：

  ```
  if (true) {
  
  } else {
  
  }
  ```

  ```
  switch () {
    case 1: ...  break;
    case 2: ...  break;
    ...
    default: ...
  }
  ```

  ```
  (条件) ? 表达式1 : 表达式2
  ```

- 循环语句：

  ```
  while (条件) {
    ...
  }
  ```

  ```
  for(初始化表达式;条件;递增表达式) {
    ...
  }
  ```

  ```
  do {
    ...
  } while(条件);  //后面有个分号不能省略
  ```

  break：用于**跳出**代码块或循环

  continue：用于终止**本轮**循环，**返回循环结构头部**，**开始下一轮循环**。

  ```
  var i = 0;
  while(i < 100) {
    i++;
    if(i === 10)  //break：i等于10就直接跳出while循环
                  //continue：i等于10直接开始下一轮循环
    console.log(i);
  }
  ```

  如果存在多轮循环，`break`和`continue`**只针对最内层循环**

- label标签：用于跳转到程序的任意位置。通常与`break`和`continue`配合使用，跳出特点的循环，标签可以是任意除了保留字之外的标识符。

  ```
  lable:
    语句
  ```

