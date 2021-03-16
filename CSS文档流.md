# CSS文档流

文档流即文档流动的方向

### 几个基本概念

---

- 文档流

- 块、内联、内联块

- margin合并

- 两种盒模型

  

### 文档流

---

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

---

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

---

由于block（块元素）是有内部文档流元素决定的，可以设置height。那么，有些元素是否可以不在文档流中？

- 如何让元素脱离文档流：

​       float

​       position：absolute / fixed

![](C:\Users\Administrator\Desktop\note\css\picture\d.png)

- 如何让元素不脱离文档流：

​       不用以上元素即可

