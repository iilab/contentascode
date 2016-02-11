---
layout: page
title: Approach
---

* TOC
{:toc}

## Problem

There is a problem with content management in a Post-CMS context. For projects which have complex editorial workflows, adopting more lightweight approaches such as static site generation is still difficult, can create friction and are lacking in functionality.

## Approach

Software engineering as a discipline, has been dealing with complex contribution processes requiring to create, move, merge, transform large quantities of code. This has led to the creation of tool to be able to trace the history of changes, allow very large team contributing to similar code bases and manage, reuse vast amounts of other project's code, track changes and organise review by peers, manage documentation and its obsolecence, translations of manuals and software, test problems as early as possible in order to rapidly and frequently build software artifacts that can be deployed across servers, computer and mobile devices.

Applying these concepts and lessons to editorial workflows is not trivial and requires a strong focus on author experience (as well as editor and translator experience).

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

### Track changes and manage contributions

> Maintain editorial coherence by making it easy to track, review and comment on changes coming from a range of sources and improving the editor's experience is a design goal.

### Content Reuse

> Allowing the discovery, tracking and updating of content used from other sources is a design goal.

Multimedia content, internal links or external links should be easy to navigate and include in content.

### Multiple publication channels

> Publishing to the web, books, mobile apps or other channels is a design goal.


## Workflow FAQ

### What does Post-CMS means?

That we've been seduced and then disappointed by CMSes which add too much complexity and therefore create problems of maintainability of content.

### Why use Markdown and not AsciiDoc/ReStructure/Textile/Wiki syntax?

That's a question of taste and we'll focus on Markdown first but we'll implement other syntaxes (and focus on software libraries that can switch syntaxes) and will accept contributions that go in this direction.

### Why not create a Word plugin?

Yes! There are existing plugins to manage Markdown in Word and this fits our goals to be interoperable and extensible.

### What about open formats for multimedia content

Yes! We love SVG and projects like MermaidJS which are promising ways to develop graphical content which can be reused, remixed and composed.
