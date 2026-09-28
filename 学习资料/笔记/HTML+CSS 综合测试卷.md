# HTML + CSS 综合测试卷
> 覆盖范围：HTML4 基础 · HTML5 新增 · CSS2 基础 · CSS3 新增

> **题型分布：**一、单项选择题 30×2=60 分 ｜ 二、多项选择题 10×3=30 分 ｜ 三、判断题 15×1=15 分 ｜ 四、填空题 20×1=20 分 ｜ 五、简答题 8×5=40 分 ｜ 六、代码阅读与编写题 35 分。
> 多项选择题**多选、少选、错选均不得分**；填空题每空 1 分。点击右上角按钮可显示／隐藏参考答案。

## 一、单项选择题　每题 2 分，共 60 分

**1.** 下列选项中，**不属于** HTML5 新增语义化标签的是（ ）

**A.** header　**B.** nav　**C.** center　**D.** aside

**2.** CSS 的全称是（ ）

- **A.** Cascading Style Sheets
- **B.** Computer Style Sheets
- **C.** Creative Style Sheets
- **D.** Colorful Style Sheets

**3.** 下列关于 HTML 文档声明的说法，正确的是（ ）

- **A.** 必须写在 `html` 标签内部
- **B.** 必须写在网页第一行，且在 `html` 标签的外侧
- **C.** 可以写在 `body` 标签中
- **D.** 只能写成 `<!DOCTYPE HTML5>`

**4.** 下列字符集中，收录范围最广、包含世界上所有语言的文字与符号的是（ ）

**A.** ASCII　**B.** GB2312　**C.** GBK　**D.** UTF-8

**5.** 选择器权重 (1,0,0) 与 (0,2,2) 比较，结果是（ ）

**A.** (0,2,2) 大　**B.** (1,0,0) 大　**C.** 一样大　**D.** 无法比较

**6.** 下列关于行内元素的说法，正确的是（ ）

**A.** 在页面中独占一行　**B.** 可以通过 CSS 自由设置宽高　**C.** 默认宽度由内容撑开　**D.** 可以包含块级元素

**7.** 让单行文字在固定高度的盒子中实现垂直居中，最常用的做法是（ ）

- **A.** `text-align:center`
- **B.** `vertical-align:middle`
- **C.** 让 `height` 等于 `line-height`
- **D.** `margin:0 auto`

**8.** 下列现象属于 **margin 塌陷**的是（ ）

- **A.** 上面兄弟元素的下外边距和下面兄弟元素的上外边距取较大值
- **B.** 第一个子元素的上外边距作用在了父元素上
- **C.** 浮动元素的父元素高度变为 0
- **D.** 行内元素设置上下外边距无效

**9.** 清除浮动时，笔记中**推荐**使用的方法是（ ）

- **A.** 给父元素指定高度
- **B.** 给父元素也设置浮动
- **C.** 给父元素设置伪元素并设置 `clear:both`
- **D.** 给父元素设置 `overflow:visible`

**10.** 关于绝对定位 `position:absolute`，下列说法**错误**的是（ ）

**A.** 会脱离文档流　**B.** 参考它的包含块定位　**C.** 参考自己原来的位置定位　**D.** 与浮动同时设置时，浮动失效

**11.** 让绝对定位元素在包含块中水平垂直居中，下列写法可以的是（ ）

- **A.** `left:50%; top:50%; margin:auto;`
- **B.** `left:0; right:0; top:0; bottom:0; margin:auto;`
- **C.** `left:50%; top:50%; transform:translate(-50%,-50%);`
- **D.** B 和 C 都可以（B 需设置宽高）

**12.** 元素进行 3D 变换的首要操作是让父元素开启 3D 空间，应使用属性（ ）

- **A.** `perspective`
- **B.** `transform-style: preserve-3d`
- **C.** `backface-visibility`
- **D.** `transform-origin`

**13.** 下列属性中，**不能**被继承的是（ ）

**A.** `color`　**B.** `font-size`　**C.** `text-align`　**D.** `border`

**14.** flex 布局中，设置**主轴对齐方式**的属性是（ ）

**A.** `align-items`　**B.** `justify-content`　**C.** `align-content`　**D.** `flex-direction`

