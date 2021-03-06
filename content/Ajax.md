# [返回主页](../README.md)

<b><details><summary>1、Ajax 是什么?如何创建一个 Ajax？</summary></b>

Ajax 并不算是一种新的技术，全称是 asychronous javascript and xml，可以说是已有技术的组合，主要用来实现客户端与服务器端的异步通信效果，实现页面的局部刷新，早期的浏览器并不能原生支持 ajax，可以使用隐藏帧（iframe）方式变相实现异步效果，后来的浏览器提供了对 ajax 的原生支持

使用 ajax 原生方式发送请求主要通过 XMLHttpRequest(标准浏览器)、ActiveXObject(IE 浏览器)对象实现异步通信效果

基本步骤：

var xhr =null;//创建对象

if(window.XMLHttpRequest){

xhr = new XMLHttpRequest();

}else{

xhr = new ActiveXObject("Microsoft.XMLHTTP");

}

xhr.open(“方式”,”地址”,”标志位”);//初始化请求

xhr.setRequestHeader(“”,””);//设置 http 头信息

xhr.onreadystatechange =function(){}//指定回调函数

xhr.send();//发送请求

js 框架（jQuery/EXTJS 等）提供的 ajax  API 对原生的 ajax 进行了封装，熟悉了基础理论，再学习别的框架就会得心应手，好多都是换汤不换药的内容

</details>

<b><details><summary>2、同步和异步的区别?</summary></b>

同步：阻塞的

-张三叫李四去吃饭，李四一直忙得不停，张三一直等着，直到李四忙完两个人一块去吃饭

=浏览器向服务器请求数据，服务器比较忙，浏览器一直等着（页面白屏），直到服务器返回数据，浏览器才能显示页面

异步：非阻塞的

-张三叫李四去吃饭，李四在忙，张三说了一声然后自己就去吃饭了，李四忙完后自己去吃

=浏览器向服务器请求数据，服务器比较忙，浏览器可以自如的干原来的事情（显示页面），服务器返回数据的时候通知浏览器一声，浏览器把返回的数据再渲染到页面，局部更新

</details>

<b><details><summary>3、如何解决跨域问题?</summary></b>

理解跨域的概念：协议、域名、端口都相同才同域，否则都是跨域

出于安全考虑，服务器不允许 ajax 跨域获取数据，但是可以跨域获取文件内容，所以基于这一点，可以动态创建 script 标签，使用标签的 src 属性访问 js 文件的形式获取 js 脚本，并且这个 js 脚本中的内容是函数调用，该函数调用的参数是服务器返回的数据，为了获取这里的参数数据，需要事先在页面中定义回调函数，在回调函数中处理服务器返回的数据，这就是解决跨域问题的主流解决方案

</details>

<b><details><summary>4、页面编码和被请求的资源编码如果不一致如何处理？</summary></b>

对于 ajax 请求传递的参数，如果是 get 请求方式，参数如果传递中文，在有些浏览器会乱码，不同的浏览器对参数编码的处理方式不同，所以对于 get 请求的参数需要使用 encodeURIComponent 函数对参数进行编码处理，后台开发语言都有相应的解码 api。对于 post 请求不需要进行编码

</details>

<b><details><summary>5、简述 ajax 的过程。</summary></b>

1. 创建 XMLHttpRequest 对象,也就是创建一个异步调用对象

2. 创建一个新的 HTTP 请求,并指定该 HTTP 请求的方法、URL 及验证信息

3. 设置响应 HTTP 请求状态变化的函数

4. 发送 HTTP 请求

5. 获取异步调用返回的数据

6. 使用 JavaScript 和 DOM 实现局部刷新

</details>

<b><details><summary>6、阐述一下异步加载 JS。</summary></b>

1. 异步加载的方案： 动态插入 script 标签

2. 通过 ajax 去获取 js 代码，然后通过 eval 执行

3. script 标签上添加 defer 或者 async 属性

4. 创建并插入 iframe，让它异步执行 js

</details>

<b><details><summary>7、请解释一下 JavaScript 的同源策略。</summary></b>

同源策略是客户端脚本（尤其是 Javascript）的重要的安全度量标准。它最早出自 Netscape Navigator2.0，其目的是防止某个文档或脚本从多个不同源装载。所谓同源指的是：协议，域名，端口相同，同源策略是一种安全协议，指一段脚本只能读取来自同一来源的窗口和文档的属性。

</details>

<b><details><summary>8、GET 和 POST 的区别，何时使用 POST？</summary></b>

