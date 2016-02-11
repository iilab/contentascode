# Content as Code

**Content as Code** is a partnership to support content re-use and improve maintainability of content.

It is formed of implementers in organisations publishing free/libre and open source content and wanting to have lightweight (post-CMS) approaches to content management that focus on the author experience (as well as editor and translator experience).

## Goals

To develop workflows and technology in order to **make content authoring and management benefit from software engineering collaboration best practices**.

In particular by:
 - Using **Git** for version control
 - Using **Mardown** and enhanced flavors of Markdown for authoring
 - Developing better tools focusing on **author experience**
 - Developing pathways for **content contribution and review**
 - Enabling **translation workflows**
 - Support **static website generation** and interoperability with **content management systems**
 - Enable content reuse

# Roadmap

  - [Kick off](https://github.com/iilab/contentascode-site/milestones)

# Reference Implementation

This repo contains the source (```master``` branch) and generated (```gh-pages``` branch) site which is building http://iilab.github.io/contentascode-site

It is a reference implementation for the crump workflow for Github/Github Pages/Prose/Transifex and also depends on:
 - https://github.com
 - https://prose.io
 - https://transifex.com

Other implementations based on self-hosted software Gitlab/Jekyll/Prose will be developed.

## Install

 - You might need a ruby version manager (such as rvm)
 - You might need to ```bundle update```

## Build

To build the site:

 - Run ```bundle exec jekyll build``` (to generate the site in ```/_site```) or ```bundle exec jekyll serve``` (optionally with the ```--watch``` flag to rebuild automatically when a source markdown file changes) 

## Notes

 - This site was built by reusing the [using the Hyde](https://github.com/poole/hyde) theme.
 - Minor changes were made such as:
   - adding the ```gems``` key/values
   - removing the ```relative_permalinks: true``` 
   - kramdown's auto table of contents
   - adding source and edit links