**15.** flex 复合属性中，`flex:1` 等价于（ ）

**A.** `flex:1 1 auto`　**B.** `flex:1 1 0`　**C.** `flex:0 1 auto`　**D.** `flex:0 0 auto`

**16.** 希望 `width` 和 `height` 设置的是盒子总大小（怪异盒模型），应使用（ ）

- **A.** `box-sizing:content-box`
- **B.** `box-sizing:border-box`
- **C.** `box-model:border-box`
- **D.** `display:border-box`

**17.** `background-size` 的取值中，将背景图等比缩放至**完全覆盖容器**的是（ ）

**A.** `contain`　**B.** `cover`　**C.** `auto`　**D.** `100% 100%`

**18.** 关于 `text-overflow:ellipsis` 的生效条件，下列说法**错误**的是（ ）

- **A.** 容器必须是块容器
- **B.** `overflow` 的值不能是 `visible`
- **C.** `white-space` 必须为 `nowrap`
- **D.** 必须同时设置 `text-align:center`

**19.** HTML5 中，语义为"侧边栏"的标签是（ ）

**A.** `aside`　**B.** `article`　**C.** `section`　**D.** `nav`

**20.** 关于 `article` 与 `section`，下列说法**错误**的是（ ）

- **A.** `article` 里面可以有多个 `section`
- **B.** `section` 强调的是分段或分块
- **C.** `article` 比 `section` 更强调独立性
- **D.** `section` 里面不能写 `article`

**21.** HTML5 中用于显示"某个任务完成进度"的标签是（ ）

**A.** `meter`　**B.** `progress`　**C.** `datalist`　**D.** `mark`

**22.** 表单中要让多个单选框实现单选效果，必须保证它们的（ ）属性值相同

**A.** `id`　**B.** `value`　**C.** `name`　**D.** `checked`

**23.** 下列 `input` 的 type 值中，表单提交时**会**验证格式的是（ ）

**A.** `search`　**B.** `tel`　**C.** `email`　**D.** `range`

**24.** 下列关于伪元素 `::before` 的说法，正确的是（ ）

**A.** 必须配合 `content` 属性使用　**B.** 只能用于 `a` 标签　**C.** 它属于伪类选择器　**D.** 只能在元素内部最后创建内容

**25.** 动态伪类选择器建议遵循的顺序（LVHA）是（ ）

- **A.** :link → :visited → :hover → :active
- **B.** :link → :hover → :visited → :active
- **C.** :hover → :link → :visited → :active
- **D.** :visited → :link → :hover → :active

**26.** 下列关于元素显示模式的说法，**错误**的是（ ）

- **A.** 块级元素在页面中独占一行
- **B.** 行内元素可以完美设置左右 margin
- **C.** 行内元素可以完美设置上下 padding
- **D.** 行内块元素可以设置宽高

**27.** 下列长度单位中，相对于**根元素字体大小**计算的是（ ）

**A.** `px`　**B.** `em`　**C.** `rem`　**D.** `vw`

**28.** Firefox 浏览器的 CSS3 私有前缀是（ ）

**A.** `-webkit-`　**B.** `-moz-`　**C.** `-ms-`　**D.** `-o-`

**29.** 关于粘性定位 `position:sticky`，下列说法正确的是（ ）

**A.** 会脱离文档流　**B.** 不会脱离文档流，最常用的值是 top　**C.** 参考视口定位　**D.** 参考最近的已定位祖先元素定位

**30.** 下列**不属于** BFC 能解决的问题是（ ）

**A.** 子元素产生 margin 塌陷　**B.** 自身被其他浮动元素覆盖　**C.** 子元素浮动导致自身高度塌陷　**D.** 行内元素设置上下 margin 无效

## 二、多项选择题　每题 3 分，共 30 分（多选、少选、错选均不得分）

**1.** 下列属于 HTML5 新增语义化标签的有（ ）

**A.** `header`　**B.** `section`　**C.** `center`　**D.** `footer`　**E.** `main`

**2.** CSS 的三大特性包括（ ）

**A.** 层叠性　**B.** 继承性　**C.** 优先级　**D.** 浮动性

