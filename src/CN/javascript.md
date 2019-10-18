
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
