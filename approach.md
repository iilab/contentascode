---
layout: page
title: Approach
---

> [Contribute your ideas and discuss the approach of Content as Code](https://github.com/iilab/contentascode/issues/1)

* TOC
{:toc}


## Design Goals

These goals articulate our user-centric focus applied to the author/editor/translator/publisher experiences.

### Focused Writing

> The ability for authors to focus on their content and not have to think about the technology is a design goal.

The tools should disappear (literally with distraction free modes, or when using tools that are so familiar to us that we don't pay attention to them anymore - like the keyboard, or... Word).

Being able to let authors use the tools that allow them to be most productive and happy is a key goal of Content as Code. Allowing a diversity of tools to be used in this workflow is a design goal, but promoting and prioritising tools that are open source, modular and well designed is part of the implementation approach.

Read more about the [technology approach for content authoring](../technology/authoring)

### Localisation and translation

> Integrating translation and localisation deeply in the workflow and without adding complexity is a design goal.

Read more about the [technology approach for translation](../technology/translation)

### Low barrier to collaboration

> Allowing others to spot problems, develop new content or adapt content for new purposes is a design goal.

This should include the collaborative creation, adaptation and translation of content in sprints, remotely or with other innovative approaches.

### Track changes and manage contributions

> Maintain editorial coherence by making it easy to track, review and comment on changes coming from a range of sources and improving the editor's experience is a design goal.

### Content Reuse

> Allowing the discovery, tracking and updating of content used from other sources is a design goal.

Multimedia content, internal and external links should be easy to navigate and include in new content.

### Multiple publication channels

> Publishing to the web, books, mobile apps or other channels is a design goal.

# Content as Code Approach

There is a problem with content management in a [Post-CMS](#what-does-post-cms-means) context. For projects which have complex editorial workflows, adopting more lightweight approaches such as static site generation is still difficult, can create friction and are lacking in functionality.

Software engineering as a discipline, has been dealing with complex contribution processes requiring to create, move, merge, transform large quantities of code. This has led to the creation of tool to be able to trace the history of changes, allow very large team contributing to similar code bases and manage, reuse vast amounts of other project's code, track changes and organise review by peers, manage documentation and its obsolecence, translations of manuals and software, test problems as early as possible in order to rapidly and frequently build software artifacts that can be deployed across servers, computer and mobile devices.

Applying these concepts and lessons to editorial workflows is not trivial and requires a strong focus on author experience (as well as editor and translator experience).

## FAQ

### What does Post-CMS mean?

That we've been seduced and then disappointed by [CMSes](https://en.wikipedia.org/wiki/Content_management_system "Content Management Systems") which add too much complexity and therefore create problems of maintainability of content.

### Why use Markdown and not AsciiDoc/ReStructure/Textile/Wiki syntax?

That's a question of taste and we'll focus on Markdown first but we'll implement other syntaxes (and focus on software libraries that can switch syntaxes) and will accept contributions that go in this direction.

### Why not use XML/JSON/YAML... as the storage format?

Having a format which is has a track record for data storage seems like a natural direction to go to, however the popularity of Markdown and of formats like YAML (both used as the data format in this format, like in Jekyll and other static website generators) is based on the fact that the representation of the content/data is elegant mainly because it removes clutter/noise and it is more resilient to syntax errors (which some could see as allowing more data corruptions).

With this approach the thinking is that data corruptions will be caught by a quick feedback loop to the author, or simply by hiding structured data.

### Markdown + YAML or whatever format you design to store content/data is not proven!

That's not a question but ok, we understand why you're excited or worried about this. It's true that Markdown has a history of causing pains because of loose specifications but that's pretty much settled with the [CommonMark standard](http://commonmark.org/) with a wide range of [compliant implementations](https://github.com/jgm/CommonMark/wiki/List-of-CommonMark-Implementations). Also what we're proposing is to introduce block-level metadata or [```middlematter```](https://github.com/iilab/contentascode/issues/12). There is a tradition of deriving markdown and adding flavors. This has led to a ecosystem of sometimes competing approaches to do similar things (syntax for tables is a good example of this). We'll make sure to follow this tradition and generate a strong specification for our flavor. Given that the existing practice is already to mix Markdown and YAML, Markdown probably only needs to be extended very minimally in able to allow YAML to be included inline, in a way that is elegant and minimises clutter.

This integration should result in 2 well defined approaches to be used as a storage format and provide equivalence to other better known formats.

### Why not create a Word plugin?

Yes! There are existing plugins to manage Markdown in Word and this fits our goals to be interoperable and extensible.

### What about open formats for multimedia content

Yes! We love SVG and projects like MermaidJS which are promising ways to develop graphical content which can be reused, remixed and composed.