**3.** 下列关于 CSS 编写位置的说法，正确的有（ ）

- **A.** 行内样式写在标签的 `style` 属性中，只能控制当前标签
- **B.** 内部样式写在 `<style>` 标签中，一般放在 `head` 中
- **C.** 外部样式通过 `<link>` 引入，`link` 标签要写在 `head` 中
- **D.** 优先级：行内样式 > 内部样式 = 外部样式

**4.** 下列关于盒子模型的说法，正确的有（ ）

- **A.** 盒子大小 = content + 左右 padding + 左右 border
- **B.** `margin` 不影响盒子大小，但会影响盒子的位置
- **C.** `padding` 的值可以是负数
- **D.** `margin` 的值可以是负数，也可以是 `auto`

**5.** 下列可以开启 BFC 的方式有（ ）

- **A.** 根元素
- **B.** 浮动元素
- **C.** `overflow:hidden` 的块元素
- **D.** `display:flow-root`
- **E.** 行内块元素

**6.** 下列属于 CSS3 新增长度单位的有（ ）

**A.** `rem`　**B.** `vw`　**C.** `vh`　**D.** `em`

**7.** 下列关于过渡 `transition` 的说法，正确的有（ ）

- **A.** `transition-property` 值为 `all` 时表示过渡所有能过渡的属性
- **B.** `transition-duration` 的默认值是 0
- **C.** 复合写法中设置一个时间表示 duration，两个时间分别是 duration 和 delay
- **D.** 所有 CSS 属性都支持过渡

**8.** 下列关于多媒体标签 `video` / `audio` 的说法，正确的有（ ）

- **A.** 两者都是双标签
- **B.** `controls` 用于向用户显示播放控件
- **C.** 使用 `autoplay` 时会忽略 `preload` 属性
- **D.** `muted` 表示静音，`poster` 用于设置视频封面

**9.** 下列属于 HTML5 表单新增属性（或新增属性值）的有（ ）

**A.** `placeholder`　**B.** `required`　**C.** `autofocus`　**D.** `novalidate`

**10.** 下列属于 HTML 全局属性的有（ ）

**A.** `id`　**B.** `class`　**C.** `style`　**D.** `title`　**E.** `lang`

## 三、判断题　每题 1 分，共 15 分（正确打"√"，错误打"×"）

**1.** HTML 标签名不区分大小写，但推荐使用小写。（ ）

**2.** HTML 注释可以嵌套使用。（ ）

**3.** 一个元素的 class 属性可以写多个值，用空格隔开。（ ）

**4.** 多个元素的 id 属性值可以相同。（ ）

**5.** `p` 标签中可以嵌套 `div` 标签。（ ）

**6.** 行内元素中可以写块级元素。（ ）

**7.** `img` 标签的 `alt` 属性最主要的作用是让搜索引擎得知图片的内容。（ ）

**8.** 相对路径中的 `./` 可以省略不写。（ ）

**9.** `li` 标签最好写在 `ul` 或 `ol` 中，不要单独使用。（ ）

**10.** `table` 的 `border` 属性值的大小可以控制单元格边框的宽度。（ ）

**11.** 内部样式与外部样式优先级相同，后面的会覆盖前面的。（ ）

**12.** 通配选择器 `*` 的权重高于元素选择器。（ ）

**13.** `visibility:hidden` 隐藏元素后，元素不再占据原来的位置。（ ）

**14.** 浮动元素会脱离文档流，并且能够完美设置四个方向的 margin 和 padding。（ ）

**15.** 只有定位的元素设置 `z-index` 才有效。（ ）

## 四、填空题　每空 1 分，共 20 分

**1.** CSS 的全称是 ______ ；HTML 的全称是 ______ 。

**2.** HTML 文档声明必须写在网页的 ______ ，并且在 `html` 标签的 ______ 。

**3.** 为让浏览器正确渲染，需要用 `meta` 标签配合 `charset` 属性指定字符编码，写法为 ______ （写出完整标签）。

**4.** `img` 标签中，指定图片路径的属性是 ______ ，用于图片描述的属性是 ______ 。

