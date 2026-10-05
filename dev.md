# Learning Js don't use the typescript, js is all you need
1. node main.js 
2. ECMAScript
3. 引擎
    - V8 —— Chrome、Opera 和 Edge 中的 JavaScript 引擎
    - SpiderMonkey —— Firefox 中的 JavaScript 引擎。
    - ……还有其他一些代号，像 “Chakra” 用于 IE，“JavaScriptCore”、“Nitro” 和 “SquirrelFish” 用于 Safari，等等
4. 浏览器中的 JavaScript 可以做下面这些事
    - 在网页中添加新的 HTML，修改网页已有内容和网页的样式。
    - 响应用户的行为，响应鼠标的点击，指针的移动，按键的按动。
    - 向远程服务器发送网络请求，下载和上传文件（所谓的 AJAX 和 COMET 技术）。
    - 获取或设置 cookie，向访问者提出问题或发送消息。
    - 记住客户端的数据（“本地存储”）
5. 浏览器中的 JavaScript 不能做什么？
    - 为了用户的（信息）安全，在浏览器中的 JavaScript 的能力是受限的。目的是防止恶意网页获取用户私人信息或损害用户数据。
    - 网页中的 JavaScript 不能读、写、复制和执行硬盘上的任意文件。它没有直接访问操作系统的功能。现代浏览器允许 JavaScript 做一些文件相关的操作，但是这个操作是受到限制的。仅当用户做出特定的行为，JavaScript 才能操作这个文件。例如，用户把文件“拖放”到浏览器中，或者通过 <input> 标签选择了文件。有很多与相机/麦克风和其它设备进行交互的方式，但是这些都需要获得用户的明确许可。因此，启用了 JavaScript 的网页应该不会偷偷地启动网络摄像头观察你，并把你的信息发送到 美国国家安全局。
    - 不同的标签页/窗口之间通常互不了解。有时候，也会有一些联系，例如一个标签页通过 JavaScript 打开的另外一个标签页。但即使在这种情况下，如果两个标签页打开的不是同一个网站（域名、协议或者端口任一不相同的网站），它们都不能相互通信。这就是所谓的“同源策略”。为了解决“同源策略”问题，两个标签页必须 都 包含一些处理这个问题的特定的 JavaScript 代码，并均允许数据交换。本教程会讲到这部分相关的知识。这个限制也是为了用户的信息安全。例如，用户打开的 http://anysite.com 网页必须不能访问 http://gmail.com（另外一个标签页打开的网页）也不能从那里窃取信息。
    - JavaScript 可以轻松地通过互联网与当前页面所在的服务器进行通信。但是从其他网站/域的服务器中接收数据的能力被削弱了。尽管可以，但是需要来自远程服务器的明确协议（在 HTTP header 中）。这也是为了用户的信息安全。
6. TypeScript 专注于添加“严格的数据类型”以简化开发，以更好地支持复杂系统的开发。由微软开发。
7. 最新的规范草案请见 https://tc39.es/ecma262/
8. 想了解最新最前沿的功能，包括“即将纳入规范的”（所谓的 “stage 3”），请看这里的提案 https://github.com/tc39/proposals
9. MDN（Mozilla）JavaScript 索引 是一个带有用例和其他信息的主要的手册。它是一个获取关于个别语言函数、方法等深入信息的很好的信息来源 在 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference 阅读它
10. 兼容性表
    - https://caniuse.com —— 每个功能的支持表，例如，查看哪个引擎支持现代加密（cryptography）函数：https://caniuse.com/#feat=cryptography。
    - https://kangax.github.io/compat-table —— 一份列有语言功能以及引擎是否支持这些功能的表格。
11. 现代模式，"use strict"
12. 重用还是新建？
    - 最后一点，有一些懒惰的程序员，倾向于重用现有的变量，而不是声明一个新的变量。结果是，这个变量就像是被扔进不同东西盒子，但没有改变它的贴纸。现在里面是什么？谁知道呢。我们需要靠近一点，仔细检查才能知道。这样的程序员节省了一点变量声明的时间，但却在调试代码的时候损失数十倍时间。额外声明一个变量绝对是利大于弊的。现代的 JavaScript 压缩器和浏览器都能够很好地对代码进行优化，所以不会产生性能问题。为不同的值使用不同的变量可以帮助引擎对代码进行优化。
13. 可以通过将 n 附加到整数字段的末尾来创建 BigInt 值
    - const bigInt = 1234567890123456789012345678901234567890n;
14. `${variable}` StringValue
15. type
    - typeof(number, bigInt, string, undefined, object, symbol, boolean, function, null)
16. confirm, prompt, alert
17. == and ===
    - 普通的相等性检查 == 存在一个问题，它不能区分出 0 和 false
    - 严格相等运算符 === 在进行比较时不会做任何的类型转换