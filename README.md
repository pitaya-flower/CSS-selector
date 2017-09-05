# class 和 id 的使用场景

id定位到页面上唯一元素，而class定位到某一类元素。

# CSS选择器种类

 （1）基础选择器

 ```
* 通用选择器，匹配页面任何元素（这便决定了它很少被使用）

#id id选择器，匹配特定id的元素

.class 类选择器，匹配class特定类的元素

element标签选择器
```
（2）组合选择器
```
E，F 多元素选择器，用，分隔，同时匹配元素E和元素F

E F后代选择器，用空格分隔，匹配E元素所有的后代

E>F子元素选择器，用>分隔，匹配E元素所有的直接元素（注意此处选择是第一层级的，而嵌套的不会被选择）

E~F普通相邻选择器，匹配E元素之后的所有同级元素

E+F直接相邻选择器，匹配E元素之后的相邻同级元素F

.class1.class2表示既..又..（注意中间没有分隔符）

element#id用的不多#id本身就可以选择
```
（3）属性选择器
```
E[attr] 匹配所有具有属性attr的元素

E[attr=value]匹配所有属性为value的元素

E[attr~=value]匹配所有属性attr，具有多个空格分隔，其中一个值等于 value的元素。

E[attr^=value]匹配属性attr的值以value开头的元素

E[attr$=value]匹配属性attr的值以value结尾的元素

E[attr*=value]匹配属性attr的值包含value的元素
```
（4）伪类选择器
```
E:first-child 匹配作为长子的元素E

E:link 匹配所有未被点击的链接

E:visited 匹配所有已被点击的链接

E:active匹配鼠标已经按下但没有释放的元素

E:hover 匹配鼠标悬停其上的元素

E:focus 匹配获得当前焦点的元素

E:long(c)匹配long属性=c的元素

E:enabled 匹配表单中可用的元素

E:disabled 匹配表单中禁用的元素

E:checked 匹配表单中被选中的radio或checkbox元素

E:selection 匹配用户当前选中的元素

E:root 匹配文档的根元素，对于HTML文档，就是HTML元素

E:nth-child(n) 匹配其父元素的第n个子元素，第一个编号为1

E:nth-of-type(n)  与nth-child(n)作用类似，但是仅匹配使用同种标签的元素
```
（5）伪元素选择器
```
E::first-line 匹配E元内容的第一行

E::first-letter 匹配E元素内容的第一个字母

E::before 在E元素之前插入生成的内容

E::after 在E元素之后插入生成的内容
```
3. 选择器优先级；复杂场景如何计算优先级
```
（1）优先级（高到低）

1.在属性后面使用！important 会覆盖页面内任何位置定义的元素样式

2.作为style属性写在元素标签的内联样式

3.id选择器

4.类选择器

5.伪类选择器

6.属性选择器

7.标签选择器

8.通配符选择器

9.浏览器自定义
```
```
（2）复杂场景如何计算优先级：作如下归类：a=行内样式<div style="xxx"></div>；b=id选择器；c=类、属性和伪类选择器；d=标签、伪元素选择器；通过计算和比较大小来定夺谁优先，a大则最优先，a相等则比较b，以此类推。
```
## a:link, a:hover, a:active, a:visited 的顺序及原因
```
四个伪类选择器定义了"链接、已访问过的链接、鼠标停在上方时、点下鼠标时"的样式，正确使用顺序为：a:link  a:visited  a:hover  a:active 存在覆盖问题故要严格遵照这个顺序进行。
```

## 以下选择器含义
```
#header{ }    id为header的元素

.header{ }     class为header的元素

.header .logo{ }      class为header 子元素中 class为logo的元素

.header.mobile{ }     class同时包含header和mobile的元素

.header p, .header h3{ }     class为header元素中的p标签和h3标签

#header .nav>li{ }      id为header的class为nav元素的直接子元素为li的标签

#header a:hover{ }       id为header元素中的a标签的hover状态

#header .logo~p{ }      id为header下 class为logo标签之后所有的p标签

#header input[type=“text”]{ }      id为header的后代中，input标签中，属性type的值为"text"的元素集合
```

## div :first-child和div :first-of-type的作用和区别
```
first-child 匹配其父元素的第一个子元素

first-of-type 匹配其父元素下使用同种标签的第一个元素

div :first-child:匹配div下的第一个子元素

div :first-of-type:匹配div下同种类型第一个，得到可能不止一个

【 ！需要注意：加个空格会变成组合选择器，而这两个的区别同上两个一样，所匹配的目标不一样】
```
