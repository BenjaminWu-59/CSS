# CSS随记：

### **border调试法**

---

任何元素都加个border：1px solid color（如果border会干扰整体，则使用outline）；



### 块元素居中

---

​      用

​            `margin： 0 auto；`

​      或

​             `margin-left： auto；`

​             `margin-right： auto；` 

​    第二个会更好, auto居中常只对块元素有用。



### rgba颜色应用

---

最后一位可以设置透明度，因此可以用来测试一些css属性。

在开发者工具中，我们可以找到相关代码，按下alt+下方向键来调整。



### css分层问题

---

margin和padding都是距离单位，剩下能够显示出来的有background、border、内容！

若>为覆盖，则：

​                              内容（最上层） > border > background (最下层) 



### 不准换行

---

 让文字不准换行的常用代码：

   `  white-space： nowrap；`



