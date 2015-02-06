tinymce-quick-upload
===================
This is a quick upload plugin for tinymce.

use it
--------
1. download quickupload folder, and save it in tinymce plugins path.

2. download and include [plupload](http://www.plupload.com/).

	```html
	<script src="../tinymce-path/tinymce.min.js"></script>
	<script src="../plupload-path/plupload.full.min.js"></script>
	```

3. add plugin "quickupload", and button "quickupload".

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
		upload_basepath: '/_develop/plupload/js/',
		upload_url: './moxiemanager/api.php',
		upload_callback: function(res) {
			if (res.status == 200)
				return res.response;  // a image path.
			else
				return false;
		}
	});
	```