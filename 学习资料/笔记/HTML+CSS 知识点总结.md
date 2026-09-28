# HTML + CSS 知识点总结

> 依据本文件夹四份笔记整理：`HTML4笔记.pdf`、`HTML5笔记.pdf`、`CSS2笔记.pdf`、`CSS3笔记.pdf`

---

## 第一部分　HTML4 基础

### 一、前序知识

| 项目 | 要点 |
| --- | --- |
| 计算机 | 硬件（看得见摸得着）+ 软件（指挥硬件的指令） |
| 软件分类 | 系统软件（Windows / Linux / Android / Harmony）、应用软件（微信 / QQ / 王者荣耀 / PhotoShop） |
| C/S 架构 | client-server，需安装、偶尔更新、不跨平台、开发更具针对性 |
| B/S 架构 | browser-server，无需安装、无需更新、可跨平台、开发更具通用性 |
| 前端工程师 | 主要负责编写 B/S 架构中的网页（呈现界面、实现交互） |
| 五大浏览器 | Chrome、Safari、IE、Firefox、Opera |
| 网页相关概念 | 网址（输入的地址）、网页（呈现的每一个页面）、网站（多个网页构成） |

### 二、HTML 简介

- **全称**：HyperText Markup Language（超文本标记语言）
  - 超文本：比普通文本内容更丰富
  - 标记：文本变成超文本需要各种标记符号
  - 语言：标记的写法、读音、使用规则组成标记语言
- **国际组织**：
  - IETF（1985 年底）：互联网技术标准化组织
  - W3C（1994 年）：万维网联盟，Web 领域最具影响力的标准机构
  - WHATWG（2004 年）：网页超文本应用技术工作小组，推动 HTML5 标准
- **最新标准**：HTML5

### 三、HTML 入门（必背）

1. **标签（元素）**：HTML 的基本组成单位；分**双标签**与**单标签**（绝大多数是双标签）；标签名不区分大小写，推荐小写。
2. **标签关系**：并列关系、嵌套关系。
3. **标签属性**：给标签提供附加信息，写在**起始标签**或**单标签**中。
   - 属性名、属性值都不区分大小写，推荐小写
   - 推荐使用双引号
   - 标签中不要出现同名属性，否则后写的失效
   - 特殊属性可以没有属性名，只有属性值，如 `<input disabled>`
4. **基本结构**：
   ```html
   <html>
     <head>
       <title>网页标题</title>
     </head>
     <body>……</body>
   </html>
   ```
   - 想呈现的内容写在 `body` 中；`head` 内容不显示；`title` 指定网页标题
5. **【检查】与【查看网页源代码】的区别**：前者看到的是浏览器"处理"后的源代码，后者是程序员编写的源代码；日常开发中【检查】用得最多。
6. **注释**：`<!-- 注释 -->`，会被浏览器忽略，**不能嵌套**。
7. **文档声明**：告诉浏览器网页版本，必须写在**网页第一行**、且在 **html 标签外侧**。推荐 `<!DOCTYPE html>`。
8. **字符编码**：
   | 字符集 | 内容 |
   | --- | --- |
   | ASCII | 大小写字母、数字、符号，共 128 个 |
   | ISO 8859-1 | 扩充希腊字符等，共 256 个 |
   | GB2312 | 6763 个常用汉字、682 个字符 |
   | GBK | 汉字和符号 20000+，支持繁体 |
   | **UTF-8** | 包含世界上所有语言的文字与符号（最常用） |
   - 原则 1：存储时务必采用合适的字符编码，否则数据丢失
   - 原则 2：存储时用什么编码，读取时就用什么解码，否则乱码
   - 统一采用 UTF-8，用 `<meta charset="UTF-8"/>` 指定
9. **设置语言**：`<html lang="zh-CN">`，作用是有利于搜索引擎优化、显示对应翻译提示。`zh-CN` 中国大陆、`zh-TW` 中国台湾、`en-US` 美国。
10. **标准结构**：输入 `!` 回车即可生成；存放 `favicon.ico` 可配置网站图标。

### 四、HTML 基础

#### 1. 排版标签

| 标签 | 含义 | 类型 |
| --- | --- | --- |
| `h1`~`h6` | 标题 | 双 |
| `p` | 段落 | 双 |
| `div` | 无含义，用于整体布局 | 双 |

- `h1` 最好只写一个；`h1`~`h6` 不能互相嵌套
- `p` 中不能有 `h1`~`h6`、`p`、`div`

#### 2. 语义化标签

概念：用特定的标签表达特定的含义。**原则：标签的默认效果不重要，语义最重要**。
优势：结构清晰可读性强、有利于 SEO、方便设备解析（屏幕阅读器）。

#### 3. 块级元素与行内元素

