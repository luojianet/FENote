# 笔记
* Javascript的语法源自Java，它的一等函数(first-class function)来自于Scheme，它的基于原型(prototype-based)的继承来自于Self。
* 当学习一门新的编程语言的时候，应当对照书中的示例边学边动手做，反复演练以加深自己的理解。
* 表达式是Javascript中的一个短语，这个短语可以通过运算得出一个值。通过“.”和“[]”来引用对象属性或数组元素的值就构成一个表达式。
* 语句和表达式之间有很多共同之处，粗略地讲，表达式仅仅计算出一个值但并不作任何操作，它并不改变程序的运行状态。而语句并不包含一个值，但它们改变程序的运行状态。在上文中已经见过变量声明语句和赋值语句。另一类语句是“控制结构”，比如条件判断和循环。
* 函数是一种值,可以赋值给变量。
	```javascript
	var square = function(x){
		return x*x;
	};
	```
* 当将函数和对象合并写在一起时，函数就变成了“方法”。
* a.push(1,2,3) //push()方法向数组中添加元素
* 按照惯例构造函数均以大写字母开始
	```javascript
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
* 当一个数字直接出现在JavaScript程序中，我们称之为数字直接量(numeric literal)。在任何数字直接量前添加负号(-)可以得到他们的负值。但负号是一元求反运算符，并不是数字直接量语法的组成部分。
* Math.max(x,y,z),Math.min(x,y,z)
* 被零整除在JavaScript并不报错：它只是简单的返回无穷大(Infinity)或负无穷大(-Infinity)。但有一个例外，零除以零是没有意义的，这种整除运算结果也是一个非数字(not-a-number)值，用NaN表示。无穷大除以无穷大、给任意负数作开方运算或者算术运算符与不是数字或无法转换为数字的操作数一起使用时都将返回NaN。
* Javascript中的非数字值有一点特殊：它和任何值都不相等，包括自身。也就是说，没办法通过x==NaN来判断变量x是否是NaN。相反，应当使用x！=x来判断，当且仅当x为NaN的时候，表达式的结果才为true。函数isNaN()的作用与此类似，如果参数是NaN或者是一个非数字值，则返回true。JavaScript中有一个类似的函数isFinite()，在参数不是NaN、Infinity、或-Infinity的时候返回true。
* 在ECMAScript3中，字符串直接量必须写在一行中，而ECMAScript5中，字符串直接量可以拆分成数行，每行必须以反斜线(\\)结束，反斜线和行结束符都不算是字符串直接量的内容。
* str.substring(index,index),str.slice(index,index),str.slice(-index),str.toUpperCase(),str.toLowerCase()。
* 在javascript中字符串是固定不变的，类似replace()和toUpperCase()的方法都返回新字符串，原字符串本身并没有发生改变。在ECMAScript5中，字符串可以当做只读数组，除了使用charAt()方法，也可以使用方括号来访问字符串总的单个字符。
* RegExp并不是JavaScript的基本类型。和Date一样，它只是一种具有实用API的特殊对象。正则表达式的语法很复杂，API也很丰富。在两条斜线之间的文本构成了一个正则表达式直接量。第二条斜线之后也可以跟随一个或多个字母，用来修饰匹配模式的含义。
* RegExp对象定义了很多有用的方法，字符串同样具有可以接受RegExp参数的方法。`pattern.test`,`text.search`,`text.match`,`text.replace`,`text.split`
* 通常认为null是它自有类型的唯一一个成员，它可以表示数字、字符串、对象是“无值”的。undefined是预定义的全局变量(它和null不一样，它不是关键字)，它的值就是“未定义”。
* 字符串既然不是对象，为什么它会有属性呢？只要引用了字符串s的属性，JavaScript就会将字符串值通过调用new String(s)的方式转换成对象，这个对象继承了字符串的方法，并被用来处理属性的引用。一旦属性引用结束，这个心创建的对象就会销毁。同字符串一样，数字和布尔值也具有各自的方法：通过Number()和Boolean()构造函数创建一个临时对象，这些方法的调用均是来自这个临时对象。null和undefined没有包装对象：访问它们的属性会造成一个类型错误。
	```javascript
		var str = "xl";
		str.len=2;//创建一个临时对象
		str.len=>undefined//创建另一个临时对象
	```
* 当运行这段代码时，str.len的值是undefined。第二行代码创建一个临时字符串对象，并给其len属性赋值为4，随即销毁这个对象。第三行通过原始的字符串值创建一个新字符串对象，尝试读取其len属性，这个属性自然不存在，表达式求值结果为undefined。这段代码说明了在读取字符串、数字和布尔值的属性值或方法的时候，表现的像对象一样。但如果你试图给其属性赋值，则会忽略这个操作：修改只是发生在临时对象身上，而这个临时对象并未继续保留下来。
* 存取字符串、数字或布尔值的属性的时创建的临时对象称做包装对象，它只是偶尔用来区分字符串值和字符串对象、数字和数值对象以及布尔值和布尔对象。通常，包装对象只是被看做是一种实现细节，而不用特别关注。
* javascript中的取值类型非常灵活，我们已经从布尔值看到了这一点：当javascript期望使用一个布尔值的时候，你可以提供任意类型值，javascript将根据需要自行转换类型。真值转换为true，假值转换为false。这在其它类型中同样适用：如果javascript期望使用一个字符串，它把给定的值将转换为字符串。如果javascript期望使用一个数字，它把给定的值将转换为字符串。如果javascript期望使用一个数字，它把给定的值将转换为数字，如果转换结果无意义的话将会返回NaN。
# 遗留的问题
* 二进制浮点数和四舍五入错误，IEEE-754浮点数表示法，JavaScript权威指南37page