GET：一般用于信息获取，使用 URL 传递参数，对所发送信息的数量也有限制，一般在 2000 个字符，有的浏览器是 8000 个字符

POST：一般用于修改服务器上的资源，对所发送的信息没有限制

在以下情况中，请使用 POST 请求：

1. 无法使用缓存文件（更新服务器上的文件或数据库）

2. 向服务器发送大量数据（POST 没有数据量限制）

3. 发送包含未知字符的用户输入时，POST 比 GET 更稳定也更可靠

</details>

<b><details><summary>9、ajax 是什么?ajax 的交互模型?同步和异步的区别?如何解决跨域问题?</summary></b>

1.  通过异步模式，提升了用户体验

2.  优化了浏览器和服务器之间的传输，减少不必要的数据往返，减少了带宽占用

3.  Ajax 在客户端运行，承担了一部分本来由服务器承担的工作，减少了大用户量下的服务器负载。

</details>

<b><details><summary>10、 Ajax 的最大的特点是什么。</summary></b>

Ajax 可以实现异步通信效果，实现页面局部刷新，带来更好的用户体验；按需获取数据，节约带宽资源；

</details>

<b><details><summary>11、ajax 的缺点</summary></b>

1、ajax 不支持浏览器 back 按钮。

2、安全问题 AJAX 暴露了与服务器交互的细节。

3、对搜索引擎的支持比较弱。

4、破坏了程序的异常机制。

</details>

<b><details><summary>12、ajax 请求的时候 get 和 post 方式的区别</summary></b>

get 一般用来进行查询操作，url 地址有长度限制，请求的参数都暴露在 url 地址当中，如果传递中文参数，需要自己进行编码操作，安全性较低。

post 请求方式主要用来提交数据，没有数据长度的限制，提交的数据内容存在于 http 请求体中，数据不会暴漏在 url 地址中。

</details>

<b><details><summary>13、解释 jsonp 的原理，以及为什么不是真正的 ajax</summary></b>

Jsonp 并不是一种数据格式，而 json 是一种数据格式，jsonp 是用来解决跨域获取数据的一种解决方案，具体是通过动态创建 script 标签，然后通过标签的 src 属性获取 js 文件中的 js 脚本，该脚本的内容是一个函数调用，参数就是服务器返回的数据，为了处理这些返回的数据，需要事先在页面定义好回调函数，本质上使用的并不是 ajax 技术

</details>

<b><details><summary>14、什么是 Ajax 和 JSON，它们的优缺点。</summary></b>

Ajax 是全称是 asynchronous JavaScript andXML，即异步 JavaScript 和 xml，用于在 Web 页面中实现异步数据交互，实现页面局部刷新。

优点：可以使得页面不重载全部内容的情况下加载局部内容，降低数据传输量，避免用户不断刷新或者跳转页面，提高用户体验

缺点：对搜索引擎不友好；要实现 ajax 下的前后退功能成本较大；可能造成请求数的增加跨域问题限制；

JSON 是一种轻量级的数据交换格式，ECMA 的一个子集

优点：轻量级、易于人的阅读和编写，便于机器（JavaScript）解析，支持复合数据类型（数组、对象、字符串、数字）

</details>

<b><details><summary>16、一个页面从输入 URL 到页面加载显示完成，这个过程中都发生了什么？</summary></b>

分为 4 个步骤：

1. 当发送一个 URL 请求时，不管这个 URL 是 Web 页面的 URL 还是 Web 页面上每个资源的 URL，浏览器都会开启一个线程来处理这个请求，同时在远程 DNS 服务器上启动一个 DNS 查询。这能使浏览器获得请求对应的 IP 地址。

2. 浏览器与远程 Web 服务器通过 TCP 三次握手协商来建立一个 TCP/IP 连接。该握手包括一个同步报文，一个同步-应答报文和一个应答报文，这三个报文在 浏览器和服务器之间传递。该握手首先由客户端尝试建立起通信，而后服务器应答并接受客户端的请求，最后由客户端发出该请求已经被接受的报文。

3. 一旦 TCP/IP 连接建立，浏览器会通过该连接向远程服务器发送 HTTP 的 GET 请求。远程服务器找到资源并使用 HTTP 响应返回该资源，值为 200 的 HTTP 响应状态表示一个正确的响应。

4. 此时，Web 服务器提供资源服务，客户端开始下载资源。

</details>