- 块级元素：独占一行；行内元素：不独占一行
- 使用原则：块级元素中几乎什么都能写；行内元素中只能写行内元素，不能写块级元素
- 特殊规则：`h1`~`h6` 不能互相嵌套；`p` 中不要写块级元素
- `marquee` 已废弃，不推荐使用

#### 4. 常用文本标签（行内元素）

`em`（着重阅读）、`strong`（十分重要）、`span`（无语义通用容器）、`cite`（作品标题）、`dfn`（特殊术语）、`del`/`ins`（删除/插入文本）、`sub`/`sup`（下标/上标）、`code`（代码）、`samp`（设备输出）、`kbd`（键盘文本）、`abbr`（缩写，配合 title）、`bdo`（改变文本方向，配合 dir）、`var`（变量）、`address`（地址信息，块级）、`blockquote`（长引用，块级）。
很少使用：`small`、`b`、`i`、`u`、`q`。

#### 5. 图片标签 `img`（单标签）

- `src`：图片路径；`alt`：图片描述；`width`/`height`：宽高（像素）
- `alt` 最主要的作用：**让搜索引擎得知图片的内容**；图片无法展示时显示；盲人阅读器朗读
- 尽量不同时修改宽高，避免比例失调
- **路径**：
  - 相对路径：`./` 同级（可省略）、`/` 下一级、`../` 上一级
  - 绝对路径：本地绝对路径（很少用）、网络绝对路径（注意防盗链）
- **图片格式**：

| 格式 | 特点 |
| --- | --- |
| jpg/jpeg | 有损压缩，颜色丰富、体积小、不支持透明和动态 |
| png | 无损压缩，质量高、支持透明、不支持动态 |
| bmp | 不压缩，细节多、体积极大、不支持透明和动态 |
| gif | 仅 256 色、支持简单透明、支持动态 |
| webp | 兼具多种优点，但兼容性不太好 |
| base64 | 图片编码成文本，直接作为 src 的值，不受文件位置影响 |

#### 6. 超链接 `a`

- `href`：跳转目标；`target`：`_self`（本窗口）、`_blank`（新窗口）；`id`/`name` 可设置锚点
- `download` 属性可强制触发下载
- 锚点：`<a name="test1"></a>` 或 `<h2 id="test2">`；`href="#"` 回到顶部；`href=""` 刷新本页面
- 唤起应用：`tel:`、`mailto:`、`sms:`
- 多个空格、多个回车都会被浏览器解析成一个空格
- `a` 是行内元素，但可以包裹除自身外的任何元素

#### 7. 列表

- 有序列表 `ol > li`；无序列表 `ul > li`；列表可以嵌套（结构要写完整）
- 自定义列表 `dl > dt + dd`（一个 `dt` 术语名可对应多个 `dd` 描述）
- `li` 最好写在 `ul` 或 `ol` 中

#### 8. 表格

结构：`table`（表格）、`caption`（标题）、`thead`（头部）、`tbody`（主体）、`tfoot`（脚注）、`tr`（行）、`th`/`td`（单元格）。

常用属性：
- `table`：`width`、`height`（最小高度）、`border`（边框宽度）、`cellspacing`（单元格间距）
- `thead`/`tbody`/`tfoot`/`tr`：`height`、`align`（left/center/right）、`valign`（top/middle/bottom）
- `td`/`th`：`width`、`height`、`align`、`valign`、`rowspan`（跨行）、`colspan`（跨列）

注意：`border` 只控制表格最外侧边框宽度；列宽默认由该列最长文字决定；设置某个单元格宽/高后，所在整列/整行随之确定。

#### 9. 常用标签补充

`br`（换行，单）、`hr`（分隔，单）、`pre`（按原文显示，常用于嵌入大段代码，双）。
不要用 `br` 增加行间隔，应使用 `p` 或 CSS 的 `margin`。

#### 10. 表单

- `form`：`action`（提交地址）、`target`（_self/_blank）、`method`（get/post）
- 常用控件：
  - 文本输入框 `<input type="text">`：`name`、`value`（默认值）、`maxlength`
  - 密码输入框 `<input type="password">`
  - 单选框 `radio`：多个 radio 的 `name` 必须一致；`value`、`checked`
  - 复选框 `checkbox`：`name`、`value`、`checked`
  - 隐藏域 `hidden`：`name`、`value`，用于携带固定数据
  - 提交按钮 `submit`、重置按钮 `reset`、普通按钮 `button`（`button` 标签 type 默认值是 submit，且不要指定 name）
  - 文本域 `textarea`：`rows`（行数→高度）、`cols`（列数→宽度），不能写 type
  - 下拉框 `select > option`：`name`、`value`（不写 value 则提交标签中间文字）、`selected`
- `disabled` 可禁用：`input`、`textarea`、`button`、`select`、`option`
- `label` 关联表单控件的两种方式：`for` 等于控件的 `id`；或把控件套在 `label` 里
- `fieldset` 分组 + `legend` 分组标题

