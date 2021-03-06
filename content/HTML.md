# [返回主页](../README.md)

<b><details><summary>1.简述一下你对 HTML 语义化的理解？</summary></b></b>

用正确的标签做正确的事情。

html 语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;即使在没有样式 CSS 情况下也以一种文档格式显示，并且是容易阅读的;

搜索引擎的爬虫也依赖于 HTML 标记来确定上下文和各个关键字的权重，利于 SEO;

使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

</details>

<b><details><summary>2.Label 的作用是什么？是怎么用的？</summary></b>

label 标签来定义表单控制间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。

```

<label for="Name">Number:</label>

<input type=“text“name="Name" id="Name"/>

<label>Date:<input type="text" name="B"/></label>

```

</details>

<b><details><summary>3.iframe 有那些缺点？</summary></b>

- iframe 会阻塞主页面的 Onload 事件；

- 搜索引擎的检索程序无法解读这种页面，不利于 SEO;

- iframe 和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。

使用 iframe 之前需要考虑这两个缺点。如果需要使用 iframe，最好是通过 javascript。动态给 iframe 添加 src 属性值，这样可以绕开以上两个问题。

</details>

<b><details><summary>4.HTML 与 XHTML —— 二者有什么区别，你觉得应该使用哪一个并说出理由。</summary></b>

```

1.XHTML 元素必须被正确地嵌套。

错误：<p><span>this is example.</p></span>

正确：<p><span>this is example.</span></p>

2.XHTML 元素必须被关闭。

错误：<p>this is example.

正确：<p>this is example.</p>

3.标签名必须用小写字母。

错误：<P>this is example.<P>

正确：<p>this is example.</p>

3.1空标签也必须被关闭

错误：<br>

正确：<br/>

4.XHTML 文档必须拥有根元素。

所有的 XHTML 元素必须被嵌套于 <html> 根元素中。

```

</details>

<b><details><summary>5.常见的浏览器内核有哪些？</summary></b>

Trident 内核：IE,MaxThon,TT,The World,360,搜狗浏览器等。[又称 MSHTML]

Gecko 内核：Netscape6 及以上版本，FF,MozillaSuite/SeaMonkey 等

Presto 内核：Opera7 及以上。 [Opera 内核原为：Presto，现为：Blink;]

Webkit 内核：Safari,Chrome 等。 [ Chrome 的：Blink（WebKit 的分支）]

</details>

<b><details><summary>6.HTML5 的 form 如何关闭自动完成功能？</summary></b>

给不想要提示的 form 或某个 input 设置为 autocomplete=off。

</details>

<b><details><summary>8.实现不使用 border 画出 1px 高的线，在不同浏览器的标准模式与怪异模式下都能保持一致的效果。</summary></b>

```

<div style="height:1px;overflow:hidden;background:red"></div>

```

</details>

<b><details><summary>9.title 与 h1 的区别、b 与 strong 的区别、i 与 em 的区别？</summary></b>

```

title属性没有明确意义只表示是个标题，H1则表示层次明确的标题，对页面信息的抓取也有很大的影响；

strong是标明重点内容，有语气加强的含义，使用阅读设备阅读网络时：<strong>会重读，而<B>是展示强调内容。

i内容展示为斜体，em表示强调的文本；

Physical Style Elements -- 自然样式标签

b, i, u, s, pre

Semantic Style Elements -- 语义样式标签

strong, em, ins, del, code

应该准确使用语义样式标签, 但不能滥用, 如果不能确定时首选使用自然样式标签。

```

</details>

<b><details><summary>10.请描述下 SEO 中的 TDK？</summary></b>

在 SEO 中，所谓的 TDK 其实就是 title、description、keywords 这三个标签，这三个标签在网站的优化过程中

title 标题标签，description 描述标签，keywords 关键词标签

</details>

<b><details><summary>13.前端页面有哪三层构成，分别是什么？作用是什么？</summary></b>

分成：结构层、表示层、行为层。

结构层（structural layer）

由 HTML 或 XHTML 之类的标记语言负责创建。标签，也就是那些出现在尖括号里的单词，对网页内容的语义含义做出了描述，但这些标签不包含任何关于如何显示有关内容的信息。例如，P 标签表达了这样一种语义：“这是一个文本段。”

表示层（presentation layer）

由 CSS 负责创建。 CSS 对“如何显示有关内容”的问题做出了回答。

行为层（behaviorlayer）

负责回答“内容应该如何对事件做出反应”这一问题。这是 Javascript 语言和 DOM 主宰的领域。

</details>

<b><details><summary>14.每个 HTML 文件头里都有个很重要的东西，Doctype，知道这是干什么的么？</summary></b>

  <!DOCTYPE> 声明位于文档中的最前面的位置，处于 <html> 标签之前。