<b><details><summary>17、ajax 请求的时候 get 和 post 方式的区别</summary></b>

get 一般用来进行查询操作，url 地址有长度限制，请求的参数都暴露在 url 地址当中，如果传递中文参数，需要自己进行编码操作，安全性较低。

post 请求方式主要用来提交数据，没有数据长度的限制，提交的数据内容存在于 http 请求体中，数据不会暴漏在 url 地址中。

</details>

<b><details><summary>18、ajax 请求时，如何解释 json 数据</summary></b>

使用 eval() 或者 JSON.parse() 鉴于安全性考虑，推荐使用 JSON.parse()更靠谱，对数据的安全性更好。

</details>

<b><details><summary>1、ajax 过程</summary></b>

(1)创建 XMLHttpRequest 对象,也就是创建一个异步调用对象.

(2)创建一个新的 HTTP 请求,并指定该 HTTP 请求的方法、URL 及验证信息.

(3)设置响应 HTTP 请求状态变化的函数.

(4)发送 HTTP 请求.

(5)获取异步调用返回的数据.

(6)使用 JavaScript 和 DOM 实现局部刷新.

</details>

<b><details><summary>2、异步加载和延迟加载</summary></b>

1.异步加载的方案： 动态插入 script 标签

2.通过 ajax 去获取 js 代码，然后通过 eval 执行

3.script 标签上添加 defer 或者 async 属性

4.创建并插入 iframe，让它异步执行 js

5.延迟加载：有些 js 代码并不是页面初始化的时候就立刻需要的，而稍后的某些情况才需要的。

</details>

<b><details><summary>5、eval 是做什么的？</summary></b>

它的功能是把对应的字符串解析成 JS 代码并运行；

应该避免使用 eval，不安全，非常耗性能（2 次，一次解析成 js 语句，一次执行）。

</details>

<b><details><summary>7、AMD 和 CMD 规范的区别</summary></b>

1、对于依赖的模块，AMD 是提前执行，CMD 是延迟执行

2、CMD 推崇依赖就近，AMD 推崇依赖前置

</details>

<b><details><summary>8、HTTP 状态码</summary></b>

100 ?Continue ?继续，一般在发送 post 请求时，已发送了 http header 之后服务端将返回此信息，表示确认，之后发送具体参数信息

200 ?OK ? 正常返回信息

201 ?Created ?请求成功并且服务器创建了新的资源

202 ?Accepted ?服务器已接受请求，但尚未处理

301 ?Moved Permanently ?请求的网页已永久移动到新位置。

302 Found ?临时性重定向。

303 See Other ?临时性重定向，且总是使用 GET 请求新的 URI。

304 ?Not Modified ?自从上次请求后，请求的网页未修改过。

400 Bad Request ?服务器无法理解请求的格式，客户端不应当尝试再次使用相同的内容发起请求。

401 Unauthorized ?请求未授权。

403 Forbidden ?禁止访问。

404 Not Found ?找不到如何与 URI 相匹配的资源。

500 Internal Server Error ?最常见的服务器端错误。

503 Service Unavailable 服务器端暂时无法处理请求（可能是过载或维护）。

</details>

<b><details><summary>9、栈和队列的区别?</summary></b>

栈的插入和删除操作都是在一端进行的，而队列的操作却是在两端进行的。

队列先进先出，栈先进后出。

栈只允许在表尾一端进行插入和删除，而队列只允许在表尾一端进行插入，在表头一端进行删除

栈和堆的区别？

栈区（stack）—    由编译器自动分配释放   ，存放函数的参数值，局部变量的值等。

堆区（heap）   —    一般由程序员分配释放，    若程序员不释放，程序结束时可能由 OS 回收。

堆（数据结构）：堆可以被看成是一棵树，如：堆排序；

栈（数据结构）：一种先进后出的数据结构。

</details>

<b><details><summary>10、XML 和 JSON 的区别？</summary></b>

(1).数据体积方面。

JSON 相对于 XML 来讲，数据的体积小，传递的速度更快些。

(2).数据交互方面。

JSON 与 JavaScript 的交互更加方便，更容易解析处理，更好的数据交互。

(3).数据描述方面。

JSON 对数据的描述性比 XML 较差。

(4).传输速度方面。

JSON 的速度要远远快于 XML。

</details>

<b><details><summary>12、ajax 加载的页面，跳转到另外一个页面再跳转回来，内容相同，如何节约读取请求?</summary></b>

答：后台做缓存，读取缓存里面的数据。CDN

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>