**5.** 超链接标签是 ______ ，其中控制跳转时如何打开页面的属性是 ______ ，其常用值有 `_self` 和 ______ 。

**6.** 有序列表使用 ______ 标签，无序列表使用 ______ 标签，自定义列表使用 ______ 标签。

**7.** 表格中跨行使用 ______ 属性，跨列使用 ______ 属性。

**8.** 选择器权重 (a, b, c) 中，a 表示 ______ 的个数，b 表示 ______ 的个数，c 表示 ______ 的个数。

**9.** 盒子模型由 ______ 、 ______ 、 ______ 、 ______ 四部分组成。

**10.** 让块级元素在父元素中水平居中，可以给该块级元素设置 ______ ；让行内元素或行内块元素在父元素中水平居中，可以给父元素设置 ______ 。

**11.** flex 布局中，改变主轴方向的属性是 ______ ，设置主轴对齐方式的属性是 ______ ，设置侧轴对齐方式（一行）的属性是 ______ 。

**12.** 开启 3D 空间使用 ______ 属性；设置景深使用 ______ 属性，且该属性要写在发生 3D 变换元素的 ______ 上。

## 五、简答题　每题 5 分，共 40 分

**1.** 简述 C/S 架构与 B/S 架构的区别。

**2.** 简述块级元素、行内元素、行内块元素三者在"是否独占一行""默认宽高""能否设置宽高"上的区别，并各举两个例子。

**3.** 简述 CSS 的三种编写位置，并说明各自的优缺点。

**4.** 什么是 margin 塌陷？如何解决？

**5.** 简述元素浮动后的特点，并写出清除浮动的常用方案（至少三种）。

**6.** 简述相对定位、绝对定位、固定定位、粘性定位的参考点，以及各自是否脱离文档流。

**7.** 什么是 BFC？开启 BFC 能解决哪些问题？请写出至少四种开启 BFC 的方式。

**8.** 简述 flex 布局中 `justify-content` 与 `align-items` 的作用与区别，并各写出三个常用值。

## 六、代码阅读与编写题　共 35 分

**1.** （10 分）写出下列选择器的含义，并计算其权重 (a, b, c)。

（1）`ul>li` （2）`#atguigu .slogan a:hover` （3）`.subject li.front-end`
（4）`div+p` （5）`div[title^="a"]`

**2.** （8 分）用 HTML 编写一个学生信息表格，要求：

① 使用完整表格结构（表格标题、表格头部、表格主体）；
② 表头为"姓名、性别、年龄"；
③ 至少两行数据；
④ 表格显示边框。

**3.** （8 分）按要求编写 CSS 代码：

（1）制作一个 200px × 200px 的盒子，红色背景，圆角 20px，并添加 `10px 10px 20px 3px blue inset` 的盒子阴影；
（2）让该盒子在父元素中水平垂直居中（使用绝对定位 + transform 实现）。

**4.** （5 分）补全代码：父容器 400px × 400px，使用 flex 布局让内部 `.inner` 元素水平垂直居中（写出两种方式）。

```
.outer { width: 400px; height: 400px; background-color: #888; /* 请补充 */ }
.inner { width: 100px; height: 100px; background-color: orange; /* 请补充 */ }
```

**5.** （4 分）写出媒体查询代码：当屏幕宽度小于等于 768px 时，让 `.box` 的宽度变为 100%；当屏幕宽度在 768px ~ 1200px 之间时，宽度为 50%。

---

## 参考答案与解析　阅卷用

### 一、单项选择题（每题 2 分，共 60 分）

| 题号 | 答案 | 题号 | 答案 | 题号 | 答案 | 题号 | 答案 | 题号 | 答案 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | C | 7 | C | 13 | D | 19 | A | 25 | A |
| 2 | A | 8 | B | 14 | B | 20 | D | 26 | C |
| 3 | B | 9 | C | 15 | B | 21 | B | 27 | C |
| 4 | D | 10 | C | 16 | B | 22 | C | 28 | B |
| 5 | B | 11 | D | 17 | B | 23 | C | 29 | B |
| 6 | C | 12 | B | 18 | D | 24 | A | 30 | D |