#### 11. 框架标签 `iframe`

在网页中嵌入其他文件。属性：`name`（可与 target 配合）、`width`、`height`、`frameborder`（0 或 1）。
应用：嵌入广告、与超链接或表单的 target 配合展示不同内容。

#### 12. HTML 实体

由 `&` + 实体名称（或 `#` + 实体编号）+ `;` 组成。
常用：`&nbsp;`（空格）、`&lt;`、`&gt;`、`&amp;`、`&quot;`、`&copy;`、`&reg;`、`&trade;`、`&times;`、`&divide;`、`&yen;`。

#### 13. 全局属性

`id`（唯一标识，不能重复）、`class`（类名）、`style`、`dir`（ltr/rtl）、`title`（文字提示）、`lang`。

#### 14. meta 元信息

字符编码、IE 兼容性（`X-UA-Compatible`）、移动端 viewport、关键字 `keywords`、描述 `description`、搜索引擎爬虫 `robots`（index/noindex、follow/nofollow、all/none、noarchive）、作者 `author`、生成工具 `generator`、版权 `copyright`、自动刷新 `refresh`。

---

## 第二部分　HTML5 新增

### 一、简介

- 2014 年 10 月由 W3C 完成标准制定；狭义指新一代 HTML 标准，广义指整个前端
- 优势：新增可操作接口、新增语义化标签与全局属性、新增多媒体标签替代 flash、更侧重语义化对 SEO 友好、可移植性好
- 兼容性：IE 必须 9 及以上才支持，且 IE9 仅支持部分新特性

### 二、新增语义化标签

`header`（头部）、`footer`（底部）、`nav`（导航）、`article`（文章/帖子/新闻）、`section`（某段文字，通常含标题）、`aside`（侧边栏）、`main`（主要内容，IE 不支持，几乎不用）、`hgroup`（连续标题，W3C 已删除）。

> article 与 section：一个 article 里可以有多个 section；section 强调分段分块；article 更强调独立性。

### 三、新增状态标签

- `meter`：已知范围内的标量测量。属性：`high`、`low`、`max`、`min`、`optimum`、`value`
- `progress`：任务完成进度条。属性：`max`（目标值）、`value`（当前值）

### 四、新增列表标签

`datalist`（搜索框关键字提示，配合 `input` 的 `list` 属性）、`details` + `summary`（展示问题和答案）。

### 五、新增文本标签

- `ruby` + `rt`：文本注音
- `mark`：标记，W3C 建议用于标记搜索结果中的关键字

### 六、新增表单功能

| 新增属性 | 功能 |
| --- | --- |
| `placeholder` | 提示文字（不是默认值，value 才是默认值） |
| `required` | 必填，适用于除按钮外其他表单控件 |
| `autofocus` | 自动获取焦点，适用于所有表单控件 |
| `autocomplete` | 自动完成 on/off；密码框、多行输入框不可用 |
| `pattern` | 正则校验；多行输入不可用；空的输入框不验证 |

新增 `input` 的 type 值：`email`、`url`、`number`（三者提交时验证格式，为空不验证）、`search`、`tel`、`range`（默认 50）、`color`（默认黑色）、`date`、`month`、`week`、`time`、`datetime-local`。
`form` 新增属性：`novalidate`（提交时不再验证）。

### 七、新增多媒体标签

- `video`（双标签）：`src`、`width`、`height`、`controls`、`muted`、`autoplay`、`loop`、`poster`、`preload`（auto/metadata/none；若使用 autoplay 则忽略该属性）
- `audio`（双标签）：`src`、`controls`、`autoplay`、`muted`、`loop`、`preload`

### 八、新增全局属性

`contenteditable`、`draggable`、`hidden`、`spellcheck`、`contextmenu`、`data-*`。

### 九、HTML5 兼容性处理

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
<meta name="renderer" content="webkit">
<!--[if lt ie 9]>
<script src="../sources/js/html5shiv.js"></script>
<![endif]-->
```
条件注释运算符：`lt` 小于、`lte` 小于等于、`gt` 大于、`gte` 大于等于、`!` 逻辑非。

---

## 第三部分　CSS2 基础

### 一、CSS 基础

- 全称：Cascading Style Sheets（层叠样式表）
- 核心思想：HTML 搭建结构，CSS 添加样式，实现**结构与样式的分离**

**三种编写位置**：

| 分类 | 优点 | 缺点 | 使用频率 | 作用范围 |
| --- | --- | --- | --- | --- |
| 行内样式（`style` 属性） | 优先级最高 | 未分离、结构混乱、不能复用 | 很低 | 当前标签 |
| 内部样式（`<style>`） | 可复用、结构清晰 | 未彻底分离、不能多页面复用 | 一般 | 当前页面 |
| 外部样式（`.css` + `<link>`） | 可多页面复用、结构清晰、可触发缓存、彻底分离 | 需引入 | **最高** | 多个页面 |

- 优先级：**行内样式 > 内部样式 = 外部样式**；同级遵循"后来者居上"
- `<link rel="stylesheet" href="./xxx.css">`，link 标签要写在 `head` 中
- 语法规范：选择器 + 声明块；声明格式 `属性名: 属性值;`
- 注释 `/* …… */`
- 代码风格：展开风格（开发时推荐）、紧凑风格（上线时推荐，减小体积）

### 二、选择器

**基本选择器**

| 选择器 | 特点 | 用法 |
| --- | --- | --- |
| 通配 `*` | 选中所有标签，一般用于清除样式 | `*{color:red}` |
| 元素 | 选中所有同种标签，不能差异化 | `h1{color:red}` |
| 类 `.` | 按 class 值选中，使用频率很高 | `.say{color:red}` |
| id `#` | 选中 id 唯一的那一个元素 | `#earthy{color:red}` |

