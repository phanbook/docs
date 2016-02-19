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


### Partials

You can also use options `/partials` for your theme. This should include any part templates you want to use across your Q&A or Blog site, for example `list-posts.volt` might include your template for outputting a single post in a list, which might then used on the home, author, tags page. See the example code below:


```
├── /assets
    ├── /css
        ├── app.css
    ├── /fonts
    ├── /images
    ├── /js
├── /partials
    ├── list-post.volt

```

One way to use partials is to treat them as the equivalent of subroutines: as a way to move details out of a view so that your code can be more easily understood. For example, you might have a view that looks like this:

```
<div class="top"><?php $this->partial("partials/header"); ?></div>

<div class="content">
    <h1>Robots</h1>

    <p>Check out our specials for robots:</p>
    ...
</div>

<div class="footer"><?php $this->partial("partials/footer"); ?></div>
```

Or Volt stynax 


```
<div class="top">{{ partial("partials/header")}}</div>

<div class="content">
    <h1>Robots</h1>

    <p>Check out our specials for robots:</p>
    ...
</div>

<div class="footer">{{partial("partials/footer")}}</div>
```
You can also passing the value to partials, take look example below

```
<div id="footer">
    <div id="footer">{{ partial("partials/footer", ['links': links]) }}</div>
</div>

```

### Layouts

Using a `layouts/layout.volt` file as a default layout for all templates is highly recommended. You can extend the layout.volt file in any other file using the layout syntax:

```
{% extends 'layouts/layout.volt' %}

```

It is possible to specify multiple layouts, and also to nest layouts. Also you can see template inheritance at [here](https://docs.phalconphp.com/en/latest/reference/volt.html#template-inheritance)



