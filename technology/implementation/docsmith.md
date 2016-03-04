---
title: docsmith
---

# docsmith

> An npm module called [docsmith](https://www.npmjs.com/package/docsmith) has been published with the following README.md

[Content as Code](https://contentascode.io) aims to make it easy to start a website in just a few steps but also build complex content publishing pipelines. It develops best practices to managing content workflows inspired from how code is managed in large collaborative software engineering projects.

**docsmith** implements the [Content as Code](https://contentascode.io) framework using metal*smith*, pan*doc* and *doc*ker microservice deployment.

## Getting Started

The simplest way to get started is to fork one of our sample repos on github:
 - https://github.com/contentascode/blog: A template for a simple blog
 - https://github.com/contentascode/wiki: A template for a wiki
 - https://github.com/contentascode/doc: A template for software documentaiton
 - https://github.com/contentascode/site: A template for a simple website

You can have these templates up and running simply by [activating Github pages on your fork](link). This will make the site available after a few minutes on http://USER.github.io/REPO where ORG is the name of the user or organisation which forked the repo, and REPO is the name of the REPO (which should be blog or site, unless you renamed it.)

Wow, that was easy and fast. What can I do next?

### Use your own domain name

You can make your new site available on the domain name of your choice. If you have procured a domain name you can simply create a CNAME file at the base of this repository and point your DNS following these instructions.

### Collaboration

The Content as Code workflow uses best practices to allow different people to contribute to your content project, in the way that large software engineering projects in the open source world do it.

The sample repos use Github (soon Prose) to help with content editing. By default, all pages of your new website have built in links to  

### Checking Links

You can go to the next level by using another free online service (Travis CI) to build your site. This will provide you with additional features such as using validations. For instance to check that links are working or that your content is generally well formatted and readable. You can activate travis by going to travis-ci.com signing up and activating travis for your USER/REPO project.

Is that it? Yes, now you'll receive emails with notifications each time there is a problem with your website build, like a broken link or possible other problems with your site.

### Choose a theme

You can change our default website layout and theme if you have activated Travis CI in the previous step. In that case, you can edit the docsmith.yml file and change the theme to another content as code enabled jekyll theme we support.

### What next?

We're planning to implement many more features with a content as code approach for instance doing diagrams, interactive content, or integration with and migration from your existing content management system.

If you want to go deeper into **docsmith** and content as code, you can also help us develop the command line tool we have started designing below which will help more advanced users with more sophisticated content management needs. It is based on a modular approach

## Docsmith CLI tool

 - ```npm install -g docsmith``` : installs content CLI tool.

 - ```docsmith init```: Or ```docsmith init <template>``` like ```docsmith init blog```, ```docsmith init doc``` or ```docsmith init wiki```.
 - ```docsmith install``` : in a repo would read content.yml and create package.json, metalsmith.json and docker-compose.json and run necessary installations (npm install,...). 

 - ```docsmith build```: Build the content locally.
 - ```docsmith serve```: Serve the content locally. (Should probably open a console and allow to `pull`,`update` or `pull` within it)
 - ```docsmith publish```: Publishes the content (and configure and/or deploy needed microservices).

 - ```docsmith load/pull``` : Get local content updates 
 - ```docsmith load/pull <version>```: Get specific version.
 - ```docsmith update```: Get remote content dependency updates.
 - ```docsmith save/push``` : Push content source updates and advertise changes.
 - ```docsmith save/push <version>``` : Push content source updates and advertise changes.

Example ```docsmith.yml```:

```yaml
source: .                       # By default uses current directory, should be able to pull a remote directory too.
build: 'auto'                   # Uses the default mode of the build system to determine where to build
components:
  source: 'github'              # Defaults to github could also be gitlab or a local folder or a remote url. Gollum for a wiki?
  transform: ''                 # Maybe some type of pre-processing
  validate: ''                  # Defaults to empty. List of validation scripts, for instance links,...
  editor: 'github'              # What is the content authoring environment? Could be prose, realms,...
  build: 'github-pages'         # How is the build pipeline managed. could be travis, gitlab-ci, drone, local Makefile...  
  generate: 'github-pages'      # How is the site generated. Could be github-pages, jekyll, metalsmith, hugo... 
  publish: 'github-pages'       # Where is the content hosted? 
  discuss: 'github-issues'      # Discussion threads, comments, wiki style discuss page...
  review: 'github'              # Line based review like github code comments
  stats: 'piwik'
  dependencies: ''
```

 - ```docsmith modules``` : display list of available modules.
 - ```docsmith source``` : display current source settings.
 - ```docsmith source gitlab``` : changes repo to gitlab.
 - ```docsmith build travis-ci``` : changes build system to travis ci.
 - ```docsmith validate links``` : Adds link validator module.

# Components API

## repo 

### API

 - pull: get the latest (or default) version from the content repo.
 - update: pulls dependencies (through git submodules or a package management approach or another yet to be developed approach)
 - version: get a specific version (github version tag or branch or ). From docsmith's perspective all versions are really branches that can be worked on a later merged onto other versions aiming to pick the best merge strategy based on heuristics.
 - push: pushes local changes to content repo.

### Implementation

Configures the build pipeline (for now metalsmith) with the proper and desired source content version. This should allow to wrap dependency management (include with git submodules if wanted).

### repo-github

 * This module connects docsmith to a github repository as a content source.
 * Configuration options
     - `repo`: 
         + `url` : (Required) URL of repo.
         + `branch`: (Optional - Defaults to master) 


## build

### API

 - build: 
 - watch:

### build-github-pages

 * Configuration options
     - `source`
       +

## validate

