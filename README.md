Get Started
=====

## 不喜欢原始的ui，打算拿来自己改，把图标全部换成fontawesome的图标，或者阿里的图标库，并对不常用功能删减，优化文件上传，剔除底层后台语言的配置功能，使用自定义上传地址来完成上传，使上传七牛等第三方库更方便

## ueditor富文本编辑器介绍

UEditor是由百度web前端研发部开发所见即所得富文本web编辑器，具有轻量，可定制，注重用户体验等特点，开源基于MIT协议，允许自由使用和修改代码。

## 1 入门部署和体验

### 1.1 下载编辑器

1. `git clone ` 仓库
2. `npm install` 安装依赖（如果没有安装 grunt , 请先在全局安装 grunt）
3. 在终端执行 `grunt default`

### 1.2 创建demo文件
解压下载的包，在解压后的目录创建demo.html文件，填入下面的html代码

```html
<!DOCTYPE HTML>
<html lang="en-US">
<head>
	<meta charset="UTF-8">
	<title>ueditor demo</title>
</head>
<body>
	<!-- 加载编辑器的容器 -->
	<script id="container" name="content" type="text/plain">这里写你的初始化内容</script>
	<!-- 配置文件 -->
	<script type="text/javascript" src="ueditor.config.js"></script>
	<!-- 编辑器源码文件 -->
	<script type="text/javascript" src="ueditor.all.js"></script>
	<!-- 实例化编辑器 -->
	<script type="text/javascript">
	    var ue = UE.getEditor('container');
	</script>
</body>
</html>
```

### 1.3 在浏览器打开demo.html

如果看到了下面这样的编辑器，恭喜你，初次部署成功！

![部署成功](http://fex.baidu.com/ueditor/doc/images/demo.png)

### 1.4 传入自定义的参数

编辑器有很多可自定义的参数项，在实例化的时候可以传入给编辑器：
```javascript
var ue = UE.getEditor('container', {
    autoHeight: false
});
```

配置项也可以通过ueditor.config.js文件修改，具体的配置方法请看[前端配置项说明](http://fex.baidu.com/ueditor/#start-config1.4 前端配置项说明.md)

### 1.5 设置和读取编辑器的内容

通getContent和setContent方法可以设置和读取编辑器的内容
```javascript
var ue = UE.getEditor();
//对编辑器的操作最好在编辑器ready之后再做
ue.ready(function(){
    //设置编辑器的内容
    ue.setContent('hello');
    //获取html内容，返回: <p>hello</p>
    var html = ue.getContent();
    //获取纯文本内容，返回: hello
    var txt = ue.getContentTxt();
});
```

## 2 详细文档

ueditor 官网：[http://ueditor.baidu.com](http://ueditor.baidu.com "ueditor 官网")

ueditor API 文档：[http://ueditor.baidu.com/doc](http://ueditor.baidu.com/doc "ueditor API 文档")

ueditor github 地址：[http://github.com/fex-team/ueditor](http://github.com/fex-team/ueditor "ueditor github 地址")
