

# Web基础

## 网页的基础结构

![网页的基础结构](./assets/%E7%BD%91%E9%A1%B5%E7%9A%84%E5%9F%BA%E7%A1%80%E7%BB%93%E6%9E%84.png)

## Html

```html
<!DOCTYPE html> <!--声明规范-->
<html>

	<head>	<!--开头-->
		<meta charset="utf8" />	<!--声明字符集-->
		<title>标题</title>
	</head>
    
	<body>
	<!--主体-->
	</body>

</html>
```

### 单标签or空标签

```html
<hr/>水平线
<br/>换行
```

### 标题

```html
<hn align="对齐方式">标题文件</hn>
<!--n取值1-6，align为可选属性默认为左对齐-->

<h2 align="center">你好，欢迎来的我的网站</h2>
<h3 align="right">Hello,Welcome to my WebSite</h3>


<p>
    文字段
</p>
```

### 插入图片

```html
<img src="图片路径"/>
```

### 超链接

```html
<!-- 文字链接 -->
<a href="https://www.example.com">点击跳转</a>

<!--给图片插入超链接-->
<a href="https://目标网址">
  <img src="图片路径.jpg" alt="描述文字">
</a>
```

### 锚点链接

> **id 唯一性**：同一页面内锚点 `id` 必须唯一。
>
> **兼容性**：部分旧浏览器可能不支持特殊字符（如空格），建议用短横线（`-`）命名。
>
> **动态内容**：单页面应用（SPA）可能需要额外处理锚点跳转逻辑。

```html
<!--建跳转链接
用 href="#id名称" 指向锚点
-->
<a href="#section1">跳转到第一章</a>

<!-- 跨页面跳转锚点
若从其他页面跳转，需在链接中包含页面路径和锚点：
-->
<a href="page.html#section1">跳转到其他页面的锚点</a>


<p><a href="#A">1.6-12个月宝宝语言激发方案</a></p>

<p><a name="A">1.6-12个月宝宝语言激发方案</a></p>
```

### 转义字符

| 显示 | 说明           | 实体名称 | 实体编号 |
| ---- | -------------- | -------- | -------- |
|      | 半方大的空白   | &ensp    | &#8194   |
|      | 全方大的空白   | &emsp    | &#8195   |
|      | 不断行的空白格 | &nbsp    | &#160    |
| <    | 小于           | &lt      | &#60     |
| >    | 大于           | &gt      | &#62     |
| &    | &符号          | &amp     | &#38     |
| "    | 双引号         | &quot    | &#34     |
| ©    | 版权           | &copy    | &#169    |
| ®    | 已注册商标     | &reg     | &#174    |
| ™    | 商标（美国）   | &trade   | &#8482   |
| ×    | 乘号           | &times   | &#215    |
| ÷    | 除号           | &divide  | &#247    |

### 表格

```html
<table>
	<tr>行
	<th></th>表头
	</tr>
	<td>元素定义单元格
</table>
```

### 列表

#### 无序列表

```html
<ul type=编号类型--默认为实心圆>
    <li>第一项</li>
	<li>第二项</li>
	<li>第三项</li>
</ul>

disc--实心圆
circle--空心圆
square--小方块
```

#### 有序列表

```html
<ol type=编号类型 start=value>
    <li>第一项</li>
	<li>第二项</li>
	<li>第三项</li>
</ol>

1--表示列表项月用数字标号(1.2.3...)
A--表示列表项目用大写字母标号(A,B,C...)
a--表示列表项目用小写字母标号(a,b,c...)
I--表示列表项目用大写罗马数字标号(I,II,III...)
i--表示列表项目用小写罗马数宁标号(i ii i.)
```

#### 定义列表

```html

```



## 构建网站层叠样式表即CSS  Cascading Style Sheet

### 基础选择器&标签选择器

```css
p {
    color:red;
    font-size:18px;
    e
    line-height:30;
}

选择器{
    属性1:属性值1;
    属性2:属性值2;
    属性3:属性值3;
}
```

![基础选择器](./assets/%E5%9F%BA%E7%A1%80%E9%80%89%E6%8B%A9%E5%99%A8.png)

### 调用

```css
行内样式
<p style="background-color:#f00;color: #fff;font-size:24px;font-family:'微软雅黑';">Hello,Html</p>

内部样式
<head>
<style type="text/css">
		p{
			background-color:#f00;
			color: #fff;
			font-size:24px;
			font-family:'微软雅黑';
		}
		</style>
</head>
<body>
	<p>内容</p>
</body>
```

### 链接样式表

> index.html

```html
<head>
		<meta charset="utf-8" />
		<title></title>
		<link href="css/style.css" type="text/css" rel="stylesheet"/>
<!--
href="css/style.css"
表示CSS文件的路径：
css/ 是文件夹名
style.css 是具体文件名
路径类型：
相对路径（相对于当前HTML文件所在位置）
若使用绝对路径可写为：/css/style.css（从网站根目录开始）

type="text/css"
声明资源类型为CSS（HTML5中可省略，浏览器会自动识别）

rel="stylesheet"
定义关联关系为样式表（必须属性）
-->
	</head>
	<body>
		<section>
			<header>
				<h2>安徽黄山</h2>
			</header>
			<p>世界文化与自然双重遗产，世界地质公园，国家AAAAA级旅游景区，国家级风景名胜区。</p>
		</section>

```

> style.css

```css
section{
	margin: 5px auto;
	width:940px;
	height: 190px;
	background-image: url(../img/banner.png);
	border-radius: 0.625rem;
	
}

h2{
	color: #FFFFFF;
	font-family: "微软雅黑";
	text-align: center;
	line-height: 3.75rem;
	
}

p{
	color: #fff;
	font-size: 18px;
	text-align: center;
}
```

### 类选择器&自定义标签类型

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>类选择器</title>
        <!--创建style type="text/css" 在标签内定义标签类型-->
        <!--格式为： .类型名{格式} -->
		<style type="text/css">
			.redtitle{font-family: "微软雅黑";color: red; text-align: center; text-decoration: underline;}
			.content{color: green;}
			.font30{font-size: 30px;}
		</style>
		
	</head>
	<body>
        <!--使用class调用-->
		<h2 class="redtitle">类选择器</h2>
		<p class="content">类选择器能够把不同元素分类定义成不同的样式</p>
		<p class="content font30">定义时，在自定义类的前边需要加一个英文.</p>
	</body>
</html>

```

类选择器

![类选择器](./assets/%E7%B1%BB%E9%80%89%E6%8B%A9%E5%99%A8.png)

id选择器

标签指定式选择器

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style>
			p{color: blue;}
			.special{color: green;}
			p.special{color: red;}
            <!--碰到p的时候变为红色-->
			
		</style>
		
	</head>
	<body>
		<p>普通段落文本（蓝色）</p>
		<p class="special">指定了.special类的段落文本（红色）</p>
		<h2 class="special">指定了.special类的标题文本（绿色）</h2>
	</body>
</html>
```

