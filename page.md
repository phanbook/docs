##The page context

Use: {{ post.getType() == 'pages'}} to detect this context.

## Description

Whenever you're viewing a static page, you're in the `page` context. The `page` context is not set on posts, which uses the [post context](doc:post-context) instead.

You can now create static pages (About, Contact, etc) easily in Phanbook. You just click the “New post link from the left menu, give your post a title (e.g “About Us”), and write the content of the post. Before hitting the “Publish” button, select the “Static Page” check box from the “Post Settings” menu, and this will remove your page from your post feed.

## Routes

The URL used to render a static page is always `/:slug/`. This cannot be customised, unlike post permalinks.

## Templates

The default template for a page is `page.volt`. 


Additionally, you can provide a custom template for a specific page. If there is a `pages/slug` file with the `slug` matching the static page's slug this will be used instead. 

For example, if you have an 'About' page with the url `/about/`, adding a template called `pages/about.volt` will cause that template to be used for the about page, instead of page.volt.


### Data

The `post` context provides access to the post object which match the route. Take look example below:

```
{{ post.id }} //get ID
{{ post.title }} or we get use {{post.getTitle()}}
```

Also, if you want to use array to instead object just convert for it `post.toArray()` and using

```
{{ post['id']}}
{{ post['title']}}

```

### Post (page) object attributes

- **id** - the incremental ID of the page  
- **title** - the title of your post page ([title helper](doc:title))
- **excerpt** - a short preview of your page content ([excerpt helper](doc:excerpt))
- **content** - the content of the page ([content helper](content))
- **url** - the web address for the static page ([url helper](doc:url))
- **thumbnail** - the cover image thumbnail with the page  ([image helper](doc:image))
- **editedAt** - date and time when the page was last updated  ([date helper](doc:date))
- **createdAt** - date and time when the page was created  ([date helper](doc:date))
- **tags** - a list of tags associated with the page (see [tags](doc:tags) for details)
- **usersId** - the user id of post page
- **type** - the type posts such as the blog, page, hackernews, etc
- **numberViews** - the users viewing this post page
- **numberReply** - the users replies on this post
- **sticked** - the sticked for this post default is "N"

- Also post have relationship with some object, for example to get information user: `post.user` is object of model Users so that you can gets any properties this model [here](https://github.com/phanbook/phanbook/blob/master/core/common/models/Users.php). Also you can try this for tag `post.tag`

## Helpers

Tobe update

## Example Code

```
{% if page is defined %}
        <div class="inner-container">
            <div class="single-content">
                <h1>{{ page.getTitle()}}</h1>
                <div class="item-content">
                    {{ page.getContent() }}
                </div>
            </div>
        </div>
{% else %}
    <p>You have not created this page /backend/pages</p>
{% endif %}
```