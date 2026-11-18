# 复习自测题合集

> 按章节分组，共 **45 题**。点击问题展开答案；建议先默写再核对。

[返回总目录](README.md) · [一页纸速查](CHEATSHEET.md) · [完整阅读版](NOTE.md)

---

## 按章阅读

- [第 01 章](docs/ch01.md)
- [第 02 章](docs/ch02.md)
- [第 03 章](docs/ch03.md)
- [第 04 章](docs/ch04.md)
- [第 05 章](docs/ch05.md)
- [第 06 章](docs/ch06.md)
- [第 07 章](docs/ch07.md)
- [第 08 章](docs/ch08.md)
- [第 09 章](docs/ch09.md)
- [第 10 章](docs/ch10.md)
- [第 11 章](docs/ch11.md)
- [第 12 章](docs/ch12.md)
- [第 13 章](docs/ch13.md)
- [第 14 章](docs/ch14.md)
- [第 15 章](docs/ch15.md)

---

## 第 01 章 · 认识 HTML：网页的骨架

[阅读本章](docs/ch01.md)

<details>
<summary>HTML 是什么？它与 CSS、JavaScript 如何分工？</summary>

HTML 是描述网页结构与内容的标记语言；HTML 管结构、CSS 管表现、JavaScript 管行为。

</details>

<details>
<summary>标签、元素、属性三者有什么区别？</summary>

标签是尖括号关键字；元素是「开始标签 + 内容 + 结束标签」整体；属性是在开始标签里补充信息的 `名="值"`。

</details>

<details>
<summary>浏览器解析 HTML 后生成什么？举出 5 个空元素。</summary>

生成 DOM 树。空元素如 `img`、`br`、`hr`、`input`、`meta`、`link`、`source`。

</details>

---

## 第 02 章 · 开发环境与第一个页面

[阅读本章](docs/ch02.md)

<details>
<summary>`<!DOCTYPE html>` 是标签吗？省略会怎样？</summary>

不是标签，是文档类型声明；省略会触发怪异模式，盒模型等渲染行为与标准不一致。

</details>

<details>
<summary>为什么 charset 要放在 head 最前面？</summary>

浏览器只在前 1024 字节内识别编码声明，位置靠后或缺失会导致中文乱码；文件也必须以 UTF-8 保存。

</details>

<details>
<summary>相对路径 `./`、`../`、`/` 各表示什么？viewport 有什么用？</summary>

同级目录 / 上一级目录 / 站点根目录。`viewport` 让移动端按设备宽度渲染，是响应式页面的前提。

</details>

---

## 第 03 章 · 文本与排版标签

[阅读本章](docs/ch03.md)

<details>
<summary>块级、行内、行内块元素有什么区别？各举两例。</summary>

块级独占一行可设宽高（div、p、h1、ul）；行内随文字流、宽高由内容决定（span、a、strong）；行内块不换行但可设宽高（img、input）。

</details>

<details>
<summary>`strong` 与 `b`、`em` 与 `i` 该优先用哪个？</summary>

优先 `strong` / `em`，它们带「重要 / 强调」语义，利于屏幕阅读器与 SEO；b / i 只描述外观。

</details>

<details>
<summary>为什么 `<p>` 里不能嵌 `<div>`？连续空格如何保留？</summary>

浏览器遇到块级元素会自动闭合段落，导致结构错乱。保留空白用 `<pre>` 或 CSS `white-space`，也可用 `&nbsp;`。

</details>

---

## 第 04 章 · 链接与图片

[阅读本章](docs/ch04.md)

<details>
<summary>`alt` 与 `title` 的区别是什么？</summary>

`alt` 是图片替代文本，加载失败时显示、供屏幕阅读器与搜索引擎使用，必写；`title` 只是悬停提示，不能替代 alt。

</details>

<details>
<summary>`target="_blank"` 为什么要加 `rel="noopener"`？</summary>

避免新页面通过 `window.opener` 反向操作原页面，属于安全与性能最佳实践。

</details>

<details>
<summary>`picture` / `srcset` 解决什么问题？为什么建议写 width / height？</summary>

按视口宽度或像素密度选择最合适的图片资源，节省流量；显式尺寸可避免图片加载时的布局抖动（CLS）。

