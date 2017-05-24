---
layout: post
title: Creating file templates
date: 2017-05-23 20:21:00
categories: Plugins
author:
  name: 'Colin Bartlett'
  email: 'colin@colinabartlett.com'
  url: 'https://colinabartlett.com'
  github: cbartlett
---

Software projects are commonly composed of similar files in a specific location and new files typically require some minimal boilerplate. Tim Pope's [projectionist.vim](https://github.com/tpope/vim-projectionist) offers a handy way to templatize the creation of new files directly in Vim.

The [Vim Tricks codebase](https://github.com/cbartlett/vimtricks), which is based on [Jekyll](https://jekyllrb.com/), is a perfect candidate for such a file template since creating new Vim Tricks requires adding a file to the _\_posts_ directory. and that file follows a standard format with metadata.

After installing Projectionist, we can create a _.projections.json_ file in the project root that defines the file type we want. In this case, _post_. The most basic usage of Projectionist simply defines the file type along with a path glob:

{% highlight json %}
{
  "_posts/*.md": {
    "type": "post"
  }
}
{% endhighlight %}

After reopening Vim, we can now use `:Epost` along with tab completion to open any existing post. If we pass the name of a file that does not exist, Projectionist opens a new empty buffer for us at that path. For example:

`:Epost 2017-10-31-carving-a-pumpkin`

will open a buffer called _\_posts/2017-10-31-carving-a-pumpkin.md_.

From here, we can extend our projection to include a template for new posts:

{% highlight json %}
{
  "_posts/*.md": {
    "type": "post",
    "template": [
      "---",
      "layout: post",
      "title: {blank}",
      "date:",
      "categories:",
      "author:",
      "  name:",
      "  email:",
      "  url:",
      "  github:",
      "---",
    ]
  }
}
{% endhighlight %}

The _template_ attribute of the projection accepts an array of lines to prepopulate the buffer. There are even a host of filters such as _capitalize_, _camelcase_, or _blank_ which we've used here to convert the _-_ characters to spaces.

Now, when we navigate to a new post with `:Epost whatever-we-want`, the file will open with the exact template we need to create a new post!

{% highlight yaml %}
---
layout: post
title: Whatever we want
date:
categories:
author:
  name:
  email:
  url:
  github:
---
{% endhighlight %}

This same technique is used in the [rails.vim plugin](https://github.com/tpope/vim-rails) to prepopulate models, controllers, helpers, and more. You can really extend this to just about any file type and it requires running no generation script from a command line.
