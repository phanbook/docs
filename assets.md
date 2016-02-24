##Asset

{{asset}} Helper - Safely add assets to your theme

### Description

The {{asset}} helper exists to take the pain out of asset management. It component that allows you to manage static resources such as CSS stylesheets or JavaScript libraries in a web application.

### Example

To use the {{asset}} helper to output the path for an asset, simply provide it with the path for the asset you want to load, relative to the assets folder.

For css:

```
<link rel="stylesheet" type="text/css" href="{{asset "css/app.css"}}" />

```

For js

```
<script type="text/javascript" src="{{asset "js/app.js"}}"></script>

```

For theme images:

```
<img src="{{asset "images/my-image.jpg"}}" />
```

Note: There's no need to switch between double and single quotes when writing HTML with handlebars. Double quotes can be used for both because the handlebars is executed first.

If you want to use assets of Phalcon go to [here](https://docs.phalconphp.com/en/latest/reference/assets.html)

