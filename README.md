XLoader
=======
A simple jQuery multi-image upload plugin.

简单的jQuery多图片上传插件

浏览器支持：Chrome，Safari，Firefox

使用方式
-------
1.引入jQuery与XLoader.js

2.创建表单：

    <form action="upload.php" method="post" enctype="multipart/form-data">
      <input id="file" type="file" name="images[]" accept="image/*" multiple>
      <button type="submit">Upload</button>
    </form>

3.激活多图片上传功能：

    <script type="text/javascript">
    $('#file').XLoader({
    	target : 'target.php' // 多图片上传目标脚本（必须）
    });
    </script>

参数说明
-------
当激活XLoader时，需要传递一个数组对象，以配置参数，参数列表如下：

* `target` : 多图片上传目标脚本（必须），图片上传通过此脚本进行
* `container` : 图片列表容器，默认在图片选择按钮下面展示
* `registerStyle` : 是否注册自带样式，默认注册
* `tableOptions` : 表格属性设置，默认：{id:'XLoaderTable'}
* `columnOptions` : 表格列设置，您可以指定哪些列显示，目前支持6列：number, image, name, size, textarea, modify
* `imageOptions` : 图片属性设置，默认：{}
* `textareaOptions` : 输入框设置，默认：{name : 'descriptions[]'}
* `deleteLinkOptions` : 删除链接属性设置，默认：{text:'Delete', class:'XLoaderDeleteLink'}
* `hiddenFieldName` : 图片文件名隐藏域的名称，默认：'imageNames[]'
* `resourcesUrl` : 资源请求url，如果需要载入已有图片，请设置该参数，默认：''

案例
-------
Bootstrap风格：

    <script type="text/javascript">
    $('#file').XLoader({
		target : 'target.php',
		container : '#XLoaderContainer',
		registerStyle : false,
		tableOptions : {class : 'table table-striped'},
		columnOptions : {
			number : {class : 'col-md-1'},
			image : {class : 'col-md-3'},
			name : {class : 'col-md-2'},
			size : {class : 'col-md-1'},
			textarea : {class : 'col-md-3'},
			modify : {class : 'col-md-2'}
		},
		textareaOptions : {class : 'form-control'},
		deleteLinkOptions : {class : 'btn btn-danger'},
		imageOptions : {class : 'img-rounded'}
	});
	</script>
	
