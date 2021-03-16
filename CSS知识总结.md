# css基础概念

css发明者：赖先生（Håkon Wium Lie）首先提出。



### CSS最强之处：层叠样式

------

#### 层叠指什么？

- **样式层叠**

  可以多次对同一选择器进行样式声明

- **选择器层叠**

  可以用不同选择器对同一个元素进行样式声明

- **文件层层叠**

​       可以用多个文件进行层叠



### 了解各个浏览器支持的特性的方法

------

使用 caniuse.com 



### CSS学习方法

------

- **学习语法**
- **调试（怎么知道自己写错了）**
- **在哪里查资料**
- **标准制定者是谁（权威资料及解释）**



### 语法一

------

```css
选择器{

     属性名: 属性值;

     /*注释*/

}
```

**注意事项：**

1. 所有符号都是**英文符号**，如果写错了，浏览器会警告
2. 区分大小写，a和A是不同的东西
3. 没有//注释，必须 /**/,最好放分号后面
4. 最后一个分号可以省略，但建议不要省略
5. 任何地方写错了，都不会报错，浏览器会直接忽略
6. 如何检查错误？



### 语法二： at 语法

------

@charset  "UTF-8";

@import url(2.css);

@media (min-width: 100px) and (max-width: 200px){

​          语法一

}

**注意：**

- @charset 必须放在第一行

- 前两个at 语法必须以；结尾

- @ media 语法后面单独

- charset 是字符集的意思，但utf-8是字符编码encoding，这是历史遗留问题

  

### 如何调试

------

**方法**

