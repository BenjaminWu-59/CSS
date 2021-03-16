# CSS盒子模型

### 两种盒模型

---

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

---

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

      1. **兄弟合并阻止方法**（兄弟合并本身就是预期的）：

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

### 