</details>

---

## 第 05 章 · 列表：无序、有序与描述列表

[阅读本章](docs/ch05.md)

<details>
<summary>`ul`、`ol`、`dl` 分别适用什么场景？</summary>

ul 无先后顺序的项目；ol 有步骤 / 排名含义；dl 是术语与解释的键值对。

</details>

<details>
<summary>`ol` 有哪些常用属性？</summary>

`start` 起始编号、`type` 编号样式（1 / A / a / I / i）、`reversed` 倒序；单项还可用 `value`。

</details>

<details>
<summary>嵌套列表的正确写法是什么？</summary>

子列表必须放进 `<li>` 内部，不能直接作为 `<ul>` / `<ol>` 的子元素。

</details>

---

## 第 06 章 · 表格：结构与合并单元格

[阅读本章](docs/ch06.md)

<details>
<summary>一个规范表格由哪些标签组成？</summary>

`table` > `caption` + `thead` / `tbody` / `tfoot` > `tr` > `th` / `td`，还有 `colgroup` / `col`。

</details>

<details>
<summary>`colspan` 与 `rowspan` 有什么区别？最容易犯什么错？</summary>

前者横向合并列、后者纵向合并行；合并后必须删除被覆盖的单元格，否则表格错位。

</details>

<details>
<summary>`th` 的 `scope` 有什么作用？为什么不用表格做布局？</summary>

`scope="col|row"` 指明表头方向，帮助屏幕阅读器关联单元格；表格语义是二维数据，用来布局会破坏可访问性与响应式。

</details>

---

## 第 07 章 · 表单：与用户对话的入口

[阅读本章](docs/ch07.md)

<details>
<summary>GET 与 POST 该怎么选？</summary>

GET 把数据拼在 URL 上，适合搜索 / 筛选等无副作用请求；POST 放请求体，适合登录、写入、上传。

</details>

<details>
<summary>某个输入框的值没被提交，最可能是什么原因？</summary>

控件缺少 `name`，或被 `disabled` 禁用；只有带 name 且启用的控件才会被序列化。

</details>

<details>
<summary>`label` 有哪两种关联方式？`disabled` 与 `readonly` 有何不同？</summary>

`for` 指向控件 id，或把控件直接包进 label；disabled 不聚焦、不提交，readonly 可聚焦、可复制、仍会提交。

</details>

---

## 第 08 章 · 语义化与页面结构

[阅读本章](docs/ch08.md)

<details>
<summary>语义化能带来哪些实际收益？</summary>

屏幕阅读器可跳转导航、搜索引擎更易理解正文、样式丢失仍可阅读、代码更易维护。

</details>

<details>
<summary>`section`、`article`、`div` 怎么选？`main` 能有几个？</summary>

可独立分发用 article，带主题分组用 section，纯布局用 div；一个页面只能有一个 main。

</details>

<details>
<summary>标题层级有什么规则？</summary>

从 h1 开始逐级递进，不跳级（h1 → h2 → h3），一个页面通常只有一个 h1。

</details>

---

## 第 09 章 · 多媒体与嵌入内容

[阅读本章](docs/ch09.md)

<details>
<summary>`video` 有哪些常用属性？为什么自动播放经常失效？</summary>

src / controls / poster / width / height / autoplay / loop / muted / preload；浏览器会拦截带声音的自动播放，需加 muted 或由用户手势触发。

</details>

<details>
<summary>内联 SVG 与 canvas 有什么区别？</summary>

SVG 是矢量、可用 CSS 控制、缩放不失真，适合图标图表；canvas 是位图画布，靠 JS 逐帧绘制，适合游戏与图像处理。

</details>

<details>
<summary>使用 iframe 时要注意什么？</summary>

必写 `title` 说明用途；用 `sandbox` 限制权限；`loading="lazy"` 延迟加载；注意跨域与响应式尺寸。

</details>

---

## 第 10 章 · head 元信息与资源引入

[阅读本章](docs/ch10.md)

<details>
<summary>head 里通常放哪些元素？</summary>

charset、viewport、title、description、favicon（link:icon）、外部 CSS、script（建议 defer）、canonical、Open Graph。

</details>