- 类选择器注意：class 值不带 `.`，选择器要带；一个元素不能写多个 class 属性，但一个 class 属性可写多个值（空格隔开）
- id 值：尽量字母、数字、下划线、短杠组成，最好字母开头、不含空格、区分大小写；一个元素只能有一个 id，多个元素 id 不能相同

**复合选择器**

- 交集选择器：`选择器1选择器2{}`，含义"并且"；有标签名必须写在前面；最常用 `p.beauty`
- 并集选择器：`选择器1,选择器2{}`，含义"或者"；一般竖着写，用于集体声明
- 后代选择器：`祖先 后代{}`，空格隔开
- 子代选择器：`父 > 子{}`
- 相邻兄弟选择器：`前 + 后{}`；通用兄弟选择器：`前 ~ 后{}`（都选择下面的兄弟）
- 属性选择器：`[属性名]`、`[属性名="值"]`、`[属性名^="值"]`（开头）、`[属性名$="值"]`（结尾）、`[属性名*="值"]`（包含）

**伪类选择器**

- 动态伪类：`:link`、`:visited`、`:hover`、`:active`、`:focus`（表单元素才有；顺序 **LVHA**）
- 结构伪类：`:first-child`、`:last-child`、`:nth-child(n)`、`:first-of-type`、`:last-of-type`、`:nth-of-type(n)`
  - n 的取值：`2n`/`even` 偶数、`2n+1`/`odd` 奇数、`-n+3` 前 3 个
  - 了解：`:nth-last-child`、`:nth-last-of-type`、`:only-child`、`:only-of-type`、`:root`、`:empty`
- 否定伪类：`:not(选择器)`
- UI 伪类：`:checked`、`:enabled`、`:disabled`
- 目标伪类 `:target`、语言伪类 `:lang()`

**伪元素选择器**：`::first-letter`、`::first-line`、`::selection`、`::placeholder`、`::before`、`::after`（后两者必须用 `content` 指定内容）。

**优先级（权重）**：
- 简记：行内样式 > ID 选择器 > 类选择器 > 元素选择器 > 通配选择器
- 详细：(a, b, c)，a=ID 个数、b=类/伪类/属性个数、c=元素/伪元素个数
- 比较规则：从左到右依次比较，当前位胜出后不再对比，如 (1,0,0) > (0,2,2)
- 特殊规则：`!important` > 行内样式 > 所有选择器
- 并集选择器的每一个部分**分开算**

### 三、三大特性

1. **层叠性**：样式冲突时按优先级进行覆盖
2. **继承性**：元素自动拥有父元素/祖先元素的某些样式，优先继承离得近的
   - 可继承：`text-??`、`font-??`、`line-??`、`color` 等（不影响布局的）
   - 不可继承：边框、背景、内边距、外边距、宽高、溢出方式
3. **优先级**：`!important` > 行内样式 > ID > 类 > 元素 > `*` > 继承的样式

### 四、常用属性

**颜色表示**：颜色名；`rgb`/`rgba`（0~255 或百分比，a 为透明度）；`HEX`/`HEXA`（`#rrggbb`，可简写 `#f98`、`#f986`）；`HSL`/`HSLA`（色相 0~360、饱和度 0%~100%、亮度 0%~100%）。
- `rgb(0,0,0)` 黑，`rgb(255,255,255)` 白；三值相同为灰色
- IE 不支持 HEXA，但支持 HEX
- 开发中常用 rgb/rgba 或 HEX/HEXA

**字体属性**
- `font-size`：Chrome 最小 12px、默认 16px；不同浏览器默认不一致；通常给 body 设置
- `font-family`：英文名兼容性更好；含空格要加引号；可写多个按序查找，最后通常写 `serif` 或 `sans-serif`
- `font-style`：`normal`、`italic`（推荐）、`oblique`
- `font-weight`：`lighter`/`normal`/`bold`/`bolder`；数值 100~1000，400~500 等同 normal，600 及以上等同 bold
- `font` 复合：**字体大小、字体族必须都写**；字体族最后一位，字体大小倒数第二位

