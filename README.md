# html5
### 记录有关html5的知识
# 网页：文字和图片，相当于是一个网络应用程序
# 美工
- UI设计师（界面设计）
- 前端开发工程师（交互）

# 网页排版：使用html来排版，成对出现
# html超文本标记语言，文件的扩展名为html或者htm
# html基本结构

```html
<!--文档声明，为html5-->
<!DOCTYPE html>
<!--定义网页的语言-->
<html lang="zh-CN">
<head>
    <!--定义网页的编码-->
    <meta charset="UTF-8">
    <!--定义网页的标题-->
    <title>我的第一个网页</title>
</head>
<body>
    欢迎访问我的网页
</body>
</html>
```
# 一个html文档就是一个网页，以html5为主
1. 标签建议全部小写
2. 属性值用双引号引起来
3. 标签应该闭合，成对的标签应该成对出现，单个的标签应该在结尾加" /"
4. img必须要加alt属性(对图片的描述)

```html
<!-- 成对出现的标签  -->
<body>......</body>
<p>......</p>
<div>......</div>
<b>......</b>

<!-- 单个出现的标签  -->
<br />
<img src="..." />
<input type="..." />

<!-- 标签之间的嵌套  -->
<p>
    <span>...</span>
    <a href="...">...</a>
</p>
<div>
      <h3>...</h3>
      <div>
              <span>...</span>
              <p>...</p>
      </div>
</div>
```
# 标题表签
```html
<h1>这是一级标题</h1>
<h2>这是二级标题</h2>
<h3>这是三级标题</h3>
```
# 段落标签
```html
<p>
HTML是 HyperText Mark-up Language 的首字母简写，意思是超文本标记语言，超
文本指的是超链接，标记指的是标签，是一种用来制作网页的语言，这种语言由一个个的
标签组成，用这种语言制作的文件保存的是一个文本文件，文件的扩展名为html或者htm。
</p>
```
# 换行标签

`<br />`
# 字符实体
- 空格：`&nbsp;`
- “<” 和 “>” 的字符实体为&lt;和&gt;
```html
<p>
    3 &lt; 5 <br>
    10 &gt; 5
</p>
```
# html块
- div标签:块元素，表示一块内容，没有具体的语义
- span标签:行内元素，表示一行中的一小段内容，没有具体的语义(类似于p标签)

# 含样式和语义的标签(实际开发中不使用，面试中使用)
1. em标签:行内元素，表示语气中的强调词
2. i标签:行内元素，原本没有语义，w3c强加了语义，表示专业词汇
3. b标签:行内元素，原本没有语义，w3c强加了语义，表示文档中的关键字或者产品名（加粗效果）
4. strong标签:行内元素，表示非常重要的内容（加粗效果）

# html图像，绝对路径和相对路径
```html
<img src="images/pic.jpg" alt="产品图片" />
```
- 其中alt属性值为图片加载失败时显示的文字
- 绝对地址在整体文件迁移时会因为磁盘和顶层目录的改变而找不到文件，相对路径就没有这个问题。相对路径的定义技巧：

- “ ./ ” 表示当前文件所在目录下，比如：“./pic.jpg” 表示当前目录下的pic.jpg的图片，这个使用时可以省略。

- “ ../ ” 表示当前文件所在目录下的上一级目录，比如：“../images/pic.jpg” 表示当前目录下的上一级目录下的images文件夹中的pic.jpg的图片。

# html链接
- <a>标签可以在网页上定义一个链接地址，通过src属性定义跳转的地址，通过title属性定义鼠标悬停时弹出的提示文字框。

```html
<a href="#"></a> 或者 <a href="">缺省值</a> # 表示链接到页面顶部  
<a href="http://www.itcast.cn/" title="跳转的传智播客网站">传智播客</a>
<a href="http://www.baidu.com" title="跳转到百度的网站">
    <img src="./images/3.png" alt="图片">
</a> # 图片链接
<a href="2.html">测试页面2</a> #跳转到另外一个页面
<a href="javascript:;">啥也不干</a> #表示什么事情也不做
```
- 注意：其中的target属性默认为_self,表示在本地覆盖，_blank表示新开一个窗口
# 定义页面内滚动跳转（页面的锚点）