作用：

1.告知浏览器文档使用哪种 HTML 或 XHTML 规范。

2.告诉浏览器按照何种规范解析页（如果你的页面没有 DOCTYPE 的声明，那么 compatMode 默认就是 BackCompat,浏览器按照自己的方式解析渲染页面）

</details>

<b><details><summary>15.为什么用多个域名存储网站资源更有效？</summary></b>

1、CDN 缓存更方便

2、突破浏览器并发限制

3、节约 cookie 带宽

4、节约主域名的连接数，优化页面响应速度

5、防止不必要的安全问题

</details>

<b><details><summary>16.请描述一下 cookies，sessionStorage 和 localStorage 的区别</summary></b>

cookie 在浏览器和服务器间来回传递。 sessionStorage 和 localStorage 不会

sessionStorage 和 localStorage 的存储空间更大；

sessionStorage 和 localStorage 有更多丰富易用的接口；

sessionStorage 和 localStorage 各自独立的存储空间；

</details>

<b><details><summary>3. Quirks(怪癖）模式是什么？它和 Standards（标准）模式有什么区别</summary></b>

1 以 ie6 为例，如果写了 DTD，就意味着这个页面将采用对 CSS 支持更好的布局，而如果没有，则采用兼容之前的布局方式。这就是 Quirks 模式（怪癖模式，诡异模式，怪异模式）。

2 区别：总体会有布局、样式解析和脚本执行三个方面的区别。

设置一个元素的宽度和高度

给<span>等行内元素设置 width 和 height

用 margin:0 auto 设置水平居中

从 IE6 开始，引入了 Standards 模式，标准模式中，浏览器尝试给符合标准的文档在规范上的正确处理达到在指定浏览器中的程度。

在 IE6 之前 CSS 还不够成熟，所以 IE5 等之前的浏览器对 CSS 的支持很差， IE6 将对 CSS 提供更好的支持，然而这时的问题就来了，因为有很多页面是基于旧的布局方式写的，而如果 IE6  支持 CSS 则将令这些页面显示不正常，如何在即保证不破坏现有页面，又提供新的渲染机制呢？

在写程序时我们也会经常遇到这样的问题，如何保证原来的接口不变，又提供更强大的功能，尤其是新功能不兼容旧功能时。遇到这种问题时的一个常见做法是增加参数和分支，即当某个参数为真时，我们就使用新功能，而如果这个参数   不为真时，就使用旧功能，这样就能不破坏原有的程序，又提供新功能。IE6 也是类似这样做的，它将 DTD（文档类型定义）当成了这个“参数”，因为以前的页面大家都不会去写 DTD，所以 IE6 就假定   如果写了 DTD，就意味着这个页面将采用对 CSS 支持更好的布局，而如果没有，则采用兼容之前的布局方式。这就是 Quirks 模式（怪癖模式，诡异模式，怪异模式）。

区别：

总体会有布局、样式解析和脚本执行三个方面的区别。

盒模型：在 W3C 标准中，如果设置一个元素的宽度和高度，指的是元素内容的宽度和高度，而在 Quirks  模式下，IE 的宽度和高度还包含了 padding 和 border。

设置行内元素的高宽：在 Standards 模式下，给<span>等行内元素设置 wdith 和 height 都不会生效，而在 quirks 模式下，则会生效。

设置百分比的高度：在 standards 模式下，一个元素的高度是由其包含的内容来决定的，如果父元素没有设置百分比的高度，子元素设置一个百分比的高度是无效的

用 margin:0 auto 设置水平居中：使用 margin:0 auto 在 standards 模式下可以使元素水平居中，但在 quirks 模式下却会失效。

（还有很多，答出什么不重要，关键是看他答出的这些是不是自己经验遇到的，还是说都是看文章看的，甚至完全不知道。）

</details>

<b><details><summary>4. div+css 的布局较 table 布局有什么优点？</summary></b>

分离 方便改版 快清晰简洁 seo

1.改版的时候更方便 只要改 css 文件。

2.页面加载速度更快、结构化清晰、页面显示简洁。

3.表现与结构相分离。

4.易于优化（seo）搜索引擎更友好，排名更容易靠前。

</details>

<b><details><summary>6. 你能描述一下渐进增强和优雅降级之间的不同吗?</summary></b>

渐进增强  progressive enhancement：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

（一开始保证最基本的功能，再改进和追加功能）

优雅降级  graceful degradation：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

（一开始就构建完整的功能，再针对低版本浏览器进行兼容。）

区别：优雅降级是从复杂的现状开始，并试图减少用户体验的供给，而渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要。降级（功能衰减）意味着往回看；而渐进增强则意味着朝前看，同时保证其根基处于安全地带。

</details>

<b><details><summary>8. 请谈一下你对网页标准和标准制定机构重要性的理解。</summary></b>

降低开发难度及开发成本，减少各种 BUG、安全问题， 提高网站易用性

</details>

<b><details><summary>10. 简述一下 src 与 href 的区别。</summary></b>

src 用于替换当前元素，href 用于在当前文档和引用资源之间确立联系。

</details>

<b><details><summary>12. 知道什么是微格式吗？谈谈理解。在前端构建中应该考虑微格式吗？</summary></b>

微格式（Microformats）是一种让机器可读的语义化 XHTML 词汇的集合，是结构化数据的开放标准。是为特殊应用而制定的特殊格式。

优点：将智能数据添加到网页上，让网站内容在搜索引擎结果界面可以显示额外的提示。（应用范例：豆瓣，有兴趣自行 google）

</details>

<b><details><summary>13. 在 css/js 代码上线之后开发人员经常会优化性能，从用户刷新网页开始，一次 js 请求一般情况下有哪些地方会有缓存处理？</summary></b>

答案：dns 缓存，cdn 缓存，浏览器缓存，服务器缓存。

</details>

<b><details><summary>14. 一个页面上有大量的图片（大型电商网站），加载很慢，你有哪些方法优化这些图片的加载，给用户更好的体验。</summary></b>

图片懒加载，在页面上的未可视区域可以添加一个滚动条事件，判断图片位置与浏览器顶端的距离与页面的距离，如果前者小于后者，优先加载。

如果为幻灯片、相册等，可以使用图片预加载技术，将当前展示图片的前一张和后一张优先下载。

如果图片为 css 图片，可以使用 CSSsprite，SVGsprite，Iconfont、Base64 等技术。

如果图片过大，可以使用特殊编码的图片，加载时会先加载一张压缩的特别厉害的缩略图，以提高用户体验。

如果图片展示区域小于图片的真实大小，则因在服务器端根据业务需要先行进行图片压缩，图片压缩后大小与展示一致。

</details>

<b><details><summary>39. html 常见兼容性问题？</summary></b>

1.双边距 BUG float 引起的   使用 display

2.3 像素问题 使用 float 引起的 使用 dislpay:inline -3px

3.超链接 hover 点击后失效   使用正确的书写顺序 link visited hover active

4.Ie z-index 问题 给父级添加 position:relative

5.Png 透明 使用 js 代码 改

6.Min-height 最小高度 ！Important 解决’

7.select 在 ie6 下遮盖 使用 iframe 嵌套

8.为什么没有办法定义 1px 左右的宽度容器（IE6 默认的行高造成的，使用 over:hidden,zoom:0.08 line-height:1px）

9.IE5-8 不支持 opacity，解决办法：

.opacity {

opacity: 0.4

filter: alpha(opacity=60); /_ for IE5-7 _/

-ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=60)"; /_ for IE 8_/

}

