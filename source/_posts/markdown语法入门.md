---
title: Markdown(.md)语法入门
categories: 技术
tags: markdown
---
  .md即markdown文件的基本常用编写语法,是一种快速标记、快速排版语言。
  
  ### 一、基本符号：* - +. >

  基本上所有的markdown标记都是基于这四个符号或组合，需要注意的是，如果以基本符号开头的标记，注意基本符号后有一个用于分割标记符和内容的空格。
  
  ### 二、标题
  
  #### 1.前面带#号，后面带文字，分别表示h1-h6,只到h6，而且h1下面会有一条横线
  
  ``` bash
  # 一级标题
  ## 二级标题
  ### 三级标题
  #### 四级标题
  ##### 五级标题
  ###### 六级标题
  ```
  
  #### 2.相当于标签闭合
  
  ``` bash
  # 一级标题 #
  ## 二级标题 ##
  ### 三级标题 ###
  #### 四级标题 ####
  ##### 五级标题 #####
  ###### 六级标题 #####
  ```
  
  效果如下：
  # 一级标题
  ## 二级标题
  ### 三级标题
  #### 四级标题
  ##### 五级标题
  ###### 六级标题
  
  ### 三、列表
  
  #### 1、无序列表
  
  ``` bash
  + a
  + b
  + c

  - d
  - e
  - f

  * g
  * h
  * i
  ```
  
  以上三种形式，效果其实都是一样的：
  
  + a
  + b
  + c

  - d
  - e
  - f

  * g
  * h
  * i


  #### 2、有序列表
  
  ``` bash
  1. abc
  2. bcd
  3. cde

  2. fgh
  3. ghi
  5. hij
  ```
  
  效果如下：
  
  1. abc
  2. bcd
  3. cde

  2. fgh
  3. ghi
  5. hij


  #### 3、嵌套列表
  
  ``` bash

  + 123
      + abc
      + bcd
      + cde
  + 465
  + 789

  1. abcd
      1. abcde
      2. abcde
      3. abcde
  2. bcde
  3. cdef
  ```
  
  效果如下：
 
  + 123
      + abc
      + bcd
      + cde
  + 465
  + 789

  1. abcd
      1. abcde
      2. abcde
      3. abcde
  2. bcde
  3. cdef


  ### 四、引用说明区块

  对某个部分做的内容做一些说明或者引用某某的话等，可以用这个语法。
  
  #### 1、正常形式
  
  ``` bash
  > 引用内容、说明内容。在语句前面加一个 > ，注意是英文的那个右尖括号，注意空格，引用因为是一个区块，理论上是应该什么内容都可以放，比如说：标题，列表，引用等等。
  ```
  
  效果：
  <div style='background: #f9f9f9;border-left: 10px solid #ccc;margin: 1.5em 10px;padding: 1em 10px 1em 10px;quotes: "\201C""\201D""\2018""\2019";'>引用内容、说明内容。在语句前面加一个 > ，注意是英文的那个右尖括号，注意空格，引用因为是一个区块，理论上是应该什么内容都可以放，比如说：标题，列表，引用等等。</div>

  #### 2、嵌套区块
  
  ``` bash
  > 一级引用
  ```
  
  效果：
  
  <div style='background: #f9f9f9;border-left: 10px solid #ccc;margin: 1.5em 10px;padding: 1em 10px 1em 10px;quotes: "\201C""\201D""\2018""\2019";'>一级引用</div>
  
  ### 五、代码块

  #### 1、少量代码，单行使用，直接用`包裹起来就行了
  
  ``` bash
  ` shaoliangdaima,danhangshiyong `
  ```
  
  效果：
  ` shaoliangdaima,danhangshiyong `
  
  #### 2、大量代码，需要多行使用，用```包裹起来

  \``` bash
	  daliangdaima,xuyaoduohangshiyong
	  daliangdaima,xuyaoduohangshiyong
	  daliangdaima,xuyaoduohangshiyong
	  daliangdaima,xuyaoduohangshiyong
	  daliangdaima,xuyaoduohangshiyong
  \```
  效果：
  ```
  	  daliangdaima,xuyaoduohangshiyong
  	  daliangdaima,xuyaoduohangshiyong
  	  daliangdaima,xuyaoduohangshiyong
  	  daliangdaima,xuyaoduohangshiyong
  	  daliangdaima,xuyaoduohangshiyong
  ```
  
  ### 六、链接

  #### 1、行内式

  链接的文字放在[]中，链接地址放在随后的()中，链接也可以带title属性，链接地址后面空一格，然后用引号引起来
  
  ``` bash
  [github](https://www.github.com "代码开源社区"),
  github是共产主义在软件开发领域的具体实现样板之一，即以生产资料社会公有制为基础（代码开源），以社会化合作（离散化的个人、组织等社会颗粒）为生产方式，主要采用合作社组织形式（项目组）的技术支撑平台。
  ```

  #### 2、参数式
  
  链接的文字放在[]中，链接地址放在随后的:后，链接地址后面空一格，然后用引号引起来
  
  ``` bash 
  [github]:https://www.github.com "代码开源社区", 
  是共产主义在软件开发领域的具体实现样板之一，即以生产资料社会公有制为基础（代码开源），以社会化合作（离散化的个人、组织等社会颗粒）为生产方式，主要采用合作社组织形式（项目组）的技术支撑平台。
  [github]:https://www.github.com '代码开源社区',
  是共产主义在软件开发领域的具体实现样板之一，即以生产资料社会公有制为基础（代码开源），以社会化合作（离散化的个人、组织等社会颗粒）为生产方式，主要采用合作社组织形式（项目组）的技术支撑平台。
  [github]:https://www.github.com (代码开源社区),
  是共产主义在软件开发领域的具体实现样板之一，即以生产资料社会公有制为基础（代码开源），以社会化合作（离散化的个人、组织等社会颗粒）为生产方式，主要采用合作社组织形式（项目组）的技术支撑平台。
  [github]:<https://www.github.com "代码开源社区">,
  是共产主义在软件开发领域的具体实现样板之一，即以生产资料社会公有制为基础（代码开源），以社会化合作（离散化的个人、组织等社会颗粒）为生产方式，主要采用合作社组织形式（项目组）的技术支撑平台。 
  ```
  
  两者效果都是：
  [github](https://www.github.com "代码开源社区"),是共产主义在软件开发领域的具体实现样板之一，即以生产资料社会公有制为基础（代码开源），以社会化合作（离散化的个人、组织等社会颗粒）为生产方式，主要采用合作社组织形式（项目组）的技术支撑平台。
  
  ### 七、图片

  #### 1、行内式

  和链接的形式差不多，图片的名字放在[]中，图片地址放在随后的()中，title属性（图片地址后面空一格，然后用引号引起来）,注意的是[]前要加上!
  
  ``` bash
  ![github.png](https://dss0.bdstatic.com/6Ox1bjeh1BF3odCf/it/u=593140000,1704329025&fm=218&app=92&f=PNG?w=121&h=75&s=6BE43A629ED797B53DA9AC8403008091 "github")
  ```
  
  #### 2、参数式
 
  图片的文字放在[]中，图片地址放在随后的:后，title属性（图片地址后面空一格，然后用引号引起来）,注意引用图片的时候在[]前要加上!
  
  ``` bash
  ![github.png]:https://dss0.bdstatic.com/6Ox1bjeh1BF3odCf/it/u=593140000,1704329025&fm=218&app=92&f=PNG?w=121&h=75&s=6BE43A629ED797B53DA9AC8403008091 "github"
  
  ![github.png]:https://dss0.bdstatic.com/6Ox1bjeh1BF3odCf/it/u=593140000,1704329025&fm=218&app=92&f=PNG?w=121&h=75&s=6BE43A629ED797B53DA9AC8403008091 'github'
  
  ![github.png]:https://dss0.bdstatic.com/6Ox1bjeh1BF3odCf/it/u=593140000,1704329025&fm=218&app=92&f=PNG?w=121&h=75&s=6BE43A629ED797B53DA9AC8403008091 ("github")
  
  ![github.png]:<https://dss0.bdstatic.com/6Ox1bjeh1BF3odCf/it/u=593140000,1704329025&fm=218&app=92&f=PNG?w=121&h=75&s=6BE43A629ED797B53DA9AC8403008091> "github"
  
  ```
  
  两者效果都是：
  ![github.png](https://dss0.bdstatic.com/6Ox1bjeh1BF3odCf/it/u=593140000,1704329025&fm=218&app=92&f=PNG?w=121&h=75&s=6BE43A629ED797B53DA9AC8403008091 "github")
  
  ### 八、分割线
  
  分割线可以由* - _（星号，减号，底线）这3个符号的至少3个符号表示，注意至少要3个，且不需要连续，有空格也可以
  
  ``` bash
  ---
  - - -
  ------
  ***
  * * *
  ******
  ___
  _ _ _
  ______
  ```
  
  效果：
  ------
  
  
  ### 九、其他
  
  #### 1、强调字体
  
  一个星号或者是一个下划线包起来，会转换为\<em\>倾斜，如果是2个，会转换为\<strong\>加粗
  
  ``` bash
  *md*    
  **md**
  _md_   
  __md__
  ```
  
  效果：
  *md*
  **md**
  _md_   
  __md__
  
  #### 2、转义

  基本上和js转义一样,\加需要转义的字符
  
  ``` bash
  \\
  \*
  \+
  \-
  \`
  \_
  ```
  
  #### 3、删除线

  用~~把需要显示删除线的字符包裹起来
  
  ``` bash
  ~~删除~~
  ```
  
  效果：
  ~~删除~~hhhhhaaaa
  
  ### 十、表格

  ``` bash
  |123|234|345|
  |:-|:-:|-:|
  |abc|bcd|cde|
  |abc|bcd|cde|
  |abc|bcd|cde|

  |123|234|345|
  |:---|:---:|---:|
  |abc|bcd|cde|
  |abc|bcd|cde|
  |abc|bcd|cde|

  123|234|345
  :-|:-:|-:
  abc|bcd|cde
  abc|bcd|cde
  abc|bcd|cde
  ```
  
  1. 表格的格式不一定要对的非常起，但是为了良好的变成风格，尽量对齐是最好的
  2. 分割线后面的冒号表示对齐方式，写在左边表示左对齐，右边为右对齐，两边都写表示居中

  效果如下：

  |123|234|345|
  |:-|:-:|-:|
  |abc|bcd|cde|
  |abc|bcd|cde|
  |abc|bcd|cde|

  |123|234|345|
  |:---|:---:|---:|
  |abc|bcd|cde|
  |abc|bcd|cde|
  |abc|bcd|cde|

  123|234|345
  :-|:-:|-:
  abc|bcd|cde
  abc|bcd|cde
  abc|bcd|cde
  

  ### 注：由于个别样式与博客样式冲突，效果与实际不符。请以[Markdown](http://markdown.p2hp.com/index.html "中文网")为准
  
  