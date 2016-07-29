---
layout: post
title: Metalsmith Static Website Generator: Plugins
---

As Content management systems become increasingly bloated, buggy, and rife with security exploits, programmers are looking for better website creation tools. The <a href="https://developmentseed.org/blog/2012/07/27/build-cms-free-websites/">post-CMS</a> approach replaces poorly coded and integrated functionality of CMS programs with a suite of established open source tools such as Static Website Generators, Git version control, web-based content editors, and microservices. The new movement called <a href="http://iilab.github.io/contentascode">Content As Code,</a> aims for programmers to limit program complexity and pick the tools that most support the content. In this post I will review <a href="http://www.metalsmith.io">Metalsmith</a> Static Website Generator and walk through several core Metalsmith plugins that aim to provide powerful functionality using as little code as possible. I will also show how plugin functionality is invoked and why this is essential. You will gain a practical understanding of Static Generator applications as an alternative to CMS program page creation process. This post is intended as an introduction for new programmers. 

To generate static pages, Metalsmith reads content in a source directory, executes a series of actions defined by plugins, and writes the processed data to a destination directory. The sequential compiling of plugins is a process unique to Metalsmith. Within the context of Metalsmith, plugins are single purpose components invoked by a configuration file.  Remarkable in comparison to traditional CMS programs like Drupal, only two plugins, metalsmith-markdown and metalsmith-layouts, are necessary to generate a static page.

Metalsmith source files are formatted using<a href ="http://daringfireball.net/projects/markdown/syntax#precode"> markdown </a>. Because markdown is a plain text language, it is both human readable and easily translated to HTML and many other languages. 

* An example of a simple markdown file.
```
---
title: First Post
date: 2012-08-20
layout: post.html
---
An interesting post about how it's going to be different this time around. I'm going write a lot more nowadays and use this blog to improve my writing.
```
Markdown files consist of <a href ="https://jekyllrb.com/docs/frontmatter/">frontmatter</a> and content. The frontmatter, which is flanked by a set of dashed lines, is metadata that provides Metalsmith and it’s plugins with parameters for handling the file’s content. Everything after frontmatter is considered content. 

Metalsmith-markdown plugin translates markdown syntax to HTML. 

* The translated content from the previous example looks like this.
```
<p>An interesting post about how it&#39;s going to be different this time around. I&#39;m going write a lot more nowadays and use this blog to improve my writing.</p>
```
----------
To then structure the file, Metalsmith-layouts plugin parses the HTML tagged content into a layout template defined in the source file’s frontmatter.

* An example of a template file.
```
<html>
<head>
  <title>My Blog</title>
</head>
<body>
  <h1 style="color:{{ color }}">{{ title }}</h1>
  <time>{{ date | date('Y-m-d') }}</time>
  {{ contents | safe }}
</body>
</html>
```
* A set of double brackets indicates placeholders in the template file where metalsmith-layouts parses in content from the source file. 
```
{{ contents | safe }}
```

* Template files also contain placeholders where frontmatter content is inserted. 

A frontmatter pattern.
```
{{ title }}
```
* Relevant frontmatter.
```
title: First Post
```
----------
* The compiled markdown and template outputs a static webpage.
```
<html>
<head>
  <title>My Blog</title>
</head>
<body>
  <h1 style="color:">First Post</h1>
  <time>2012-08-20</time>
  <p>An interesting post about how it&#39;s going to be different this time around. I&#39;m going write a lot more nowadays and use this blog to improve my writing.</p>
</body>
</html>
```
----------
Metalsmith-markdown and Metalsmith-layouts is all that is required to render a basic static webpage. However, there are many more plugins to choose from to add functionality. Next, I walk through three additional plugins, metalsmith-permalinks, metalsmith-drafts, and metalsmith-debug. 

To structure a permalink, a formatted file path, metalsmith-permalinks plugin transforms file names with a pattern. A key/value pair provides the pattern parameters. Plugin objects and their parameters are invoked in the main Metalsmith configuration file, metalsmith.json.
```
"metalsmith-permalinks": {
        "pattern": ":title"
     }
```
In this example, Metalsmith-permalinks generates a permalink based on the title provided in the frontmatter.

* Relevant frontmatter.
```
title: First Post
```
* The generated permalink.
```
first_post/index.html 
```
----------
The ability to create draft pages is an important tool in managing website content. It allows for content creation and page publication to be controlled separately. Metalsmith-drafts plugin looks to see if the source file is earmarked as a draft. 

```
draft: true
``` 
If this is the case, Metalsmith does not generate a static html file.

----------
Logging tools are essential to understanding and debugging code. Metalsmith-debug plugin enables processing and compiling logs. To view the most recent log file enter into the terminal window.
```
DEBUG=* metalsmith 
```
----------

Because plugins are separate components, a good mechanism for managing and invoking them is vital. This is the job of the metalsmith.json configuration file. It contains all necessary plugin parameters in one plugin object.

```
{
  "source": "./_posts",
  "destination": "./_site",
  "metadata": {
    "title": "My Jekyll-Powered Blog",
    "description": "My second, super-cool, Jekyll-powered blog."
  },
    "plugins": {
      "metalsmith-markdown": {},
      "metalsmith-drafts": true,
      "metalsmith-permalinks": {
        "pattern": ":title"
     },

      "metalsmith-layouts": {
         "engine": "swig",
         "directory": "_layouts"
    },
     "metalsmith-debug": {}
  }
}
```
The small file also contains metadata, including the locations of source and destination directories.

In summary, Metalsmith is comprised of separate single function plugins managed by one configuration file. Rather than the default extensive and interdependent functionality of a CMS program, Metalsmith’s modular components and lean programming enables better control of the page creation process which in turn promotes site ownership. Metalsmith and Static Web Generators are just one tool in the post-CMS goal of content prioritization. I encourage you to read further about <a href ="https://www.staticgen.com">Static Website Generators</a> and explore some additional tools such as <a href="https://git-scm.com">Git version control</a> and <a href="http://prose.io/#about">web-based content editors.</a>