10. IE6 不支持 PNG 透明背景，解决办法: IE6 下使用 gif 图片

</details>

<b><details><summary>40. 对 WEB 标准以及 W3C 的理解与认识</summary></b>

答：标签闭合、标签小写、不乱嵌套、提高搜索机器人搜索几率、使用外 链 css 和 js 脚本、结构行为表现的分离、文件下载与页面速度更快、内容能被更多的用户所访问、内容能被更广泛的设备所访问、更少的代码和组件，容易维 护、改版方便，不需要变动页面内容、提供打印版本而不需要复制内容、提高网站易用性。

</details>

<b><details><summary>44. CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3 新增伪类有那些？</summary></b>

```

  1.id选择器（ # myid）

        2.类选择器（.myclassname）

        3.标签选择器（div, h1, p）

        4.相邻选择器（h1 + p）

        5.子选择器（ul < li）

        6.后代选择器（li a）

        7.通配符选择器（ * ）

        8.属性选择器（a[rel = "external"]）

        9.伪类选择器（a: hover, li: nth - child）

    *   可继承： font-size font-family color, UL LI DL DD DT;

    *   不可继承 ：border padding margin width height ;

    *   优先级就近原则，样式定义最近者为准;

    *   载入样式以最后载入的定位为准;

优先级为:

       !important >  id > class > tag  

       important 比 内联优先级高

CSS3新增伪类举例：

    p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。

    p:last-of-type  选择属于其父元素的最后 <p> 元素的每个 <p> 元素。

    p:only-of-type  选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。

    p:only-child    选择属于其父元素的唯一子元素的每个 <p> 元素。

    p:nth-child(2)  选择属于其父元素的第二个子元素的每个 <p> 元素。

    :enabled、:disabled 控制表单控件的禁用状态。

    :checked，单选框或复选框被选中。

```

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>

<b><details><summary></summary></b>

</details>