**文本属性**
- `color` 文字颜色
- `letter-spacing` 字母间距、`word-spacing` 单词间距（按空格识别词）
- `text-decoration`：`none`、`underline`、`overline`、`line-through`，可搭配 `dotted`、`wavy`、颜色
- `text-indent` 首行缩进
- `text-align`：`left`（默认）、`right`、`center`
- `line-height`：`normal`、px、数字（自身 font-size 的倍数，很常用）、百分比；最小值为 0，不能为负；可继承
  - 应用：多行文字控制行距；单行文字让 `height = line-height` 实现垂直居中
- `vertical-align`：`baseline`（默认）、`top`、`middle`、`bottom`；**不能控制块元素**

**列表属性**：`list-style-type`（`none` 很常用、`square`、`disc`、`decimal` 等）、`list-style-position`（inside/outside）、`list-style-image`、`list-style` 复合。

**表格属性**：边框相关（`border-width`/`border-color`/`border-style`/`border`，其他元素也能用）；表格独有（`table-layout`、`border-spacing`、`border-collapse`、`empty-cells`、`caption-side`）。

**背景属性**：`background-color`（默认 transparent）、`background-image`、`background-repeat`（repeat/repeat-x/repeat-y/no-repeat）、`background-position`（关键字或坐标）、`background` 复合。

**鼠标属性**：`cursor`：`pointer`（小手）、`move`、`text`、`crosshair`、`wait`、`help`；可自定义 `cursor: url("./arrow.png"),pointer;`。

### 五、盒子模型

**长度单位**：`px`、`em`（相对元素 font-size 的倍数）、`rem`（相对根字体大小）、`%`（相对父元素）。CSS 中设置长度必须加单位。

**显示模式**

| 模式 | 是否独占一行 | 默认宽度 | 默认高度 | 能否设置宽高 |
| --- | --- | --- | --- | --- |
| 块 block | 是 | 撑满父元素 | 由内容撑开 | 可以 |
| 行内 inline | 否 | 由内容撑开 | 由内容撑开 | 不可以 |
| 行内块 inline-block | 否 | 由内容撑开 | 由内容撑开 | 可以 |

- 块元素：`html`/`body`、`h1`~`h6`/`hr`/`p`/`pre`/`div`、`ul`/`ol`/`li`/`dl`/`dt`/`dd`、`table`/`thead`/`tbody`/`tfoot`/`tr`/`caption`、`form`/`option`
- 行内元素：`br`/`em`/`strong`/`sup`/`sub`/`del`/`ins`、`a`/`label`
- 行内块元素：`img`、`td`/`th`、`input`/`textarea`/`select`/`button`、`iframe`
- `display`：`none`（隐藏）、`block`、`inline`、`inline-block`

**盒子组成**：`margin`（外边距）、`border`（边框）、`padding`（内边距）、`content`（内容）
- 盒子大小 = content + 左右 padding + 左右 border
- margin 不影响盒子大小，但影响盒子位置

**content**：`width`/`max-width`/`min-width`/`height`/`max-height`/`min-height`
**padding**：`padding-top/right/bottom/left`、`padding`（1~4 个值，上右下左顺时针）；不能为负数；行内元素的上下内边距不能完美设置
**border**：`border-style`（none/solid/dashed/dotted/double）、`border-width`（默认 3px）、`border-color`（默认黑色）、`border` 复合；共 20 个边框属性
**margin**：四个方向、`margin` 复合；子元素 margin 参考父元素的 content；上/左 margin 影响自己位置，下/右影响后面兄弟；行内元素上下 margin 无效；`margin: 0 auto` 可实现块级元素水平居中；可为负值

- **margin 塌陷**：第一个子元素的上 margin 会作用在父元素上，最后一个子元素的下 margin 会作用在父元素上
  - 解决：①父元素设置不为 0 的 padding；②父元素设置宽度不为 0 的 border；③父元素 `overflow:hidden`
- **margin 合并**：上面兄弟的下外边距与下面兄弟的上外边距取最大值而非相加；无需解决

**处理内容溢出**：`overflow`：`visible`（默认）、`hidden`、`scroll`、`auto`；另有 `overflow-x`、`overflow-y`。

**隐藏元素**：`visibility:hidden`（看不见但占位）；`display:none`（彻底隐藏，不占位）。

**默认样式**：`a` 下划线/颜色/小手；`h1`~`h6` 加粗/字号/上下外边距；`p` 上下外边距；`ul`/`ol` 左内边距；`body` 8px 外边距。
优先级：元素默认样式 > 继承的样式。