- 页面内定义了“id”或者“name”的元素，可以通过a标签链接到它的页面滚动位置，前提是页面要足够高，有滚动条，且元素不能在页面顶部，否则页面不会滚动。

```html
<a href="#mao1">标题一</a>
......
......
<h3 id="mao1">跳转到的标题</h3>
```

# html列表
## 有序列表(实际开发中用的较少)
- 在网页上定义一个有编号的内容列表可以用ol、li配合使用来实现，代码如下：
```html
<ol>
    <li>列表文字一</li>
    <li>列表文字二</li>
    <li>列表文字三</li>
</ol>
```
- 在网页上生成的列表，每条项目上会按1、2、3编号，有序列表在实际开发中较少使用。

## 无序列表(实际开发中使用较多)
- 在网页上定义一个无编号的内容列表可以用<ul>、<li>配合使用来实现，代码如下：
```html
<ul>
    <li>列表文字一</li>
    <li>列表文字二</li>
    <li>列表文字三</li>
</ul>
```
## 定义列表
- 定义列表通常用于术语的定义。dl标签表示列表的整体。dt标签定义术语的题目。dd标签是术语的解释。一个dl中可以有多个题目和解释，代码如下：
```html
<h3>前端三大块</h3>
<dl>
    <dt>html</dt>
    <dd>负责页面的结构</dd>

    <dt>css</dt>
    <dd>负责页面的表现</dd>

    <dt>javascript</dt>
    <dd>负责页面的行为</dd>

</dl>
```
# html表格
## table常用标签
1. table标签：声明一个表格

2. tr标签：定义表格中的一行

3. td和th标签：定义一行中的一个单元格，td代表普通单元格，th表示表头单元格

## table常用属性：

1. border 定义表格的边框

2. cellpadding 定义单元格内内容与边框的距离

3. cellspacing 定义单元格与单元格之间的距离

4. align 设置单元格中内容的水平对齐方式,设置值有：left | center | right

5. valign 设置单元格中内容的垂直对齐方式 top | middle | bottom

6. colspan 设置单元格水平合并

7. rowspan 设置单元格垂直合并

## 传统布局 ##

- 传统的布局方式就是使用table来做整体页面的布局，布局的技巧归纳为如下几点：

1. 定义表格宽高，将border、cellpadding、cellspacing全部设置为0

2. 单元格里面嵌套表格

3. 单元格中的元素和嵌套的表格用align和valign设置对齐方式

4. 通过属性或者css样式设置单元格中元素的样式

# html表单 #
```html
<!-- form定义一个表单区域,action属性定义表单数据提交的地址，
method属性定义提交的方式。   -->
<form action="http://www..." method="get">

<!-- label标签定义表单控件的文字标注，input类型为text，定义了
一个单行文本输入框  -->
<p>
<label>姓名：</label><input type="text" name="username" />
</p>

<!-- input类型为password定义了一个密码输入框  -->
<p>
<label>密码：</label><input type="password" name="password" />
</p>

<!-- input类型为radio定义了单选框  -->
<p>
<label>性别：</label>
<input type="radio" name="gender" value="0" /> 男
<input type="radio" name="gender" value="1" /> 女
</p>

<!-- input类型为checkbox定义了多选框  -->
<p>
<label>爱好：</label>
<input type="checkbox" name="like" value="sing" /> 唱歌
<input type="checkbox" name="like" value="run" /> 跑步
<input type="checkbox" name="like" value="swiming" /> 游泳
</p>

<!-- input类型为file定义上传照片或文件等资源  -->
<p>
<label>照片：</label>
<input type="file" name="person_pic">
</p>

<!-- textarea定义多行文本输入  -->
<p>
<label>个人描述：</label>
<textarea name="about"></textarea>
</p>

<!-- select定义下拉列表选择  -->
<p>
<label>籍贯：</label>
<select name="site">
    <option value="0">北京</option>
    <option value="1">上海</option>
    <option value="2">广州</option>
    <option value="3">深圳</option>
</select>
</p>

<!-- input类型为submit定义提交按钮  
     还可以用图片控件代替submit按钮提交，一般会导致提交两次，不建议使用。如：
     <input type="image" src="xxx.gif">
-->
<p>
<input type="submit" name="" value="提交">

<!-- input类型为reset定义重置按钮  -->
<input type="reset" name="" value="重置">
</p>

</form>
```

