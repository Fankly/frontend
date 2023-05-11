# JavaScript现代教程

## JavaScript简介

> 什么是JavaScript
>
> -   直接写在网页的 HTML 中，在页面加载的时候自动执行
> -   脚本语言
>
> 引擎
>
> -   V8 google opera Edge
> -   SpiderMonkey FireFox
> -   JavaScriptCore
> -   ...
>
> JS引擎工作
>
> 0.  引擎（如果是浏览器，则引擎被嵌入在其中）读取（“解析”）脚本
> 0.  然后，引擎将脚本转化（“编译”）为机器语言
> 0.  然后，机器代码快速地执行
>
> 引擎会对流程中的每个阶段都进行优化。它甚至可以在编译的脚本运行时监视它，分析流经该脚本的数据，并根据获得的信息进一步优化机器代码。

## 手册与规范

> ### 规范
>
> ECMA-262 规范包含了大部分深入的、详细的、规范化的关于 JavaScript的信息。这份规范明确地定义了这门语言
>
> ### 手册
>
> MDN（Mozilla）JavaScript 索引是一个带有用例和其他信息的主要的手册。它是一个获取关于个别语言函数、方法等深入信息的很好的信息来源

## 代码编辑器

> IDE
>
> -   VScode
> -   WebStrom
>
> 轻量级编辑器
>
> -   sublime
> -   NotePad++
> -   Vim

## 开发者控制台

> Google chrome
>
> -   F12开启控制台,调式代码
> -   shift+enter支持多行输入

## JavaScript基础知识

### script标签

> ```js
> <!DOCTYPE HTML>
> <html>
> 
> <body>
> 
> <p>script 标签之前...</p>
> 
> <script>
> alert('Hello, world!');
> </script>
> 
> <p>...script 标签之后</p>
> 
> </body>
> 
> </html
> ```
>
> 现代标记(markup),放在scirpt标签上
>
> -   type特性 type="text/javascript"
>
>     -   声明,现在不需要写
>
> -   language特性 language="JavaScript"
>
>     -   默认为JavaScript语言,不需要写
>
> -   src特性 src="JavaScript路径"
>
>     -   外部引入JS代码
>
>     -   注意事项
>
>         -   src引入的script标签内部不能写代码
>         -   标签内部的代码不会生效

## 代码结构

### 语句

> 语句是执行行为（action）的语法结构和命令,每条语句独占一行，以提高代码的可读性
>
> ```js
> alert('Hello');
> alert('World');
> ```

### 分号

> 当存在换行符（line break）时，在大多数情况下可以省略分号
>
> ```js
> alert('Hello')
> alert('World')
> ```
>
> 注意事项
>
> -   建议每条语句结束后,尽量加上分号
>
> ```js
> alert("Hello")
> 
> [1, 2].forEach(alert);
> 
> // 上面代码会让编译器理解成 alert("Hello")[1, 2].forEach(alert);
> ```

### 注释

> // 单行注释
>
> /**/ 多行注释

## 严格模式

> "use strict"
>
> -   确保"use strict"出现在脚本的最顶部，否则严格模式可能无法启用
> -   严格模式一旦启用,无法关闭

## 变量

> 变量是数据的"命名存储",使用变量访问存储的信息
>
> 创建变量可以使用let、var、const关键字
>
> ```js
> let message = "hello"
> ```
>
> 注意事项
>
> -   let声明的变量不能重复声明
>
> 变量命名
>
> -   变量名必须包含字母,数字,符号$和_
> -   首字符必须非数字
> -   建议采用小驼峰命名法,做到见名知意
> -   变量名区分大小写
> -   不能使用关键字
> -   如果使用严格模式,不定义直接赋值,会报错
>
> 常量
>
> -   一般声明常量使用const
> -   常量声明时,作为常数,值永远不发生改变,变量名建议大写
> -   如果页面加载之前是不确定的,变量名小写

## 数据类型

