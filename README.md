# jQuery File Browser version 0.6.4

jQuery File Browser is a plugin for creating OS like file browsers.

[Demo](http://codepen.io/jcubic/pen/aBKYRR)

#installation

to install you can grab the files from the repo or install from

## bower

```
browser install jquery.filebrowser --save
```

## npm

```
npm install jquery.filebrowser --save
```

include the files:

```html
<script src="js/jquery.filebrowser.min.js"></script>
<link href="css/jquery.filebrowser.min.css" rel="stylesheet"/>
```

and you can use this code to initialize the plugin:

```javascript
$(function() {
	var browse = $('#browser').browse({
		root: '/',
		separator: '/',
		dir: function(path, callback) {
			if (path == '/') {
				callback({dirs: ['foo', 'bar'], files: []});
			} else if (path == '/foo/') {
				callback({dirs: [], files: ['baz', 'quux']});
			} else if (path == '/bar/') {
				callback({dirs: [], files: ['lorem', 'ipsum']});
			} else {
				callback(null); // for cases when you type wrong path in address bar
			}
		},
		open: function(filename) {
			console.log('opening ' + filename);
		}
	});
});
```

# License

Licensed under [MIT](http://opensource.org/licenses/MIT) license

Copyright (c) 2016 [Jakub Jankiewicz](http://jcubic.pl)