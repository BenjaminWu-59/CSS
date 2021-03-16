# css基础概念

css发明者：赖先生（Håkon Wium Lie）首先提出。



### CSS最强之处：层叠样式

---

#### 层叠指什么？

- **样式层叠**

  可以多次对同一选择器进行样式声明

- **选择器层叠**

  可以用不同选择器对同一个元素进行样式声明

- **文件层层叠**

​       可以用多个文件进行层叠



### 了解各个浏览器支持的特性的方法

---

使用 caniuse.com 



### CSS学习方法

---

- **学习语法**
- **调试（怎么知道自己写错了）**
- **在哪里查资料**
- **标准制定者是谁（权威资料及解释）**



### 语法一

---
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

---

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

---

**方法**

- 使用[W3C验证器](https://jigsaw.w3.org/css-validator/#validate_by_input)

- VScode看颜色

- webstorm看颜色

- 开发者工具看警告(一般会有黄色感叹号提示)

  

**如何使用开发者工具**

找到你脑中的标签看它是否有选择器，看它的样式是否被划掉，看它的样式是否有警告



### Border调试法

---

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

---

- **网站推荐**

  google搜索关键词时加 MDN

  CSS tricks

  张鑫旭的博客

  

- **书籍推荐**

  不推荐
  
  

### 素材搜索

---

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

---

  CSS2.1标准[中文版](http://www.ayqy.net/doc/css2-1/cover.html)

