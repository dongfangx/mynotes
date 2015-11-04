### HTML学习教程
#### 基础

```
- <div>
- <h1> - <h6>
- <span>
- <p>
- <a>
- <img>
- <ul>
- <ol>
- <hr/>
- <br/>
- <!- ->
```
#### 表单

```
- <form>
- <input>
- <textarea>
- <label>
- <select> - <option>
- <button>
- <fieldset> 
```

#### 头部

```
- <title>
- <base>
- <meta>
- <script> - <noscript>
- <style>
```

#### URL

```
scheme://host.domain:port/path/filename

- scheme - 定义因特网服务的类型。最常见的类型是 http
- host - 定义域主机（http 的默认主机是 www）
- domain - 定义因特网域名，比如 w3school.com.cn
- :port - 定义主机上的端口号（http 的默认端口号是 80）
- path - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。
- filename - 定义文档/资源的名称 
```

#### 案列

```html
<!DOCTYPE html>
<html>
<head>
	<title>Title of the document</title>
	<link rel="stylesheet" type="text/css" href="mystyle.css">
	<meta name="keywords" content="HTML, CSS, XML" />

	<style type="text/css">
		body {background-color: red}
		p {margin-left: 20px}
	</style>
	<script type="text/javascript">
		document.write("Hello World!")
	</script>
	<noscript>Your browser does not support JavaScript!</noscript>
</head>
<body>
	<div><span>test</span></div>
	<h1>test</h1>
	<p>This is my first paragraph.</p>
	<a href="http://www.w3school.com.cn">This is a link</a>
	<img src="w3school.jpg" width="104" height="142" />

	<table border="1">
		<th>
			<td>t1</td>
			<td>t1</td>
		</th>
		<tr>
			<td>row 1, cell 1</td>
			<td>row 1, cell 2</td>
		</tr>
		<tr>
			<td></td>
			<td>row 2, cell 2</td>
		</tr>
	</table>

	<ul>
		<li>Coffee</li>
		<li>Milk</li>
	</ul>

	<ol>
		<li>Coffee</li>
		<li>Milk</li>
	</ol>

	<form>
		<labe>First name: </labe>
		<input type="text" name="firstname" />
		<br />
		<labe>Last name: </labe>
		<input type="text" name="lastname" />

		<input type="radio" name="sex" value="male" /> Male
		<br />
		<input type="radio" name="sex" value="female" /> Female

		<input type="checkbox" name="bike" />I have a bike
		<br />
		<input type="checkbox" name="car" />I have a car

		<input type="submit" value="Submit" />
	</form>
</body>
</html>
```