**布局小技巧**
- 行内、行内块元素可被父元素当做文本处理（可用 `text-align`、`line-height`、`text-indent`）
- 子元素水平居中：块元素 → 父元素 `margin:0 auto`；行内/行内块 → 父元素 `text-align:center`
- 子元素垂直居中：块元素 → 子元素 `margin-top = (父 content − 子盒子总高)/2`；行内/行内块 → 父元素 `height = line-height` + 子元素 `vertical-align:middle`

**元素之间的空白问题**：行内、行内块元素之间的换行被解析为空白字符；解决方案：给父元素 `font-size:0`，再给需要显示文字的元素单独设置字体大小。

**行内块的幽灵空白问题**：行内块与文本基线对齐导致底部有间隙；解决方案：设置 `vertical-align` 不为 baseline；或图片 `display:block`；或父元素 `font-size:0`。

### 六、浮动

- 最初用于文字环绕图片，现为主流布局方式之一
- **特点**：脱离文档流；默认宽高由内容撑开且可设置宽高；不独占一行；不会 margin 合并/塌陷，能完美设置四方向 margin 和 padding；不会被当做文本处理
- **影响**：对兄弟——后面的兄弟元素会占据浮动元素之前的位置，显示在浮动元素下面；对父元素——不能撑起父元素高度，导致高度塌陷
- **清除浮动**：
  1. 给父元素指定高度
  2. 给父元素也设置浮动（带来其他影响）
  3. 给父元素设置 `overflow:hidden`
  4. 在所有浮动元素最后添加块级元素并设置 `clear:both`
  5. 给浮动元素的父元素设置伪元素清除浮动（**推荐**）
  ```css
  .parent::after { content: ""; display: block; clear: both; }
  ```
- 布局原则：兄弟元素要么全都浮动，要么全都不浮动
- `float`：`left`/`right`/`none`；`clear`：`left`/`right`/`both`

### 七、定位

| 定位 | 设置 | 参考点 | 是否脱离文档流 |
| --- | --- | --- | --- |
| 相对定位 | `position:relative` | 自己原来的位置 | 不脱离 |
| 绝对定位 | `position:absolute` | 包含块 | 脱离 |
| 固定定位 | `position:fixed` | 视口 | 脱离 |
| 粘性定位 | `position:sticky` | 最近的一个拥有"滚动机制"的祖先元素 | 不脱离 |

- **包含块**：没脱离文档流的元素 → 父元素；脱离文档流的元素 → 第一个拥有定位属性的祖先元素（都没有则整个页面）
- 共同点：`left` 不能与 `right` 同设，`top` 不能与 `bottom` 同设；都能用 margin 调整（不推荐）；定位元素显示层级高于普通元素
- 绝对/固定定位：与浮动同时设置时浮动失效；元素都变成"定位元素"（默认宽高由内容撑开，且可自由设置宽高）
- **定位层级**：`z-index`，数字无单位，值越大层级越高；**只有定位的元素设置才有效**
- **特殊应用**（仅针对绝对/固定定位）：
  - 宽充满包含块：`left:0; right:0;`；高充满：`top:0; bottom:0;`
  - 居中方案一：`left:0;right:0;top:0;bottom:0;margin:auto;`（必须设置宽高）
  - 居中方案二：`left:50%;top:50%;margin-left:-宽度一半;margin-top:-高度一半;`（或 `transform:translate(-50%,-50%)`）

### 八、布局

- **版心**：固定宽度且水平居中的盒子，宽度一般 960~1200px
- **常用布局名词**：`topbar`、`header`/`page-header`、`nav`/`navbar`、`search-box`、`banner`、`content`/`main`、`aside`/`sidebar`、`footer`/`page-footer`
- **重置默认样式**：方案一全局选择器 `*`；方案二 `reset.css`；方案三 `Normalize.css`（保留有价值的默认样式，更温和）

---

## 第四部分　CSS3 新增

### 一、简介与私有前缀

- CSS3 是 CSS2 的升级版本，按模块化发展
- 新特性：更实用的选择器、更好的视觉效果（圆角/阴影/渐变）、丰富的背景效果、弹性盒子、Web 字体、增强颜色（HSL/HSLA/RGBA、opacity）、2D/3D 变换、动画与过渡
- 私有前缀：`-webkit-`（Chrome/Safari/Edge）、`-moz-`（Firefox）、`-o-`（旧 Opera）、`-ms-`（旧 IE）
- 查询兼容性：caniuse.com

### 二、基本语法

**新增长度单位**：`rem`（根元素字体大小的倍数）、`vw`（视口宽度的百分之多少）、`vh`（视口高度的百分之多少）、`vmax`、`vmin`。
**新增颜色**：rgba、hsl、hsla。

### 三、新增盒模型属性

- `box-sizing`：`content-box`（默认，宽高设置的是内容区）、`border-box`（怪异盒模型，宽高设置的是盒子总大小）
- `resize`：`none`（默认）、`both`、`horizontal`、`vertical`
- `box-shadow: h-shadow v-shadow blur spread color inset`（前两个必须写；默认值 none）
- `opacity`：0~1，设置整个元素（含内容）的不透明度；与 rgba 的区别是后者只调整颜色透明度

