##View Helpers

Writing and maintaining HTML markup can be quickly become a tedious tasks because of the naming conversions and numerous attributes that have to be taken into consideration. Phanbook build on Phalcon so it have full feature view helper Phalcon

### Take look some examples:

Assigning HTML attributes:

```
{{ text_field("price", "size": 20, "maxlength": 30, "placeholder": "Enter a price") }}

```

The following HTML is generated:

```
<input type="text" name="price" id="price" size="20" maxlength="30" placeholder="Enter a price" />

```

Static content hepler

Phalcon also provide helpers to generate tags such as script, link or img. They aid in quick and easy generation of the static resources of your application


```

{# Generate <img src="/your-app/img/hello.gif"> #}
{{ image("img/hello.gif") }}

{# Generate <img alt="alternative text" src="/your-app/img/hello.gif"> #}
{{ image("img/hello.gif", "alt": "alternative text") }}

```

To see full example go to https://docs.phalconphp.com/en/latest/reference/tags.html