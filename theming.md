#Theme Development

This article is about developing Phanbook Themes. If you wish to learn more about how to install and use Themes, review checkout [here](#)

## Why Phanbook Themes

Phanbook Themes are files that work together to create the design and use functionality of a Phanbook site.  Each Theme may be different, offering many choices for site owners to instantly change their website look.

## How To

You should check  directory themes at [github](https://github.com/phanbook/phanbook/tree/master/apps/themes), you juts to copy it then rename to your theme

## Template Files List

Here is the list of the Theme files recognized by Phanbook. Of course, your Theme can contain any other stylesheets, images, or files. Just keep in mind that the following have special meaning to Phanbook.


[**layout.volt**](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/layout.volt): The main template. If your Theme provides its own templates, layout.volt must be present. Because we use posts to for the page template. It will list all posts when you at [index page](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/posts/index.volt)


[**single page**](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/posts/view.volt) We have there view, first view page by question see here [view.volt](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/posts/view.volt), second we have article page see at [viewTip.volt](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/posts/viewTip.volt) and the signle page [hackernew.volt](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/posts/viewHackernew.volt). You can change anything structer html


[Author]() To custom layout user ask question, just to change structer html [user-ask.volt](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/user-ask.volt) similar for [user-anser.volt](https://github.com/phanbook/phanbook/blob/master/apps/themes/discourse/user-answer.volt)


##Css

Currently we have create a [custom.css](https://github.com/phanbook/phanbook/blob/master/public/css/custom.css) just to add css into that. Or you can create a directory ```themes/your-theme``` then put a css file