**重点解析：**  
1. `center` 是 HTML4 的排版标签，不是 HTML5 新增语义化标签。  
3. 文档声明必须在网页第一行且位于 `html` 标签外侧。  
5. 权重比较从左到右逐位对比，a 位 1 > 0，故 (1,0,0) 更大。  
8. margin 塌陷指"第一个子元素的上 margin / 最后一个子元素的下 margin 作用在父元素上"；A 描述的是 margin 合并。  
11. B 方案（四方向为 0 + margin:auto）必须同时设置宽高才生效；C 方案（50% + translate(-50%,-50%)）同样可行，故选 D。  
13. 能继承的属性都是"不影响布局"的（字体、文本、颜色等），`border` 属于盒子模型相关属性，不可继承。  
18. `text-overflow` 生效只要求"块容器 + overflow 非 visible + white-space:nowrap"，与 `text-align` 无关。  
23. `email`、`url`、`number` 提交时会验证格式（为空则不验证）；`search`、`tel`、`range` 等不验证。  
26. 行内元素的左右内边距可以完美设置，**上下内边距不能完美设置**，故 C 错误。  
30. BFC 能解决 margin 塌陷、被浮动元素覆盖、浮动导致的高度塌陷；行内元素上下 margin 无效是显示模式本身的限制，与 BFC 无关。

### 二、多项选择题（每题 3 分，共 30 分）

| 题号 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 答案 | ABDE | ABC | ABCD | ABD | ABCDE | ABC | ABC | ABCD | ABCD | ABCDE |

**重点解析：**  
1. `center` 不属于 HTML5 新增语义化标签（H5 新增为 header、footer、nav、article、section、aside、main、hgroup）。  
4. `padding` 的值**不能为负数**，故 C 错误；`margin` 可以为负数，也可以为 auto。  
6. `em` 是 CSS2 就有的单位（相对元素自身 font-size），不属于 CSS3 新增。  
7. 只有"值为数字、或值能转为数字"的属性才支持过渡（如颜色、长度、百分比、z-index、opacity、2D/3D 变换、阴影），并非所有属性，故 D 错误。  
8. 四个选项均正确，注意"使用 autoplay 时会忽略 preload"。

### 三、判断题（每题 1 分，共 15 分）

| 题号 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 答案 | √ | × | √ | × | × | × | √ | √ | √ | × | √ | × | × | √ | √ |

2. 注释不可嵌套。 4. id 不能重复。 5. `p` 中不能写 `div`。 6. 行内元素中不能写块级元素。  
10. `border` 只控制表格最外侧边框宽度，单元格边框宽度需靠 CSS 控制。 12. `*` 权重最低。  
13. `visibility:hidden` 元素看不见但**仍占位**；`display:none` 才彻底不占位。

### 四、填空题（每空 1 分，共 20 分）

1. 层叠样式表（Cascading Style Sheets）／超文本标记语言（HyperText Markup Language）

2. 第一行／外侧

3. `<meta charset="UTF-8">`

4. `src`／`alt`

5. `<a>`／`target`／`_blank`

6. `ol`／`ul`／`dl`

7. `rowspan`／`colspan`

8. ID 选择器／类、伪类、属性选择器／元素、伪元素选择器

9. margin（外边距）／border（边框）／padding（内边距）／content（内容）（顺序可互换）

10. `margin: 0 auto;`／`text-align: center;`

11. `flex-direction`／`justify-content`／`align-items`

12. `transform-style: preserve-3d`／`perspective`／父元素

### 五、简答题（每题 5 分，共 40 分）

**1. C/S 与 B/S 架构的区别**

C/S（client-server）：需要安装、偶尔更新、不跨平台、开发更具针对性；  
B/S（browser-server）：无需安装、无需更新、可跨平台、开发更具通用性。  
前端工程师主要负责编写 B/S 架构中的网页（呈现界面、实现交互）。

**2. 三种显示模式的区别**

① 块级元素（block）：独占一行；默认宽度撑满父元素、默认高度由内容撑开；可以设置宽高。例：`div`、`p`。  
② 行内元素（inline）：不独占一行；默认宽高都由内容撑开；**无法**通过 CSS 设置宽高。例：`span`、`a`。  
③ 行内块元素（inline-block）：不独占一行；默认宽高都由内容撑开；可以设置宽高。例：`img`、`input`。

