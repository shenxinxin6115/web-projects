# HTML + CSS 专项突破练习册
> 六个专题 · 按难点拆分 · 逐个攻破 · 不计分

> **怎么用：**每个专题先看「速记卡」（一屏能扫完的要点），然后直接做题。 **点题号**可以把这题标记成"已做"（再点一次取消），右上角会显示进度。 做完一个专题再点「显示参考答案」对照，别边做边看。

## 目录

- [选择器与优先级](#t1)
- [盒模型与浮动布局](#t2)
- [定位](#t3)
- [Flex 伸缩盒模型](#t4)
- [2D / 3D 变换 · 过渡 · 动画](#t5)
- [响应式布局与 BFC](#t6)

## 专题一 选择器与优先级　25 题

> **速记卡**
>
> - **基本选择器**：`*` 通配 ／ `标签名` 元素 ／ `.类名` 类 ／ `#id` ID
> - **复合选择器**：交集 `p.box`（并且）／ 并集 `a, b`（或者）／ 后代 `a b` ／ 子代 `a > b` ／ 相邻兄弟 `a + b` ／ 通用兄弟 `a ~ b`
> - **属性**：`[attr]` ／ `[attr="v"]` ／ `^=` 开头 ／ `$=` 结尾 ／ `*=` 包含
> - **权重 (a, b, c)**：a = ID 数 ／ b = 类·伪类·属性 数 ／ c = 元素·伪元素 数
> - **比较**：从左到右逐位比，当前位胜出就不再比后面。`(1,0,0) > (0,2,2)`
> - **特例**：`!important` > 行内样式 > ID > 类 > 元素 > `*` > 继承；并集选择器**分开算**权重

**1.** 写出选中"类名为 box 的 div 元素"的选择器。

**2.** 写出选中"id 为 nav 的元素内部的**直接子元素** a"的选择器。

**3.** 写出选中"id 为 nav 的元素内部**所有后代** a"的选择器。

**4.** 写出选中"紧跟在 h2 后面的第一个 p"的选择器。

**5.** 写出选中"h2 后面所有同级 p"的选择器。

**6.** 写出选中"所有 title 属性以 http 开头的 a 元素"的选择器。

**7.** 写出选中"所有 href 以 .pdf 结尾的 a 元素"的选择器。

**8.** 写出选中"所有偶数序号的 li"（两种写法）。

**9.** 写出选中"前 3 个 li"的选择器。

**10.** 写出选中"除第一个以外的所有 li"的选择器。

**11.** 写出选中"被选中的复选框"的选择器。

**12.** 写出选中"被禁用（有 disabled）的表单控件"的选择器。

**13.** 写出选中"用户用鼠标选中（划蓝）的那部分文字"的伪元素。

**14.** 写出选中"输入框的提示文字"的伪元素。

**15.** 写出在元素**内容最前面**插入一段文字"必看"的伪元素写法。

**16.** 用一行选择器把页面上所有元素的 margin 和 padding 清零。

**17.** 计算权重：`ul > li`

**18.** 计算权重：`.nav li.item a`

**19.** 计算权重：`#app .list li:hover`

**20.** 计算权重：`div.card::before`

**21.** 下面两段代码，文字最终是什么颜色？为什么？

```
<style>
    #box .text { color: green; }   /* 权重 (1,1,0) */
    div .text  { color: red; }     /* 权重 (0,1,1) */
</style>
<div id="box"><p class="text">我是什么颜色</p></div>
```

**22.** 下面这段代码，p 最终是什么颜色？为什么？

```
<style>
    div { color: blue; }
    p { color: red; }
    .wrap { color: green; }
</style>
<div class="wrap">
    <p>我是什么颜色</p>
</div>
```

**23.** 下面的选择器能选中几号元素？说明原因。

```
<div class="a b">1</div>
<div class="a">2</div>
<div class="b">3</div>

.a.b { color: red; }
.a, .b { color: blue; }
```

**24.** 写出同时选中"id 为 header、类名为 top、或标签为 footer"这三种元素的并集选择器，并说明它的权重怎么算。

**25.** 写出选中"ul 中所有 li 里的 a"，但**排除**类名为 disabled 的那些 a 的选择器。

## 专题二 盒模型与浮动布局　20 题

> **速记卡**
>
> - **盒子**：margin（外）→ border（框）→ padding（内）→ content（内容）
> - **盒子大小** = content + 左右 padding + 左右 border；margin **不影响**盒子大小，只影响位置
> - **padding / margin 复合**：1 值 = 四方向；2 值 = 上下 / 左右；3 值 = 上 / 左右 / 下；4 值 = 上右下左（顺时针）
> - **padding 不能为负**；margin 可以为负，也可以 auto
> - **块级水平居中** `margin:0 auto` ／ **行内水平居中** 父元素 `text-align:center`
> - **单行垂直居中**：`height = line-height`
> - **margin 塌陷**：子元素上下 margin 作用到父元素上 → 父元素加非 0 padding / border / `overflow:hidden`
> - **margin 合并**：相邻兄弟上下 margin 取最大值 → **无需解决**
> - **浮动**：脱离文档流、可设宽高、不独占一行、无 margin 合并塌陷、不被当文本处理；父元素高度塌陷
> - **清除浮动推荐**：`.parent::after{content:"";display:block;clear:both;}`

**1.** 下面这个盒子的实际占位宽度是多少？内容区宽度是多少？

```
.box {
    width: 200px;
    padding: 10px 20px;
    border: 5px solid #333;
    margin: 0 30px;
}
```

**2.** 不设置 `width` 时，一个块级元素的"总宽度"和"内容区宽度"分别怎么计算？

**3.** `padding: 10px 20px 30px;` 四个方向分别是多少？

**4.** `margin: 5px 10px 15px 20px;` 四个方向分别是多少？

**5.** `margin: 0 auto;` 在什么条件下才能让元素水平居中？行内元素能用吗？

**6.** 给一个 `span` 设置 `margin: 50px 0;` 和 `padding: 50px 0;`，页面上会看到什么效果？为什么？

**7.** 一个宽 300px、高 100px 的 div，里面只有一行文字，如何让文字水平垂直居中？

**8.** 一个父元素里放了三个行内块元素，想让它们在父元素里水平居中，该给谁设置什么？

**9.** 复现 margin 塌陷：写出一段能观察到该现象的代码，并给出三种解决方案。

**10.** 什么是 margin 合并？为什么它不需要"解决"？布局时应该怎么做？

**11.** 一个宽高都是 200px 的盒子，里面有一段很长的文字。分别写出让溢出内容"隐藏"和"出现滚动条"的写法。

**12.** `visibility:hidden` 和 `display:none` 有什么区别？各自适合什么场景？

**13.** 一行里放了一张 `img`，图片下方总是多出几个像素的空隙。这是什么问题？写出三种解决办法。

**14.** 两个行内块元素写在两行（中间有换行），渲染出来中间多了一个空格。为什么？怎么解决？

**15.** 用 `box-sizing:border-box` 重写第 1 题，使盒子总宽度正好是 200px，写出代码并说明此时内容区宽度是多少。

**16.** 用浮动实现一个三栏布局：左 200px、右 200px、中间自适应，整体 1200px 居中，并清除浮动。

**17.** 接上题：把中间的 div 写在 HTML 的最前面（顺序为 中、左、右），还能实现吗？需要怎么调整？

**18.** 写出清除浮动的五种方案，并说明为什么推荐伪元素方案。

**19.** 下面的代码有什么问题？怎么改？

```
<div class="wrap">
    <div class="item">A</div>
    <div class="item">B</div>
    <p>我是后面的文字</p>
</div>
<style>
    .item { float: left; width: 100px; height: 100px; }
</style>
```

**20.** 用浮动做一个水平导航栏（四个 li 横向排列，有间距，超链接无下划线，悬停变色）。

## 专题三 定位　18 题

> **速记卡**
>
> - **relative**：参考自己原来的位置，**不脱离**文档流
> - **absolute**：参考包含块，**脱离**文档流
> - **fixed**：参考视口，**脱离**文档流
> - **sticky**：参考最近的有滚动机制的祖先，**不脱离**，最常用 top
> - **包含块**：未脱离 → 父元素；已脱离 → 第一个有定位的祖先元素（都没有则整个页面）
> - **共同点**：left/right 不能同设，top/bottom 不能同设；层级高于普通元素
> - **absolute / fixed** 与浮动同时设置 → 浮动失效；元素变成"定位元素"（可自由设宽高）
> - **z-index**：数字无单位，越大越靠上，**只有定位元素才有效**

**1.** 相对定位的参考点在哪里？它会不会影响周围元素的位置？

**2.** 绝对定位的参考点在哪里？分别写出"父元素有定位"和"所有祖先都没定位"两种情况下的结果。

**3.** 固定定位的参考点是什么？说出一个最典型的使用场景。

**4.** 粘性定位的参考点是什么？它和相对定位的共同点、区别分别是什么？

**5.** 让一个绝对定位元素的**宽度充满包含块**，怎么写？高度充满呢？

**6.** 写出让绝对定位元素在包含块中水平垂直居中的两种方案，并说明各自的前提条件。

**7.** 给一个普通 `div` 设置 `z-index:9999` 却不生效，可能是什么原因？

**8.** 两个都定位了的元素位置重叠，默认谁在上面？想改变顺序有哪两种办法？

**9.** 一个元素同时设置了 `float:left` 和 `position:absolute`，最终会怎样？

**10.** 行内元素 `span` 设置为绝对定位后，还能设置宽高吗？为什么？

**11.** 实现一个"回到顶部"按钮：固定在视口右下角，距离右边和下边各 30px。

**12.** 实现一张图片右下角的"文字角标"（图片上叠一行半透明黑底白字）。

**13.** 一个元素想在自己原有位置基础上往右挪 10px、往下挪 20px，但不想影响后面元素，用定位怎么写？用 transform 又怎么写？

**14.** 实现一个粘性头部：页面滚动时导航栏固定在顶部，且不脱离文档流。

**15.** 用"绝对定位 + transform"实现水平垂直居中（要求元素宽高固定为 300×200），写出完整代码。

**16.** 下面的代码，子元素距离父元素的哪条边有多远？

```
<div class="parent">
    <div class="child"></div>
</div>
<style>
    .parent { width: 400px; height: 400px; padding: 20px;
              border: 10px solid #000; position: relative; }
    .child  { position: absolute; left: 0; top: 0;
              width: 50px; height: 50px; }
</style>
```

**17.** 接上题：如果父元素的 `position` 改成 `static`，子元素会跑到哪里？

**18.** 综合题：实现一个"弹窗遮罩"效果——半透明黑色遮罩铺满整个视口，弹窗 400×300 在视口正中。

## 专题四 Flex 伸缩盒模型　22 题

> **速记卡**
>
> - **容器**：`display:flex`；**项目**：容器的**所有子元素**（孙辈不算），全部"块状化"
> - **主轴**默认水平从左到右，**侧轴**默认垂直从上到下
> - **flex-direction**：row ／ row-reverse ／ column ／ column-reverse
> - **justify-content**（主轴）：flex-start ／ flex-end ／ center ／ space-between ／ space-around ／ space-evenly
> - **align-items**（侧轴·单行）：flex-start ／ flex-end ／ center ／ baseline ／ stretch
> - **align-content**（侧轴·多行）：同上 + stretch（默认）
> - **flex 复合**默认 `0 1 auto`；`flex:auto` = 1 1 auto；`flex:1` = 1 1 0；`flex:none` = 0 0 auto
> - **flex-grow** 默认 0（放大）／ **flex-shrink** 默认 1（收缩）／ **flex-basis** 默认 auto
> - **居中两法**：① 容器 justify-content + align-items；② 项目 `margin:auto`

**1.** 写出让一个 div 变成伸缩容器的代码。它的哪些元素会变成伸缩项目？

**2.** `display:flex` 和 `display:inline-flex` 有什么区别？

**3.** 写出 `flex-direction` 的四个取值及各自的主轴方向。改变了主轴后侧轴会怎样？

**4.** 写出 `flex-wrap` 的三个取值及含义。

**5.** 用 `flex-flow` 一行写出"主轴水平、自动换行"。

**6.** 写出 `justify-content` 的六个取值，并分别用一句话描述效果。

**7.** `space-between`、`space-around`、`space-evenly` 三者的区别是什么？（提示：从两端间距和中间间距的关系说）

**8.** 写出 `align-items` 的五个取值及含义，其中哪个是默认值？

**9.** `align-items` 和 `align-content` 分别在什么情况下使用？

**10.** 用两种方式实现"子元素在父容器中水平垂直居中"，写出完整代码。

**11.** 实现"三个子元素平分父容器宽度"。

**12.** 实现"左侧固定 200px，右侧自适应剩余宽度"的两栏布局。

**13.** 实现"左侧自适应，右侧固定 200px"的两栏布局。

**14.** `flex:1`、`flex:auto`、`flex:none`、`flex:0 auto` 分别等价于哪三个值？

**15.** `flex-basis` 的作用是什么？它和 `width` 冲突时谁生效？

**16.** 三个项目的 `flex-grow` 分别是 1、2、3，容器剩余空间 600px，各自能分到多少？

**17.** 三个项目宽度分别是 200px、300px、200px，`flex-shrink` 分别是 1、2、3，容器只有 400px。写出收缩量的计算过程。

**18.** `order` 属性的作用是什么？默认值是多少？

**19.** 一个 flex 容器里有 3 个项目，只想让第 2 个垂直居中，其他保持默认，怎么写？

**20.** 实现一个导航栏：左边是 logo，右边是 4 个菜单项，整体两端对齐、垂直居中。

**21.** 实现"一行 4 张卡片，卡片间距 20px，剩余宽度等分"的布局。

**22.** 实现"圣杯布局"：头部、三栏（左固定 200px、中自适应、右固定 200px）、底部，整体高度撑满视口。

## 专题五 2D / 3D 变换 · 过渡 · 动画　24 题

> **速记卡**
>
> - **2D**：`translate` 位移 ／ `scale` 缩放（1 不变）／ `rotate` 旋转（deg，正顺时针）／ `skew` 扭曲
> - **位移百分比参考自身**（相对定位参考父元素）；位移对**行内元素无效**
> - **多重变换**：写在同一个 `transform` 里，**建议最后旋转**
> - **transform-origin**：默认元素中心；对位移无影响，对旋转缩放有影响
> - **3D 三件套**：父元素 `transform-style:preserve-3d` + 父元素 `perspective` + 自身 `backface-visibility`
> - **transition**：property ／ duration（默认 0）／ delay ／ timing-function（默认 ease）；复合里**一个时间是 duration，两个时间是 duration + delay**
> - **@keyframes**：`from/to` 或 `0%~100%`；`animation` 复合规则同 transition
> - **animation-play-state** 一般单独使用

**1.** 让元素向右移动 30px、向下移动 40px，写出三种写法（translateX/Y、translate 两个值、translate 一个值）。

**2.** `translate(-50%, -50%)` 里的百分比是相对什么计算的？和相对定位的百分比参考有什么不同？

**3.** 为什么位移对行内元素无效？如果想移动一个 span 该怎么办？

**4.** 写出让元素放大 1.5 倍的三种写法。

**5.** 怎么借助缩放实现"小于 12px 的文字"？

**6.** 写出让元素逆时针旋转 45 度的写法。

**7.** `rotate(20deg)` 和 `rotateZ(20deg)` 是等价的吗？

**8.** 写出一行代码：先位移再旋转 45 度（多重变换）。并说明为什么建议最后旋转。

**9.** `transform-origin` 的默认值是什么？它对位移、旋转、缩放分别有没有影响？

**10.** 写出 `transform-origin: 0;` 的效果（两个坐标分别是多少）。

**11.** 元素做 3D 变换前，父元素必须先做什么？写出代码。

**12.** `perspective` 要写在哪个元素上？它的作用是什么？`none` 是什么含义？

**13.** `translateZ(100px)` 和 `translateZ(-100px)` 视觉效果有什么不同？`translateZ` 能写百分比吗？

**14.** 写出 `rotate3d(1,1,1,30deg)` 的含义。

**15.** `backface-visibility` 写在哪个元素上？`hidden` 的效果是什么？

**16.** 写出 `transition` 的四个子属性及各自作用，并指出默认值。

**17.** `transition: 1s 0.5s linear all;` 中两个时间分别代表什么？

**18.** 为什么给 `display` 设置过渡没效果？什么样的属性才支持过渡？

**19.** 写出 `transition-timing-function` 的九个取值及含义。

**20.** 写出定义关键帧的两种写法（from/to 与百分比），要求至少 5 个关键帧。

**21.** 写出 `animation` 的全部子属性及作用，并解释 `forwards` 和 `backwards` 的区别。

**22.** 实现一个加载圆环：40×40，持续旋转，每圈 1s，线性，无限循环。

**23.** 实现一个"心跳"动画：1s 一次，先放大到 1.2 倍再还原，来回交替运行，无限循环。

**24.** 实现一个 3D 翻转卡片：正面蓝色、背面红色，鼠标悬停时沿 Y 轴翻转 180°，翻转过程 0.6s，背面朝上时不可见。

## 专题六 响应式布局与 BFC　14 题

> **速记卡**
>
> - **语法**：`@media 媒体类型 and (媒体特性) { ... }`
> - **媒体类型**：all ／ screen ／ print（其余基本已废弃）
> - **媒体特性**：width ／ max-width ／ min-width ／ height ／ device-width ／ orientation（portrait 纵向、landscape 横向）
> - **运算符**：`and` 并且 ／ `,` 或 ／ `not` 否定 ／ `only` 肯定
> - **BFC** = 块级格式上下文，元素的一个"特异功能"，满足条件后激活
> - **BFC 解决**：① 子元素 margin 塌陷 ② 自身被浮动元素覆盖 ③ 子元素浮动导致自身高度塌陷
> - **开启**：根元素 ／ 浮动 ／ 绝对·固定定位 ／ 行内块 ／ 表格单元格 ／ overflow≠visible 的块 ／ 伸缩项目 ／ 多列容器 ／ column-span:all ／ `display:flow-root`

**1.** 写出媒体查询的基本语法结构，并解释各部分含义。

**2.** 写出媒体类型 `screen`、`print`、`all` 各自的含义。

**3.** 写出检测视口宽度、最小宽度、最大宽度的三个媒体特性。它们和 `device-width` 有什么区别？

**4.** `orientation:portrait` 和 `landscape` 分别代表什么状态？

**5.** 写出媒体查询的四种运算符及含义。

**6.** 写出"屏幕宽度小于等于 768px 时应用"的媒体查询。

**7.** 写出"屏幕宽度在 768px 到 1200px 之间时应用"的媒体查询。

**8.** 写出媒体查询结合外部样式表使用的两种写法。

**9.** 什么是 BFC？用你自己的话说清楚"激活"是什么意思。

**10.** 开启 BFC 能解决哪三个问题？分别举一个具体的页面场景。

**11.** 写出至少八种开启 BFC 的方式。

**12.** 实现"左侧浮动 100px 宽的图片 + 右侧文字不环绕图片（自成一块）"的效果，用 BFC 实现。

**13.** 一个父元素里两个子元素都浮动，父元素高度变成 0。用两种方式解决（一种用 BFC，一种不用）。

**14.** 综合题：做一个响应式页面，PC 端（>1200px）三栏、平板（768~1200px）两栏、手机（≤768px）单栏，三栏用 flex 实现，说明媒体查询该改哪些属性。

---

## 参考答案

### 专题一 选择器与优先级

```
1.  div.box
2.  #nav > a
3.  #nav a
4.  h2 + p
5.  h2 ~ p
6.  a[title^="http"]
7.  a[href$=".pdf"]
8.  li:nth-child(2n)   或   li:nth-child(even)
9.  li:nth-child(-n+3)
10. li:not(:first-child)   或   li:nth-child(n+2)
11. :checked   （更精确：input[type="checkbox"]:checked）
12. :disabled
13. ::selection
14. ::placeholder
15. .box::before { content: "必看"; }
16. * { margin: 0; padding: 0; }
17. (0,0,2)
18. (0,2,3)   —— .nav 一个类、.item 一个类；li、a 两个元素
19. (1,2,1)   —— #app 一个 ID；.list 一个类、:hover 一个伪类；li 一个元素
20. (0,1,1)   —— .card 一个类；div 一个元素、::before 一个伪元素
21. 绿色。#box .text 权重 (1,1,0) > div .text 权重 (0,1,1)，a 位 1 > 0，直接胜出。
22. 红色。三条规则里 p 选择器直接选中了 p 元素，权重 (0,0,1)；
    div 和 .wrap 设置的 color 是通过"继承"传给 p 的。
    规则：元素默认样式 > 继承的样式，而"直接选中的样式"优先级高于继承来的样式。
23. .a.b 是交集选择器（并且），只有 1 号元素同时有 a 和 b 两个类，所以只有 1 号变红。
    .a, .b 是并集选择器（或者），1、2、3 号都命中，三个都变蓝。
    最终 1 号同时命中两条规则，比较权重：.a.b (0,2,0) > .a (0,1,0)，所以 1 号是红色。
24. #header, .top, footer { }
    并集选择器权重"分开算"：#header 是 (1,0,0)，.top 是 (0,1,0)，footer 是 (0,0,1)。
    三个部分各自独立参与比较，不要把它们加起来。
25. ul li a:not(.disabled) { }
```

### 专题二 盒模型与浮动布局

```
1. 内容区宽度 = 200px
   盒子占位宽度 = 200 + (20 × 2) + (5 × 2) = 250px   ← padding 左右 20，border 左右 5
   实际占位（含 margin）= 250 + (30 × 2) = 310px
   注意：margin 不算进"盒子大小"，但占版面空间。

2. 总宽度 = 父的 content − 自身的左右 margin
   内容区宽度 = 父的 content − 自身左右 margin − 自身左右 border − 自身左右 padding

3. 上 10px、左右 20px、下 30px

4. 上 5px、右 10px、下 15px、左 20px（顺时针：上 右 下 左）

5. 需要同时满足两个条件：① 该元素是块级元素（有确定宽度）② 已设置 width。
   行内元素不能用，因为行内元素宽度由内容撑开，没有"剩余空间"可分配。
   行内元素水平居中的做法是给父元素 text-align:center。

6. margin 上下无效（左右有效），padding 上下会被"画出来"但不撑开行高、
   会与上下行内容重叠。原因：行内元素的上下 margin 无效；上下 padding 可以完美设置，
   但不会影响行盒的高度计算。

7. .box {
       width: 300px;
       height: 100px;
       line-height: 100px;    /* 单行文字：height = line-height */
       text-align: center;
   }

8. 给父元素设置 text-align: center;（行内块可以被父元素当作文本处理）

9. 复现：
   .parent { background: #ddd; }
   .child  { margin-top: 50px; height: 50px; background: #f99; }
   现象：父元素顶部被"顶"下来 50px，父子一起往下走。
   解决：① .parent { padding-top: 1px; }  ② .parent { border-top: 1px solid transparent; }
        ③ .parent { overflow: hidden; }（开启 BFC）

10. 合并：上面兄弟的 margin-bottom 和下面兄弟的 margin-top 会取最大值，而不是相加。
    不需要解决，因为这是 CSS 的正常规则，且"取最大值"本身就是合理的视觉结果。
    布局时只给其中一个元素设置上下外边距即可，避免双重间距。

11. 隐藏：  overflow: hidden;
    滚动条：overflow: auto;   （或 overflow: scroll; 总是显示滚动条）

12. visibility:hidden —— 看不见，但元素仍然占据原来的位置和大小。
    适合"保留布局占位"的隐藏，比如 hover 切换时不想让其他元素跳动。
    display:none —— 彻底隐藏，不占任何位置，没有大小宽高。
    适合真正移除元素、重新参与布局的场景。

13. 这是"行内块幽灵空白问题"。原因是行内块元素与文本的基线对齐，
    而文本基线与文本最底端之间有一段距离（descender 区域）。
    解决：① img { vertical-align: middle; }（不为 baseline 即可，top/bottom 也行）
        ② img { display: block; }（父元素里只有一张图时最省事）
        ③ 父元素 { font-size: 0; }（若图片内部还有文字需单独设置 font-size）

14. 原因是行内/行内块元素之间的换行符会被浏览器解析成一个空白字符。
    解决：① 去掉 HTML 里的换行和空格（不推荐，代码难维护）
        ② 父元素 { font-size: 0; }，再给需要显示文字的元素单独设置 font-size（推荐）

15. .box {
        width: 200px;
        box-sizing: border-box;
        padding: 10px 20px;
        border: 5px solid #333;
    }
    此时内容区宽度 = 200 − 20×2 − 5×2 = 150px

16. <div class="wrap">
        <div class="left">左</div>
        <div class="right">右</div>
        <div class="middle">中</div>
    </div>
    <style>
        .wrap { width: 1200px; margin: 0 auto; }
        .wrap::after { content: ""; display: block; clear: both; }
        .left   { float: left;  width: 200px; height: 200px; }
        .right  { float: right; width: 200px; height: 200px; }
        .middle { height: 200px; margin: 0 200px; }   /* 用 margin 让出左右空间 */
    </style>

17. 可以。中间元素不需要浮动，只要给中间元素设置 margin: 0 200px 让出左右空间，
    左右元素一左一右浮动即可。这样中间元素写在最前面也没问题。

18. ① 给父元素指定高度
    ② 给父元素也设置浮动（会带来新的影响）
    ③ 给父元素设置 overflow: hidden
    ④ 在所有浮动元素最后添加一个块级元素并设置 clear: both
    ⑤ 给浮动元素的父元素设置伪元素清除浮动
    推荐 ⑤ 的原因：不需要额外增加 HTML 标签（不污染结构），
    原理同 ④（content + display:block + clear:both），
    且不会像 ② 那样带来新的浮动副作用，也不会像 ① 那样写死高度。

19. 问题：两个 item 浮动后脱离文档流，父元素 .wrap 高度塌陷为 0；
    同时后面的 <p> 会占据浮动元素原来的位置，文字被浮动元素盖住。
    改法：给 .wrap 清除浮动（推荐伪元素方案），
    若还想让 p 完全不被浮动元素影响，可以给 p 设置 overflow: hidden 开启 BFC。

20. <ul class="nav">
        <li><a href="#">首页</a></li>
        <li><a href="#">课程</a></li>
        <li><a href="#">关于</a></li>
        <li><a href="#">联系</a></li>
    </ul>
    <style>
        .nav { list-style: none; margin: 0; padding: 0; }
        .nav::after { content: ""; display: block; clear: both; }
        .nav li { float: left; margin-right: 24px; }
        .nav a  { text-decoration: none; color: #333; }
        .nav a:hover { color: #1f6feb; }
    </style>
```

### 专题三 定位

```
1. 参考自己原来的位置。不会影响周围元素的位置——位置变化只是视觉效果，
   其他元素仍按它原来的位置排版（不脱离文档流）。

2. 参考它的"包含块"。
   ① 父元素有定位（relative/absolute/fixed/sticky）→ 包含块就是父元素（更准确说是最近的已定位祖先）
   ② 所有祖先都没定位 → 包含块是整个页面（初始包含块），left/top 从页面左上角算起

3. 参考视口（看网页的那扇"窗户"）。
   典型场景：返回顶部按钮、悬浮客服、固定导航栏。

4. 参考离它最近的一个拥有"滚动机制"的祖先元素。
   和相对定位的共同点：都不脱离文档流，都能用 left/right/top/bottom 微调位置，
   元素都保持原来的显示模式。
   区别：粘性定位可以在滚动到某个位置时把元素"钉住"，相对定位不行。

5. 宽充满：left: 0; right: 0;
   高充满：top: 0; bottom: 0;
   （前提：元素设置了 position 为 absolute 或 fixed）

6. 方案一：left: 0; right: 0; top: 0; bottom: 0; margin: auto;
          前提：必须给元素设置明确的 width 和 height，否则会撑满包含块。
   方案二：left: 50%; top: 50%; margin-left: -宽度的一半; margin-top: -高度的一半;
          前提：必须知道元素的宽高。
   （更常用的等价写法：left:50%; top:50%; transform: translate(-50%,-50%); 不需要知道宽高）

7. 最常见的原因：该元素没有设置 position（不是定位元素）。
   z-index 只对定位元素有效。另外也可能是被设置了 z-index 的父级/包含块层级压制住了。

8. 后写的元素盖在先写的元素上面。
   改变顺序：① 调整 HTML 中两个元素的书写顺序 ② 用 z-index 调整（需为定位元素）

9. 浮动失效，以定位为主，元素表现为绝对定位。

10. 能设置宽高。因为绝对定位（和固定定位）后元素变成了"定位元素"，
    默认宽高被内容撑开，且可以自由设置宽高，与它原来是什么显示模式无关。

11. <a href="#" class="to-top">↑</a>
    <style>
        .to-top {
            position: fixed;
            right: 30px;
            bottom: 30px;
            width: 50px; height: 50px;
            line-height: 50px; text-align: center;
            background: rgba(0,0,0,.5); color: #fff;
            border-radius: 50%; text-decoration: none;
        }
    </style>

12. <div class="pic">
        <img src="./a.jpg" alt="">
        <span class="badge">热销</span>
    </div>
    <style>
        .pic { position: relative; display: inline-block; }
        .badge {
            position: absolute;
            right: 0; bottom: 0;
            background: rgba(0,0,0,.6); color: #fff;
            padding: 2px 8px; font-size: 12px;
        }
    </style>

13. 用定位：position: relative; left: 10px; top: 20px;
    用 transform：transform: translate(10px, 20px);
    区别：两者都不脱离文档流、都不影响其他元素；
    但 transform 的百分比参考自身，且浏览器对位移有优化，处理效率更高。

14. .topbar {
        position: sticky;
        top: 0;
        height: 60px;
        background: #fff;
        z-index: 10;
    }

15. .modal {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        width: 300px;
        height: 200px;
    }

16. 父元素 padding 是 20px，border 是 10px。
    绝对定位元素的 left:0; top:0 是相对"包含块的 padding box"定位的，
    即包含块的 padding 区域外边缘。所以子元素左上角紧贴父元素内容区左上角，
    距离父元素 border 内侧 20px（也就是距离父元素外边缘 20 + 10 = 30px）。

17. 父元素变成 static（非定位），就不再是子元素的包含块。
    子元素会继续向上找已定位的祖先，都没有的话就相对整个页面定位，
    子元素会跑到页面左上角（并脱离原来的父元素位置）。

18. <div class="mask">
        <div class="modal">我是弹窗</div>
    </div>
    <style>
        .mask {
            position: fixed;
            left: 0; right: 0; top: 0; bottom: 0;   /* 铺满视口 */
            background: rgba(0, 0, 0, .5);
        }
        .modal {
            position: absolute;
            left: 50%; top: 50%;
            transform: translate(-50%, -50%);
            width: 400px; height: 300px;
            background: #fff;
        }
    </style>
```

### 专题四 Flex 伸缩盒模型

```
1. display: flex;
   容器的"所有直接子元素"会变成伸缩项目。孙子、重孙子等后代不算。

2. display:flex  —— 容器本身按块级元素参与布局（独占一行）
   display:inline-flex —— 容器本身按行内块参与布局（不独占一行）
   实际开发中 inline-flex 很少用，因为可以直接把外层容器也设为 flex。

3. row           主轴水平，从左到右（默认）
   row-reverse   主轴水平，从右到左
   column        主轴垂直，从上到下
   column-reverse 主轴垂直，从下到上
   改变了主轴方向后，侧轴方向也随之改变（侧轴始终与主轴垂直）。

4. nowrap（默认）不换行；wrap 自动换行；wrap-reverse 反向换行。

5. flex-flow: row wrap;

6. flex-start    主轴起点对齐（默认）
   flex-end      主轴终点对齐
   center        主轴居中
   space-between 两端对齐，中间平均分布（最常用）
   space-around  每个项目两侧间距相等，两端距离是中间距离的一半
   space-evenly  所有间距（含两端）完全相等

7. space-between：两端贴着边缘，中间均分 → 两端间距为 0
   space-around ：每个项目左右各留等距，两端间距 = 中间间距 / 2
   space-evenly ：所有间距完全相等，两端间距 = 中间间距

8. flex-start 侧轴起点对齐
   flex-end   侧轴终点对齐
   center     侧轴居中
   baseline   项目第一行文字的基线对齐
   stretch    项目未设高度时占满容器高度（默认值）

9. align-items  —— 用于"一行"的情况，调整每个项目在侧轴上的对齐
   align-content —— 用于"多行"（配合 flex-wrap:wrap）的情况，调整多行整体在侧轴上的分布

10. 方式一：
    .outer { display: flex; justify-content: center; align-items: center; }
    方式二：
    .outer { display: flex; }
    .inner { margin: auto; }

11. .outer { display: flex; }
    .item  { flex: 1; }        /* 或 flex-grow: 1; */

12. .outer { display: flex; }
    .left  { width: 200px; }   /* 也可以写 flex: 0 0 200px; */
    .right { flex: 1; }

13. .outer { display: flex; }
    .left  { flex: 1; }
    .right { width: 200px; }

14. flex:1    =  flex: 1 1 0
    flex:auto =  flex: 1 1 auto
    flex:none =  flex: 0 0 auto
    flex:0 auto = flex: 0 1 auto  （flex 的初始值）

15. flex-basis 设置的是主轴方向的基准长度，它会让 width（主轴横向时）或 height（主轴纵向时）失效。
    与 width 冲突时 flex-basis 生效。默认值 auto，即使用元素自身的宽或高。

16. 总份数 = 1 + 2 + 3 = 6
    第一个：600 × 1/6 = 100px
    第二个：600 × 2/6 = 200px
    第三个：600 × 3/6 = 300px

17. ① 计算分母：(200 × 1) + (300 × 2) + (200 × 3) = 200 + 600 + 600 = 1400
    ② 计算比例：项目一 200/1400、项目二 600/1400、项目三 600/1400
    ③ 需要收缩的总量：700 − 400 = 300px
    ④ 各自收缩：项目一 300 × 200/1400 ≈ 42.9px
                项目二 300 × 600/1400 ≈ 128.6px
                项目三 300 × 600/1400 ≈ 128.6px

18. order 定义伸缩项目的排列顺序，数值越小排列越靠前，默认值为 0。

19. .outer { display: flex; }          /* 默认 align-items: stretch */
    .item:nth-child(2) { align-self: center; }
    注意：若容器是 stretch 默认值且项目没设高度，第 2 个需要设高度才能看出居中效果。

20. .navbar {
        display: flex;
        justify-content: space-between;   /* 两端对齐 */
        align-items: center;              /* 垂直居中 */
        height: 60px;
    }
    <div class="navbar">
        <div class="logo">LOGO</div>
        <ul class="menu">...</ul>
    </div>

21. .list { display: flex; gap: 20px; }
    .card { flex: 1; }        /* 4 张卡片 + gap，剩余宽度等分 */
    /* 若卡片宽度必须精确为 (100% - 60px) / 4，则写：
       .card { flex: 0 0 calc((100% - 60px) / 4); } */

22. .page { display: flex; flex-direction: column; height: 100vh; }
    .page main { flex: 1; display: flex; }   /* 中间区域撑满剩余高度 */
    .page .left   { width: 200px; }
    .page .center { flex: 1; }
    .page .right  { width: 200px; }
    .page header, .page footer { height: 60px; }
```

### 专题五 2D / 3D 变换 · 过渡 · 动画

```
1. transform: translateX(30px) translateY(40px);
   transform: translate(30px, 40px);
   transform: translate(30px) translateY(40px);   /* 一个值代表水平 */

2. 相对元素"自身"的宽高计算。
   相对定位的百分比参考的是父元素的宽高，这是二者的关键区别。

3. 行内元素不能设置宽高，其盒子模型也不参与常规的块级布局，
   所以位移（以及缩放、旋转）对行内元素不生效。
   想移动 span：先把它变成行内块或块级（display: inline-block / block），再位移。

4. transform: scale(1.5);
   transform: scale(1.5, 1.5);
   transform: scaleX(1.5) scaleY(1.5);

5. 先按正常大小设置字号（比如 24px），再用 transform: scale(0.4) 缩小，
   视觉上就得到了 24 × 0.4 ≈ 9.6px 的文字。
   （Chrome 最小字号限制是 12px，直接写 font-size: 10px 会被强制提升）

6. transform: rotate(-45deg);

7. 等价。rotateZ(20deg) 就是 rotate(20deg)。

8. transform: translate(50px, 50px) rotate(45deg);
   原因：多重变换是按书写顺序依次作用的，坐标系会跟着变换一起转。
   如果先旋转再位移，位移的方向会变成旋转后的坐标轴方向，结果往往不符合预期；
   先位移后旋转则是在原坐标系里先平移、再自转，更符合直觉。

9. 默认值 transform-origin: 50% 50%（元素中心）。
   对位移没有影响；对旋转和缩放有影响。

10. transform-origin: 0;  只写一个值时，第二个值默认为 50%。
    所以等价于 transform-origin: 0 50%，即左边中点。

11. 父元素必须开启 3D 空间：
    .parent { transform-style: preserve-3d; }
    （默认值是 flat，表示子元素处于 2D 空间）

12. perspective 要写在"发生 3D 变换元素的父元素"上。
    作用是设置景深，即观察者与 z=0 平面的距离，让 3D 变换产生透视效果、看起来更立体。
    none 表示不指定透视（默认值）；也可以写长度值，不允许负值。

13. translateZ(100px)：元素朝屏幕外（朝观察者）移动，看起来变大、更近。
    translateZ(-100px)：元素朝屏幕里移动，看起来变小、更远。
    translateZ 不能写百分比。

14. 表示 x、y、z 三个轴各旋转 30 度。
    前三个参数是坐标轴（1 表示绕该轴），第四个参数是旋转角度，四个参数都不允许省略。

15. 写在"发生 3D 变换元素的自身"上。
    hidden 表示元素背面朝上时不可见（不显示正面的镜像），
    做翻转卡片时必须用它，否则正反两面会互相透出来。

16. transition-property        要过渡的属性，默认 none
    transition-duration        过渡持续时间，默认 0（没有过渡）
    transition-delay           延迟时间，默认 0
    transition-timing-function 过渡类型，默认 ease

17. 第一个 1s 是 duration（持续时间），第二个 0.5s 是 delay（延迟时间）。
    规则：复合写法里一个时间表示 duration，两个时间第一个是 duration、第二个是 delay。

18. display 的值不是数字、也不能转换为数字，所以不支持过渡。
    支持过渡的属性：值本身是数字、或能转换为数字的属性。
    常见的有：颜色、长度值、百分比、z-index、opacity、2D/3D 变换属性、阴影。

19. ease           平滑过渡（默认）
    linear         线性过渡
    ease-in        慢 → 快
    ease-out       快 → 慢
    ease-in-out    慢 → 快 → 慢
    step-start     等同于 steps(1, start)
    step-end       等同于 steps(1, end)
    steps(整数, start|end)  步进函数，第一个参数为正整数（步数），
                            第二个参数默认 end
    cubic-bezier(n,n,n,n)   特定的贝塞尔曲线

20. 写法一：
    @keyframes move {
        from { transform: translateX(0); }
        to   { transform: translateX(300px); }
    }
    写法二：
    @keyframes move {
        0%   { transform: translateX(0); }
        20%  { transform: translateX(60px); }
        40%  { transform: translateX(120px); }
        60%  { transform: translateX(180px); }
        80%  { transform: translateX(240px); }
        100% { transform: translateX(300px); }
    }

21. animation-name            指定要用的关键帧名字
    animation-duration        动画持续时间
    animation-delay           动画延迟时间
    animation-timing-function 动画类型（取值同 transition）
    animation-iteration-count 播放次数，数字或 infinite（无限）
    animation-direction       播放方向：normal / reverse / alternate / alternate-reverse
    animation-fill-mode       动画之外的状态：forwards 保持结束状态 / backwards 保持开始状态
    animation-play-state      播放状态：running（默认）/ paused（一般单独使用）
    复合写法：一个时间表示 duration，两个时间分别是 duration 和 delay。
    forwards 与 backwards 的区别：
    forwards  —— 动画结束后，元素停留在最后一帧的状态
    backwards —— 动画开始前（延迟期间），元素先呈现第一帧的状态

22. @keyframes spin {
        from { transform: rotate(0deg); }
        to   { transform: rotate(360deg); }
    }
    .loading {
        width: 40px; height: 40px;
        border: 4px solid #ddd;
        border-top-color: #1f6feb;
        border-radius: 50%;
        animation: spin 1s linear infinite;
    }

23. @keyframes heart {
        0%   { transform: scale(1); }
        50%  { transform: scale(1.2); }
        100% { transform: scale(1); }
    }
    .heart {
        animation-name: heart;
        animation-duration: 1s;
        animation-iteration-count: infinite;
        animation-direction: alternate;
    }

24. <div class="card">
        <div class="face front">正面</div>
        <div class="face back">背面</div>
    </div>
    <style>
        .card {
            width: 200px; height: 300px;
            position: relative;
            transform-style: preserve-3d;   /* 开启 3D 空间 */
            perspective: 1000px;            /* 景深 */
            transition: transform .6s;      /* 翻转过渡 */
        }
        .card:hover { transform: rotateY(180deg); }

        .face {
            position: absolute; inset: 0;
            backface-visibility: hidden;    /* 背面不可见，加在自身 */
            display: flex; align-items: center; justify-content: center;
        }
        .front { background: #cfe0ff; }
        .back  { background: #ffd6d6; transform: rotateY(180deg); }
    </style>
```

### 专题六 响应式布局与 BFC

```
1. @media 媒体类型 and (媒体特性) {
        /* CSS 代码 */
    }
   @media  —— 媒体查询的关键字
   媒体类型 —— screen / print / all 等
   and      —— 连接媒体类型和媒体特性的运算符
   (媒体特性) —— 如 (max-width: 768px)

2. screen —— 检测电子屏幕（电脑、平板、手机）
   print  —— 检测打印机
   all    —— 检测所有设备

3. width / min-width / max-width 检测的都是"视口"宽度。
   device-width / min-device-width / max-device-width 检测的是"设备屏幕"宽度。
   区别：视口宽度会随浏览器窗口大小变化，设备屏幕宽度是硬件固定值。
   做响应式布局一般用 width 系列（视口），更符合用户实际看到的宽度。

4. portrait  —— 视口纵向，即高度 ≥ 宽度（竖屏）
   landscape —— 视口横向，即宽度 > 高度（横屏）

5. and  —— 并且，多个条件同时满足
   ,    —— 或，任意一个条件满足即可
   not  —— 否定，排除某个媒体类型
   only —— 肯定，让不支持媒体查询的浏览器忽略这段样式

6. @media screen and (max-width: 768px) { ... }

7. @media screen and (min-width: 768px) and (max-width: 1200px) { ... }

8. 写法一（在 HTML 里）：
   <link rel="stylesheet" media="screen and (max-width: 768px)" href="mobile.css">
   写法二（在 CSS 里）：
   @media screen and (max-width: 768px) { /* ... */ }

9. BFC 全称 Block Formatting Context（块级格式上下文），
   可以理解成元素的一个"特异功能"。这个功能默认是关闭的，
   当元素满足了某些条件之后，"特异功能"就被激活了 ——
   专业说法就是：该元素创建了 BFC（开启了 BFC）。

10. ① 子元素不再产生 margin 塌陷
       场景：一个卡片内部有标题和正文，标题的 margin-top 把整张卡片往下顶。
    ② 自身不会被其他浮动元素覆盖
       场景：左浮动侧边栏 + 右侧正文，正文加 overflow:hidden 后不会被压到侧边栏下面。
    ③ 子元素浮动时，自身高度也不会塌陷
       场景：父元素里的子元素全部浮动，父元素高度不再是 0。

11. ① 根元素（html）
    ② 浮动元素（float 不为 none）
    ③ 绝对定位、固定定位元素（position: absolute / fixed）
    ④ 行内块元素（display: inline-block）
    ⑤ 表格单元格（table / thead / tbody / tfoot / tr / th / td / caption）
    ⑥ overflow 的值不为 visible 的块元素
    ⑦ 伸缩项目（flex item）
    ⑧ 多列容器
    ⑨ column-span 为 all 的元素
    ⑩ display 的值为 flow-root

12. <div class="news">
        <img class="pic" src="./a.jpg" alt="">
        <p>这里是一段很长的文字……</p>
    </div>
    <style>
        .pic { float: left; width: 100px; }
        .news p { overflow: hidden; }   /* 开启 BFC，文字自成一块，不环绕图片 */
    </style>

13. 方式一（用 BFC）：
    .parent { overflow: hidden; }
    方式二（不用 BFC）：
    .parent::after { content: ""; display: block; clear: both; }

14. 三栏用 flex 实现：
    .main { display: flex; }
    .left, .right { width: 200px; }
    .center { flex: 1; }

    平板（768~1200px）变两栏：隐藏左栏（或右栏），中间自适应：
    @media screen and (max-width: 1200px) {
        .left { display: none; }
    }

    手机（≤768px）变单栏：把 flex 主轴改成纵向，三个区块上下排列：
    @media screen and (max-width: 768px) {
        .main { flex-direction: column; }
        .left, .right, .center { width: 100%; }
    }

    关键：媒体查询里改的是 flex-direction、width 和 display 这几个属性。
```

---

*HTML + CSS 专项突破练习册 · 六个专题 · 共 123 题 · 依据《HTML4 / HTML5 / CSS2 / CSS3 笔记》编制*
