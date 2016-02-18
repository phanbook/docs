## Overview of Phanbook file structure

The recommend files structure is:

```
.
├── /assets
|   └── /css
|       ├── app.css
|   ├── /fonts
|   ├── /images
|   ├── /js
├── info.php  [required]
├── post.volt [required]
└── single.volt [required]
└── [required]
|__ /layouts
	|
	|___layout.volt [required]


```

To see whole structure you can take look at http://github.com/phanbook/blog or inside directory content/themes/default

If you use assets, it is required that you keep them inside of an assets folder of the themes, and make use of the `{{assets}}` helper for service css, js, images and other assets files. Without this, your theme may use customs assets collection from component Phalcon PHP, see [here](https://docs.phalconphp.com/en/latest/reference/assets.html)