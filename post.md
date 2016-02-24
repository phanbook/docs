##The post context


### Description

Whenever you're viewing a single blog post, you're in the `post` context. The post context is not set on static pages, which uses the [page context](/docs/page) instead.


### Routes

The URL used to render a single post is configuration in the Phanbook dashboard. The default is `/blog/:id/:slug`. Phanbook has also options for date-based permalinks but we will commit coming soon

### Templates

The post context always uses the `single.volt` template. This template is required in all Phanbook themes. At present there is no support for custom post templates as there is for pages.


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

- Note: **post.status** have some type below:

```
'publish' - A published post or page
'pending' - post is pending review
'draft'   - a post in draft status
'future'  - a post to publish in the future
'private' - not visible to users who are not logged in
'trash'   - post is in trash bin.

```

### Helpers

Tobe update

### Example Code

```
{# Check post have exist #}
{% if post is defined %}
	<div class="inner-container media-padded">
        <h1 class="h2">{{ post.getTitle() }}</h1>
        <div class="author-container">
            <a href="/@{{post.user.getUsername()}}">
                {{post.user.getUsername()}}
            </a>
            <h2 class="author-name">by <a href="">{{ post.user.getInforUser() }}</a></h2>
            <div class="date">on {{ date("M j/y \a\t h:i", post.getCreatedAt()) }}</div>
        </div>
    </div>
{% endif %}
```