**3. CSS 的三种编写位置**

① 行内样式（`style` 属性）：优先级最高；但结构与样式未分离、代码结构混乱、样式不能复用，使用频率很低，作用范围仅当前标签。  
② 内部样式（`<style>`，一般放 head 中）：样式可复用、结构清晰；但未彻底分离、不能多页面复用，使用频率一般，作用范围当前页面。  
③ 外部样式（`.css` + `<link>`）：可多页面复用、结构清晰、可触发浏览器缓存机制、彻底分离；缺点是需要引入。使用频率最高，实际开发几乎都用它。

**4. margin 塌陷**

含义：第一个子元素的上 margin 会作用在父元素上，最后一个子元素的下 margin 会作用在父元素上。  
解决：①给父元素设置不为 0 的 padding；②给父元素设置宽度不为 0 的 border；③给父元素设置 `overflow:hidden`（开启 BFC）。

**5. 浮动的特点与清除浮动**

特点：脱离文档流；不管浮动前是什么元素，浮动后默认宽高都由内容撑开且可设置宽高；不独占一行，可与其他元素共用一行；不会 margin 合并、也不会 margin 塌陷，能完美设置四个方向的 margin 和 padding；不会像行内块一样被当作文本处理。  
影响：后面的兄弟元素会占据浮动元素之前的位置（显示在其下面）；父元素不能被撑开，导致高度塌陷。  
清除方案：①给父元素指定高度；②给父元素也设置浮动；③给父元素设置 `overflow:hidden`；④在所有浮动元素最后添加块级元素并设置 `clear:both`；⑤给浮动元素的父元素设置伪元素清除浮动（推荐）。

**6. 四种定位的对比**

相对定位 `relative`：参考自己原来的位置；**不**脱离文档流。  
绝对定位 `absolute`：参考它的包含块（第一个拥有定位属性的祖先元素，都没有则整个页面）；脱离文档流。  
固定定位 `fixed`：参考视口；脱离文档流。  
粘性定位 `sticky`：参考离它最近的一个拥有"滚动机制"的祖先元素；**不**脱离文档流，最常用的是 top 值。

**7. BFC**

含义：BFC 即块级格式上下文（Block Formatting Context），可以理解为元素的一个"特异功能"，默认关闭，满足某些条件后即被激活（创建了 BFC）。  
能解决：①子元素不再产生 margin 塌陷；②自身不会被其他浮动元素覆盖；③子元素浮动时自身高度也不会塌陷。  
开启方式（任答四种即可）：根元素；浮动元素；绝对/固定定位元素；行内块元素；表格单元格；`overflow` 值不为 visible 的块元素；伸缩项目；多列容器；`column-span:all` 的元素；`display:flow-root`。

**8. justify-content 与 align-items**

区别：`justify-content` 控制**主轴**方向的对齐方式；`align-items` 控制**侧轴**方向的对齐方式（针对一行的情况，多行用 `align-content`）。  
`justify-content` 常用值：flex-start（默认）、flex-end、center、space-between（最常用）、space-around、space-evenly。  
`align-items` 常用值：flex-start、flex-end、center、baseline、stretch（默认）。

### 六、代码阅读与编写题（共 35 分）

**1.（10 分）选择器含义与权重**

```
（1）ul>li                含义：选中 ul 的子代 li 元素                     权重 (0,0,2)
（2）#atguigu .slogan a:hover
                         含义：选中 id 为 atguigu 的元素内部、
                               类名为 slogan 的元素内部的、处于悬停状态的 a 元素
                                                                    权重 (1,2,1)
（3）.subject li.front-end 含义：选中类名为 subject 的元素内部、
                               同时具有 front-end 类名的 li 元素     权重 (0,2,1)
（4）div+p                 含义：选中 div 后面紧邻的那个兄弟 p 元素        权重 (0,0,2)
（5）div[title^="a"]       含义：选中具有 title 属性、
                               且 title 值以 a 开头的 div 元素         权重 (0,1,1)
```

**2.（8 分）学生信息表格**

