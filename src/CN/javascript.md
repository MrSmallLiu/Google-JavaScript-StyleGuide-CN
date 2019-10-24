
- [1. 引言](#1-引言)
  - [1.1 术语说明](#11-术语说明)
  - [1.2 指南说明](#12-指南说明)
- [2. 源文件](#2-源文件)
  - [2.1 文件名](#21-文件名)
  - [2.2 文件编码：UTF-8](#22-文件编码utf-8)
  - [2.3 特殊字符](#23-特殊字符)
    - [2.3.1 空格字符](#231-空格字符)
    - [2.3.2 特殊转义序列](#232-特殊转义序列)
    - [2.3.3 非ASCII码字符](#233-非ascii码字符)
- [3. 文件结构](#3-文件结构)
- [4. 格式](#4-格式)
- [5. 语言功能](#5-语言功能)
  - [5.1 局部变量声明](#51-局部变量声明)
    - [5.1.1 使用`const`和`let`](#511-使用const和let)
    - [5.1.2 每次声明一个变量](#512-每次声明一个变量)
    - [5.1.3 在需要时进行声明，并尽快初始化](#513-在需要时进行声明并尽快初始化)
    - [5.1.4 根据需要声明类型](#514-根据需要声明类型)
  - [5.2 数组字面量](#52-数组字面量)
    - [5.2.1 使用结尾逗号](#521-使用结尾逗号)
    - [5.2.2 不要使用可变参数的Array构造函数](#522-不要使用可变参数的array构造函数)
    - [5.2.3 非数值属性](#523-非数值属性)
    - [5.2.4 解构](#524-解构)
    - [5.2.5 展开运算符](#525-展开运算符)
  - [5.3 对象字面量](#53-对象字面量)
    - [5.3.1 使用结尾逗号](#531-使用结尾逗号)
    - [5.3.2 不使用`Object`构造函数](#532-不使用object构造函数)
    - [5.3.3 请勿混合使用带引号与不带引号的键值](#533-请勿混合使用带引号与不带引号的键值)
    - [5.3.4 计算属性名称](#534-计算属性名称)
    - [5.3.5 方法简写](#535-方法简写)
    - [5.3.6 简写属性](#536-简写属性)
    - [5.3.7 解构](#537-解构)
    - [5.3.8 枚举](#538-枚举)
  - [5.4 类](#54-类)
    - [5.4.1 构造函数（翻译疑问）](#541-构造函数翻译疑问)
    - [5.4.2 字段](#542-字段)
    - [5.4.3 计算属性](#543-计算属性)
- [6. 命名](#6-命名)
  - [6.1 所有标识符通用的规则](#61-所有标识符通用的规则)
  - [6.2 按标识符类型划分的规则](#62-按标识符类型划分的规则)
    - [6.2.1 包名](#621-包名)
    - [6.2.2 类名](#622-类名)
    - [6.2.3 方法名](#623-方法名)
    - [6.2.4 枚举名称](#624-枚举名称)
    - [6.2.5 常量名称](#625-常量名称)
      - [6.2.5.1 “常量”的定义](#6251-常量的定义)
      - [6.2.5.2本地别名](#6252本地别名)
    - [6.2.6 非常量字段名称](#626-非常量字段名称)
    - [6.2.7 参数名称](#627-参数名称)
    - [6.2.8 局部变量名称](#628-局部变量名称)
    - [6.2.9 模板参数名称](#629-模板参数名称)
    - [6.2.10 本地模块（Module-local）名称](#6210-本地模块module-local名称)
  - [6.3 驼峰式：定义](#63-驼峰式定义)
- [7. JSDoc](#7-jsdoc)
- [8. 规则](#8-规则)
- [9. 附录](#9-附录)
# 1. 引言
> 本文档是Google的JavaScript语言源码标准的完整定义，当且仅当JavaScript源文件遵循此规则时，它才被描述为Google风格。
## 1.1 术语说明
> 在文档中，除非另有说明：
> 1. 术语“注释”始终指“实施注释”。我们不使用短语“文档注释”，而是使用通用术语“JSDoc”来表示其中的人类可读文本和机器可读文本 /** … */。
> 2. 本样式指南在使用短语“必须”，“不能”，“应该”，“不应该”和“可能”时使用[RFC 2119](https://tools.ietf.org/html/rfc2119)术语。术语“首选”和“避免”分别对应于“应该”和“不应该”。强制性和陈述性陈述是规定性的，与“必须”陈述相符。  
> 其他术语说明会出现在文档中。
## 1.2 指南说明
> 本文档中的示例代码是**非规范性**的。也就是说，尽管这些示例采用的是Google样式，但它们可能并不能说明表示代码的唯一时尚方式。在示例中做出的可选格式选择不得作为规则执行。
# 2. 源文件
## 2.1 文件名
> 文件名必须全部小写，并且可以包含下划线（_）或破折号（-），但不能包含其他标点符号。请遵循项目使用的约定。文件名的扩展名必须为.js。
## 2.2 文件编码：UTF-8
> 源文件以UTF-8编码。
## 2.3 特殊字符
### 2.3.1 空格字符
> 除了行终止符序列之外，ASCII水平空格字符（0x20）是唯一出现在源文件中任何地方的空格字符。这意味着
> 1. 字符串文字中的所有其他空白字符均被转义
> 2. 制表符不用于缩进。
### 2.3.2 特殊转义序列
### 2.3.3 非ASCII码字符
# 3. 文件结构
# 4. 格式
# 5. 语言功能
> JavaScript包含许多可疑(甚至危险)的功能。本节描述了哪些功能可以使用，哪些功能可以不使用，以及使用这些功能的其他限制。
## 5.1 局部变量声明
### 5.1.1 使用`const`和`let`
> 用`const`或`let`声明所有局部变量。默认情况下使用const，除非需要重新为变量赋值。不得使用`var`关键字。
### 5.1.2 每次声明一个变量
> 每次局部变量声明仅声明一个变量：`let a = 1, b = 2;`不使用类似的声明。
### 5.1.3 在需要时进行声明，并尽快初始化
> 局部变量不是习惯性的定义在块或类似块结构的开头，而是定义再接近他们第一次使用的地方，以最大程度的减小其作用域范围。
### 5.1.4 根据需要声明类型
> JSDoc允许类型注释在变量声明行的上方，如果没有其它JSDoc也可以在行内注释。
> 示例：   
```javascript
const / **！Array <number> * / data = [];
/ **
 *一些描述。
 * @type {！Array <number>}
 * /
const data = [];
```
> 不允许使用混合使用行内注释，编译器仅处理第一个JSDoc，并且行内注释将丢失。
```javascript
/ **一些描述。* /
const / **！Array <number> * / data = [];
```
> 提示：在许多情况下编译器可以推断模板化类型，但是不能推断参数的类型。尤其是调用不包含任何值的模板参数类型来初始化文字或者构造函数以及在闭包中修改变量时编译器不能推断参数的类型（例如空数组、对象、Map或者Set）。在这些情况下局部变量类型注释特别有用，因为编译器会将模板参数推断为未知。
## 5.2 数组字面量
### 5.2.1 使用结尾逗号
> 只要最后一个元素和右括号之间换行了，那么就要在末尾加上逗号。
> 示例：
```javascript
const values = [
  'first value',
  'second value',
];
```
### 5.2.2 不要使用可变参数的Array构造函数
> 如果添加或者删除参数这个构造函数很容易出错。用显示声明代替。
> 不允许：
```javascript
const a1 = new Array(x1, x2, x3);
const a2 = new Array(x1, x2);
const a3 = new Array(x1);
const a4 = new Array();
```
> 除了第三种情况外其余的可以按照预期工作：如果`x1`是一个整数，那么`a3`将是一个长度为`x1`的数组，并且里面的元素都是`undefined`。如果`x1`是一个其它数字，那么将引发异常，并且如果它是其它值那么将是一个单值数组。
   
> 作者添加示例：
```javascript
const a1 = new Array(2) //长度为2的空数组
const a2 = new Array(-2) //错误异常 RangeError: Invalid array length
const a3 = new Array('2') // ['2']
```
> 正确写法：
```javascript
const a1 = [x1，x2，x3];
const a2 = [x1，x2];
const a3 = [x1];
const a4 = [];
```
在适当的情况下允许使用`new Array(length)`来给一个数组分配明确的长度。
### 5.2.3 非数值属性
> 不要给数组定义或者使用非数字属性（`length`除外）。使用`Map`（或者`Object`）代替。
### 5.2.4 解构
> 数组字面量可以在分配的左边来执行解构（例如从单个Array或者Iterable中解压多个值）。可以在最后包含一个“rest”元素（...与变量名之前没有空格）。如果元素未使用应该省略。
```javascript
const [a, b, c, ...rest] = generateResults();
let [, b,, d] = someArray;
```
> 解构也可以用于函数参数（注意参数名是必需的但是会被忽略）。如果数组解构参数是可选的那么就要使用`[]`作为默认值，并且在左侧提供默认值。
```javascript
/** @param {!Array<number>=} param1 */
function optionalDestructuring([a = 4, b = 2] = []) { … };
```
> 不允许：
```javascript
function badDestructuring([a, b] = [4, 2]) { … };
```
> 提示：在可能的情况下，对于打包（解压）多个值作为函数的参数或者函数返回值时应该使用对象解构而不是数组解构，因为对象解构可以提供元素名称以及为每一个元素指定不同的类型。
### 5.2.5 展开运算符
> 数组字面量可以使用展开运算符(`...`)来将一个或多个可遍历对象中的元素展开。应该使用展开运算符而不是使用更笨拙的构造函数`Array.prototype`。`...`之后没有空格。
> 示例：
```javascript
[...foo]   // preferred over Array.prototype.slice.call(foo)
[...foo, ...bar]   // preferred over foo.concat(bar)
```
## 5.3 对象字面量
### 5.3.1 使用结尾逗号
> 最后属性与右括号之间如果有换行需要添加逗号。
### 5.3.2 不使用`Object`构造函数
> 尽管`Object`没有与`Array`同样的问题，但是出于一致性的考虑仍然不允许这样做。请使用对象字面量代替（`{}`或者`{a: 0, b:1, c:2}`）。
### 5.3.3 请勿混合使用带引号与不带引号的键值
> 对象字面量可以表示结构（不带引号的键值和/或symbols）或者字典（带有引号的键值和/或计算键值）。在单个对象字面量中不要将这些建混合使用
> 不允许：
```javascript
{
  width: 42, // struct-style unquoted key
  'maxWidth': 43, // dict-style quoted key
}
```
> 这还将扩展到将属性传递给函数，例如`hasOwnProperty`。特别是这样做之后会破坏编译后的代码，因为编译器不能重命名/混淆字符串字面量。
> 不允许：
```javascript
/** @type {{width: number, maxWidth: (number|undefined)}} */
const o = {width: 42};
if (o.hasOwnProperty('maxWidth')) {
  ...
}
```
> 最好的实现方式：
```javascript
/** @type {{width: number, maxWidth: (number|undefined)}} */
const o = {width: 42};
if (o.maxWidth != null) {
  ...
}
```
### 5.3.4 计算属性名称
> 除非计算属性是`symbol`（例如`[Symbol.iterator]`），要不然是允许使用计算属性名称的（例如`{['key'+foo()]:42}`），并且将其视作字典样式（带引号）的键（即不得与不带引号的键混用）。枚举值也可以当作计算属性键，但是不应该与非枚举键混用。
### 5.3.5 方法简写
> 在对象中可以用方法简写代替冒号（`{method(){...}}`）来定义方法，在后面紧跟一个函数或者箭头函数。
> 示例：
```javascript
return {
  stuff: 'candy',
  method() {
    return this.stuff;  // Returns 'candy'
  },
};
```
> 请注意，`this`在方法或者方法简写中指向对象本身，而`this`在箭头函数中指向对象之外的范围。
> 示例：
```javascript
class {
  getObjectLiteral() {
    this.stuff = 'fruit';
    return {
      stuff: 'candy',
      method: () => this.stuff,  // Returns 'fruit'
    };
  }
}
```
### 5.3.6 简写属性
> 在对象中允许简写属性。
> 示例：
```javascript
const foo = 1;
const bar = 2;
const obj = {
  foo,
  bar,
  method() { return this.foo + this.bar; },
};
assertEquals(3, obj.method());
```
### 5.3.7 解构
> 对象允许在赋值表达式左侧使用对象解构，以此执行解构并且从单对象中提取多个值。
> 对象解构也可以用在函数参数上，但是应该尽量的保持简单：单个的不带引号的速记属性。参数解构中不能使用深层的嵌套和计算属性。在解构参数的左侧指定默认值(`{str = 'some default'} = {}`,而不是`{str} = {str: 'some default'}`)，并且如果解构对象本身是可选的，那么它的默认值必须是`{}`。JSDoc可以给解构参数指定任意的名字（该名称虽然未使用，但是编译器必须需要）。
> 示例：
```javascript
/**
 * @param {string} ordinary
 * @param {{num: (number|undefined), str: (string|undefined)}=} param1
 *     num: The number of times to do something.
 *     str: A string to do stuff to.
 */
function destructured(ordinary, {num, str = 'some default'} = {})
```
> 不允许：
```javascript
/** @param {{x: {num: (number|undefined), str: (string|undefined)}}} param1 */
function nestedTooDeeply({x: {num, str}}) {};
/** @param {{num: (number|undefined), str: (string|undefined)}=} param1 */
function nonShorthandProperty({num: a, str: b} = {}) {};
/** @param {{a: number, b: number}} param1 */
function computedKey({a, b, [a + b]: c}) {};
/** @param {{a: number, b: string}=} param1 */
function nontrivialDefault({a, b} = {a: 2, b: 4}) {};
```
> 解构也可以用于`goog.require`语句，在这种情况下，不得将其包装起来：无论输入语句多长只能占据一行()
### 5.3.8 枚举
> 枚举是通过将`@enum`注释添加到对象中来定义的。枚举被定义后不能再添加属性。枚举必须是常量，并且所有枚举值必须是不可变的。
```javascript
/**
 * Supported temperature scales.
 * @enum {string}
 */
const TemperatureScale = {
  CELSIUS: 'celsius',
  FAHRENHEIT: 'fahrenheit',
};

/**
 * An enum with two options.
 * @enum {number}
 */
const Option = {
  /** The option used shall have been the first. */
  FIRST_OPTION: 1,
  /** The second among two options. */
  SECOND_OPTION: 2,
};
```
## 5.4 类
### 5.4.1 构造函数（翻译疑问）
> 构造函数是可选的。子类在设置任何字段或者其它的访问`this`之前必须调用`super()`。接口在构造函数中应该声明为非函数属性。
### 5.4.2 字段
> 所有的具体的对象字段在构造函数中设置(即方法以外的所有属性)。用`@const`注释字段不能重新赋值(这些字段没有必要是深层次固定的)。用适当的可视的注释说明来注释非公共字段(`@private, @protected, @package`)，并且所有的`@private`字段的名字需要以下划线结尾。字段永远不能设置在具体类的`prototype`上。
> 示例：
```javascript
class Foo {
  constructor() {
    /** @private @const {!Bar} */
    this.bar_ = computeBar();

    /** @protected @const {!Baz} */
    this.baz = computeBaz();
  }
}
```
> 提示：构造函数初始化完成后属性不应该在增加或者删除，因为它会严重影响VM的优化能力。如有必要，在构造函数中稍后初始化的字段应该明确的设置为`undefined`，防止以后形状改变。添加`@struct`标识的对象将会检查未添加或者访问没有声明的属性。类在默认情况下已经添加。
### 5.4.3 计算属性
> 当属性是symbol类型时，只能在类中使用属性。不允许使用字典样式的属性（即带引号或者非符号的计算属性）。

# 6. 命名
## 6.1 所有标识符通用的规则
> 标识符仅使用ASCII字母和数字，并且在以下少数情况下使用下划线，并且很少使用（当诸如Angular之类的框架要求时）美元符号。

> 在合理的范围内，尽可能给出描述性的名称。不必担心节省水平空间，因为让新读者立即理解您的代码更为重要。不要使用项目外部读者不清楚或不熟悉的缩写，也不要通过删除单词中的字母来缩写。
```javascript
errorCount           //无缩写。
dnsConnectionIndex   //大多数人知道“ DNS”代表什么。
ReferrerUrl          //与“URL”相同。
customerId           //“ Id”无处不在，不太可能被误解。
```
不允许：
```javascript
n                    //毫无意义。
nErr                 //模棱两可的缩写。
nCompConns           //模棱两可的缩写。
wgcConnections       //只有您的小组知道这代表什么。
pcReader             //很多东西都可以缩写为“ pc”。
cstmrId              //删除内部字母。
kSecondsPerDay       //不使用匈牙利表示法。
```
## 6.2 按标识符类型划分的规则
### 6.2.1 包名
> 包名全是**lowerCamelCase（小驼峰）**。例如，`my.exampleCode.deepSpace`但不是`my.examplecode.deepspace`或`my.example_code.deep_space`。
### 6.2.2 类名
> 类、接口、记录和typedef名称用**UpperCamelCase（大驼峰）**。未导出的类仅是局部变量：它们没有标记`@private`，因此没有用下划线标记。

> 类型名称通常是名词或名词短语。例如Request、ImmutableList、或VisibilityMode。此外，接口名称有时也可以是形容词或形容词短语（例如Readable）。
### 6.2.3 方法名
> 方法名采用**lowerCamelCase（小驼峰）**。`@private`方法的名称必须下划线结尾。

> 方法名称通常是动词或动词短语。例如，sendMessage或 stop_。永远不需要属性的getter和setter方法，但是如果使用它们，那么就要命名为getFoo（或可选地isFoo，hasFoo 对于booleans）或setFoo(value)setter 进行命名。

> 下划线也可能出现在JsUnit测试方法名称中，以分隔名称的逻辑组成部分。test<MethodUnderTest>_<state>_<expectedOutcome>例如， 一种典型的模式是 testPop_emptyStack_throws。没有一种命名测试方法的正确方法。
### 6.2.4 枚举名称
> 枚举名称用编写**UpperCamelCase（大驼峰）**，类似于类，通常应为单数名词。枚举中的各个项目以命名 **CONSTANT_CASE**（全大写，单词之间用下划线分隔）。
### 6.2.5 常量名称
> 常量名称使用**CONSTANT_CASE**：所有大写字母，单词之间用下划线分隔。没有必要使用结尾的下划线来命名常量，因为私有静态属性可以由（隐式私有）模块本地代替。

#### 6.2.5.1 “常量”的定义
> 每个常量都是@const静态属性或模块本地const 声明，但并非所有@const静态属性和module-local、const都是常量。在选择常量大小写之前，请考虑该字段是否真的像一个深不可更改的常量。例如，如果该实例的可观察状态中的任何一个可以更改，则几乎可以肯定它不是常量。仅企图从不改变对象通常是不够的。

示例：
```javascript
// Constants
const NUMBER = 5;
/** @const */ exports.NAMES = ImmutableList.of('Ed', 'Ann');
/** @enum */ exports.SomeEnum = { ENUM_CONSTANT: 'value' };

// Not constants
let letVariable = 'non-const';
class MyClass { constructor() { /** @const {string} */ this.nonStatic = 'non-static'; } };
/** @type {string} */ MyClass.staticButMutable = 'not @const, can be reassigned';
const /** Set<string> */ mutableCollection = new Set();
const /** ImmutableSet<SomeMutableType> */ mutableElements = ImmutableSet.of(mutable);
const Foo = goog.require('my.Foo');  // mirrors imported name
const logger = log.getLogger('loggers.are.not.immutable');
```
> 常量的名称通常是名词或名词短语。

#### 6.2.5.2本地别名
只要本地别名提高了标准名称的可读性，就应使用本地别名。遵循与goog.requires 相同的规则（3.6 goog.require和goog.requireType语句），并保留别名的最后一部分。别名也可以在功能内使用。别名必须为const。

示例：

```javascript
const staticHelper = importedNamespace.staticHelper;
const CONSTANT_NAME = ImportedClass.CONSTANT_NAME;
const {assert, assertInstanceof} = asserts;
```
  
### 6.2.6 非常量字段名称
> 非常量字段名称（静态或其他）用lowerCamelCase（小驼峰），私有字段后跟下划线。 
  
> 这些名称通常是名词或名词短语。例如，computedValues 或index_。

### 6.2.7 参数名称
> 参数名称用编写lowerCamelCase（小驼峰）。请注意，即使参数需要构造函数，这也适用。

> 单字符参数名称不应在公共方法中使用。

> 例外：当第三方框架要求时，参数名称可以以开头$。此例外不适用于任何其他标识符（例如，局部变量或属性）。

### 6.2.8 局部变量名称
> lowerCamelCase如上所述，局部变量名称用编写，除了模块局部（顶级）常量外。函数范围中的常量仍在中命名lowerCamelCase。请注意，lowerCamelCase即使变量包含构造函数，也要使用它。

### 6.2.9 模板参数名称
> 模板参数名称应为简明，单个单词或单个字母的标识符，并且必须为大写字母，例如TYPE或THIS。

### 6.2.10 本地模块（Module-local）名称
> 未导出的模块本地名称是隐式私有的。它们没有标记@private，也不以下划线结尾。这适用于类，函数，变量，常量，枚举和其他模块本地标识符。

## 6.3 驼峰式：定义
> 有时，有多种合理的方法可以将英语短语转换为驼峰式大小写，例如，当出现首字母缩写词或类似IPv6或 iOS的异常结构时。为了提高可预测性，Google样式指定了以下（几乎）确定性方案。

> 从名字的散列形式开始：
> 1. 将短语转换为纯ASCII并删除所有撇号。例如，“Müller's algorithm”可能会变成“Muellers algorithm”。
> 2. 将结果划分为单词，在空格和所有剩余的标点符号（通常为连字符）之间进行分割。
推荐：如果某个字词在常规用法中已经具有常规的驼峰式外观，则将其分成几个组成部分（例如， “AdWords”变成“ad words”）。请注意，诸如iOS之类的词本身并不是驼峰式的。它违反任何约定，因此该建议不适用。
> 3. 现在将所有内容（包括首字母缩写词）都小写，然后将按照下方规则进行改写大写：
>> - 每个单词首字母大写，以产生大驼峰式命名，或者
>> - 除第一个单词外的每个单词首字母大写，以产生小驼峰式命名
> 4. 最后，将所有单词合并为一个标识符。

> 请注意，几乎完全忽略了原始单词的大小写。

示例：

| 散列形式               |       正确        | 不正确的           |
| --------------------- | :---------------: | ----------------- |
| XML HTTP request      |  XmlHttpRequest   | XMLHTTPRequest    |
| new customer ID       |   newCustomerId   | newCustomerID     |
| inner stopwatch       |  innerStopwatch   | innerStopWatch    |
| supports IPv6 on iOS? | supportsIpv6OnIos | supportsIPv6OnIOS |
| YouTube importer      |  YouTubeImporter  | YoutubeImporter*  |
*可以接受，但不推荐。

注意：在英语中某些单词是模棱两可的：例如nonempty和non-empty都是正确的，因此方法名checkNonempty和checkNonEmpty同样都是正确的。
# 7. JSDoc
# 8. 规则
# 9. 附录