- 使用[W3C验证器](https://jigsaw.w3.org/css-validator/#validate_by_input)

- VScode看颜色

- webstorm看颜色

- 开发者工具看警告(一般会有黄色感叹号提示)

  

**如何使用开发者工具**

找到你脑中的标签看它是否有选择器，看它的样式是否被划掉，看它的样式是否有警告



### Border调试法

------

**步骤**

当你怀疑某个元素有问题的时候，就给他加border

```border:1px solid red;```

**如果border没出现？**

说明选择器或语法错了

**如果border出现了？**

看看边界是否符合预期

当bug解决了，才能将其删除

**注意：有时候使用border可能会由于border-box扰乱横向布局，我们也可以用outline代替**(outline与border类似，但具有不占空间的属性)

**记住**

CSS的border调试法基本相当于JS的log调试法

 

### 资料查询

------

- **网站推荐**

  google搜索关键词时加 MDN

  CSS tricks

  张鑫旭的博客

  

- **书籍推荐**

  不推荐

  

### 素材搜索

------

- **PSD**

  freepik 搜索[PSD web](https://xiedaimala.com/users/c78d7166-f1ed-4414-8c17-d82df582b626/#/courses)

  365PSD里的**UI套件**

- **效果图**（不提供下载，可以进行格式模仿）

  [**dribbble.com**](https://dribbble.com/shots/15264821-George-Washington-animated-portrait)

  直接肉眼模仿

- **商业网站** 

  直接模仿你喜欢的网站

- **临摹目标**

  PC网站、手机网站、UI套件 三者每种两个即可

  

#### 标准制定者（实在查不到可用此网站）

------

  CSS2.1标准[中文版](http://www.ayqy.net/doc/css2-1/cover.html)



# CSS文档流

文档流即文档流动的方向

### 几个基本概念

------

- 文档流

- 块、内联、内联块

- margin合并

- 两种盒模型

  

### 文档流

------

- **流动方向**

  inline（内联元素）： 从左到右，到达最右边才换行

  block（块元素） ：从上到下，每个元素占一行

  inline-block（内联块元素）：从左到右，但保持块状

- **宽度**

  inline（内联元素） 宽度为内部inline元素的和，不能用width指定

  block（块元素） 默认自动计算宽度，可用width指定

  inline-block（内联块元素） 结合前两者特点。可用width调整

- **高度**

  inline（内联元素） 高度由line-height（行高：文本内容高度）间接确定，跟height（元素自身的高度）无关,不能用height指定

  block（块元素）高度由内部文档流元素决定，可以设置height

  inline-block（内联块元素）跟block类似，可以设置height

![](C:\Users\Administrator\Desktop\note\css\picture\a.png)

inline与block元素初始情况下的样子刚好相反，一个宽被默认，一个长被默认：

![](C:\Users\Administrator\Desktop\note\css\picture\f.png)

**注意：**

**1.不要在inline元素里加入block元素**

**2.width永远不要写100%**

**3.dispaly:inline-block会尽量压缩自己的宽度**，**常常针对内联元素使用**



### overflow溢出

------

本情况只有内容大于容器时会出现，如下图：

![](C:\Users\Administrator\Desktop\note\css\picture\b.png)

可以用overflow来设置是否显示滚动条，如下图：

![](C:\Users\Administrator\Desktop\note\css\picture\c.png)

**注意：**

红色为块元素div，当无内容时，其高度为0，宽度默认为一行

绿色为span，当无内容时，高度为默认行高，宽度为0



**overflow各属性：**

- auto 灵活设置
- scroll 永远显示
- hidden 直接隐藏溢出部分
- visible（默认）直接显示溢出部分
- overflow可以分为overflow-x和overflow-y，即针对不同方向的溢出调整

 

### **脱离文档流**

------

由于block（块元素）是有内部文档流元素决定的，可以设置height。那么，有些元素是否可以不在文档流中？

- 如何让元素脱离文档流：

​       float

​       position：absolute / fixed

![](C:\Users\Administrator\Desktop\note\css\picture\d.png)

- 如何让元素不脱离文档流：

​       不用以上元素即可

# CSS盒子模型

### 两种盒模型

------

content-box和border-box

![](C:\Users\Administrator\Desktop\note\css\picture\g.png)

- **种类**

  content-box 内容盒：即内容就是盒子的边界（width）

  border-box 边框盒：即边框才是盒子的边界

- **公式**

  content-box width= 内容宽度

  border-box width=内容宽度+padding+border

- **常用**

​      一般常用border-box，指定的内容多，宽度计算较为便捷



### margin合并问题

------

- **magin合并情况**

**1.父子 margin 合并**

​       在父级没有border的情况下，有且仅有首位和末尾子集的margin与父级margin合并重叠（左右不重叠），谁的margin值大，则与谁合并

![](C:\Users\Administrator\Desktop\note\css\picture\h.png)

​       如上图，parent的margin值比孩子1和孩子5的margin值大，则parent的外边距吞并child的外边距



**2.兄弟 margin 合并**

   同级的块元素之间的margin也会合并，典型的如下图：

![](C:\Users\Administrator\Desktop\note\css\picture\i.png)

  孩子1与孩子2之间的margin被合并了！

  与父子合并相同，兄弟合并，同样是谁的mergin大，则显示它的margin。



- **阻止合并方法**

  ```
  1. **兄弟合并阻止方法**（兄弟合并本身就是预期的）：
  ```

​        引入 display：inline-block 使其由块元素变成内联块  

​    2.**父子合并阻止方法**：

​          **a.**用padding / border**挡住**； ![](C:\Users\Administrator\Desktop\note\css\picture\j.png)

​    

​        如图，在parent中加入border-top，即可挡住孩子1 侵占的12px！

​        还可以加入padding： ![](C:\Users\Administrator\Desktop\note\css\picture\k.png)

​        

​          加入padding后， 紫色部分增加孩子1上边框以上的紫色为孩子1本身的margin30px，空白部分为parent的margin

​       **b.使用overflow：hidden**

​          使用前： ![](C:\Users\Administrator\Desktop\note\css\picture\l.png)

​          使用后：

![](C:\Users\Administrator\Desktop\note\css\picture\m.png)

​         紫色部分增加，孩子1上边框以上的紫色为孩子1本身的margin30px，空白部分为parent的margin。

​       **c.加入 display：flex**



# CSS布局

CSS页面的布局技术允许我们拾取网页中的元素，并且控制它们相对正常布局流、周边元素、父容器或者主视口/窗口的位置。这使得我们对于网页界面的控制大大提升。



### 布局分类

---

css主要分为固定宽度布局、不固定宽度布局、响应式布局。

不固定宽度布局主要是依靠文档流，响应式布局是pc上固定宽度，手机上不固定宽度。

如何决定css布局呢？

**首先考虑是否需要兼容IE9**

**需要的话**，则：

​                            使用float布局 **->** 左浮两个，固定宽度，不要响应式 **->** 记得给父元素添加clearfix **->** 必要时候记得采用 -margin；

**不需要的话**，又分为两种情况，如果**只需要兼容最新的浏览器**，则：

​                             使用grid布局；

如果**不需要兼容最新的浏览器**，则：

​                             使用flex布局（必要的时候采用 -margin）

​                         

### float布局

---

- **步骤**

  子元素加float：left和width

  父元素加 .clearfix

- **经验**

  主要用于应付IE9，了解即可

### flex布局

---

   Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。

   实现 flex 布局需要先指定一个容器，任何一个容器都可以被指定为 flex 布局，这样容器内部的元素就可以使用 flex 来进行布局。

如：

```css
.container {
    display: flex | inline-flex;       //可以有两种取值
}
```

   **有六种属性可以设置于容器**：flex-direction、flex-wrap、flex-flow、justify-content、align-items、align-content。

-    flex-direction    **决定主轴的方向(即项目的排列方向)**
-    flex-wrap  **决定容器内项目是否可换行**
-    flex-flow  **flex-direction 和 flex-wrap 的简写形式**
-    justify-content  **定义了项目在主轴的对齐方式。**
-    align-items **定义了项目在交叉轴上的对齐方式**
-    align-content **定义了多根轴线的对齐方式，如果项目只有一根轴线，那么该属性将不起作用**

   ***有六种属性可运用在 item 项目上*（容器内部的元素）：**

- order **定义项目在容器中的排列顺序，数值越小，排列越靠前，默认值为 0**

- flex-basis **定义了在分配多余空间之前，项目占据的主轴空间，浏览器根据这个属性，计算主轴是否有多余空间**

- flex-grow  **定义项目的放大比例**

- flex-shrink **定义了项目的缩小比例**

- align-self **允许单个项目有与其他项目不一样的对齐方式**

- flex： **flex-grow flex-shrink flex-basis  缩写加，空格隔开**（**例子：**flex：1 100 100px；）

  

### gird布局

---

grid布局也叫网格布局，是最强大的 CSS 布局方案。

采用网格布局的区域，称为"容器"（container）。容器内部采用网格定位的子元素，称为"项目"（item）。

其主要适合不规则布局，想要了解或练习，可以参考：

 https://cssgridgarden.com/#zh-cn



# CSS定位

不同于css布局（平面），css定位是垂直于屏幕的。

我们可以通过下图来理解：

![](C:\Users\Administrator\Desktop\note\css\picture\o.png)





其用法主要是通过**position**属性指定一个元素在文档中的定位方式。[`top`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/top)，[`right`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/right)，[`bottom`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/bottom) 和 [`left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/left) 属性则决定了该元素的最终位置。

**主要属性：**

- `static`

  默认值。此时 `top`, `right`, `bottom`, `left` 和 `z-index `属性无效。

- `relative`

  相对定位，升起来但不脱离文档流，即本身位置不变，但脱离文档流。position:relative 对 table-*-group, table-row, table-column, table-cell, table-caption 元素无效。

- `absolute`

  绝对定位，元素会被移出正常文档流，并不为元素预留空间，通过指定元素相对于最近的非 static 定位祖先元素的偏移，来确定元素位置。绝对定位的元素可以设置外边距（margins），且不会与其他边距合并。

- `fixed`

  固定定位，定位记住你是viewport，元素会被移出正常文档流，并不为元素预留空间，而是通过指定元素相对于屏幕视口（viewport）的位置来指定元素位置。

`sticky`

元素根据正常文档流进行定位，然后相对它的*最近滚动祖先（nearest scrolling ancestor）*和 [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block) (最近块级祖先 nearest block-level ancestor)，包括table-related元素，基于`top`, `right`, `bottom`, 和 `left`的值进行偏移。偏移值不会影响任何其他元素的位置。



**经验：**

如果你写了absolute，一般都得补一个relative（父级元素）

如果你写了absolute或fixed，一定要补top和left

sticky兼容很差，主要用于面试ZB



**层叠上下文**：

- 比喻

  每个层叠上下文就是一个新的小世界（作用域）

  这个小世界里的z-index跟外界无关

  处在同一个小世界的z-index才能比较

- 可创建z-index的属性

  看[MDN文档](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)

  

​        

#  CSS动画

CSS动画最常用的属性有三个：transform（变形）、transition（过度）、animation（动态属性定位，配合@keyframe使用），在了解三个常用属性之前，我们可以先看看浏览器渲染原理。

### 浏览器渲染原理

---

**步骤：**

处理 HTML 标记并构建 **DOM 树**

处理 CSS 标记并构建 **CSSOM 树**

将 DOM 与 CSSOM 合并成一个渲染树（**render tree**）

**Layout**布局：根据渲染树来布局，以计算每个节点的几何信息（文档流、盒模型、计算大小和位置）

**Paint**绘制（把边框颜色、文字颜色、阴影等画出来）

**Compose**合成（根据层叠关系展示画面）



**更新样式：**

有三种更新方式，如下图：

![](C:\Users\Administrator\Desktop\note\css\picture\p.png)



**三种更新方式：**

- **第一种，全走**

  [div.remove()](http://js.jirengu.com/jagel/1/edit?html,css,js,output) 触发当前小事，其他元素relayout（重新布局）

  渲染查看： 开发者工具 -》 eac键 -》 rendering -》 paint flashing

- **第二种，跳过layout**

  [改变背景颜色](http://js.jirengu.com/jidam/1/edit?html,css,js,output)，直接repaint+composite

- **第三种，跳过layout和paint**

  [改变transform](http://js.jirengu.com/wusew/1)，只需composite。 必须全屏查看效果，在iframe里看有问题

  

 **如何知道每个属性触发的流程？**

 网站：https://csstriggers.com/



### transform

---

- **四个常用功能**

  位移 translate

  缩放 scale

  旋转 rotate

  倾斜 skew

- **经验**

  一般需要配合transition 过渡

  inline 元素不支持transform，需要先变成block

- **其他**

  [看mdn文档](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform)

### transition

---

- **作用**

  补充中间帧，为transform过渡

- **语法**

  transition：属性名 时长 过渡方式 延迟

  ​                        transition：left 200ms linear

  可以用否好分隔两个不同属性

  ​                        transition：left 200ms，top 400ms

  可以用all代表所有属性

  ​                        transition：all 200ms

  过渡方式有：linear 、 ease 、 ease-in 、ease-out 、ease-in等

- **注意**

​       并不是所有的属性都过渡，如：

​                                  display：none =》 block 没法过渡

​                                  一般改成visibility：hidden =》 visible

​        display和visibility区别在于：

​                                 display：none完全移除不显示，visibility：hidden不显示但会保留位置

​        background和opacity均可过渡

### animation

---

animation：时长 |过渡方式 | 延迟| 次数 | 方向 |  填充模式 | 是否暂停| 动画名；

时长： 1s 或 1000ms；

过渡方式： 跟transition一样；

次数： 3 或 2.4 infinite

方向： reverse | alternate | alternate-reverse

填充模式：none | forwards | backwards |both

是否暂停： paused | running

 以上属性都有对应的单独属性

**实践：**

transform动画红心：http://js.jirengu.com/nonud/1/edit?html,css,output

animation动画红心：http://js.jirengu.com/kabus/1/edit