```
<table border="1">
    <caption>学生信息</caption>
    <thead>
        <tr>
            <th>姓名</th>
            <th>性别</th>
            <th>年龄</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>张三</td>
            <td>男</td>
            <td>18</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>女</td>
            <td>20</td>
        </tr>
    </tbody>
</table>
```

**3.（8 分）CSS 代码**

```
.box {
    /* （1）盒子样式 */
    width: 200px;
    height: 200px;
    background-color: red;
    border-radius: 20px;
    box-shadow: 10px 10px 20px 3px blue inset;

    /* （2）在父元素中水平垂直居中 */
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}
```

**4.（5 分）flex 水平垂直居中（两种方式）**

```
/* 方式一：justify-content + align-items */
.outer {
    width: 400px;
    height: 400px;
    background-color: #888;
    display: flex;
    justify-content: center;
    align-items: center;
}
.inner { width: 100px; height: 100px; background-color: orange; }

/* 方式二：父容器开启 flex，子元素 margin:auto */
.outer {
    width: 400px;
    height: 400px;
    background-color: #888;
    display: flex;
}
.inner { width: 100px; height: 100px; background-color: orange; margin: auto; }
```

**5.（4 分）媒体查询**

```
@media screen and (max-width: 768px) {
    .box { width: 100%; }
}

@media screen and (min-width: 768px) and (max-width: 1200px) {
    .box { width: 50%; }
}
```

## 附：知识点覆盖对照表

| 知识模块 | 覆盖的知识点 | 对应题号 |
| --- | --- | --- |
| HTML4 | 计算机基础与 C/S、B/S 架构；浏览器与内核；HTML 概念与国际组织；标签、属性、双/单标签；基本结构与文档声明；注释；字符编码与 meta；lang 语言设置；排版标签与语义化；块级/行内元素；文本标签；img 与 alt；路径与图片格式；超链接与锚点；列表；表格与跨行跨列；br/hr/pre；表单与各类控件、label、fieldset；iframe；HTML 实体；全局属性；meta 元信息 | 单选 3、4、6、19(部分)、22、24、26；多选 3、10；判断 1~10；填空 1~7；简答 1~3；代码 2 |
| HTML5 | HTML5 简介与兼容性；新增语义化标签（含 article/section 区别）；meter / progress；datalist / details / summary；ruby / rt / mark；表单新增属性与 input 新增 type；video / audio 及属性；新增全局属性；html5shiv 与条件注释 | 单选 1、19、20、21、23；多选 1、8、9；简答 7(部分) |
| CSS2 | CSS 概念与三种编写位置及优先级；语法规范与代码风格；基本选择器与复合选择器；伪类与伪元素；权重计算；层叠性、继承性、优先级；颜色表示；字体属性；文本属性（含 line-height、vertical-align）；列表、表格、背景、鼠标属性；盒子模型（content/padding/border/margin）；margin 塌陷与合并；overflow；隐藏元素；默认样式与重置；浮动与清除浮动；四种定位与 z-index；版心与常用布局名词 | 单选 2、5、7、8、9、10、11、13、24、25、26、27、29；多选 2、3、4、6；判断 11~15；填空 1、8~10；简答 2~6；代码 1、3 |
| CSS3 | CSS3 概述与私有前缀；新增长度单位（rem/vw/vh/vmax/vmin）；box-sizing / resize / box-shadow / opacity；背景新增属性（origin/clip/size/复合/多背景）；border-radius 与外轮廓；文本新增（text-shadow / white-space / text-overflow / text-decoration 升级 / 文字描边）；渐变（线性、径向、重复）；@font-face 与字体图标；2D 变换与 transform-origin；3D 变换（3D 空间、景深、位移/旋转/缩放、背部可见性）；transition 过渡；animation 动画；多列布局；flex 伸缩盒模型；媒体查询响应式；BFC | 单选 12、14、15、16、17、18、28、30；多选 5、6、7；填空 11、12；简答 7、8；代码 4、5 |

---

*HTML + CSS 综合测试卷 · 依据《HTML4 笔记》《HTML5 笔记》《CSS2 笔记》《CSS3 笔记》编制 · 共 200 分*
