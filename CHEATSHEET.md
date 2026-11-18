# HTML 一页纸速查表

> 复习专用：按「场景 → 该用什么」组织，五分钟过一遍全部核心知识点。

[返回总目录](README.md) · [完整阅读版](NOTE.md) · [复习自测题](REVIEW.md) · [知识补遗](docs/ch16.md) · [HTML 交互版](index.html)

---

## 1. 文档骨架（背下来）

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>页面标题</title>
  <meta name="description" content="一句话描述">
  <link rel="icon" href="favicon.ico">
  <link rel="stylesheet" href="style.css">
  <script src="app.js" defer></script>
</head>
<body>
  <header>…<nav>…</nav></header>
  <main>…</main>
  <footer>…</footer>
</body>
</html>
```

**四条铁律**：DOCTYPE 第一行 · charset 最靠前 · viewport 必写 · 页面只有一个 `main`。

---

## 2. 标签分类速查

| 分类 | 标签 |
| --- | --- |
| 文档结构 | `html` `head` `body` `title` `base` `link` `meta` `style` `script` `noscript` |
| 页面分区 | `header` `nav` `main` `article` `section` `aside` `footer` `div` `span` |
| 标题段落 | `h1`~`h6` `p` `br` `hr` `pre` `blockquote` `figure` `figcaption` |
| 行内语义 | `a` `strong` `em` `b` `i` `del` `ins` `sub` `sup` `mark` `small` `q` `code` `time` `abbr` `cite` |
| 列表 | `ul` `ol` `li` `dl` `dt` `dd` |
| 图片媒体 | `img` `picture` `source` `audio` `video` `track` `svg` `canvas` `iframe` `object` `embed` |
| 表格 | `table` `caption` `colgroup` `col` `thead` `tbody` `tfoot` `tr` `th` `td` |
| 表单 | `form` `fieldset` `legend` `label` `input` `textarea` `select` `optgroup` `option` `button` `datalist` `output` |
| HTML5 交互 | `details` `summary` `dialog` `progress` `meter` `template` |

**空元素（无结束标签）**：`area` `base` `br` `col` `embed` `hr` `img` `input` `link` `meta` `param` `source` `track` `wbr`

---

## 3. 全局属性

| 属性 | 作用 | 属性 | 作用 |
| --- | --- | --- | --- |
| `id` | 文档内唯一标识 | `class` | 可复用类名（空格分隔多值） |
| `style` | 行内样式（少用） | `title` | 悬停提示 |
| `lang` / `dir` | 语言 / 文字方向 | `data-*` | 自定义数据，JS 用 `dataset` 读 |
| `hidden` | 布尔属性，隐藏元素 | `tabindex` | Tab 顺序（0 可聚焦、-1 仅脚本） |
| `contenteditable` | 内容可编辑 | `draggable` | 可拖拽 |
| `spellcheck` | 拼写检查 | `translate` | 是否参与翻译 |
| `role` / `aria-*` | 辅助技术语义补充 | `accesskey` | 快捷键（少用） |

---

## 4. input 类型与常用属性

| type | 用途 | type | 用途 |
| --- | --- | --- | --- |
| `text` | 单行文本 | `password` | 密码 |
| `email` `url` `tel` | 带格式校验 / 移动端键盘 | `search` | 搜索框 |
| `number` | 数字（min/max/step） | `range` | 滑块 |
| `date` `time` `datetime-local` `month` `week` | 日期时间 | `color` | 取色器 |
| `radio` | 单选（同组 name 相同） | `checkbox` | 多选 |
| `file` | 上传（配 `accept` / `multiple`） | `hidden` | 隐藏字段 |
| `submit` `reset` `button` | 按钮 | — | — |

| 属性 | 作用 |
| --- | --- |
| `name` / `value` | 提交时的键与值（**没有 name 不提交**） |
| `required` / `readonly` / `disabled` | 必填 / 只读 / 禁用 |
| `placeholder` / `autocomplete` / `autofocus` | 占位提示 / 自动填充 / 自动聚焦 |
| `pattern` / `minlength` / `maxlength` | 正则与长度校验 |
| `min` / `max` / `step` | 数值范围与步长 |
| `checked` / `selected` / `multiple` | 布尔属性：**写上即生效** |

**form 属性**：`action` `method`(get/post) `enctype`(上传文件用 `multipart/form-data`) `target` `autocomplete` `novalidate`

---

## 5. 表格 / 链接 / 图片高频属性

| 元素 | 属性 |
| --- | --- |
| `a` | `href`(URL / `#锚点` / `mailto:` / `tel:`) `target` `rel="noopener"` `download` `hreflang` |
| `img` | `src` **`alt`（必写）** `width` `height` `srcset` `sizes` `loading="lazy"` `decoding` |
| `table` 单元格 | `colspan` `rowspan` `scope` `headers` |
| `video` / `audio` | `src` `controls` `poster` `autoplay`(需 `muted`) `loop` `preload` |
| `iframe` | `src` **`title`** `sandbox` `allow` `loading` `referrerpolicy` |
| `script` | `src` `defer`(推荐) `async`(独立脚本) `type="module"` `crossorigin` `integrity` |
| `link` | `rel`(stylesheet / icon / preload / preconnect / canonical) `href` `media` |

---

## 6. 常用字符实体

| 显示 | 实体 | 显示 | 实体 |
| --- | --- | --- | --- |
| 不换行空格 | `&nbsp;` | `<` `>` | `&lt;` `&gt;` |
| `&` | `&amp;` | `"` `'` | `&quot;` `&#39;` |
| © ® ™ | `&copy;` `&reg;` `&trade;` | × ÷ | `&times;` `&divide;` |

---

## 7. 语义化页面模板

```html
<header>
  <h1>站点名</h1>
  <nav aria-label="主导航"><a href="/">首页</a> …</nav>
</header>
<main id="main">
  <article>
    <header><h2>文章标题</h2><time datetime="2026-11-18">2026-11-18</time></header>
    <section><h3>章节</h3><p>正文…</p></section>
    <figure><img src="a.png" alt="描述"><figcaption>图注</figcaption></figure>
  </article>
  <aside>相关阅读</aside>
</main>
<footer>版权信息</footer>
```

---

## 8. 十个最容易错的点

1. 漏 `<!DOCTYPE html>` → 怪异模式，盒模型异常。
2. 文件编码与 `charset` 不一致 → 中文乱码。
3. 图片没写 `alt`，装饰图没写 `alt=""`。
4. `target="_blank"` 忘了 `rel="noopener"`。
5. 表单控件漏 `name` → 提交数据丢失。
6. 用 `<br><br>` 撑间距、用 `<h1>` 只为变大 → 语义错乱。
7. `<p>` 里嵌 `<div>` → 浏览器自动闭合段落。
8. 嵌套列表直接放在 `<ul>` 下（应放进 `<li>`）。
9. `colspan` 合并后没删多余单元格 → 表格错位。
10. 移动端漏 `viewport` → 页面被缩小、字号异常。

---

## 9. 复习路径

**速查本页 → [分章笔记](docs/ch01.md) → [知识补遗](docs/ch16.md) → [45 道自测题](REVIEW.md) → [HTML 交互版](index.html) 动手改代码看效果。**
