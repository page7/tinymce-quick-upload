tinymce-quick-upload
===================
A quick-upload plugin of tinymce.

How to use
--------
1. download quickupload folder, and save it in tinymce plugins path.

2. download and include [plupload](http://www.plupload.com/).

	```html
	<script src="../tinymce-path/tinymce.min.js"></script>
	<script src="../plupload-path/plupload.full.min.js"></script>
	```

3. add plugin "quickupload", and add button "quickupload".

	```js
	tinymce.init({
		selector: "textarea",
		plugins: ["quickupload"],
		toolbar: "quickupload",
		......
	});
	```

4. setting upload options.

	```js
	tinymce.init({
		.....
		plupload_basepath	: "../plupload-path/",
		upload_url			: "../upload.php",
		upload_post_params	: {action:"upload"},
		upload_file_size	: '1mb',
		upload_callback		: function(res) {
			if (res.status == 200)
				return res.response;  //image path
			else
				return false;
		}
	});
	```