<details>
<summary>defer 与 async 的执行时机和顺序有何不同？</summary>

两者都并行下载；defer 等 HTML 解析完按顺序执行，async 下载完立即执行、不保证顺序。页面脚本优先 defer。

</details>

<details>
<summary>Open Graph 与 canonical 分别解决什么问题？</summary>

OG 让链接在社交平台显示标题 / 摘要 / 封面；canonical 指定权威 URL，避免重复内容分散搜索权重。

</details>

---

## 第 11 章 · 全局属性、字符实体与编码

[阅读本章](docs/ch11.md)

<details>
<summary>id 与 class 有什么区别？</summary>

id 文档内唯一，用于锚点 / JS 精确定位；class 可复用、可多值，主要用于样式选择器。

</details>

<details>
<summary>`data-*` 有什么用？JavaScript 怎么读？</summary>

存自定义数据而不污染 class；通过元素的 `dataset` 读取，如 `el.dataset.chapter`。

</details>

<details>
<summary>为什么要写字符实体？中文乱码怎么排查？</summary>

`<`、`>`、`&` 在 HTML 中有特殊含义，显示本身须写 `&lt;` / `&gt;` / `&amp;`；乱码查文件编码与 charset 是否一致。

</details>

---

## 第 12 章 · HTML5 新特性与相关 Web API

[阅读本章](docs/ch12.md)

<details>
<summary>`progress` 与 `meter` 有什么区别？</summary>

progress 表示任务完成进度（value / max）；meter 表示已知范围内的度量值（min / max / low / high / optimum）。

</details>

<details>
<summary>原生 `dialog` 怎么打开和关闭？`template` 有什么特点？</summary>

用 JS 的 `showModal()` / `close()`；template 内容不会被渲染，是惰性的，供 JS 克隆复用。

</details>

<details>
<summary>localStorage 与 sessionStorage 的区别？</summary>

localStorage 持久化保存（约 5MB），sessionStorage 仅在当前标签页会话有效，关闭即清除。

</details>

---

## 第 13 章 · 可访问性、编码规范与排错

[阅读本章](docs/ch13.md)

<details>
<summary>可访问性最基础的四件事是什么？</summary>

图片写 alt、控件关联 label、使用语义标签与连续标题层级、保证键盘可聚焦与焦点顺序。

</details>

<details>
<summary>ARIA 的使用原则是什么？</summary>

优先使用原生语义标签；只有原生元素无法表达时才补 `role` / `aria-*`，且不要与原生语义冲突。

</details>

<details>
<summary>页面出问题时常用哪些工具排查？</summary>

F12 开发者工具（Elements / Console）、W3C Markup Validator 校验标签、Lighthouse / axe 审计可访问性与 SEO。

</details>

---

## 第 14 章 · 综合实战：一个完整的个人主页

[阅读本章](docs/ch14.md)

<details>
<summary>动手写页面前应该先做什么？</summary>

先画结构草图，确定 header / nav / main / section / aside / footer 的分区，再用语义标签搭骨架，最后填内容与补样式。

</details>

<details>
<summary>综合示例里用到了哪些表单与 HTML5 元素？</summary>

form / fieldset / legend / label / input / textarea / checkbox / required，以及 progress、details / summary、time、figure。

</details>

<details>
<summary>HTML 阶段最应该追求什么？</summary>

结构正确、语义清晰、可访问，而不是视觉好看；视觉交给 CSS，行为交给 JavaScript。

</details>

---

## 第 15 章 · 速查表、自测题与后续路线

[阅读本章](docs/ch15.md)

<details>
<summary>速查表是按什么维度组织标签的？</summary>

按用途分为文档与结构、文本与内容、列表表格媒体、表单与交互四组，便于按场景反查。

</details>

<details>
<summary>学完 HTML 之后的合理路线是什么？</summary>

CSS（盒模型、Flex / Grid、响应式）→ JavaScript（DOM、事件、异步）→ Git 与工程化 → 框架 → 性能与可访问性进阶。

</details>

<details>
<summary>怎样检验自己真的掌握了 HTML？</summary>

能不看资料写出规范骨架、能解释每个标签的语义、能通过 W3C 校验、能用键盘走通页面、能完成自测题。

</details>

---