### 四、新增背景属性

- `background-origin`：`padding-box`（默认）、`border-box`、`content-box`
- `background-clip`：`border-box`（默认）、`padding-box`、`content-box`、`text`（需加 `-webkit-` 前缀）
- `background-size`：长度值、百分比、`auto`（默认）、`contain`（等比缩放完整包含，可能有留白）、`cover`（等比缩放完全覆盖，可能显示不完整，相对较好）
- `background: color url repeat position / size origin clip`（size 必须写在 position 后面并用 `/` 分开；origin 和 clip 只写一个值则同时设置）
- 多背景图：用逗号分隔多组背景

### 五、新增边框属性

- `border-radius`：`border-top-left-radius`、`border-top-right-radius`、`border-bottom-right-radius`、`border-bottom-left-radius`；一个值是正圆半径，两个值是椭圆的 x/y 半径
- 综合写法：`border-radius: 左上x 右上x 右下x 左下x / 左上y 右上y 右下y 左下y`
- 外轮廓：`outline-width`、`outline-color`、`outline-style`（none/dotted/dashed/solid/double）、`outline-offset`（与边框的距离，独立属性）、`outline` 复合

### 六、新增文本属性

- `text-shadow: h-shadow v-shadow blur color`（前两个必须写）
- `white-space`：`normal`（默认）、`pre`、`pre-wrap`、`pre-line`、`nowrap`（强制不换行）
- `text-overflow`：`clip`（默认）、`ellipsis`；生效条件：块容器必须显式定义 `overflow` 非 visible，且 `white-space:nowrap`
- `text-decoration` 升级为复合属性：`text-decoration-line`、`text-decoration-style`（solid/double/dotted/dashed/wavy）、`text-decoration-color`
- 文本描边（仅 webkit 内核）：`-webkit-text-stroke-width`、`-webkit-text-stroke-color`、`-webkit-text-stroke`

### 七、新增渐变

- 线性渐变 `linear-gradient`：默认从上到下；关键词方向 `to top`、`to right top`；角度 `30deg`；位置 `red 50px, yellow 100px, green 150px`
- 径向渐变 `radial-gradient`：默认从圆心四散；`at right top`、`at 100px 50px` 调整圆心；`circle` 正圆；`100px`、`50px 100px` 调整半径
- 重复渐变：`repeating-linear-gradient`、`repeating-radial-gradient`

### 八、Web 字体

```css
@font-face { font-family: "情书字体"; src: url('./方正手迹.ttf'); }
```
高兼容性写法依次提供 `eot`、`woff2`、`woff`、`ttf`、`svg` 并配合 `format()`。
字体图标优点：比图片清晰、灵活性高、兼容性好。阿里图标库：https://www.iconfont.cn/

### 九、2D 变换

- `transform`，可链式编写；**位移对行内元素无效**
- 位移：`translateX`、`translateY`、`translate`（百分比参考自身宽高）；不脱离文档流；与相对定位的区别是百分比参考自身而非父元素
- 缩放：`scaleX`、`scaleY`、`scale`（1 不缩放，>1 放大，<1 缩小）；可实现小于 12px 的文字
- 旋转：`rotate(deg)`，正值顺时针，负值逆时针；`rotateZ(20deg)` 相当于 `rotate(20deg)`
- 扭曲：`skewX`、`skewY`、`skew`（几乎不用）
- 多重变换：建议**最后旋转**
- 变换原点：`transform-origin`，默认元素中心；对位移无影响，对旋转和缩放有影响

### 十、3D 变换

- **首要操作**：父元素必须开启 3D 空间 —— `transform-style: preserve-3d`（默认 flat）
- 景深：`perspective`，设置给**父元素**；`none`（默认）或长度值（不允许负值）
- 透视点位置：`perspective-origin`，默认在元素中心，通常不需要调整
- 3D 位移：`translateZ`（正值向屏幕外，不能写百分比）、`translate3d(x,y,z)`（不能省略）
- 3D 旋转：`rotateX`、`rotateY`、`rotate3d(x,y,z,deg)`
- 3D 缩放：`scaleZ`、`scale3d(x,y,z)`
- 背部可见性：`backface-visibility`：`visible`（默认）、`hidden`；加在发生 3D 变换元素的**自身**上

### 十一、过渡 transition

- `transition-property`：`none`、`all`、具体属性名（多个用逗号分隔）；值为数字或能转为数字的属性才支持过渡
- `transition-duration`：默认 0；s 或 ms
- `transition-delay`：延迟时间
- `transition-timing-function`：`ease`（默认）、`linear`、`ease-in`（慢→快）、`ease-out`（快→慢）、`ease-in-out`、`step-start`、`step-end`、`steps(整数, start|end)`、`cubic-bezier(...)`
- 复合：一个时间表示 duration，两个时间分别是 duration 和 delay