> ### JavaScript 中有 8 种基本的数据类型（译注：7 种原始类型和 1 种引用类型）
>
> ### Number类型
>
> -   *number* 类型代表整数和浮点数
> -   Infinity
> -   -Infinity
> -   NaN
>
> ### BigInt类型
>
> -   number” 类型可以存储更大的整数（最多 `1.7976931348623157 * 10308`），但超出安全整数范围 `±(253-1)` 会出现精度问题，因为并非所有数字都适合固定的 64 位存储。因此，可能存储的是“近似值”,所以可以使用bigInt存储
> -   尾部的 "n" 表示这是一个 BigInt 类型
> -   const bigInt = 1234567890123456789012345678901234567890n;
>
> ### String类型
>
> -   let str = "hello"
>
>     -   可以使用双引号,单引号或者反引号
>
> -   反引号
>
>     -   可以将变量和表达式包装在 `${…}` 中，来将它们嵌入到字符串中
>
>         -   alert( `Hello, *${**name}*!` ); // Hello, John!
>
>     -   `${…}` 内的表达式会被计算，计算结果会成为字符串的一部分
>
>         -   alert( "the result is ${1 + 2}" ); // the result is ${1 + 2}（使用双引号则不会计算 ${…} 中的内容）
>
> ### Boolean类型
>
> -   通常有两个值true和false
>
> ### Null类型
>
> -   特殊的 `null` 值不属于上述任何一种类型
> -   只包含null值
> -   表示无,空或则和值未知
>
> ### Undefined类型
>
> -   和null类型类似,不属于上述任何一种类型
> -   变量定义没有赋值,就会是undefined
>
> ### Object类型和Symbol类型
>
> -   object类型是特殊类型
> -   其他所有的数据类型都被称为“原始类型”，因为它们的值只包含一个单独的内容（字符串、数字或者其他）。相反，`object` 则用于储存数据集合和更复杂的实体
> -   `symbol` 类型用于创建对象的唯一标识符
>
> ### typeof运算符
>
> -   `typeof` 运算符返回参数的类型。当我们想要分别处理不同类型值的时候，或者想快速进行数据类型检验时，非常有用
>
> ```js
> typeof undefined // "undefined"
> 
> typeof 0 // "number"
> 
> typeof 10n // "bigint"
> 
> typeof true // "boolean"
> 
> typeof "foo" // "string"
> 
> typeof Symbol("id") // "symbol"
> 
> typeof Math // "object"  (1)
> 
> typeof null // "object"  (2)
> 
> typeof alert // "function"  (3)
> ```
>
> 最后三行可能需要额外的说明
>
> 0.  `Math` 是一个提供数学运算的内建 `object`。我们会在 [数字类型](https://zh.javascript.info/number) 一节中学习它。此处仅作为一个 `object` 的示例
> 0.  `typeof null` 的结果为 `"object"`。这是官方承认的 `typeof` 的错误，这个问题来自于 JavaScript 语言的早期阶段，并为了兼容性而保留了下来。`null` 绝对不是一个 `object`。`null` 有自己的类型，它是一个特殊值。`typeof` 的行为在这里是错误的
> 0.  `typeof alert` 的结果是 `"function"`，因为 `alert` 在 JavaScript 语言中是一个函数
>
> ### 扩展
>
> -   `typeof(x)` **语法**
>
>     -   `typeof` 是一个操作符，不是一个函数。这里的括号不是 `typeof` 的一部分。它是数学运算分组的括号
>     -   通常，这样的括号里包含的是一个数学表达式，例如 `(2 + 2)`，但这里它只包含一个参数 `(x)`。从语法上讲，它们允许在 `typeof` 运算符和其参数之间不打空格，有些人喜欢这样的风格
>
> ### 总结
>
> -   JavaScript 中有八种基本的数据类型（译注：前七种为基本数据类型，也称为原始数据类型，而 `object` 为复杂数据类型）
>
> -   七种原始数据类型
>
>     -   `number` 用于任何类型的数字：整数或浮点数，在 `±(253-1)` 范围内的整数。
>     -   `bigint` 用于任意长度的整数。
>     -   `string` 用于字符串：一个字符串可以包含 0 个或多个字符，所以没有单独的单字符类型。
>     -   `boolean` 用于 `true` 和 `false`。
>     -   `null` 用于未知的值 —— 只有一个 `null` 值的独立类型。
>     -   `undefined` 用于未定义的值 —— 只有一个 `undefined` 值的独立类型。
>     -   `symbol` 用于唯一的标识符。
>
> -   以及一种非原始数据类型：
>
>     -   `object` 用于更复杂的数据结构
>
> 我们可以通过 `typeof` 运算符查看存储在变量中的数据类型
>
> -   通常用作 `typeof x`，但 `typeof(x)` 也可行。
> -   以字符串的形式返回类型名称，例如 `"string"`。
> -   `typeof null` 会返回 `"object"` —— 这是 JavaScript 编程语言的一个错误，实际上它并不是一个 `object`。

### 交互:alert,prompt,confirm

> ### alert
>
> -   弹出一个弹窗,弹出的这个带有信息的小窗口被称为 **模态窗**。“modal” 意味着用户不能与页面的其他部分（例如点击其他按钮等）进行交互，直到他们处理完窗口。在上面示例这种情况下 —— 直到用户点击“确定”按钮。
>
> ### prompt
>
> -   `prompt` 函数接收两个参数 result = prompt(title, [default]);
>
>     -   第一个参数 title 显示给用户的文本
>     -   第二个参数 default 指定input框的初始值(可选)
>
> -   **语法中的方括号** `[...]`
>
>     -   上述语法中 `default` 周围的方括号表示该参数是可选的，不是必需的
>
> -   在IE浏览器中会提供默认值
>
>     -   第二个参数是可选的。但是如果我们不提供的话，Internet Explorer 会把 `"undefined"` 插入到 prompt
>     -   所以第二个参数给定一个空字符串
>
> ### confirm
>
> -   语法
>
>     -   result = confirm(question);
>
> -   `confirm` 函数显示一个带有 `question` 以及确定和取消两个按钮的模态窗口。点击确定返回 `true`，点击取消返回 `false`
>
> ```js
> let isBoss = confirm("Are you the boss?");
> 
> alert( isBoss ); // 如果“确定”按钮被按下，则显示 true
> ```

## 类型转换

> ### 字符串转换
>
> -   alert(value)将value中的值转换为字符串
> -   String(value)转换为字符串
>
> ### 数字型转换
>
> -   算术函数和表达式中，会自动进行 number 类型转换(+比较特殊)
>
> -   Number(value)转换为number类型
>
>     -   如果字符串不是一个有效数字,转换的结果为NaN
>
> -   number类型转换规则
>
>     -   undefined => NaN
>
>     -   null => 0
>
>     -   true和false 1and0
>
>     -   string 去掉首尾空白字符（空格、换行符 `\n`、制表符 `\t` 等）后的纯数字字符串中含有的数字。如果剩余字符串为空，则转换结果为 `0`。否则，将会从剩余字符串中“读取”数字。当类型转换出现 error 时返回 `NaN`
>
>     -   注意事项
>
>         -   null变成数字0
>         -   undefined变成NaN
>
> ### 布尔型转换
>
> -   0,空字符串,null,undefined和NaN变成false
> -   其他值变成true

## 基础运算符

> ### 运算元
>
> -   运算符应用的对象
>
> ### 数学运算
>
> -   加法 `+`
> -   减法 `-`
> -   乘法 `*`
> -   除法 `/`
> -   取余 `%`
> -   求幂 `**` eg:4**(1/2) //2 相当于平方根
>
> ### +(连接字符串同时也是加法)
>
> -   当任意一个运算元是字符串,另一个运算元也将转换为字符串
> -   如果再字符串前面加上+号,会将字符串转换为数字,对数字无效,将两边空格自动过滤
> -   如果字符串是数字+其他符号,会转换为NaN
>
> ### 运算符优先级
>
> -   一元运算符优先级高于二元运算符
>
> ### 赋值运算符(=)
>
> -   优先级非常低
> -   赋值=返回一个值
>
> ### 链式赋值
>
> -   链式赋值从右到左进行计算
> -   所有变量共享一个值
>
> ### 运算符缩写
>
> -   可以使用+=或者-=等等缩写
>
> ### 自增和自减
>
> -   如果单独使用的话,++前后没有区别
> -   如果再表达式中,++再前面时会先自增,在后面++的时候,会先计算在自增
>
> ### 位运算符
>
> -   按位与 ( `&` )
> -   按位或 ( `|` )
> -   按位异或 ( `^` )
> -   按位非 ( `~` )
> -   左移 ( `<<` )
> -   右移 ( `>>` )
> -   无符号右移 ( `>>>` )
>
> ### 逗号运算符
>
> -   逗号运算符 `,` 是最少见最不常使用的运算符之一。有时候它会被用来写更简短的代码，因此为了能够理解代码，我们需要了解它
> -   **逗号运算符的优先级非常低**
> -   a = 1 + 2, 3 + 4 会计算变成 a = 3 , 7,然后赋值,7不会执行

## 值比较

> ### 比较运算符
>
> -   大于 / 小于：`a > b`，`a < b`。
> -   大于等于 / 小于等于：`a >= b`，`a <= b`。
> -   检查两个值的相等：`a == b`，请注意双等号 `==` 表示相等性检查，而单等号 `a = b` 表示赋值。
> -   检查两个值不相等：不相等在数学中的符号是 `≠`，但在 JavaScript 中写成 `a != b`
>
> ### 比较结果为boolean类型
>
> -   `true` —— 表示“yes（是）”，“correct（正确）”或“the truth（真）”。
> -   `false` —— 表示“no（否）”，“wrong（错误）”或“not the truth（非真）”。
>
> ### 字符串比较
>
> -   首先比较两个字符串的首位字符大小。
> -   如果一方字符较大（或较小），则该字符串大于（或小于）另一个字符串。算法结束。
> -   否则，如果两个字符串的首位字符相等，则继续取出两个字符串各自的后一位字符进行比较。
> -   重复上述步骤进行比较，直到比较完成某字符串的所有字符为止。
> -   如果两个字符串的字符同时用完，那么则判定它们相等，否则未结束（还有未比较的字符）的字符串更大
> -   `真正比较的是Unicode编码顺序`
>
> ### 不同类型之间的比较
>
> -   当对不同类型的值进行比较时，JavaScript 会首先将其转化为数字（number）再判定大小
>
> -   注意事项
>
>     -   若直接比较两个值，其结果是相等的。
>     -   若把两个值转为布尔值，它们可能得出完全相反的结果，即一个是 `true`，一个是 `false`
>     -   JavaScript 会把待比较的值转化为数字后再做比较（因此 `"0"` 变成了 `0`）。若只是将一个变量转化为 `Boolean` 值，则会使用其他的类型转换规则
>
> ```js
> let a = 0;
> alert( Boolean(a) ); // false
> 
> let b = "0";
> alert( Boolean(b) ); // true
> 
> alert(a == b); // true
> ```
>
> ### 严格相等
>
> -   普通的相等性检查 `==` 存在一个问题，它不能区分出 `0` 和 `false`,这是因为在比较不同类型的值时，处于相等判断符号 `==` 两侧的值会先被转化为数字。空字符串和 `false` 也是如此，转化后它们都为数字 0
> -   **严格相等运算符 `===` 在进行比较时不会做任何的类型转换**
>
> ### 对null和undefined进行比较
>
> -   **当使用严格相等** `===` **比较二者时,结果为false**
>
> -   **当使用非严格相等** `==` **比较二者时,结果为true**,
>
> -   **当使用数学式或其他比较方法** `< > <= >=` **时**,null/undefined`会被转化为数字：`null`被转化为`0`，`undefined`被转化为`NaN
>
> -   **注意事项**
>
>     ```js
>     alert( null > 0 );  // (1) false
>     alert( null == 0 ); // (2) false
>     alert( null >= 0 ); // (3) true
>         
>     alert( null > 0 );  // (1) false
>     alert( null == 0 ); // (2) false
>     alert( null >= 0 ); // (3) true
>     ```
>
>     -   `undefined` 和 `null` 在相等性检查 `==` 中不会进行任何的类型转换，它们有自己独立的比较规则
>     -   相等性检查 `==` 和普通比较符 `> < >= <=` 的代码逻辑是相互独立的。进行值的比较时，`null` 会被转化为数字，因此它被转化为了 `0`。这就是为什么（3）中 `null >= 0` 返回值是 true，（1）中 `null > 0` 返回值是 false
>
> ### 特立独行的undefined
>
> ```js
> alert( undefined > 0 ); // false (1)
> alert( undefined < 0 ); // false (2)
> alert( undefined == 0 ); // false (3)
> ```
>
> -   `(1)` 和 `(2)` 都返回 `false` 是因为 `undefined` 在比较中被转换为了 `NaN`，而 `NaN` 是一个特殊的数值型值，它与任何值进行比较都会返回 `false`。
> -   `(3)` 返回 `false` 是因为这是一个相等性检查，而 `undefined` 只与 `null` 相等，不会与其他值相等
>
> ### 注意事项
>
> -   除了严格相等 `===` 外，其他但凡是有 `undefined/null` 参与的比较，我们都需要格外小心。
> -   除非你非常清楚自己在做什么，否则永远不要使用 `>= > < <=` 去比较一个可能为 `null/undefined` 的变量。对于取值可能是 `null/undefined` 的变量，请按需要分别检查它的取值情况

## 条件分支:if和?

> ### if语句
>
> -   `if(...)` 语句计算括号里的条件表达式，如果计算结果是 `true`，就会执行对应的代码块
>
> ### 布尔转换
>
> -   `if (…)` 语句会计算圆括号内的表达式，并将计算结果转换为布尔型
>
> ### else语句
>
> -   `if` 语句有时会包含一个可选的 “else” 块。如果判断条件不成立，就会执行它内部的代码
>
> ### 多个条件:"else if"
>
> -   一个条件的表达式的变体,如果if语句不满足,执行else if语句,如果所有的else if都不满足,再执行else
>
> ### 条件运算符"?"
>
> -   条件表达式 ? value1 : value2
> -   先执行条件表达式,在计算条件结果，如果结果为真，则返回 `左边结果`，否则返回 `右边结果`
> -   如果是多个?,使用一系列问号 `?` 运算符可以返回一个取决于多个条件的值
>
> ### 逻辑运算符
>
> -   `||`（或），`&&`（与），`!`（非），`??`（空值合并运算符）
>
> -   **||(或)**
>
>     -   如果参与运算的任意一个参数为 `true`，返回的结果就为 `true`，否则返回 `false`
>
>     -   如果操作数不是布尔值，那么它将会被转化为布尔值来参与运算
>
>     -   **计算规则**
>
>         -   从左到右依次计算操作数。
>         -   处理每一个操作数时，都将其转化为布尔值。如果结果是 `true`，就停止计算，返回这个操作数的初始值。
>         -   如果所有的操作数都被计算过（也就是，转换结果都是 `false`），则返回最后一个操作数
>         -   返回的值是操作数的初始形式，不会做布尔转换
>
> -   **&&(与)**
>
>     -   当两个操作数都是真值时，与运算返回 `true`，否则返回 `false`
>
>     -   **计算规则**
>
>         -   从左到右依次计算操作数。
>         -   在处理每一个操作数时，都将其转化为布尔值。如果结果是 `false`，就停止计算，并返回这个操作数的初始值。
>         -   如果所有的操作数都被计算过（例如都是真值），则返回最后一个操作数
>
>     -   **注意事项**
>
>         -   与运算 `&&` 的优先级比或运算 `||` 要高
>         -   `a && b || c && d` 跟 `&&` 表达式加了括号完全一样：`(a && b) || (c && d)`
>
> -   **!(非)**
>
>     -   感叹符号 `!` 表示布尔非运算符
>
>     -   **计算规则**
>
>         -   将操作数转化为布尔类型：`true/false`。
>         -   返回相反的值
>
> -   **空值合并运算符??**
>
>     -   JavaScript的新特性。 旧式浏览器可能需要 polyfills
>
>     -   由于它对待 `null` 和 `undefined` 的方式类似，所以在本文中我们将使用一个特殊的术语对其进行表示。为简洁起见，当一个值既不是 `null` 也不是 `undefined` 时，我们将其称为“已定义的（defined）”
>
>     -   a ?? b
>
>         -   如果 `a` 是已定义的，则结果为 `a`，
>         -   如果 `a` 不是已定义的，则结果为 `b`
>
>     ```js
>     let firstName = null;
>     let lastName = null;
>     let nickName = "Supercoder";
>         
>     // 显示第一个已定义的值：
>     alert(firstName ?? lastName ?? nickName ?? "匿名"); // Supercoder
>     alert(firstName || lastName || nickName || "Anonymous"); // Supercoder
>     ```
>
>     -   `||`和`??`的区别
>
>         -   `||` 返回第一个 **真** 值。
>         -   `??` 返回第一个 **已定义的** 值
>         -   `||` 无法区分 `false`、`0`、空字符串 `""` 和 `null/undefined`。它们都一样 —— 假值（falsy values）。如果其中任何一个是 `||` 的第一个参数，那么我们将得到第二个参数作为结果
>
>         ```js
>         let height = 0;
>
>         alert(height || 100); // 100
>         alert(height ?? 100); // 0
>         ```
>
>     -   **优先级**
>
>         -   ??`运算符的优先级与`||`相同，它们的的优先级都为`4
>         -   像 `||`一样，空值合并运算符在 `=`和 `?`运算前计算，但在大多数其他运算（例如 `+` 和 `*`）之后计算
>
>     -   **??与&&或||一起使用**
>
>         -   JavaScript 禁止将 `??` 运算符与 `&&` 和 `||` 运算符一起使用，除非使用括号明确指定了优先级

## 循环:while和for

> ### while循环
>
> ```js
> while (condition) {
> // 代码
> // 所谓的“循环体”
> }
> 
> let i = 3;
> while (i) alert(i--);
> ```
>
> -   当 `condition` 为真时，执行循环体的 `code`
> -   **单行循环体不需要大括号**
>
> ### do...while循环
>
> ```js
> do {
>   // 循环体
> } while (condition);
> ```
>
> -   循环首先执行循环体，然后检查条件，当条件为真时，重复执行循环体
> -   种形式的语法很少使用，除非你希望不管条件是否为真，循环体 **至少执行一次**。通常我们更倾向于使用另一个形式：`while(…) {…}`
>
> ### for循环
>
> ```js
> for (begin; condition; step) {
>   // ……循环体……
> }
> ```
>
> | begin                | condition                                        | body（循环体）         | step                   |
> | -------------------- | ------------------------------------------------ | ---------------------- | ---------------------- |
> | let i = 0            | i < 3                                            | alert(i)               | i++                    |
> | 进入循环时执行一次。 | 在每次循环迭代之前检查，如果为 false，停止循环。 | 条件为真时，重复运行。 | 在每次循环体迭代后执行 |
>
> ### 省略语句段
>
> -   `for` 循环的任何语句段都可以被省略
>
> ```js
> let i = 0; // 我们已经声明了 i 并对它进行了赋值
> 
> for (; i < 3; i++) { // 不再需要 "begin" 语句段
>   alert( i ); // 0, 1, 2
> }
> 
> for (;;) {
>   // 无限循环
> }
> ```
>
> ### 跳出循环
>
> -   `break` 指令表示强制退出
> -   `continue` 指令是停止当前这一次迭代，并强制启动新一轮循环（如果条件允许的话）
>
> ### 多层嵌套跳出循环
>
> -   **标签** 是在循环之前带有冒号的标识符
> -   `break <labelName>` 语句跳出循环至标签处
> -   `continue` 指令也可以与标签一起使用。在这种情况下，执行跳转到标记循环的下一次迭代
> -   `break` 指令必须在代码块内
>
> ```js
> outer: for (let i = 0; i < 3; i++) {
> 
>   for (let j = 0; j < 3; j++) {
> 
>     let input = prompt(`Value at coords (${i},${j})`, '');
> 
>     // 如果是空字符串或被取消，则中断并跳出这两个循环。
>     if (!input) break outer; // (*)
> 
>     // 用得到的值做些事……
>   }
> }
> alert('Done!');
> ```

## switch语句

> ### 语法
>
> -   `switch` 语句有至少一个 `case` 代码块和一个可选的 `default` 代码块
>
> ### 执行规则
>
> -   比较 `x` 值与第一个 `case`（也就是 `value1`）是否严格相等，然后比较第二个 `case`（`value2`）以此类推。
> -   如果相等，`switch` 语句就执行相应 `case` 下的代码块，直到遇到最靠近的 `break` 语句（或者直到 `switch` 语句末尾）。
> -   如果没有符合的 case，则执行 `default` 代码块（如果 `default` 存在）
>
> ### 注意事项
>
> -   **如果没有 `break`，程序将不经过任何检查就会继续执行下一个 `case`**
> -   **任何表达式都可以成为** `switch/case` **的参数**
> -   **`switch` 和 `case` 都允许任意表达式**
> -   **被比较的值必须是相同的类型才能进行匹配**
>
> ```js
> switch(x) {
>   case 'value1':  // if (x === 'value1')
>     ...
>     [break]
> 
>   case 'value2':  // if (x === 'value2')
>     ...
>     [break]
> 
>   default:
>     ...
>     [break]
> }
> ```

## 函数声明

> ```js
> //使用函数声明创建函数
> function showMessage() {
> alert( 'Hello everyone!' );
> }
> ```
>
> -   `function` 关键字首先出现，然后是 **函数名**，然后是括号之间的 **参数** 列表（用逗号分隔，在上述示例中为空，我们将在接下来的示例中看到），最后是花括号之间的代码（即“函数体”）
>
> ### 函数调用
>
> -   **函数名()** 进行调用
>
> ### 局部变量
>
> -   在函数中声明的变量只在该函数内部可见
>
> ### 外部变量
>
> -   函数对外部变量拥有全部的访问权限。函数也可以修改外部变量
> -   只有在没有局部变量的情况下才会使用外部变量
> -   如果在函数内部声明了同名变量，那么函数会 **代替** 外部变量。例如，在下面的代码中，函数使用局部的 `userName`，而外部变量被忽略
>
> ```js
> let userName = 'John';
> 
> function showMessage() {
>   let userName = "Bob"; // 声明一个局部变量
> 
>   let message = 'Hello, ' + userName; // Bob
>   alert(message);
> }
> 
> // 函数会创建并使用它自己的 userName
> showMessage();
> 
> alert( userName ); // John，未被更改，函数没有访问外部变量
> ```
>
> ### 参数
>
> ```js
> function showMessage(from, text) { // 参数：from 和 text
>   alert(from + ': ' + text);
> }
> 
> showMessage('Ann', 'Hello!'); // Ann: Hello! (*)
> showMessage('Ann', "What's up?"); // Ann: What's up? (**)
> ```
>
> -   当一个值被作为函数参数（parameter）传递时，它也被称为 **参数（argument）**
> -   参数（parameter）是函数声明中括号内列出的变量（它是函数声明时的术语）
> -   参数（argument）是调用函数时传递给函数的值（它是函数调用时的术语）
>
> ### 默认值
>
> -   如果一个函数被调用，但有参数（argument）未被提供，那么相应的值就会变成 `undefined`
> -   可以使用 `=` 为函数声明中的参数指定所谓的“默认”（如果对应参数的值未被传递则使用）值
> -   可以是更复杂的表达式，并且只会在缺少参数时才会被计算和分配
>
> ```js
> function showMessage(from, text = "no text given") {
>   alert( from + ": " + text );
> }
> 
> showMessage("Ann"); // Ann: no text given
> 
> function showMessage(from, text = anotherFunction()) {
>   // anotherFunction() 仅在没有给定 text 时执行
>   // 其运行结果将成为 text 的值
> }
> ```
>
> ### 后备的默认参数
>
> -   有些时候，将参数默认值的设置放在函数执行（相较更后期）而不是函数声明时，也行得通
> -   可以使用||
> -   也可以是空值合并运算符??,在大多数假值（例如 `0`）应该被视为“正常值”时更具优势
>
> ```js
> // 方式一
> function showMessage(text) {
>   // ...
> 
>   if (text === undefined) { // 如果参数未被传递进来
>     text = 'empty message';
>   }
> 
>   alert(text);
> }
> 
> // 方式二
> showMessage(); // empty message
> 
> function showMessage(text) {
>   // 如果 text 为 undefined 或者为假值，那么将其赋值为 'empty'
>   text = text || 'empty';
>   ...
> }
> 
> // 方式三
>   function showCount(count) {
>   // 如果 count 为 undefined 或 null，则提示 "unknown"
>   alert(count ?? "unknown");
> }
> 
> showCount(0); // 0
> showCount(null); // unknown
> showCount(); // unknown
> ```
>
> ### 返回值
>
> ```js
> function sum(a, b) {
>   return a + b;
> }
> 
> let result = sum(1, 2);
> alert( result ); // 3
> ```
>
> -   函数可以将一个值返回到调用代码中作为结果
> -   指令 `return` 可以在函数的任意位置。当执行到达时，函数停止，并将值返回给调用代码（分配给上述代码中的 `result`）
> -   只使用 `return` 但没有返回值也是可行的。但这会导致函数立即退出
> -   **空值的** `return` **或没有** `return` **的函数返回值为** `undefined`
>
> ### 函数命名
>
> -   `"show"` 开头的函数通常会显示某些内容
> -   `"get…"` —— 返回一个值
> -   `"calc…"` —— 计算某些内容
> -   `"create…"` —— 创建某些内容
> -   `"check…"` —— 检查某些内容并返回 boolean 值，等

## 函数表达式

> ```js
> let sayHi = function() {
> alert( "Hello" );
> };
> ```
>
> -   允许我们在任何表达式的中间创建一个新函数
> -   无论函数是如何创建的，函数都是一个值
> -   必须通过加()才能执行函数
>
> ### 回调函数
>
> ```js
> function ask(question, yes, no) {
>   if (confirm(question)) yes()
>   else no();
> }
> 
> function showOk() {
>   alert( "You agreed." );
> }
> 
> function showCancel() {
>   alert( "You canceled the execution." );
> }
> 
> // 用法：函数 showOk 和 showCancel 被作为参数传入到 ask
> ask("Do you agree?", showOk, showCancel);
> ```
>
> -   `ask` 的两个参数值 `showOk` 和 `showCancel` 可以被称为 **回调函数** 或简称 **回调**
>
> ```js
> function ask(question, yes, no) {
>   if (confirm(question)) yes()
>   else no();
> }
> 
> ask(
>   "Do you agree?",
>   function() { alert("You agreed."); },
>   function() { alert("You canceled the execution."); }
> );
> ```
>
> -   这里直接在 `ask(...)` 调用内进行函数声明。这两个函数没有名字，所以叫 **匿名函数**。这样的函数在 `ask` 外无法访问（因为没有对它们分配变量）
>
> ### 函数表达式和函数声明区别
>
> -   **语法区别**
>
>     -   **函数声明**：在主代码流中声明为单独的语句的函数
>     -   **函数表达式**：在一个表达式中或另一个语法结构中创建的函数。下面这个函数是在赋值表达式 `=` 右侧创建的
>
> -   **执行时机**
>
>     -   **函数表达式是在代码执行到达时被创建，并且仅从那一刻起可用**
>     -   **函数声明在被定义之前，它就可以被调用**
>
> -   **严格模式下，当一个函数声明在一个代码块内时，它在该代码块内的任何位置都是可见的。但在代码块外不可见**
>
> ```js
> // 函数声明
> function sum(a, b) {
>   return a + b;
> }
> 
> // 函数表达式
> let sum = function(a, b) {
>   return a + b;
> };
> ```
>
> ### 总结
>
> -   函数是值。它们可以在代码的任何地方被分配，复制或声明。
> -   如果函数在主代码流中被声明为单独的语句，则称为“函数声明”。
> -   如果该函数是作为表达式的一部分创建的，则称其“函数表达式”。
> -   在执行代码块之前，内部算法会先处理函数声明。所以函数声明在其被声明的代码块内的任何位置都是可见的。
> -   函数表达式在执行流程到达时创建

## 箭头函数基本认知

> ```js
> // 箭头函数版本
> let sum = (a, b) => a + b;
> 
> /* 这个箭头函数是下面这个函数的更短的版本：
> 
> let sum = function(a, b) {
> return a + b;
> };
> */
> 
> alert( sum(1, 2) ); // 3
> ```
>
> -   如果我们只有一个参数，还可以省略掉参数外的圆括号，使代码更短
> -   如果没有参数，括号则是空的（但括号必须保留）
>
> ```js
> let double = n => n * 2;
> // 差不多等同于：let double = function(n) { return n * 2 }
> 
> alert( double(3) ); // 6
> 
> let sayHi = () => alert("Hello!");
> 
> sayHi();
> ```
>
> ### 多行的箭头函数
>
> ```js
> let sum = (a, b) => {  // 花括号表示开始一个多行函数
>   let result = a + b;
>   return result; // 如果我们使用了花括号，那么我们需要一个显式的 “return”
> };
> 
> alert( sum(1, 2) ); // 3
> ```
>
> ### 总结
>
> -   不带花括号：`(...args) => expression` —— 右侧是一个表达式：函数计算表达式并返回其结果。如果只有一个参数，则可以省略括号，例如 `n => n*2`。
> -   带花括号：`(...args) => { body }` —— 花括号允许我们在函数中编写多个语句，但是我们需要显式地 `return` 来返回一些内容

## Mocha自动化测试

> -   **describe("title", function() { ... })**
>
>     -   表示我们正在描述的功能是什么。在我们的例子中我们正在描述函数 `pow`。用于组织“工人（workers）” —— `it` 代码块
>
> -   **it("use case description", function() { ... })**
>
>     -   `it` 里面的描述部分，我们以一种 **易于理解** 的方式描述特定的用例，第二个参数是用于对其进行测试的函数
>
> -   **assert.equal(value1, value2)**
>
>     -   `it` 块中的代码，如果实现是正确的，它应该在执行的时候不产生任何错误
>
> -   **`assert.*` 函数用于检查 `pow` 函数是否按照预期工作。在这里我们使用了其中之一 —— `assert.equal`，它会对参数进行比较，如果它们不相等则会抛出一个错误。这里它检查了 `pow(2, 3)` 的值是否等于 `8`。还有其他类型的比较和检查**
>
> ### 简单使用(mocha.html)
>
> -   `<head>` —— 添加用于测试的第三方库和样式文件。
> -   `<script>` 包含测试函数，在我们的例子中 —— 和 `pow` 相关的代码。
> -   测试代码 —— 在我们的案例中是名为 `test.js` 的脚本，它包含上面 `describe("pow", ...)` 的那些代码。
> -   HTML 元素 `<div id="mocha">` 将被 Mocha 用来输出结果。
> -   可以使用 `mocha.run()` 命令来开始测试
>
> ```js
> <!DOCTYPE html>
> <html>
>   <head>
>     <!-- add mocha css, to show results -->
>     <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/mocha/3.2.0/mocha.css">
>     <!-- add mocha framework code -->
>     <script src="https://cdnjs.cloudflare.com/ajax/libs/mocha/3.2.0/mocha.js"></script>
>     <script>
>       // enable bdd-style testing
>       mocha.setup('bdd');
>     </script>
>     <!-- add chai -->
>     <script src="https://cdnjs.cloudflare.com/ajax/libs/chai/3.5.0/chai.js"></script>
>     <script>
>       // chai has a lot of stuff, let's make assert global
>       let assert = chai.assert;
>     </script>
>   </head>
> 
>   <body>
> 
>     <script>
>       function pow(x, n) {
>         let result = 1;
> 
>         for (let i = 0; i < n; i++) {
>           result *= x;
>         }
> 
>         return result;
>       }
>     </script>
> 
>     <!-- the script with tests (describe, it...) -->
>     <script src="test.js"></script>
> 
>     <!-- the element with id="mocha" will contain test results -->
>     <div id="mocha"></div>
> 
>     <!-- run tests! -->
>     <script>
>       mocha.run();
>     </script>
>   </body>
> 
> </html>
> ```
>
> ### test.js
>
> ```js
> describe("Raises x to power n", function () {
>   it("5 in the power of 1 equals 5", function () {
>     assert.equal(pow(5, 1), 5);
>   });
> 
>   // Mocha 将只运行这个代码块
>   it.only("5 in the power of 2 equals 25", function () {
>     assert.equal(pow(5, 2), 25);
>   });
> 
>   it("5 in the power of 3 equals 125", function () {
>     assert.equal(pow(5, 3), 125);
>   });
> });
> ```

## Polyfill和转译器

> ### Polyfille和转译器作用
>
> -   **实现现代代码在不支持新特性的旧引擎上运行**
>
> ### 转译器(Transpilers)
>
> -   Babel等等
>
> ### Polyfill
>
> -   新的语言特性可能不仅包括语法结构和运算符，还可能包括内建函数
>
>     -   `Math.trunc(n)` 是一个“截断”数字小数部分的函数，例如 `Math.trunc(1.23)` 返回 `1`
>
>     -   由于我们谈论的是新函数，而不是语法更改，因此无需在此处转译任何内容。我们只需要声明缺失的函数。
>
>         更新/添加新函数的脚本被称为“polyfill”。它“填补”了空白并添加了缺失的实现
>
> ```js
> if (!Math.trunc) { // 如果没有这个函数
>   // 实现它
>   Math.trunc = function(number) {
>     // Math.ceil 和 Math.floor 甚至存在于上古年代的 JavaScript 引擎中
>     // 在本教程的后续章节中会讲到它们
>     return number < 0 ? Math.ceil(number) : Math.floor(number);
>   };
> }
> ```
>
> -   polyfill库
>
>     -   corejs
>     -   polufill.io

## 对象

> -   通过使用带有可选 **属性列表** 的花括号 `{…}` 来创建对象,一个属性就是一个键值对（“key: value”），其中键（`key`）是一个字符串（也叫做属性名），值（`value`）可以是任何值
>
> -   **对象的创建**
>
>     -   const 对象名 = new Object() // 构造函数写法
>     -   const 对象名 = {} // 字面量的语法
>
> -   **对象的删除**
>
>     -   delete 对象名.键
>
> -   **多字词语来作为属性名，但必须给它们加上引号**
>
> ```js
> let user = {
>   name: "John",
>   age: 30,
>   "likes birds": true  // 多词属性名必须加引号
> };
> ```
>
> -   **多词属性，点操作就不能使用**
>
>     -   点符号要求 `key` 是有效的变量标识符。这意味着：不包含空格，不以数字开头，也不包含特殊字符（允许使用 `$` 和 `_`）
>
> ```js
> let user = {};
> 
> // 设置
> user["likes birds"] = true;
> 
> // 读取
> alert(user["likes birds"]); // true
> 
> // 删除
> delete user["likes birds"];
> 
> let key = "likes birds";
> 
> // 跟 user["likes birds"] = true; 一样
> user[key] = true;
> 
> // 点符号不能以类似的方式使用
> let user = {
>   name: "John",
>   age: 30
> };
> 
> let key = "name";
> alert( user.key ) // undefined
> ```
>
> -   **计算属性**
>
>     -   当创建一个对象时，我们可以在对象字面量中使用方括号。这叫做 **计算属性**
>
> ```js
> let fruit = prompt("Which fruit to buy?", "apple");
> 
> let bag = {
>   [fruit]: 5, // 属性名是从 fruit 变量中得到的
> };
> 
> alert( bag.apple ); // 5 如果 fruit="apple"
> 
> let fruit = 'apple';
> let bag = {
>   [fruit + 'Computers']: 5 // bag.appleComputers = 5
> };
> ```
>
> -   **属性的简写**
>
>     -   当属性名(键名)和属性值中(变量名)相同的时候,可以省略成一个
>
> ```js
> function makeUser(name, age) {
>   return {
>     name, // 与 name: name 相同
>     age,  // 与 age: age 相同
>     // ...
>   };
> }
> ```
>
> -   **属性名称限制**
>
>     -   变量名不能是编程语言的某个保留字，如 “for”、“let”、“return” 等……,但对象的属性名并不受此限制
>     -   属性名可以是任何字符串或者 symbol,但是其他类型的时候会被自动地转换为字符串
>     -   `__proto__` 的属性不能设置为一个非对象的值
>
> ```js
> // 这些属性都没问题
> let obj = {
>   for: 1,
>   let: 2,
>   return: 3
> };
> 
> alert( obj.for + obj.let + obj.return );  // 6
> 
> //__proto__的属性不能设置为一个非对象的值
> let obj = {};
> obj.__proto__ = 5; // 分配一个数字
> alert(obj.__proto__); // [object Object] —— 值为对象，与预期结果不同
> ```
>
> -   **in操作符**
>    -   能够被访问任何属性。即使属性不存在也不会报错！读取不存在的属性只会得到 `undefined`
>     
>    -   **语法**
>     
>        -   "key" in object
>     
>    -   **注意事项**
>     
>        -   `in` 的左边必须是 **属性名**
>         -   如果我们省略引号，就意味着左边是一个变量，它应该包含要判断的实际属性名
> 
>```js
> let user = {};
> // 大部分情况下与 undefined 进行比较来判断就可以,但是如果值存储的是undefined就不行
> alert( user.noSuchProperty === undefined ); // true 意思是没有这个属性
> 
> // "key" in object
> let user = { name: "John", age: 30 };
> 
> alert( "age" in user ); // true，user.age 存在
> alert( "blabla" in user ); // false，user.blabla 不存在。
> ```
> 
>-   **for...in循环**
> 
>    -   为了遍历一个对象的所有键（key），可以使用一个特殊形式的循环：`for..in`
> 
>    -   **语法**
> 
>        -   for (key in object) { // 对此对象属性中的每个键执行的代码 }
> 
>-   **对象排序**
> 
>    -   "有特别的顺序”：`整数属性`会被进行排序，其他属性则按照创建的顺序显示
> 
>        -   “整数属性”指的是一个可以在不做任何更改的情况下与一个整数进行相互转换的字符串
>         -   如果整数属性不想排序,可以给键名加一个+号
> 
>    -   如果属性名不是整数，那它们就按照创建时的顺序来排序
> 
>```js
> // Number(...) 显式转换为数字
> // Math.trunc 是内建的去除小数部分的方法。
> alert( String(Math.trunc(Number("49"))) ); // "49"，相同，整数属性
> alert( String(Math.trunc(Number("+49"))) ); // "49"，不同于 "+49" ⇒ 不是整数属性
> alert( String(Math.trunc(Number("1.2"))) ); // "1"，不同于 "1.2" ⇒ 不是整数属性
> ```

## 对象的引用和赋值

> -   **赋值了对象的变量存储的不是对象本身，而是该对象“在内存中的地址” —— 换句话说就是对该对象的“引用**
> -   **就是如下代码一个对象引用另一个对象的地址,两个对象地址一样,如果更改内容,两个都会改变**
>
> ```js
> let user = { name: 'John' };
> 
> let admin = user;
> 
> admin.name = 'Pete'; // 通过 "admin" 引用来修改
> 
> alert(user.name); // 'Pete'，修改能通过 "user" 引用看到
> ```
>
> ### 通过引用来比较
>
> -   仅当两个对象指向同一个地址的时候,两者才会相等
>
> ```js
> let a = {};
> let b = a; // 复制引用
> 
> alert( a == b ); // true，都引用同一对象
> alert( a === b ); // true
> 
> // 如果两个独立的空对象比较,比较结果为false,因为两个对象的地址不相同
> let a = {}
> let b = {}
> alert(a == b) // false
> ```
>
> ### 克隆和合并
>
> ```js
> let user = {
>   name: "John",
>   age: 30
> };
> 
> let clone = {}; // 新的空对象
> 
> // 将 user 中所有的属性拷贝到其中
> for (let key in user) {
>   clone[key] = user[key];
> }
> 
> // 现在 clone 是带有相同内容的完全独立的对象
> clone.name = "Pete"; // 改变了其中的数据
> 
> alert( user.name ); // 原来的对象中的 name 属性依然是 John
> ```
>
> -   通过Object.assign方法同样的效果
>
>     -   **语法**
>
>         -   Object.assign(dest,[src1,src2,...])
>         -   第一个参数dest是目标对象
>         -   更后面的参数 `src1, ..., srcN`（可按需传递多个参数）是源对象
>         -   该方法将所有源对象的属性拷贝到目标对象 `dest` 中。换句话说，从第二个开始的所有参数的属性都被拷贝到第一个参数的对象中。
>         -   调用结果返回 `dest`
>
> ```js
> let user = { name: "John" };
> 
> let permissions1 = { canView: true };
> let permissions2 = { canEdit: true };
> 
> // 将 permissions1 和 permissions2 中的所有属性都拷贝到 user 中
> Object.assign(user, permissions1, permissions2);
> 
> // 现在 user = { name: "John", canView: true, canEdit: true }
> 
> //如果被拷贝的属性的属性名已经存在，那么它会被覆盖
> let user = { name: "John" };
> 
> Object.assign(user, { name: "Pete" });
> 
> alert(user.name); // 现在 user = { name: "Pete" }
> 
> //可以用 Object.assign 代替 for..in 循环来进行简单克隆
> let user = {
>   name: "John",
>   age: 30
> };
> 
> let clone = Object.assign({}, user);
> ```
>
> ### 深层克隆
>
> ```js
> let user = {
>   name: "John",
>   sizes: {
>     height: 182,
>     width: 50
>   }
> };
> 
> let clone = Object.assign({}, user);
> 
> alert( user.sizes === clone.sizes ); // true，同一个对象
> 
> // user 和 clone 分享同一个 sizes
> user.sizes.width++;       // 通过其中一个改变属性值
> alert(clone.sizes.width); // 51，能从另外一个获取到变更后的结果
> ```
>
> -   为了解决这个问题，并让 `user` 和 `clone` 成为两个真正独立的对象，我们应该使用一个拷贝循环来检查 `user[key]` 的每个值，如果它是一个对象，那么也复制它的结构。这就是所谓的“深拷贝”,可以使用[_.cloneDeep(obj)](https://lodash.com/docs#cloneDeep)
> -   **使用 const 声明的对象也是可以被修改的**
>
> ```js
> const user = {
>   name: "John"
> };
> 
> user.name = "Pete"; // (*)
> 
> alert(user.name); // Pete
> ```

## 垃圾回收

> ### 可达性
>
> -   `可达`值是那些以某种方式可访问或可用的值。它们一定是存储在内存中的
>
> -   固有的可达值的基本集合，这些值明显不能被释放,这些值被称作 **根（roots）**
>
>     -   当前执行的函数，它的局部变量和参数。
>     -   当前嵌套调用链上的其他函数、它们的局部变量和参数。
>     -   全局变量。
>     -   （还有一些内部的）
>
> -   如果一个值可以通过引用链从根访问任何其他值，则认为该值是可达的
>
> -   JavaScript 引擎中有一个被称作 [垃圾回收器](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)) 的东西在后台执行。它监控着所有对象的状态，并删除掉那些已经不可达的
>
> ```js
> // marry 函数通过让两个对象相互引用使它们“结婚”了，并返回了一个包含这两个对象的新对象。
> function marry(man, woman) {
>   woman.husband = man;
>   man.wife = woman;
> 
>   return {
>     father: man,
>     mother: woman
>   }
> }
> 
> let family = marry({
>   name: "John"
> }, {
>   name: "Ann"
> });
> // 由此产生下面图的内存结构
> ```
>
> ![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/73614c5939e644369c185504bfd63531~tplv-k3u1fbpfcp-zoom-1.image)
>
> ```js
> delete family.father;
> delete family.mother.husband;
> 
> // 仅删除这两个引用中的一个是不够的，因为所有的对象仍然都是可达的。
> // 但是，如果我们把这两个都删除，那么我们可以看到再也没有对 John 的引用了
> ```
>
> ![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7ec3642c295947a9bfa3a5a961c88660~tplv-k3u1fbpfcp-zoom-1.image)
>
> ```js
> // 对外引用不重要，只有传入引用才可以使对象可达。所以，John 现在是不可达的，并且将被从内存中删除，同时 John 的所有数据也将变得不可达,经过垃圾回收
> ```
>
> ![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0680a8443e3a458eaba208ed0171a296~tplv-k3u1fbpfcp-zoom-1.image)
>
> ```js
> //几个对象相互引用，但外部没有对其任意对象的引用，这些对象也可能是不可达的，并被从内存中删除。源对象与上面相同
> family = null;
> 
> //显而易见，John 和 Ann 仍然连着，都有传入的引用。但是，这样还不够。
> 
> //前面说的 "family" 对象已经不再与根相连，没有了外部对其的引用，所以它变成了一座“孤岛”，并且将被从内存中删除
> ```
>
> ![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ac9a07225b464f6bbd4368a7c5f381d3~tplv-k3u1fbpfcp-zoom-1.image)
>
> ### 内部算法
>
> -   **垃圾回收的基本算法被称为 “mark-and-sweep”**
>
> -   **定期执行以下“垃圾回收”步骤**
>
>     -   垃圾收集器找到所有的根，并“标记”（记住）它们。
>     -   然后它遍历并“标记”来自它们的所有引用。
>     -   然后它遍历标记的对象并标记 **它们的** 引用。所有被遍历到的对象都会被记住，以免将来再次遍历到同一个对象。
>     -   ……如此操作，直到所有可达的（从根部）引用都被访问到。
>     -   没有被标记的对象都会被删除。
>
> -   **分代收集**
>
>     对象被分成两组：“新的”和“旧的”。在典型的代码中，许多对象的生命周期都很短：它们出现、完成它们的工作并很快死去，因此在这种情况下跟踪新对象并将其从内存中清除是有意义的。那些长期存活的对象会变得“老旧”，并且被检查的频次也会降低
>
> -   **增量收集**
>
>     如果有许多对象，并且我们试图一次遍历并标记整个对象集，则可能需要一些时间，并在执行过程中带来明显的延迟。因此，引擎将现有的整个对象集拆分为多个部分，然后将这些部分逐一清除。这样就会有很多小型的垃圾收集，而不是一个大型的。这需要它们之间有额外的标记来追踪变化，但是这样会带来许多微小的延迟而不是一个大的延迟
>
> -   **闲时收集**
>
>     垃圾收集器只会在 CPU 空闲时尝试运行，以减少可能对代码执行的影响

## 对象方法,this

> ### 对象方法
>
> -   作为对象属性的函数被称为 **方法**
>
> ```js
> let user = {
>   // ...
> };
> 
> // 首先，声明函数
> function sayHi() {
>   alert("Hello!");
> }
> 
> // 然后将其作为一个方法添加
> user.sayHi = sayHi;
> 
> user.sayHi(); // Hello!
> ```
>
> ### 方法简写
>
> -   可以省略 `"function"`，只写 `sayHi()`
>
> ```js
> // 这些对象作用一样
> 
> user = {
>   sayHi: function() {
>     alert("Hello");
>   }
> };
> 
> // 方法简写看起来更好，对吧？
> let user = {
>   sayHi() { // 与 "sayHi: function(){...}" 一样
>     alert("Hello");
>   }
> };
> ```
>
> ### 方法中this
>
> -   **为了访问该对象，方法中可以使用 `this` 关键字**
>
> ```js
> let user = {
>   name: "John",
>   age: 30,
> 
>   sayHi() {
>     // "this" 指的是“当前的对象”
>     alert(this.name);
>   }
> 
> };
> 
> user.sayHi(); // John
> ```
>
> ### this不受限制
>
> -   JavaScript 中的 `this` 可以用于任何函数，即使它不是对象的方法
>
> -   `this` 的值是在代码运行时计算出来的，它取决于代码上下文
>
> -   **在没有对象的情况下调用：** `this == undefined`
>
>     -   严格模式下的 `this` 值为 `undefined`
>     -   在非严格模式的情况下，`this` 将会是 **全局对象**
>
> ```js
> let user = { name: "John" };
> let admin = { name: "Admin" };
> 
> function sayHi() {
>   alert( this.name );
> }
> 
> // 在两个对象中使用相同的函数
> user.f = sayHi;
> admin.f = sayHi;
> 
> // 这两个调用有不同的 this 值
> // 函数内部的 "this" 是“点符号前面”的那个对象
> user.f(); // John（this == user）
> admin.f(); // Admin（this == admin）
> 
> admin['f'](); // Admin（使用点符号或方括号语法来访问这个方法，都没有关系。）
> 
> // **在没有对象的情况下调用：this == undefined
> function sayHi() {
>   alert(this);
> }
> 
> sayHi(); // undefined
> ```
>
> ### 箭头函数没有自己的this
>
> -   它们没有自己的 `this`。如果我们在这样的函数中引用 `this`，`this` 值取决于外部“正常的”函数
>
> ```js
> let user = {
>   firstName: "Ilya",
>   sayHi() {
>     let arrow = () => alert(this.firstName);
>     arrow();
>   }
> };
> 
> user.sayHi(); // Ilya
> ```

## 构造器和操作符"new"

> ### 构造函数
>
> -   **约定规则**
>
>     -   它们的命名以大写字母开头。
>     -   它们只能由 `"new"` 操作符来执行
>
> -   **new操作符执行步骤**
>
>     -   一个新的空对象被创建并分配给 `this`。
>     -   函数体执行。通常它会修改 `this`，为其添加新的属性。
>     -   返回 `this` 的值
>
> ```js
> function User(name) {
>   // this = {};（隐式创建）
> 
>   // 添加属性到 this
>   this.name = name;
>   this.isAdmin = false;
> 
>   // return this;（隐式返回）
> }
> 
> // 所以new User("Jack") 的结果是相同的对象
> let user = {
>   name: "Jack",
>   isAdmin: false
> };
> ```
>
> ### 构造器模式测试:new.target
>
> -   在一个函数内部，我们可以使用 `new.target` 属性来检查它是否被使用 `new` 进行调用
> -   对于常规调用，它为 undefined，对于使用 `new` 的调用，则等于该函数
>
> ```js
> function User() {
>   alert(new.target);
> }
> 
> // 不带 "new"：
> User(); // undefined
> 
> // 带 "new"：
> new User(); // function User { ... }
> ```
>
> ### 构造器return
>
> -   通常，构造器没有 `return` 语句。它们的任务是将所有必要的东西写入 `this`，并自动转换为结果
>
> -   如果这有一个 `return` 语句
>
>     -   如果 `return` 返回的是一个对象，则返回这个对象，而不是 `this`
>     -   如果 `return` 返回的是一个原始类型，则忽略
>     -   总结一句话,带有对象的 `return` 返回该对象，在所有其他情况下返回 `this`
>
> ```
> function BigUser() {
> 
>   this.name = "John";
> 
>   return { name: "Godzilla" };  // <-- 返回这个对象
> }
> 
> alert( new BigUser().name );  // Godzilla，得到了那个对象
> 
> 
> function SmallUser() {
> 
>   this.name = "John";
> 
>   return; // <-- 返回 this
> }
> 
> alert( new SmallUser().name );  // John
> ```
>
> ### 省略括号
>
> -   如果没有参数，我们可以省略 `new` 后的括号
>
> ```js
> let user = new User; // <-- 没有参数
> // 等同于
> let user = new User();
> ```
>
> ### 构造器中的方法
>
> -   构造函数创建对象十分灵活,不仅可以将树形添加到`this`中,还可以添加方法
>
> ```js
> // new User(name) 用给定的 name 和方法 sayHi 创建了一个对象
> function User(name) {
>   this.name = name;
> 
>   this.sayHi = function() {
>     alert( "My name is: " + this.name );
>   };
> }
> 
> let john = new User("John");
> 
> john.sayHi(); // My name is: John
> 
> /*
> john = {
>    name: "John",
>    sayHi: function() { ... }
> }
> */
> ```
>
> ### 总结
>
> -   构造函数，或简称构造器，就是常规函数，但大家对于构造器有个共同的约定，就是其命名首字母要大写
> -   构造函数只能使用 `new` 来调用。这样的调用意味着在开始时创建了空的 `this`，并在最后返回填充了值的 `this`

## 可选链"?."

> -   可选链 `?.` 是一种访问嵌套对象属性的安全的方式。即使中间的属性不存在，也不会出现错误
>
> -   注意事项
>
>     -   ?.前的变量必须已声明
>     -   如果?.左边部分不存在,就会立即停止运算,右侧的任何函数调用和操作都不会执行
>
> -   使用
>
>     -   如果value?.prop
>
>         -   如果 `value` 存在，则结果与 `value.prop` 相同，
>         -   否则（当 `value` 为 `undefined/null` 时）则返回 `undefined`
>
> -   其他使用方式
>
>     -   ?.()
>
>     ```js
>     let userAdmin = {
>       admin() {
>         alert("I am admin");
>       }
>     };
>
>     let userGuest = {};
>
>     // 首先会通过userAdmin.admin获取admin属性,如果userAdmin存在,安全读取
>     // ?.()会检查左边的部分:如果admin存在,调用admin,如果不存在停止运算,什么事情都不会发生
>     userAdmin.admin?.(); // I am admin
>
>     userGuest.admin?.(); // 啥都没发生（没有这样的方法）
>
>     // 可以配合delete一起使用
>     delete user?name //如果user存在,则删除user.name
>     ```
>
>     -   ?.[]
>
>     ```js
>     let key = "firstName";
>
>     let user1 = {
>       firstName: "John"
>     };
>
>     let user2 = null;
>
>     alert( user1?.[key] ); // John
>     alert( user2?.[key] ); // undefined
>     ```
>
> -   总结
>
>     -   可选链 `?.` 语法有三种形式：
>
>         1.  `obj?.prop` —— 如果 `obj` 存在则返回 `obj.prop`，否则返回 `undefined`。
>         1.  `obj?.[prop]` —— 如果 `obj` 存在则返回 `obj[prop]`，否则返回 `undefined`。
>         1.  `obj.method?.()` —— 如果 `obj.method` 存在则调用 `obj.method()`，否则返回 `undefined`
>
>     -   `?.` 检查左边部分是否为 `null/undefined`，如果不是则继续运算

## symbol

> 根据规范,只有两种类型可以作为对象的属性键,如果使用另一种类型,它会被自动转换为字符串
>
> -   字符串类型
> -   symbol类型
>
> ### symbol
>
> -   "symbol"值表示唯一的标识符
>
> -   使用方式
>
>     -   可以通过Symbol()创建这种类型的值 let id = Symbol()
>
> -   注意事项
>
>     -   symbol保证是唯一的
>     -   symbol不会被自动转换为字符串
>     -   如果想显示一个symbol,需要在上面调用 `.toString()`方法或者获取 `symbol.description` 属性，只显示描述（description）
>
> ```js
> let id = Symbol("test");
> 
> console.log(id.toString()) // Symbol(test)
> 
> 
> let id = Symbol("id");
> 
> console.log(id.description); // id
> ```
>
> ### "隐藏"属性
>
> symbol 允许我们创建对象的“隐藏”属性，代码的任何其他部分都不能意外访问或重写这些属性
>
> ```js
> let user = { // 属于另一个代码
>   name: "John"
> };
> 
> let id = Symbol("id");
> 
> user[id] = 1;
> 
> alert( user[id] ); // 我们可以使用 symbol 作为键来访问数据
> ```
>
> ### 对象字面量中symbol
>
> 如果我们要在对象字面量 `{...}` 中使用 symbol，则需要使用方括号把它括起来,这是因为我们需要变量 `id` 的值作为键，而不是字符串 “id”
>
> ```
> let id = Symbol("id");
> 
> let user = {
>   name: "John",
>   [id]: 123 // 而不是 "id"：123
> };
> ```
>
> ### symbol在for...in中会被跳过
>
> symbol 属性不参与 `for..in` 循环
>
> ```js
> let id = Symbol("id");
> let user = {
>   name: "John",
>   age: 30,
>   [id]: 123
> };
> 
> for (let key in user) alert(key); // name, age（没有 symbol）
> 
> // 使用 symbol 任务直接访问
> alert("Direct: " + user[id]); // Direct: 123
> ```
>
> -   **Object.keys(user)** 也会忽略它们。这是一般“隐藏符号属性”原则的一部分。如果另一个脚本或库遍历我们的对象，它不会意外地访问到符号属性,相反，**Object.assign** 会同时复制字符串和 symbol 属性,这里并不矛盾，就是这样设计的。这里的想法是当我们克隆或者合并一个 object 时，通常希望 **所有** 属性被复制（包括像 `id` 这样的 symbol）
>
> ### 全局symbol
>
> -   从注册表中读取（不存在则创建）symbol，请使用 `Symbol.for(key)`
> -   该调用会检查全局注册表，如果有一个描述为 `key` 的 symbol，则返回该 symbol，否则将创建一个新 symbol（`Symbol(key)`），并通过给定的 `key` 将其存储在注册表中
> -   注册表内的 symbol 被称为 **全局 symbol**
>
> ```js
> function createSymbol(){
>   return Symbol.for("id");
> }
> // 再次读取（可能是在代码中的另一个位置）
> let idAgain = Symbol.for("id");
> 
> // 相同的 symbol
> console.log(createSymbol()) // Symbol(id)
> console.log(idAgain) // Symbol(id)
> console.log(createSymbol() === idAgain) // true
> 
> ```
>
> ### Symbol.keyFor
>
> -   对于全局 symbol，`Symbol.for(key)` 按名字返回一个 symbol。相反，通过全局 symbol 返回一个名字，我们可以使用 `Symbol.keyFor(sym)`
> -   `Symbol.keyFor` 内部使用全局 symbol 注册表来查找 symbol 的键。所以它不适用于非全局 symbol。如果 symbol 不是全局的，它将无法找到它并返回 `undefined`
> -   symbol 都具有 `description` 属性
>
> ```js
> function createSymbol(){
>   return Symbol.for("sym");
> }
> 
> // 通过 name 获取 symbol
> let sym = Symbol.for("name");
> let sym2 = Symbol.for("id");
> 
> // 通过 symbol 获取 name
> console.log(Symbol.keyFor(sym)); // name
> console.log(Symbol.keyFor(sym2)); // id
> console.log(Symbol.keyFor(createSymbol())) // sym
> ```
>
> ### 系统symbol
>
> -   JavaScript 内部有很多“系统” symbol，我们可以使用它们来微调对象的各个方面
>
>     -   `Symbol.hasInstance`
>     -   `Symbol.isConcatSpreadable`
>     -   `Symbol.iterator`
>     -   `Symbol.toPrimitive`
>     -   ……等等
>
> -   `Symbol.toPrimitive` 允许我们将对象描述为原始值转换
>
> ### 总结
>
> -   `symbol` 是唯一标识符的基本类型
>
> -   symbol 是使用带有可选描述（name）的 `Symbol()` 调用创建的
>
> -   symbol 总是不同的值，即使它们有相同的名字。如果我们希望同名的 symbol 相等，那么我们应该使用全局注册表
>
>     -   `Symbol.for(key)` 返回（如果需要的话则创建）一个以 `key` 作为名字的全局 symbol
>     -   `Symbol.for` 多次调用 `key` 相同的 symbol 时，返回的就是同一个 symbol
>
> -   symbol 有两个主要的使用场景
>
>     -   “隐藏” 对象属性
>
>         -   如果我们想要向“属于”另一个脚本或者库的对象添加一个属性，我们可以创建一个 symbol 并使用它作为属性的键。symbol 属性不会出现在 `for..in` 中，因此它不会意外地被与其他属性一起处理。并且，它不会被直接访问，因为另一个脚本没有我们的 symbol。因此，该属性将受到保护，防止被意外使用或重写
>
>     -   JavaScript 使用了许多系统 symbol，这些 symbol 可以作为 `Symbol.*` 访问。我们可以使用它们来改变一些内建行为。例如，在本教程的后面部分，我们将使用 `Symbol.iterator` 来进行 [迭代](https://zh.javascript.info/iterable) 操作，使用 `Symbol.toPrimitive` 来设置 [对象原始值的转换](https://zh.javascript.info/object-toprimitive) 等等
>
> -   symbol 不是 100% 隐藏的。有一个内建方法 [Object.getOwnPropertySymbols(obj)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertySymbols) 允许我们获取所有的 symbol。还有一个名为 [Reflect.ownKeys(obj)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Reflect/ownKeys) 的方法可以返回一个对象的 **所有** 键，包括 symbol。但大多数库、内建方法和语法结构都没有使用这些方法

## 对象-原始类型转换

> ### 转换规则
>
> -   没有转换为布尔值。所有的对象在布尔上下文（context）中均为 `true`，就这么简单。只有字符串和数字转换
> -   数字转换发生在对象相减或应用数学函数时。例如，`Date` 对象（将在 [日期和时间](https://zh.javascript.info/date) 一章中介绍）可以相减，`date1 - date2` 的结果是两个日期之间的差值
> -   至于字符串转换 —— 通常发生在我们像 `alert(obj)` 这样输出一个对象和类似的上下文中
>
> ### hint
>
> -   `"string"`对象到字符串的转换，当我们对期望一个字符串的对象执行操作时，如 “alert”
>
> ```js
> // 输出
> alert(obj);
> 
> // 将对象作为属性键
> anotherObj[obj] = 123;
> ```
>
> -   `"number"`对象到数字的转换，例如当我们进行数学运算时,大多数内建的数学函数也包括这种转换
>
> ```js
> // 显式转换
> let num = Number(obj);
> 
> // 数学运算（除了二元加法）
> let n = +obj; // 一元加法
> let delta = date1 - date2;
> 
> // 小于/大于的比较
> let greater = user1 > user2;
> ```
>
> -   `"default"`在少数情况下发生，当运算符“不确定”期望值的类型时
>
>     -   二元加法 `+` 可用于字符串（连接），也可以用于数字（相加）。因此，当二元加法得到对象类型的参数时，它将依据 `"default"` hint 来对其进行转换
>     -   如果对象被用于与字符串、数字或 symbol 进行 `==` 比较，这时到底应该进行哪种转换也不是很明确，因此使用 `"default"` hint
>
> ```js
> // 二元加法使用默认 hint
> let total = obj1 + obj2;
> 
> // obj == number 使用默认 hint
> if (user == 1) { ... };
> ```
>
> -   像 `<` 和 `>` 这样的小于/大于比较运算符，也可以同时用于字符串和数字。不过，它们使用 “number” hint，而不是 “default”
>
> ### 为了进行转换，JavaScript 尝试查找并调用三个对象方法
>
> -   调用 `obj[Symbol.toPrimitive](hint)` —— 带有 symbol 键 `Symbol.toPrimitive`（系统 symbol）的方法，如果这个方法存在的话，
> -   否则，如果 hint 是 `"string"` —— 尝试调用 `obj.toString()` 或 `obj.valueOf()`，无论哪个存在。
> -   否则，如果 hint 是 `"number"` 或 `"default"` —— 尝试调用 `obj.valueOf()` 或 `obj.toString()`，无论哪个存在
>
> ### Symbol.toPrimitive
>
> -   `Symbol.toPrimitive` 的内建 symbol，它被用来给转换方法命名
> -   如果 `Symbol.toPrimitive` 方法存在，则它会被用于所有 hint，无需更多其他方法
>
> ```js
> let user = {
>   name: "John",
>   money: 1000,
> 
>   [Symbol.toPrimitive](hint) {
>     alert(`hint: ${hint}`);
>     return hint == "string" ? `{name: "${this.name}"}` : this.money;
>   }
> };
> 
> // 转换演示：
> alert(user); // hint: string -> {name: "John"}
> alert(+user); // hint: number -> 1000
> alert(user + 500); // hint: default -> 1500
> ```
>
> ### toString/valueOf
>
> -   如果 `Symbol.toPrimitive` 方法存在，则它会被用于所有 hint，无需更多其他方法
>
>     -   对于 `"string"` hint：调用 `toString` 方法，如果它不存在，则调用 `valueOf` 方法（因此，对于字符串转换，优先调用 `toString`）
>     -   对于其他 hint：调用 `valueOf` 方法，如果它不存在，则调用 `toString` 方法（因此，对于数学运算，优先调用 `valueOf` 方法）
>     -   这些方法必须返回一个原始值。如果 `toString` 或 `valueOf` 返回了一个对象，那么返回值会被忽略
>
> -   默认情况下，普通对象具有 `toString` 和 `valueOf` 方法
>
>     -   `toString` 方法返回一个字符串 `"[object Object]"`
>     -   `valueOf` 方法返回对象自身
>
> ```js
> let user = {
>   name: "John",
>   money: 1000,
> 
>   // 对于 hint="string"
>   toString() {
>     return `{name: "${this.name}"}`;
>   },
> 
>   // 对于 hint="number" 或 "default"
>   valueOf() {
>     return this.money;
>   }
> 
> };
> 
> alert(user); // toString -> {name: "John"}
> alert(+user); // valueOf -> 1000
> alert(user + 500); // valueOf -> 1500
> ```
>
> -   如果没有 `Symbol.toPrimitive` 和 `valueOf`，`toString` 将处理所有原始转换
>
> ```js
> let user = {
>   name: "John",
> 
>   toString() {
>     return this.name;
>   }
> };
> 
> alert(user); // toString -> John
> alert(user + 500); // toString -> John500
> ```
>
> ### 转换可以返回任何原始类型
>
> -   关于所有原始转换方法，有一个重要的点需要知道，就是它们不一定会返回 “hint” 的原始值
> -   没有限制 `toString()` 是否返回字符串，或 `Symbol.toPrimitive` 方法是否为 `"number"` hint 返回数字
> -   唯一强制性的事情是：这些方法必须返回一个原始值，而不是对象
>
> ### 进一步的转换
>
> -   如果我们将对象作为参数传递，则会出现两个运算阶段
>
>     -   对象被转换为原始值（通过前面我们描述的规则）
>     -   如果还需要进一步计算，则生成的原始值会被进一步转换
>
> ```js
> //1.乘法 obj * 2 首先将对象转换为原始值（字符串 “2”）。
> //2.之后 "2" * 2 变为 2 * 2（字符串被转换为数字）
> 
> let obj = {
>   // toString 在没有其他方法的情况下处理所有转换
>   toString() {
>     return "2";
>   }
> };
> 
> alert(obj * 2); // 4，对象被转换为原始值字符串 "2"，之后它被乘法转换为数字 2
> ```
>
> -   二元加法在同样的情况下会将其连接成字符串，因为它更愿意接受字符串
>
> ```js
> let obj = {
>   toString() {
>     return "2";
>   }
> };
> 
> alert(obj + 2); // 22（"2" + 2）被转换为原始值字符串 => 级联
> ```
>
> ### 总结
>
> -   对象到原始值的转换，是由许多期望以原始值作为值的内建函数和运算符自动调用的
>
> -   这里有三种类型（hint）
>
>     -   `"string"`（对于 `alert` 和其他需要字符串的操作）
>     -   `"number"`（对于数学运算）
>     -   `"default"`（少数运算符，通常对象以和 `"number"` 相同的方式实现 `"default"` 转换）
>
> -   [规范](https://tc39.github.io/ecma262/#sec-toprimitive)明确描述了哪个运算符使用哪个 hint
>
> -   转换算法
>
>     -   调用 `obj[Symbol.toPrimitive](hint)` 如果这个方法存在
>
>     -   否则，如果 hint 是 `"string"`
>
>         -   尝试调用 `obj.toString()` 或 `obj.valueOf()`，无论哪个存在
>
>     -   否则，如果 hint 是 `"number"` 或者 `"default"`
>
>         -   尝试调用 `obj.valueOf()` 或 `obj.toString()`，无论哪个存在
>
> -   所有这些方法都必须返回一个原始值才能工作（如果已定义）
>
> -   在实际使用中，通常只实现 `obj.toString()` 作为字符串转换的“全能”方法就足够了，该方法应该返回对象的“人类可读”表示，用于日志记录或调试

## 原始类型方法

> -   原始类型
>
>     -   是原始类型中的一种值
>     -   在 JavaScript 中有 7 种原始类型：`string`，`number`，`bigint`，`boolean`，`symbol`，`null` 和 `undefined`
>
> -   对象
>
>     -   能够存储多个值作为属性
>     -   可以使用大括号 `{}` 创建对象，例如：`{name: "John", age: 30}`。JavaScript 中还有其他种类的对象，例如函数就是对象
>
> ### 当作对象的原始类型
>
> -   为了保证原始类型轻量，原始类型必须是原始的，创建了特殊的“对象包装器”，“对象包装器”对于每种原始类型都是不同的，它们被称为 `String`、`Number`、`Boolean`、`Symbol` 和 `BigInt`
>
> -   字符串方法 [str.toUpperCase()](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) 返回一个大写化处理的字符串
>
> -   `str.toUpperCase()` 中实际发生的情况
>
>     -   字符串 `str` 是一个原始值。因此，在访问其属性时，会创建一个包含字符串字面值的特殊对象，并且具有可用的方法，例如 `toUpperCase()`。
>     -   该方法运行并返回一个新的字符串（由 `alert` 显示）。
>     -   特殊对象被销毁，只留下原始值 `str`
>
> ```js
> let str = "Hello";
> 
> alert( str.toUpperCase() ); // HELLO
> 
> let n = 1.23456;
> 
> alert( n.toFixed(2) ); // 1.23
> ```
>
> -   **构造器** `String/Number/Boolean` **仅供内部使用**
>
>     -   在 JavaScript 中可以使用new String("2")创建，创建出来的都是object，object在if中始终为真
>     -   调用不带 `new`（关键字）的 `String/Number/Boolean` 函数是可以的且有效的。它们将一个值转换为相应的类型：转成字符串、数字或布尔值（原始类型）
>
> ```js
> let num = Number("123"); // 将字符串转成数字
> ```
>
> -   **null/undefined 没有任何方法**
>
>     -   特殊的原始类型 `null` 和 `undefined` 是例外。它们没有对应的“对象包装器”，也没有提供任何方法。从某种意义上说，它们是“最原始的”

## 数字类型

> 数字（number）有两种类型
>
> -   JavaScript 中的常规数字以 64 位的格式 [IEEE-754](https://en.wikipedia.org/wiki/IEEE_754) 存储，也被称为“双精度浮点数”。这是我们大多数时候所使用的数字
> -   BigInt 用于表示任意长度的整数，常规整数不能安全地超过 `(253-1)` 或小于 `-(253-1)`,所以当超过时用BigInt代替常规整数
>
> ### 编写数字的更多方法
>
> ```js
> //假如我们需要表示 10 亿。显然，我们可以这样写
> let billion = 1000000000;
> //我们也可以使用下划线 _ 作为分隔符
> let billion = 1_000_000_000;
> 
> //这里的下划线 _ 扮演了“语法糖”的角色，使得数字具有更强的可读性。JavaScript 引擎会直接忽略数字之间的 _，所以 上面两个例子其实是一样的
> 
> //JavaScript 中，我们可以通过在数字后面附加字母 "e" 并指定零的个数来缩短数字
> let billion = 1e9;  // 10 亿，字面意思：数字 1 后面跟 9 个 0
> 
> alert( 7.3e9 );  // 73 亿（与 7300000000 和 7_300_000_000 相同）
> ```
>
> ### 十六进制，二进制和八进制数字
>
> -   [十六进制](https://en.wikipedia.org/wiki/Hexadecimal) 数字在 JavaScript 中被广泛用于表示颜色，编码字符以及其他许多东西。所以自然地，有一种较短的写方法：`0x`，然后是数字
>
> ```js
> alert( 0xff ); // 255
> alert( 0xFF ); // 255（一样，大小写没影响）
> ```
>
> -   二进制和八进制数字系统很少使用，但也支持使用 `0b` 和 `0o` 前缀
>
> ```js
> let a = 0b11111111; // 二进制形式的 255
> let b = 0o377; // 八进制形式的 255
> 
> alert( a == b ); // true，两边是相同的数字，都是 255
> ```
>
> ### toString(base)
>
> -   `num.toString(base)` 返回在给定 `base` 进制数字系统中 `num` 的字符串表示形式
>
> ```js
> let num = 255;
> 
> alert( num.toString(16) );  // ff
> alert( num.toString(2) );   // 11111111
> ```
>
> -   base的范围可以从 `2` 到 `36`。默认情况下是 `10`
>
> -   常见的用例
>
>     -   **base=16** 用于十六进制颜色，字符编码等，数字可以是 `0..9` 或 `A..F`。
>     -   **base=2** 主要用于调试按位操作，数字可以是 `0` 或 `1`。
>     -   **base=36** 是最大进制，数字可以是 `0..9` 或 `A..Z`。所有拉丁字母都被用于了表示数字。对于 `36` 进制来说，一个有趣且有用的例子是，当我们需要将一个较长的数字标识符转换成较短的时候，例如做一个短的 URL。可以简单地使用基数为 `36` 的数字系统表示
>
> ```js
> console.log(12..toString(10)) // 12 十进制
> console.log(12..toString(2)) // 1100 二进制
> ```
>
> ### 舍入
>
> -   **Math.floor**
>
>     -   向下舍入：`3.1` 变成 `3`，`-1.1` 变成 `-2`
>
> -   **Math.ceil**
>
>     -   向上舍入：`3.1` 变成 `4`，`-1.1` 变成 `-1`
>
> -   **Math.round**
>
>     -   向最近的整数舍入：`3.1` 变成 `3`，`3.6` 变成 `4`，中间值 `3.5` 变成 `4`
>
> -   **Math.trunc** **（IE 浏览器不支持这个方法）**
>
>     -   移除小数点后的所有内容而没有舍入：`3.1` 变成 `3`，`-1.1` 变成 `-1`
>
> -   数字舍入到小数点后 `n` 位
>
>     -   乘除法
>
>     ```js
>     let num = 1.23456;
>         
>     alert( Math.round(num * 100) / 100 ); // 1.23456 -> 123.456 -> 123 -> 1.23
>     ```
>
>     -   函数**toFixed(n)** 将数字舍入到小数点后 `n` 位，并以字符串形式返回结果
>
>         -   注意事项
>
>             -   这会向上或向下舍入到最接近的值，类似于 `Math.round`
>             -   注意 `toFixed` 的结果是一个字符串。如果小数部分比所需要的短，则在结尾添加零
>
>         -   可以使用一元加号或 `Number()` 调用，将其转换为数字，例如 `+ num.toFixed(5)`
>
>     ```js
>     let num = 12.34;
>     alert( num.toFixed(1) ); // "12.3"
>         
>     let num = 12.36;
>     alert( num.toFixed(1) ); // "12.4"
>         
>     let num = 12.34;
>     alert( num.toFixed(5) ); // "12.34000"，在结尾添加了 0，以达到小数点后五位
>     ```
>
> ## 不精确的计算
>
> -   在内部，数字是以 64 位格式 [IEEE-754](http://en.wikipedia.org/wiki/IEEE_754) 表示的，所以正好有 64 位可以存储一个数字：其中 52 位被用于存储这些数字，其中 11 位用于存储小数点的位置，而 1 位用于符号
> -   如果一个数字真的很大，则可能会溢出 64 位存储，变成一个特殊的数值 `Infinity`
>
> ```js
> alert( 1e500 ); // Infinity
> 
> console.log(0.1 + 0.2 === 0.3);// false
> 
> console.log(0.1 + 0.2);// 0.30000000000000004
> ```
>
> -   **为什么0.2+0.3不相等**
>
>     -   一个数字以其二进制的形式存储在内存中，一个 1 和 0 的序列。但是在十进制数字系统中看起来很简单的 `0.1`，`0.2` 这样的小数，实际上在二进制形式中是无限循环小数
>     -   什么是 `0.1`？`0.1` 就是 `1` 除以 `10`，`1/10`，即十分之一。在十进制数字系统中，这样的数字表示起来很容易。将其与三分之一进行比较：`1/3`。三分之一变成了无限循环小数 `0.33333(3)`
>     -   在十进制数字系统中，可以保证以 `10` 的整数次幂作为除数能够正常工作，但是以 `3` 作为除数则不能。也是同样的原因，在二进制数字系统中，可以保证以 `2` 的整数次幂作为除数时能够正常工作，但 `1/10` 就变成了一个无限循环的二进制小数
>     -   使用二进制数字系统无法 **精确** 存储 *0.1* 或 *0.2*，就像没有办法将三分之一存储为十进制小数一样
>     -   IEEE-754 数字格式通过将数字舍入到最接近的可能数字来解决此问题。这些舍入规则通常不允许我们看到“极小的精度损失”，但是它确实存在
>
> ```js
> alert( 0.1.toFixed(20) ); // 0.10000000000000000555
> ```
>
> -   **解决办法**
>
>     -   toFixed(n)
>
>     ```js
>     let sum = 0.1 + 0.2;
>     alert( sum.toFixed(2) ); // 0.30
>     ```
>
>     -   将数字临时乘以 100（或更大的数字），将其转换为整数，进行数学运算，然后再除回
>
>     ```js
>     console.log(0.1 + 0.2 === 0.3);// false
>     console.log(0.1 + 0.2);// 0.30000000000000004
>         
>     // 二进制浮点数的精度问题
>     console.log(9999999999999999);// 10000000000000000
>         
>     console.log(0) // 0
>     console.log(-0) // -0
>     ```
>
>     -   数字内部表示的另一个有趣结果是存在两个零：`0` 和 `-0`,这是因为在存储时，使用一位来存储符号，因此对于包括零在内的任何数字，可以设置这一位或者不设置,在大多数情况下，这种区别并不明显，因为运算符将它们视为相同的值
>
> ### isFinite和isNaN
>
> -   **特殊的数值**
>
>     -   `Infinity`（和 `-Infinity`）是一个特殊的数值，比任何数值都大（小）。
>     -   `NaN` 代表一个 error
>     -   它们属于 `number` 类型，但不是“普通”数字，因此，这里有用于检查它们的特殊函数
>
> -   `isNaN(value)` 将其参数转换为数字，然后测试它是否为 `NaN`
>
>     -   “NaN” 是独一无二的，它不等于任何东西，包括它自身
>
> ```js
> console.log(isNaN(NaN));// true
> console.log(isNaN("str")); // true
> 
> console.log(isNaN(1)); // false
> 
> console.log(NaN == NaN)// false
> ```
>
> -   `isFinite(value)` 将其参数转换为数字，如果是常规数字而不是 `NaN/Infinity/-Infinity`，则返回 `true`
>
> ```js
> console.log(isFinite("1")); // true
> 
> console.log(isFinite("1a")); // false
> 
> console.log(isFinite(Infinity)); // false
> 
> console.log(isFinite(" ")); // true  
> ```
>
> -   在所有数字函数中，包括 `isFinite`，空字符串或仅有空格的字符串均被视为 `0`
>
> -   **Object.is**方法，类似于 `===` 一样对值进行比较
>
>     -   它适用于 `NaN`：`Object.is(NaN, NaN) === true`
>     -   值 `0` 和 `-0` 是不同的：`Object.is(0, -0) === false`，从技术上讲这是对的，因为在内部，数字的符号位可能会不同，即使其他所有位均为零
>     -   在所有其他情况下，`Object.is(a, b)` 与 `a === b` 相同
>
> ```js
> console.log(Object.is(NaN, NaN)); // true
> console.log(Object.is(Infinity, Infinity)); // true
> console.log(Object.is(-0, -0)); // true
> console.log(Object.is(0, -0)); // false
> console.log(Object.is(0, +0)); // true
> console.log(Object.is(0, 0)); // true
> console.log(Object.is(1, 1)); // true
> console.log(Object.is(1, "1")); // false
> console.log(Object.is("1", "1")); // true
> ```
>
> ### parseInt和parseFloat
>
> -   使用加号 `+` 或 `Number()` 的数字转换是严格的。如果一个值不完全是一个数字，就会失败
>
> ```js
> console.log(+"100px") // NaN
> ```
>
> -   `parseInt` 和 `parseFloat` 的作用
>
>     -   它们可以从字符串中“读取”数字，直到无法读取为止。如果发生 error，则返回收集到的数字。函数 `parseInt` 返回一个整数，而 `parseFloat` 返回一个浮点数
>
> ```js
> alert( parseInt('100px') ); // 100
> alert( parseFloat('12.5em') ); // 12.5
> 
> alert( parseInt('12.3') ); // 12，只有整数部分被返回了
> alert( parseFloat('12.3.4') ); // 12.3，在第二个点出停止了读取
> ```
>
> -   某些情况下，`parseInt/parseFloat` 会返回 `NaN`。当没有数字可读时会发生这种情况
>
> ```js
> alert( parseInt('a123') ); // NaN，第一个符号停止了读取
> ```
>
> -   **parseInt(str,radix)的第二个参数**
>
>     -   `parseInt()` 函数具有可选的第二个参数。它指定了数字系统的基数，因此 `parseInt` 还可以解析十六进制数字、二进制数字等的字符串
>
> ```js
> alert( parseInt('0xff', 16) ); // 255
> alert( parseInt('ff', 16) ); // 255，没有 0x 仍然有效
> 
> alert( parseInt('2n9c', 36) ); // 123456
> ```
>
> ### 其他数学函数
>
> -   JavaScript 有一个内建的 [Math](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Math) 对象，它包含了一个小型的数学函数和常量库
>
> -   **Math.random()**
>
>     -   返回一个从 0 到 1 的随机数（不包括 1）
>
> -   **Math.max(a, b, c...)和Math.min(a, b, c...)**
>
>     -   从任意数量的参数中返回最大值和最小值
>
> ```js
> console.log(Math.max(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)); // 10
> console.log(Math.min(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)); // 1
> ```
>
> -   **Math.pow(n, power)**
>
>     -   返回 `n` 的给定（power）次幂
>
> ```js
> console.log(Math.pow(2, 53)); // 9007199254740992
> ```

## 字符串

> ### 引号
>
> -   单引号
>
> -   双引号
>
> -   反引号
>
>     -   允许字符串跨行
>
> ### 特殊字符
>
> -   换行符写作 `\n`等等
>
> ```js
> let guestList = "Guests:\n * John\n * Pete\n * Mary";
> 
> console.log(guestList); // Guests:
>                         //  * John
>                         //  * Pete
>                         //  * Mary
> ```
>
> ### 字符串长度
>
> -   `length` 属性表示字符串长度
>
> ```js
> // 注意 \n 是一个单独的“特殊”字符，所以长度确实是 3
> console.log("1\n2".length); // 3
> ```
>
> ### 访问字符
>
> -   要获取在 `pos` 位置的一个字符，可以使用方括号 `[pos]` 或者调用 [str.charAt(pos)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/String/charAt) 方法。第一个字符从零位置开始
>
> ```js
> let str = `Hello`;
> 
> // 第一个字符
> alert( str[0] ); // H
> alert( str.charAt(0) ); // H
> 
> // 最后一个字符
> alert( str[str.length - 1] ); // o
> ```
>
> -   `charAt`和`[]`的区别
>
>     -   如果没有找到字符，`[]` 返回 `undefined`，而 `charAt` 返回一个空字符串
>
> ```js
> let str = `Hello`;
> 
> alert( str[1000] ); // undefined
> alert( str.charAt(1000) ); // ''（空字符串）
> ```
>
> -   也可以使用 `for..of` 遍历字符
>
> ```js
> for (let char of "Hello") {
>   alert(char); // H,e,l,l,o（char 变为 "H"，然后是 "e"，然后是 "l" 等）
> }
> ```
>
> ### 字符串是不可变的
>
> -   字符串是不可变的
> -   通常的解决方法是创建一个新的字符串，并将其分配给 `str` 而不是以前的字符串
>
> ```js
> let str = 'Hi';
> 
> str[0] = 'h'; // error
> alert( str[0] ); // 无法运行
> ```
>
> ### 改变大小写
>
> -   [toLowerCase()](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase) 和 [toUpperCase()](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) 方法可以改变大小写
>
> ```js
> alert( 'Interface'.toUpperCase() ); // INTERFACE
> alert( 'Interface'.toLowerCase() ); // interface
> 
> alert( 'Interface'[0].toLowerCase() ); // 'i'
> ```
>
> ### 查找子字符串
>
> -   **str.indexOf(substr,pos)**
>
>     -   它从给定位置 `pos` 开始，在 `str` 中查找 `substr`，如果没有找到，则返回 `-1`，否则返回匹配成功的位置
>     -   可选的第二个参数允许我们从一个给定的位置开始检索
>
> ```js
> let str = 'Widget with id';
> 
> alert( str.indexOf('Widget') ); // 0，因为 'Widget' 一开始就被找到
> alert( str.indexOf('widget') ); // -1，没有找到，检索是大小写敏感的
> 
> alert( str.indexOf("id") ); // 1，"id" 在位置 1 处（……idget 和 id）
> 
> let str = 'Widget with id';
> 
> console.log(str.indexOf('id', 2)); // 12
> ```
>
> -   如果我们对所有存在位置都感兴趣，可以在一个循环中使用 `indexOf`。每一次新的调用都发生在上一匹配位置之后
>
> ```js
> let str = 'As sly as a fox, as strong as an ox';
> 
> let target = 'as'; // 这是我们要查找的目标
> 
> let pos = 0;
> while (true) {
>     let foundPos = str.indexOf(target, pos);
>     if (foundPos === -1) break;
>     console.log(`Found at ${foundPos}`);
>     pos = foundPos + 1; // 继续从下一个位置查找
> }
> 
> // 简写
> let str = 'As sly as a fox, as strong as an ox';
> let target = 'as'; // 这是我们要查找的目标
> let pos = -1;
> while ((pos = str.indexOf(target, pos + 1)) !== -1) {
>     console.log(pos);
> }
> ```
>
> -   **str.lastIndexOf(substr, pos)**
>
>     -   它从字符串的末尾开始搜索到开头
>
> ### 按位Not技巧
>
> -   它将数字转换为 32-bit 整数（如果存在小数部分，则删除小数部分），然后对其二进制表示形式中的所有位均取反
> -   对于 32-bit 整数，`~n` 等于 `-(n+1)`
> -   只有当 `n == -1` 时，`~n` 才为零（适用于任何 32-bit 带符号的整数 `n`）
>
> ```js
> alert( ~2 ); // -3，和 -(2+1) 相同
> alert( ~1 ); // -2，和 -(1+1) 相同
> alert( ~0 ); // -1，和 -(0+1) 相同
> alert( ~-1 ); // 0，和 -(-1+1) 相同
> 
> let str = "Widget";
> 
> if (~str.indexOf("Widget")) {
>   alert( 'Found it!' ); // 正常运行
> }
> ```
>
> ### includes,startsWith,endsWith
>
> -   **str.includes(substr,pos)**
>
>     -   根据 `str` 中是否包含 `substr` 来返回 `true/false`
>     -   `str.includes` 的第二个可选参数是开始搜索的起始位置
>
> ```js
> alert( "Widget with id".includes("Widget") ); // true
> alert( "Hello".includes("Bye") ); // false
> 
> alert( "Widget".includes("id") ); // true
> alert( "Widget".includes("id", 3) ); // false, 从位置 3 开始没有 "id"
> ```
>
> -   方法 [str.startsWith](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith) 和 [str.endsWith](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith) 的功能与其名称所表示的意思相同
>
> ```js
> alert( "Widget".startsWith("Wid") ); // true，"Widget" 以 "Wid" 开始
> alert( "Widget".endsWith("get") ); // true，"Widget" 以 "get" 结束
> ```
>
> ### 获取子字符串
>
> -   JavaScript 中有三种获取字符串的方法：`substring`、`substr` 和 `slice`
>
> -   **str.slice(start [, end])**
>
>     -   返回字符串从 `start` 到（但不包括）`end` 的部分
>     -   如果没有第二个参数，`slice` 会一直运行到字符串末尾
>     -   `start/end` 也有可能是负值
>
> ```js
> let str = "stringify";
> alert( str.slice(0, 5) ); // 'strin'，从 0 到 5 的子字符串（不包括 5）
> alert( str.slice(0, 1) ); // 's'，从 0 到 1，但不包括 1，所以只有在 0 处的字符
> 
> let str = "stringify";
> alert( str.slice(2) ); // 从第二个位置直到结束
> 
> // `start/end` 也有可能是负值
> let str = "stringify";
> 
> // 从右边的第四个位置开始，在右边的第一个位置结束
> alert( str.slice(-4, -1) ); // 'gif'
> ```
>
> -   **str.substring(start [, end])**
>
>     -   返回字符串从 `start` 到（但不包括）`end` 的部分
>     -   与 `slice` 几乎相同，但它允许 `start` 大于 `end`
>     -   不支持负参数（不像 slice），它们被视为 `0`
>
> ```js
> let str = "stringify";
> 
> // 这些对于 substring 是相同的
> alert( str.substring(2, 6) ); // "ring"
> alert( str.substring(6, 2) ); // "ring"
> 
> // ……但对 slice 是不同的：
> alert( str.slice(2, 6) ); // "ring"（一样）
> alert( str.slice(6, 2) ); // ""（空字符串）
> ```
>
> -   **str.substr(start [, length])**
>
>     -   返回字符串从 `start` 开始的给定 `length` 的部分
>     -   与以前的方法相比，这个允许我们指定 `length` 而不是结束位置
>     -   第一个参数可能是负数，从结尾算起
>
> ```js
> let str = "stringify";
> alert( str.substr(2, 4) ); // 'ring'，从位置 2 开始，获取 4 个字符
> 
> let str = "stringify";
> alert( str.substr(-4, 2) ); // 'gi'，从第 4 位获取 2 个字符
> ```
>
> ### 比较字符串
>
> -   **str.codePointAt(pos)**
>
>     -   返回在 `pos` 位置的字符代码
>
> ```js
> // 不同的字母有不同的代码
> alert( "z".codePointAt(0) ); // 122
> alert( "Z".codePointAt(0) ); // 90
> ```
>
> -   **String.fromCodePoint(code)**
>
>     -   通过数字 `code` 创建字符
>     -   用 `\u` 后跟十六进制代码，通过这些代码添加 Unicode 字符
>
> ```js
> alert( String.fromCodePoint(90) ); // Z
> 
> //用 \u 后跟十六进制代码，通过这些代码添加 Unicode 字符
> // 在十六进制系统中 90 为 5a
> alert( '\u005a' ); // Z
> 
> 
> // 代码为 65..220 的字符（拉丁字母和一些额外的字符），方法是创建一个字符串
> let str = '';
> 
> for (let i = 65; i <= 220; i++) {
>   str += String.fromCodePoint(i);
> }
> console.log(str)
> // ABCDEFGHIJKLMNOPQRSTUVWXYZ[]^_`abcdefghijklmnopqrstuvwxyz{|}~
> // ¡¢£¤¥¦§¨©ª«¬­®¯°±²³´µ¶·¸¹º»¼½¾¿ÀÁÂÃÄÅÆÇÈÉÊËÌÍÎÏÐÑÒÓÔÕÖ×ØÙÚÛÜ
> ```
>
> -   **str.localeCompare(str2)**
>
>     -   会根据语言规则返回一个整数，这个整数能指示字符串 `str` 在排序顺序中排在字符串 `str2` 前面、后面、还是相同
>
>         -   如果 `str` 排在 `str2` 前面，则返回负数
>         -   如果 `str` 排在 `str2` 后面，则返回正数
>         -   如果它们在相同位置，则返回 `0`
>
> ```js
> alert( 'Österreich'.localeCompare('Zealand') ); // -1
> ```
>
> ### 其他字符串方法
>
> -   `str.trim()` —— 删除字符串前后的空格 (“trims”)
> -   `str.repeat(n)` —— 重复字符串 `n` 次

## 数组

> ### 介绍
>
> -   **有序集合**，里面的元素都是按顺序排列
>
> ### 创建方式
>
> -   let arr = new Array()
> -   let arr = []
>
> ### 数组的基本操作
>
> -   数组可以存储任何类型的元素
> -   **以逗号结尾**
>
> ```js
> let fruits = ["Apple", "Orange", "Plum"];
> 
> // 获取元素
> alert( fruits[0] ); // Apple
> alert( fruits[1] ); // Orange
> alert( fruits[2] ); // Plum
> 
> // 替换元素
> fruits[2] = 'Pear'; // 现在变成了 ["Apple", "Orange", "Pear"]
> 
> // 向数组新加一个元素
> fruits[3] = 'Lemon'; // 现在变成 ["Apple", "Orange", "Pear", "Lemon"]
> 
> //length 属性的值是数组中元素的总个数
> let fruits = ["Apple", "Orange", "Plum"];
> 
> alert( fruits.length ); // 3
> 
> //alert 可以显示整个数组
> let fruits = ["Apple", "Orange", "Plum"];
> 
> alert( fruits ); // Apple,Orange,Plum
> ```
>
> ### 使用"at"获取最后一个元素
>
> -   **传统方法获取**
>
> ```js
> let fruits = ["Apple", "Orange", "Plum"];
> 
> alert( fruits[fruits.length-1] ); // Plum
> ```
>
> -   **新式方法**
>
> ```js
> let fruits = ["Apple", "Orange", "Plum"];
> 
> // 与 fruits[fruits.length-1] 相同
> alert( fruits.at(-1) ); // Plum
> ```
>
> -   **arr.at(i)**
>
>     -   如果 `i >= 0`，则与 `arr[i]` 完全相同。
>     -   对于 `i` 为负数的情况，它则从数组的尾部向前数
>
> ### pop/push, shift/unshift 方法
>
> -   **队列（queue)** 是最常见的使用数组的方法之一.在计算机科学中，这表示支持两个操作的一个有序元素的集合,先进先出原则
>
>     -   `push` 在末端添加一个元素
>     -   `shift` 取出队列首端的一个元素，整个队列往前移，这样原先排第二的元素现在排在了第一
>
> -   **栈**,后进先出法则
>
>     -   `push` 在末端添加一个元素
>     -   `pop` 从末端取出一个元素
>
> -   `fruits.pop()` 和 `fruits.at(-1)` 都返回数组的最后一个元素，但 `fruits.pop()` 同时也删除了数组的最后一个元素，进而修改了原数组
>
> -   调用 `fruits.push(...)` 与 `fruits[fruits.length] = ...` 是一样的
>
> -   **作用于数组首端的方法**
>
>     -   **shift** 取出数组的第一个元素并返回它
>     -   **unshift** 在数组的首端添加元素
>
> -   `push` 和 `unshift` 方法都可以一次添加多个元素
>
> ```js
> let fruits = ["Apple"];
> 
> fruits.push("Orange", "Peach");
> fruits.unshift("Pineapple", "Lemon");
> 
> // ["Pineapple", "Lemon", "Apple", "Orange", "Peach"]
> alert( fruits );
> ```
>
> ### 总结
>
> -   数组是一种特殊的对象，适用于存储和管理有序的数据项
> -   声明
>
> ```js
> // 方括号 (常见用法)
> let arr = [item1, item2...];
> 
> // new Array (极其少见)
> let arr = new Array(item1, item2...);
> ```
>
> -   调用 `new Array(number)` 会创建一个给定长度的数组，但不含有任何项
>
>     -   `length` 属性是数组的长度，准确地说，它是数组最后一个数字索引值加一。它由数组方法自动调整
>     -   如果我们手动缩短 `length`，那么数组就会被截断
>
> -   获取元素
>
>     -   你可以通过元素的索引获取元素，例如 `arr[0]`
>     -   我们也可以使用允许负索引的 `at(i)` 方法。对于负值的 `i`，它会从数组的末尾往回数。如果 `i >= 0`，它的工作方式与 `arr[i]` 相同
>
> -   可以通过下列操作以双端队列的方式使用数组
>
>     -   `push(...items)` 在末端添加 `items` 项。
>     -   `pop()` 从末端移除并返回该元素。
>     -   `shift()` 从首端移除并返回该元素。
>     -   `unshift(...items)` 从首端添加 `items` 项
>
> -   遍历数组的元素
>
>     -   `for (let i=0; i<arr.length; i++)` — 运行得最快，可兼容旧版本浏览器。
>     -   `for (let item of arr)` — 现代语法，只能访问 items。
>     -   `for (let i in arr)` — 永远不要用这个
>
> -   比较数组时，不要使用 `==` 运算符（当然也不要使用 `>` 和 `<` 等运算符），因为它们不会对数组进行特殊处理。它们通常会像处理任意对象那样处理数组，这通常不是我们想要的

## 数组方法

> ### 添加/移除数组方法
>
> -   `arr.push(...items)` —— 从尾端添加元素，
> -   `arr.pop()` —— 从尾端提取元素，
> -   `arr.shift()` —— 从首端提取元素，
> -   `arr.unshift(...items)` —— 从首端添加元素
>
> ### 删除数组方法
>
> -   `delete arr[index]`
>
> -   `arr.splice(start[, deleteCount, elem1, ..., elemN])`
>
>     -   它从索引 `start` 开始修改 `arr`：删除 `deleteCount` 个元素并在当前位置插入 `elem1, ..., elemN`。最后返回被删除的元素所组成的数组
>     -   允许负向索引
>
> ```js
> let arr = ["I", "study", "JavaScript"];
> 
> arr.splice(1, 1); // 从索引 1 开始删除 1 个元素
> 
> alert( arr ); // ["I", "JavaScript"]
> 
> 
> let arr = ["I", "study", "JavaScript", "right", "now"];
> 
> // 删除数组的前三项，并使用其他内容代替它们
> arr.splice(0, 3, "Let's", "dance");
> 
> alert( arr ) // 现在 ["Let's", "dance", "right", "now"]
> 
> 
> 
> // deleteCount 设置为 0，splice 方法就能够插入元素而不用删除任何元素
> let arr = ["I", "study", "JavaScript"];
> 
> // 从索引 2 开始
> // 删除 0 个元素
> // 然后插入 "complex" 和 "language"
> arr.splice(2, 0, "complex", "language");
> 
> alert( arr ); // "I", "study", "complex", "language", "JavaScript"
> 
> // 在这里和其他数组方法中，负向索引都是被允许的。它们从数组末尾计算位置
> let arr = [1, 2, 5];
> 
> // 从索引 -1（尾端前一位）
> // 删除 0 个元素，
> // 然后插入 3 和 4
> arr.splice(-1, 0, 3, 4);
> 
> alert( arr ); // 1,2,3,4,5
> ```
>
> -   `arr.slice([start], [end])`
>
>     -   它会返回一个新数组，将所有从索引 `start` 到 `end`（不包括 `end`）的数组项复制到一个新的数组。`start` 和 `end` 都可以是负数，在这种情况下，从末尾计算索引
>     -   不带参数地调用它：`arr.slice()` 会创建一个 `arr` 的副本。其通常用于获取副本，以进行不影响原始数组的进一步转换
>
> ```js
> let arr: string[] = ["t", "e", "s", "t"];
> 
> console.log(arr.slice(1, 3)); // e,s（复制从位置 1 到位置 3 的元素）
> 
> console.log(arr.slice(-2)); // s,t（复制从位置 -2 到尾端的元素）
> 
> console.log(arr.slice()) // t,e,s,t（复制整个数组）
> ```
>
> ### concat
>
> -   创建一个新数组，其中包含来自于其他数组和其他项的值
>
> -   **语法**
>
>     -   `arr.concat(arg1, arg2...)`
>
>         -   它接受任意数量的参数 —— 数组或值都可以
>         -   结果是一个包含来自于 `arr`，然后是 `arg1`，`arg2` 的元素的新数组
>         -   如果参数 `argN` 是一个数组，那么其中的所有元素都会被复制。否则，将复制参数本身
>
> ```js
> let arr = [1, 2];
> 
> // 从 arr 和 [3,4] 创建一个新数组
> alert( arr.concat([3, 4]) ); // 1,2,3,4
> 
> // 从 arr、[3,4] 和 [5,6] 创建一个新数组
> alert( arr.concat([3, 4], [5, 6]) ); // 1,2,3,4,5,6
> 
> // 从 arr、[3,4]、5 和 6 创建一个新数组
> alert( arr.concat([3, 4], 5, 6) ); // 1,2,3,4,5,6
> 
> let arr = [1, 2];
> 
> let arrayLike: any = {
>     0: "something",
>     length: 1
> };
> 
> console.log(arr.concat(arrayLike)) // [1, 2, {0: "something", length: 1}]
> 
> //如果类数组对象具有 Symbol.isConcatSpreadable 属性，那么它就会被 concat 当作一个数组来处理：此对象中的元素将被添加
> let arr = [1, 2];
> 
> let arrayLike:any = {
>     0: "something",
>     1: "else",
>     // @ts-ignore
>     [Symbol.isConcatSpreadable]: true,
>     length: 2
> };
> 
> console.log(arr.concat(arrayLike)) // [1, 2, "something", "else"]
> ```
>
> ### 遍历
>
> -   arr.forEach 方法允许为数组的每个元素都运行一个函数
>
> ```js
> arr.forEach(function(item, index, array) {
>   // ... do something with item
> });
> ```
>
> ### 在数组中搜索
>
> -   **indexOf/lastIndexOf和includes**
>
>     -   `arr.indexOf(item, from)` —— 从索引 `from` 开始搜索 `item`，如果找到则返回索引，否则返回 `-1`
>     -   `arr.includes(item, from)` —— 从索引 `from` 开始搜索 `item`，如果找到则返回 `true`（译注：如果没找到，则返回 `false`）
>     -   通常使用这些方法时只会传入一个参数：传入 `item` 开始搜索。默认情况下，搜索是从头开始的
>     -   `arr.lastIndexOf(item,from)`与`arr.indexOf(item, from)`相同，但从右向左查找
>
> ```js
> let arr = [1, 0, false];
> 
> alert( arr.indexOf(0) ); // 1
> alert( arr.indexOf(false) ); // 2
> alert( arr.indexOf(null) ); // -1
> 
> alert( arr.includes(1) ); // true
> 
> let fruits = ['Apple', 'Orange', 'Apple'];
> 
> alert( fruits.indexOf('Apple') ); // 0（第一个 Apple）
> alert( fruits.lastIndexOf('Apple') ); // 2（最后一个 Apple）
> ```
>
> -   **注意事项**
>
>     -   方法includes可以正确的处理`NaN`
>
> ```js
> const arr = [NaN];
> alert( arr.indexOf(NaN) ); // -1（错，应该为 0）
> alert( arr.includes(NaN) );// true（正确）
> ```
>
> ### find和findIndex/findLastIndex
>
> **find**
>
> - 对象数组中找到具有特定条件的对象
> - 依次对数组中的每个元素调用该函数
>   - `item` 是元素
>   - `index` 是它的索引
>   - `array` 是数组本身
> - 如果它返回 `true`，则搜索停止，并返回 `item`。如果没有搜索到，则返回 `undefined`
> - `arr.findIndex`方法（与 `arr.find`）具有相同的语法，但它返回找到的元素的索引，而不是元素本身。如果没找到，则返回 `-1`
> - `arr.findLastIndex`方法类似于 `findIndex`，但从右向左搜索，类似于 `lastIndexOf`
>
> ```js
> let result = arr.find(function(item, index, array) {
>   // 如果返回 true，则返回 item 并停止迭代
>   // 对于假值（falsy）的情况，则返回 undefined
> });
> 
> let users = [
>   {id: 1, name: "John"},
>   {id: 2, name: "Pete"},
>   {id: 3, name: "Mary"}
> ];
> 
> let user = users.find(item => item.id == 1);
> 
> alert(user.name); // John
> 
> let users = [
>   {id: 1, name: "John"},
>   {id: 2, name: "Pete"},
>   {id: 3, name: "Mary"},
>   {id: 4, name: "John"}
> ];
> 
> // 寻找第一个 John 的索引
> alert(users.findIndex(user => user.name == 'John')); // 0
> 
> // 寻找最后一个 John 的索引
> alert(users.findLastIndex(user => user.name == 'John')); // 3
> ```
>
> **filter**
>
> - `find` 方法搜索的是使函数返回 `true` 的第一个（单个）元素,如果需要匹配的有很多，我们可以使用**arr.filter(fn)**
> - 语法与 `find` 大致相同，但是 `filter` 返回的是所有匹配元素组成的数组
>
> ```js
> let results = arr.filter(function(item, index, array) {
>   // 如果 true item 被 push 到 results，迭代继续
>   // 如果什么都没找到，则返回空数组
> });
> 
> 
> let users = [
>   {id: 1, name: "John"},
>   {id: 2, name: "Pete"},
>   {id: 3, name: "Mary"}
> ];
> 
> // 返回前两个用户的数组
> let someUsers = users.filter(item => item.id < 3);
> 
> alert(someUsers.length); // 2
> ```
>
> ### 转换数组
>
> **map**
>
> - 它对数组的每个元素都调用函数，并返回结果数组
> - **语法**
>
> ```js
> let result = arr.map(function(item, index, array) {
>   // 返回新值而不是当前元素
> })
> 
> // 在这里我们将每个元素转换为它的字符串长度
> let lengths = ["Bilbo", "Gandalf", "Nazgul"].map(item => item.length);
> 
> console.log(lengths); // [5,7,6]
> ```
>
> **sort**
>
> - 对数组进行 **原位（in-place）** 排序，更改元素的顺序。(译注：原位是指在此数组内，而非生成一个新数组。)
> - 它还返回排序后的数组，但是返回值通常会被忽略，因为修改了 `arr` 本身
> - **语法**
>
> ```js
> let arr = [ 1, 2, 15 ];
> 
> // 该方法重新排列 arr 的内容
> arr.sort();
> 
> alert( arr );  // 1, 15, 2
> ```
>
> - **这些元素默认情况下被按字符串进行排序**,如果需要按照自己的顺序排序,需要提供一个函数`arr.sort()`的参数
>
> ```js
> // 该函数应该比较两个任意值并返回
> function compare(a, b) {
>   if (a > b) return 1; // 如果第一个值比第二个值大
>   if (a == b) return 0; // 如果两个值相等
>   if (a < b) return -1; // 如果第一个值比第二个值小
> }
> 
> // 按数字进行排序
> function compareNumeric(a, b) {
>   if (a > b) return 1;
>   if (a == b) return 0;
>   if (a < b) return -1;
> }
> 
> let arr = [ 1, 2, 15 ];
> 
> arr.sort(compareNumeric);
> 
> alert(arr);  // 1, 2, 15
> ```
>
> - **比较函数可以返回任何数字**
>   - 实际上，比较函数只需要返回一个正数表示“大于”，一个负数表示“小于”。
>
> ```js
> let arr = [ 1, 2, 15 ];
> 
> arr.sort(function(a, b) { return a - b; });
> 
> alert(arr);  // 1, 2, 15
> ```
>
> - 如果很多字母进行比较,使用`str.localeCompare`进行字母的排序
>
> ```js
> let countries = ['Österreich', 'Andorra', 'Vietnam'];
> 
> console.log(countries.sort((a, b) => a > b ? 1 : -1)); // Andorra, Vietnam, Österreich（错的）
> 
> console.log(countries.sort((a, b) => a.localeCompare(b))); // Andorra,Österreich,Vietnam（对的！）
> ```
>
> **reverse**
>
> - 用于颠倒 `arr` 中元素的顺序
> - 返回颠倒后的数组 `arr`
>
> ```js
> let arr = [1, 2, 3, 4, 5];
> arr.reverse();
> 
> alert( arr ); // 5,4,3,2,1
> ```
>
> **split**
>
> - split用于对字符串进行分割
> - split第二个参数是可选择,表示数组长度的限制
>
> ```js
> let names = 'Bilbo, Gandalf, Nazgul';
> 
> let arr = names.split(', ');
> 
> for (let name of arr) {
>   alert( `A message to ${name}.` ); // A message to Bilbo（和其他名字）
> }
> 
> let arr = 'Bilbo, Gandalf, Nazgul, Saruman'.split(', ', 2);
> 
> alert(arr); // Bilbo, Gandalf
> 
> // 如果将一个字符,拆分成每个字符
> let str = "test";
> 
> alert( str.split('') ); // t,e,s,t
> ```
>
> **join**
>
> - 与 `split` 相反。它会在它们之间创建一串由 `glue` 粘合的 `arr` 项
>
> ```js
> let arr = ['Bilbo', 'Gandalf', 'Nazgul'];
> 
> let str = arr.join(';'); // 使用分号 ; 将数组粘合成字符串
> 
> let str1 = arr.join(""); // 使用空字符串将数组粘合成字符串
> 
> console.log(str); // Bilbo;Gandalf;Nazgul
> console.log(str1) // BilboGandalfNazgul
> ```
>
> **reduce**
>
> - 语法
>   - 该函数一个接一个地应用于所有数组元素，并将其结果“搬运（carry on）”到下一个调用
>     - `accumulator` —— 是上一个函数调用的结果，第一次等于 `initial`（如果提供了 `initial` 的话）
>     - `item` —— 当前的数组元素
>     - `index` —— 当前索引
>     - `arr` —— 数组本身
>
> ```js
> let value = arr.reduce(function(accumulator, item, index, array) {
>   // ...
> }, [initial]);
> ```
>
> - 应用函数时，上一个函数调用的结果将作为第一个参数传递给下一个函数
> - 第一个参数本质上是累加器，用于存储所有先前执行的组合结果。最后，它成为 `reduce` 的结果
>
> ```js
> let arr = [1, 2, 3, 4, 5];
> 
> let result = arr.reduce((sum, current) => sum + current, 0);
> 
> alert(result); // 15
> ```
>
> - **执行过程**
>   - 在第一次运行时，`sum` 的值为初始值 `initial`（`reduce` 的最后一个参数），等于 0，`current` 是第一个数组元素，等于 `1`。所以函数运行的结果是 `1`。
>   - 在第二次运行时，`sum = 1`，我们将第二个数组元素（`2`）与其相加并返回。
>   - 在第三次运行中，`sum = 3`，我们继续把下一个元素与其相加，以此类推……
>
> ![](https://zh.javascript.info/article/array-methods/reduce.svg)
>
> ```js
> let arr = [1, 2, 3, 4, 5];
> 
> // 删除 reduce 的初始值（没有 0）
> let result = arr.reduce((sum, current) => sum + current);
> 
> alert( result ); // 15
> ```
>
> - **注意事项**
>   - 如果没有初始值，那么 `reduce` 会将数组的第一个元素作为初始值，并从第二个元素开始迭代,计算表与上面相同，只是去掉第一行,但是这种使用需要非常小心。如果数组为空，那么在没有初始值的情况下调用 `reduce` 会导致错误
>   - 建议始终指定初始值
>
> ```js
> let arr = [];
> 
> // Error: Reduce of empty array with no initial value
> // 如果初始值存在，则 reduce 将为空 arr 返回它（即这个初始值）。
> arr.reduce((sum, current) => sum + current);
> ```
>
> - `arr.reduceRight`和`arr.reduce`方法的功能一样,只是遍历为从右到左
>
> **Array.isArray(value)**
>
> - 如果 `value` 是一个数组，则返回 `true`；否则返回 `false`
>
> ### 大多数方法都支持"thisArg"
>
> ```js
> arr.find(func, thisArg);
> arr.filter(func, thisArg);
> arr.map(func, thisArg);
> // ...
> // thisArg 是可选的最后一个参数
> ```
>
> - `thisArg` 参数的值在 `func` 中变为 `this`
>
> ```js
> // 在这里我们使用 army 对象方法作为过滤器，thisArg 用于传递上下文（passes the context）
> let army = {
>     minAge: 18,
>     maxAge: 27,
>     canJoin(user) {
>         return user.age >= this.minAge && user.age < this.maxAge;
>     }
> };
> 
> let users = [
>     {age: 16},
>     {age: 20},
>     {age: 23},
>     {age: 30}
> ];
> 
> // 找到 army.canJoin 返回 true 的 user
> let soldiers = users.filter(army.canJoin, army);
> 
> console.log(soldiers)
> console.log(soldiers.length); // 2
> console.log(soldiers[0].age); // 20
> ```
>
> - 如果在上面的示例中我们使用了 `users.filter(army.canJoin)`，那么 `army.canJoin` 将被作为独立函数调用，并且这时 `this=undefined`，从而会导致即时错误
> - 可以用 `users.filter(user => army.canJoin(user))` 替换对 `users.filter(army.canJoin, army)` 的调用
>
> ### 总结
>
> - 添加/删除元素：
>   - `push(...items)` —— 向尾端添加元素，
>   - `pop()` —— 从尾端提取一个元素，
>   - `shift()` —— 从首端提取一个元素，
>   - `unshift(...items)` —— 向首端添加元素，
>   - `splice(pos, deleteCount, ...items)` —— 从 `pos` 开始删除 `deleteCount` 个元素，并插入 `items`。
>   - `slice(start, end)` —— 创建一个新数组，将从索引 `start` 到索引 `end`（但不包括 `end`）的元素复制进去。
>   - `concat(...items)` —— 返回一个新数组：复制当前数组的所有元素，并向其中添加 `items`。如果 `items` 中的任意一项是一个数组，那么就取其元素
> - 搜索元素：
>   - `indexOf/lastIndexOf(item, pos)` —— 从索引 `pos` 开始搜索 `item`，搜索到则返回该项的索引，否则返回 `-1`。
>   - `includes(value)` —— 如果数组有 `value`，则返回 `true`，否则返回 `false`。
>   - `find/filter(func)` —— 通过 `func` 过滤元素，返回使 `func` 返回 `true` 的第一个值/所有值。
>   - `findIndex` 和 `find` 类似，但返回索引而不是值。
> - 遍历元素：
>   - `forEach(func)` —— 对每个元素都调用 `func`，不返回任何内容
> - 转换数组：
>   - `map(func)` —— 根据对每个元素调用 `func` 的结果创建一个新数组。
>   - `sort(func)` —— 对数组进行原位（in-place）排序，然后返回它。
>   - `reverse()` —— 原位（in-place）反转数组，然后返回它。
>   - `split/join` —— 将字符串转换为数组并返回。
>   - `reduce/reduceRight(func, initial)` —— 通过对每个元素调用 `func` 计算数组上的单个值，并在调用之间传递中间结果。
> - 其他：
>   - `Array.isArray(value)` 检查 `value` 是否是一个数组，如果是则返回 `true`，否则返回 `false`
> - 检查数组(如果任何/所有结果为 `true`，则返回 `true`，否则返回 `false`)
>   - `some(func)`
>     - 如果 `fn` 返回一个真值，`arr.some()` 立即返回 `true` 并停止迭代其余数组项	
>   - `every(func)`
>     - 如果 `fn` 返回一个假值，`arr.every()` 立即返回 `false` 并停止对其余数组项的迭代
>
> ```js
> function arraysEqual(arr1, arr2) {
>     return arr1.length === arr2.length && arr1.every((value, index) => value === arr2[index]);
> }
> 
> console.log(arraysEqual([1, 2], [1, 2])); // true
> ```
>
> - `fill(value,start,end)`
>   - 从索引 `start` 到 `end`，用重复的 `value` 填充数组
> - `copyWithin(target,start,end)`
>   - 将从位置 `start` 到 `end` 的所有元素复制到 **自身** 的 `target` 位置（覆盖现有元素）
> - `flat(depth)/flatMap(func)`
>   - 从多维数组创建一个新的扁平数组
> - `of(element0[,element1,[,...[,elementN]]])`
>   - 基于可变数量的参数创建一个新的 `Array` 实例，而不需要考虑参数的数量或类型
>
> ### 注意事项
>
> - `sort`，`reverse` 和 `splice` 方法修改的是数组本身

## Iterable object(可迭代对象)

> 
