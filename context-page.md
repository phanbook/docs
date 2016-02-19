##The page context

Use: {{ post.getType() == 'pages'}} to detect this context.

## Description

Whenever you're viewing a static page, you're in the `page` context. The `page` context is not set on posts, which uses the [post context](doc:post-context) instead.


## Routes

The URL used to render a static page is always `/:slug/`. This cannot be customised, unlike post permalinks.

## Templates

The default template for a page is `page.volt`. 


Additionally, you can provide a custom template for a specific page. If there is a `pages/slug` file with the `slug` matching the static page's slug this will be used instead. 

For example, if you have an 'About' page with the url `/about/`, adding a template called `pages/about.volt` will cause that template to be used for the about page, instead of page.volt.


## Data

The `page` context provides access to the post object which matches the route. A page is just a special type of post, so the data object is called a post, not a page. See a full list of attributes below:

### Post (page) object attributes

- **id** - the incremental ID of the page  
- **title** - the title of your static page ([title helper](doc:title))
- **excerpt** - a short preview of your page content ([excerpt helper](doc:excerpt))
- **content** - the content of the page ([content helper](content))
- **url** - the web address for the static page ([url helper](doc:url))
- **thumbnail** - the cover image thumbnail with the page  ([image helper](doc:image))
- **updated_at:** - date and time when the page was last updated  ([date helper](doc:date))
- **created_at:** - date and time when the page was created  ([date helper](doc:date))
- **tags** - a list of tags associated with the page (see [tags](doc:tags) for details)
- 
## Helpers


## Example Code