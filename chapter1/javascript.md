# 笔记
* Javascript的语法源自Java，它的一等函数(first-class function)来自于Scheme，它的基于原型(prototype-based)的继承来自于Self。
* 当学习一门新的编程语言的时候，应当对照书中的示例边学边动手做，反复演练以加深自己的理解。
* 表达式是Javascript中的一个短语，这个短语可以通过运算得出一个值。通过“.”和“[]”来引用对象属性或数组元素的值就构成一个表达式。
* 语句和表达式之间有很多共同之处，粗略地讲，表达式仅仅计算出一个值但并不作任何操作，它并不改变程序的运行状态。而语句并不包含一个值，但它们改变程序的运行状态。在上文中已经见过变量声明语句和赋值语句。另一类语句是“控制结构”，比如条件判断和循环。
* 函数是一种值,可以赋值给变量。
	```
	var square = function(x){
		return x*x;
	};
	```
* 当将函数和对象合并写在一起时，函数就变成了“方法”。
* a.push(1,2,3) //push()方法向数组中添加元素
* 按照惯例构造函数均以大写字母开始
	```
	function Point(x,y){
		this.x = x;
		this.y = y;
	}
	```
* 注册事件兼容性写法image.addEventListener("click",hide,false),image.attachEvent("onclick",hide);
* JavaScript程序是用Unicode字符集编写的。
* JavaScript是区分大小写的语言。也就是说，关键字、变量、函数名和所有的标识符都必须采取一致的大小写形式。但需要注意的是，HTML并不区分大小写。例如，在HTML中设置事件处理程序时，onclick属性可以写成onClick，但在JavaScript代码中，必须使用小写的onclick。
* "a".charCodeAt(0).toString(16)=>61,"a"==="\u0061"
* 所谓直接量“literal”，就是程序中直接使用的数据值。数字、字符串、布尔值、正则表达式、null、undefined
* 出于可移植性和易于书写的考虑，通常我们只使用ASCII['æski]字母和数字来书写标识符。
* 如果当前语句和下一行语句无法合并解析，JavaScript则在第一行后填补分号，这是通用规则，但有两个例外。第一个例外是在涉及return、break和continue语句的场景中。第二个例外是在涉及“++”，“--”运算符的时候。
* 在编程语言中，能够表示操作的值的类型称做数据类型，编程语言最基本的特性就是能够支持多种数据类型。变量是一个值的符号名称，可以通过名称来获得对值的引用。JavaScript的数据类型分为两类：原始类型(primitive type)和对象类型(object type)。
* 普通的JavaScript对象是“命名值”的无序集合。JavaScript同样定义了一种特殊对象--数组，表示带编号的值的有序集合。JavaScript为数组定义了专用的语法，使数组拥有一些和普通对象不同的特有行为特性。
* JavaScript的类型分为原始类型和对象类型，也可分为可以拥有方法的类型和不能拥有方法的类型，同样可以分为可变(mutable)类型和不可变(immutable)类型。
* JavaScript变量是无类型的(untyped)，变量可以被赋予任何类型的值，同样一个变量也可以重新赋予不同类型的值。