[![Build Status](https://travis-ci.org/iilab/contentascode.svg?branch=master)](https://travis-ci.org/iilab/contentascode)

# Content as Code

**Content as Code** is a partnership which develops workflows and technology to improve content re-use and maintainability.

It is formed of implementers in organisations publishing free/libre and open source content and wanting to have lightweight (post-CMS) approaches to content management that focus on the author experience (as well as editor and translator experience).

## Goals

To develop workflows and technology to **make content authoring and management benefit from software engineering collaboration best practices**.

In particular by:
 - Using **Git** for version control
 - Using **Markdown** and enhanced flavors of Markdown for authoring
 - Developing better tools focusing on **author experience**
 - Developing pathways for **content contribution and review**
 - Enabling **translation workflows**
 - Support **static website generation** and interoperability with **content management systems**
 - Enabling content reuse

# Roadmap

  - [Lift off](https://github.com/iilab/contentascode/milestones)

# Reference Implementation

This repo contains the source (```master``` branch) and generated (```gh-pages``` branch) site which is building http://iilab.github.io/contentascode

It is a reference implementation for the crump workflow for Github/Github Pages/Prose/Transifex and also depends on:
 - https://github.com
 - https://prose.io
 - https://transifex.com

Other implementations based on self-hosted software Gitlab/Jekyll/Prose will be developed.

## Install

 - You might need a ruby version manager (such as rvm)
 - You might need to ```bundle update```

## Build

This repo should build automatically on Github Pages. To build the site locally for development:

```
bundle exec jekyll serve --watch --baseurl ''
```

You can also run ```bundle exec jekyll build``` (to generate the site in ```/_site```) or ```bundle exec jekyll serve``` (optionally with the ```--watch``` flag to rebuild automatically when a source markdown file changes) 

## Notes

 - This site was built with the [Hyde](https://github.com/poole/hyde) theme.
 - [Minor changes were made](https://github.com/poole/hyde/compare/master...iilab:master) such as:
   - adding the ```gems``` key/values
   - removing the ```relative_permalinks: true``` 
   - kramdown's auto table of contents
   - adding source and edit links
 - I use [this trick](http://stackoverflow.com/a/7472481) to keep the master branch synchronised with the gh-pages branch
