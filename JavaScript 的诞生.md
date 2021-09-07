# JavaScript 的诞生
1994 年，网景公司（Netscape）发布了 Navigator 浏览器0.9版。这是历史上第一个比较成熟的网络浏览器，轰动一时。但是，这个版本的浏览器只能用来浏览，不具备与访问者互动的能力。网景公司急需一种网页脚本语言，使得浏览器可以与网页互动。

当时的形势就是，网景公司的整个管理层，都是 Java 语言的信徒，Sun 公司完全介入网页脚本语言的决策。

此时，34 岁的系统程序员 Brendan Eich 登场了。1995 年 4 月，网景公司录用了他。

Brendan Eich 的主要方向和兴趣是函数式编程，网景公司招聘他的目的，是研究将 Scheme 语言作为网页脚本语言的可能性。Brendan Eich 本人也是这样想的，以为进入新公司后，会主要与 Scheme 语言打交道。

仅仅一个月之后，1995年5月，网景公司做出决策，未来的网页脚本语言必须"看上去与 Java 足够相似"，但是比 Java 简单，使得非专业的网页作者也能很快上手。这个决策实际上将 Perl、Python、Tcl、Scheme 等非面向对象编程的语言都排除在外了。

Brendan Eich 被指定为这种"简化版Java语言"的设计师。

但是，他对 Java 一点兴趣也没有。为了应付公司安排的任务，他只用 10 天时间就把 Javascript 设计出来了。

# JavaScript 的历史
JavaScript 发明之后微软进行跟进发明了 JScript，而网景公司进行反击，将 JavaScript 向 ECMA 提交标准，制定了 ECMAScript。

微软公司由于在 Windows 系统中捆绑了 IE 浏览器，导致网景公司的浏览器份额大幅下跌最后被收购。

临死之前网景公司将 FireFox 开源试图最后一搏，结果失败。

Brendan 一直协助维护 FireFox。

2001 年，IE 6 伴随 XP 系统发布。2004 年 IE 6 占领全球浏览器份额 80% 以上。而浏览器并不兼容 W3C 标准，同时持续不断的爆出各种 bug。由于 XP 系统实在过于火爆，导致 IE 6 无任何竞争对手，微软甚至解散了浏览器的大部分员工，只留下几个人象征性地维护顺便修补一下 bug。

尤其在国内，由于盗版 XP 系统的风行，导致国内开发者兼容 IE 6 苦不堪言，直到 Chrome 的登场。

由于微软对浏览器市场现状的满足和懈怠，Google 抓住这次机会，雇佣了大量 Firefox 和原 IE 员工，开始开发 Chrome。

2008 年 Chrome 发布
2011 年市场份额超过 Firefox
2016 年全球市场份额 62%
Chrome 浏览器与 IE 相比打开页面速度极快，同时对 W3C 和 ECMA 等标准积极跟进，甚至引领标准，受到大量开发者的支持。

2010 年 iPhone4 发布。2011 微软与 Nokia 合作，结局大家都知道了。也正因如此，微软在移动互联网几乎是缺席的。这导致有着大量市场的移动端应用不再需要兼容 IE，这对开发者简直是重大利好。

JavaScript 的兴起
Chrome 浏览器的崛起和移动互联网的兴起，导致前端行业蓬勃发展，而 JavaScript 作为被命运选中的孩子，也焕发新生。

萌芽-Gmail
2004 年愚人节 Gmail 发布，ajax 作为新概念被大家所认知。人们开始意识到网页上居然可以运行类似应用的东西。

爆发-Chrome
Chrome 的 V8 引擎极大的提升了 JS 代码的运行效率。直接导致了 Node.js / npm 等基础的出生，前端工程化成为可能。之后 Express 出现，JS 开发者可以开始愉快进行后端开发。再之后大量新技术蓬勃发展。

结论
JS 是历史的选择，曾经浏览器支持很多语言，Java/Flash/VB，但只有 JavaScript 活下来了

# 设计缺陷
1. 不适合开发大型程序

Javascript没有名称空间（namespace），很难模块化；没有如何将代码分布在多个文件的规范；允许同名函数的重复定义，后面的定义可以覆盖前面的定义，很不利于模块化加载。

2. 非常小的标准库

Javascript提供的标准函数库非常小，只能完成一些基本操作，很多功能都不具备。

3. null和undefined

null属于对象（object）的一种，意思是该对象为空；undefined则是一种数据类型，表示未定义。
```
　　typeof null; // object

　　typeof undefined; // undefined
```
两者非常容易混淆，但是含义完全不同。
```
　　var foo;

　　alert(foo == null); // true

　　alert(foo == undefined); // true

　　alert(foo === null); // false

　　alert(foo === undefined); // true
  ```

在编程实践中，null几乎没用，根本不应该设计它。

4. 全局变量难以控制

Javascript的全局变量，在所有模块中都是可见的；任何一个函数内部都可以生成全局变量，这大大加剧了程序的复杂性。

5. 自动插入行尾分号

Javascript的所有语句，都必须以分号结尾。但是，如果你忘记加分号，解释器并不报错，而是为你自动加上分号。有时候，这会导致一些难以发现的错误。

比如，下面这个函数根本无法达到预期的结果，返回值不是一个对象，而是undefined。
```
　　function(){

　　　　return
　　　　　　{
　　　　　　　　i=1
　　　　　　};

　　}
```
原因是解释器自动在return语句后面加上了分号。
```
　　function(){

　　　　return;
　　　　　　{
　　　　　　　　i=1
　　　　　　};

　　}
```
6. 加号运算符

+号作为运算符，有两个含义，可以表示数字与数字的和，也可以表示字符与字符的连接。
```
　　alert(1+10); // 11

　　alert("1"+"10"); // 110

如果一个操作项是字符，另一个操作项是数字，则数字自动转化为字符。

　　alert(1+"10"); // 110

　　alert("10"+1); // 101
```
这样的设计，不必要地加剧了运算的复杂性，完全可以另行设置一个字符连接的运算符。

7. NaN

NaN是一种数字，表示超出了解释器的极限。它有一些很奇怪的特性：
```
　　NaN === NaN; //false

　　NaN !== NaN; //true

　　alert( 1 + NaN ); // NaN
```
与其设计NaN，不如解释器直接报错，反而有利于简化程序。

8. 数组和对象的区分

由于Javascript的数组也属于对象（object），所以要区分一个对象到底是不是数组，相当麻烦。Douglas Crockford的代码是这样的：
```
　　if ( arr &&
　　　　typeof arr === 'object' &&
　　　　typeof arr.length === 'number' &&
　　　　!arr.propertyIsEnumerable('length')){

　　　　alert("arr is an array");

　　}
```
9. == 和 ===

==用来判断两个值是否相等。当两个值类型不同时，会发生自动转换，得到的结果非常不符合直觉。
```
　　"" == "0" // false

　　0 == "" // true

　　0 == "0" // true

　　false == "false" // false

　　false == "0" // true

　　false == undefined // false

　　false == null // false

　　null == undefined // true

　　" \t\r\n" == 0 // true
```
因此，推荐任何时候都使用"==="（精确判断）比较符。

10. 基本类型的包装对象

Javascript有三种基本数据类型：字符串、数字和布尔值。它们都有相应的建构函数，可以生成字符串对象、数字对象和布尔值对象。

与基本数据类型对应的对象类型，作用很小，造成的混淆却很大。

