- JavaScript使用<script>标签，一般只有最简单的脚本才放在HTML中，否则使用<script src="">来引入外部的脚本，这样的好处是浏览器会下载它，然后保存在浏览器缓存中，之后其他页面想要相同的脚本就可以从缓存中获取，而不用再下载。这样可以节省流量，使得页面加载更快。

- "use strict"或者'use strict'，可以开启严格模式，写在脚本或者函数的**顶部**。

- 由多个单词组成的变量的命名一般使用驼峰式（camelCase），也就是除了第一个单词，其他的每个单词以大写字母开头。ES6中使用let对变量进行声明。而当声明一个**常数变量（常量）**时，使用const，当常量是一开始就知道的值时，一般使用大写，如COLOR_RED，如果需要通过计算的常量则一般使用小写命名。

- JavaScript的数据类型：JavaScript是动态数据类型，意思是虽然编程语言中有不同的数据类型，但是你定义的变量并不会在定义后，被限制为某一数据类型。包括基本数据类型：Number、BigInt、String、Boolean、null、undefined、Symbol；引用数据类型：object

- 运算符typeof，会以字符串的形式返回数据类型，可以直接使用`typeof x`但是比较特别的是**typeof null返回的是object**。

- 浏览器与用户交互的几种函数：alert、prompt、confirm。其中alert可以显示信息；prompt显示信息要求用户输入文本，点击确定返回文本（**字符串**），点击取消则返回null；confirm显示信息等待用户点击确定则返回true，点击取消则返回false。

- 类型转换：字符串转换String()、数值型转换Number()、布尔型转换Boolean()。

  ```
  Number(undefined);  // NaN     	Boolean(undefined);    // false
  Number(NaN);        // NaN      Boolean(NaN);          // false
  Number(null);       // 0        Boolean(null);         // false
  Number("");         // 0        Boolean("");           // false
  ```

- 运算符：一元运算符优先级高于二元运算符。求幂，如 `2 ** 3 = 8`（2的3次方），同理可以 `4 ** (1/2) = 2`（1/2与平方根相同）。使用'+'连接字符串：当其中一个运算元是字符串时，另一个运算元也被转化为字符串，如`2 + "1" = "21"`，`"1" + 2 = "12"`。'+'作为一元运算符**可以进行类型转换**，如

  ```
  let a = prompt("first number:",1);
  let b = prompt("second number:",2);
  alert(+a + +b);   //输出为3，如果alert(a+b)则输出为12，因为prompt返回的是字符串。
  ```

- 三个等号：'='为赋值，'=='为普通的相等性检查，'==='为严格的相等性检查。比较字符串的时候，按照词典顺序进行比较，'a'>'A'。在使用'==='时，不会做任何数据类型转换，即如果两边数据类型不一样，就会返回false。所有比较运算符均返回布尔值：true/false。

  ```
  null == undefined;  //true
  null === undefined; //false
  'a' > 'A';    //true
  '2' > '12';   //true （字符串）
  ```

  