### 十二、动画 animation

- 帧 / 关键帧概念
- 第一步：定义关键帧
  ```css
  @keyframes 动画名 { from { } to { } }
  @keyframes 动画名 { 0% { } 50% { } 100% { } }
  ```
- 第二步：应用动画 —— `animation-name`、`animation-duration`、`animation-delay`
- 其他属性：
  - `animation-timing-function`（取值同过渡）
  - `animation-iteration-count`：数字或 `infinite`
  - `animation-direction`：`normal`（默认）、`reverse`、`alternate`、`alternate-reverse`
  - `animation-fill-mode`：`forwards`（结束状态）、`backwards`（开始状态）
  - `animation-play-state`：`running`（默认）、`paused`（一般单独使用）
- 复合：一个时间表示 duration，两个时间分别是 duration 和 delay

### 十三、多列布局

`column-count`、`column-width`、`columns`（复合）、`column-gap`、`column-rule-style`、`column-rule-width`、`column-rule-color`、`column-rule`（复合）、`column-span`（none/all）。

### 十四、伸缩盒模型（Flex）

- 2009 年 W3C 提出；传统布局 = display + position + float；flex 在移动端应用广泛
- **伸缩容器**：设置 `display:flex` 或 `display:inline-flex` 的元素
- **伸缩项目**：伸缩容器的**所有子元素**（孙辈不算）；无论原来是什么元素，成为伸缩项目后全部"块状化"
- **主轴**：默认水平、从左到右；**侧轴**：默认垂直、从上到下

| 属性 | 作用 | 常用值 |
| --- | --- | --- |
| `flex-direction` | 主轴方向 | `row`（默认）、`row-reverse`、`column`、`column-reverse` |
| `flex-wrap` | 主轴换行 | `nowrap`（默认）、`wrap`、`wrap-reverse` |
| `flex-flow` | 复合 direction + wrap | 无顺序要求 |
| `justify-content` | 主轴对齐 | `flex-start`（默认）、`flex-end`、`center`、`space-between`（最常用）、`space-around`、`space-evenly` |
| `align-items` | 侧轴对齐（一行） | `flex-start`、`flex-end`、`center`、`baseline`、`stretch`（默认） |
| `align-content` | 侧轴对齐（多行） | `flex-start`、`flex-end`、`center`、`space-between`、`space-around`、`space-evenly`、`stretch`（默认） |

- **水平垂直居中**：①父容器 `justify-content:center` + `align-items:center`；②父容器开启 flex 后子元素 `margin:auto`
- **伸缩性**：
  - `flex-basis`：主轴方向的基准长度，会让宽或高失效，默认 `auto`
  - `flex-grow`：放大比例，默认 0；都为 1 则等分剩余空间；1/2/3 则按 1/6、2/6、3/6 分配
  - `flex-shrink`：压缩比例，默认 1；收缩量按 `宽度 × shrink` 的比例分摊
- **flex 复合**：默认 `0 1 auto`
  - `flex:auto` = `1 1 auto`；`flex:1` = `1 1 0`；`flex:none` = `0 0 auto`
- `order`：排列顺序，数值越小越靠前，默认 0
- `align-self`：单独调整某个项目的对齐方式，默认 `auto`（继承父元素 align-items）

### 十五、响应式布局（媒体查询）

- **媒体类型**：`all`、`screen`、`print`、`aural`（已废弃）、`braille`、`embossed`、`handheld`、`projection`、`tty`、`tv`
- **媒体特性**：`width`、`max-width`、`min-width`、`height`、`max-height`、`min-height`、`device-width`、`max-device-width`、`min-device-width`、`orientation`（portrait 纵向 / landscape 横向）
- **运算符**：`and`（并且）、`,`（或）、`not`（否定）、`only`（肯定）
- **用法**：
  ```css
  @media screen and (max-width:768px) { /* CSS-Code */ }
  @media screen and (min-width:768px) and (max-width:1200px) { /* CSS-Code */ }
  ```
  ```html
  <link rel="stylesheet" media="具体的媒体查询" href="mystylesheet.css">
  ```

### 十六、BFC（块级格式上下文）

- 定义：Block Formatting Context，可以理解为元素的一个"特异功能"，满足条件后被激活（即创建了 BFC）
- **能解决的问题**：
  1. 子元素不再产生 margin 塌陷
  2. 自己不会被其他浮动元素覆盖
  3. 就算子元素浮动，自身高度也不会塌陷
- **如何开启**：根元素；浮动元素；绝对/固定定位元素；行内块元素；表格单元格（table、thead、tbody、tfoot、th、td、tr、caption）；`overflow` 值不为 visible 的块元素；伸缩项目；多列容器；`column-span:all` 的元素；`display:flow-root`
