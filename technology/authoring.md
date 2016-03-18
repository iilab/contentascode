---
title: Authoring
---

>  [Contribute your ideas and follow the discussion about the choice of authoring environment](https://github.com/iilab/contentascode/issues/5)

* TOC
{:toc}

## Criteria

The authoring environment should be:

 - **Open source**
 - Running in the **browser**

6 potential candidate software are considered with these additional criteria:

 - **Markdown support**
 - **Git support**
 - **Inplace editing**
 - **Actively maintained**
 - **Extensible**, it should be easy to add functionalities. See [Analysis below](#analysis)

---

|                                                          | Markdown |  Git   | Inplace | Active |
|----------------------------------------------------------|----------|--------|---------|--------|
| [Prose](http://prose.io)                                 | Yes      | github | No      | No     |
| [Gitbook](https://www.gitbook.com/editor)                | Yes      | git    | No      | Yes    |
| [Dillinger](https://github.com/joemccann/dillinger)      | Yes      | github | No      |        |
| [Aloha](http://www.alohaeditor.org/demo/aloha-ui/)       |          |        | Yes     |        |
| [Pen Editor](http://sofish.github.io/pen/)               | Yes      | No     | Yes     | Yes    |
| [ContentEditable](http://html5demos.com/contenteditable) | No       | No     | Yes     | Yes    |

## Feature Gaps

Based on the [design goals](../../approach#design-goals) the following features should be implemented:

### Non negotiables

 - **Media**: Prose for instance manages media if in a single folder. Should have some library features. 
 - **Links**: Are too easy to break, or complicated to create. Should be checked client side.
 - **Metadata**: Even if content is made of several blocks (including reused blocks), they should be invisible and be previewable as a whole, carry invisible metadata and allow various degrees of structure to be enforced.

### Nice to haves / Possible Easy Wins

 - **Iconography**: Having an icon library like glyphicons or font-awesome would be... not bad.
 - **Forms**: After all that's what GFM ```- [ ]``` are.
 - **Diagrams**: Mermaid is where it's at.
 - **Offline**: Work offline or with an unhosted approach (remote storage git layer?)

### Unicorns

Let's say goodbye to google docs.

 - **Realtime collaboration**: Substance where have you gone... OT over Git please.
 - **Spreadsheet editing**: Quip style of course. There are a number of good looking spreadsheet.js approaches. 

## Analysis


### Project

|                                                          | OSS | Active |                 Comment                  |
|----------------------------------------------------------|-----|--------|------------------------------------------|
| [Prose](http://prose.io)                                 | Yes | No     | Huge community of contributors and users |
| [Gitbook](https://www.gitbook.com/editor)                | Yes | Yes    |                                          |
| [Dillinger](https://github.com/joemccann/dillinger)      | Yes |        |                                          |
| [Aloha](http://www.alohaeditor.org/demo/aloha-ui/)       |     |        |                                          |
| [Pen Editor](http://sofish.github.io/pen/)               | Yes | Yes    |                                          |
| [ContentEditable](http://html5demos.com/contenteditable) | No  | Yes    |                                          |


### Fundamentals

|           | Markdown |  Git   | Branches |     Metadata     | Comment |
|-----------|----------|--------|----------|------------------|---------|
| Prose     | Yes      | Github | Yes      | YAML/Frontmatter |         |
| Gitbook   | Yes      | Yes    |          |                  |         |
| Dillinger | Yes      | Yes    |          |                  |         |
| Pen Edit  | Yes      | No     |          |                  |         |
| Substance | No       | No     |          |                  |         |
| Realms    | Yes      | No     |          |                  |         |
| PupPub    |          |        |          |                  |         |


### UX


|           | InPlace | Preview | Toolbar |   Media    | Links | Metadata | Offline | Focused |
|-----------|---------|---------|---------|------------|-------|----------|---------|---------|
| Prose     | No      | Yes     | Yes     | Yes        |       | Yes      | No      | Yes     |
| Gitbook   | No      | Some    |         | Yes        |       | No       | Yes?    | Some    |
| Dillinger | No      |         |         | Yes        |       | Yes      | Yes     | Yes     |
| Pen Edit  | Yes     | Yes     |         | No         |       |          |         |         |
| Substance | No      | Yes     |         | Yes        |       | Yes      | Yes     | Yes     |
| Realms    | No      | Yes     |         | No toolbar |       | No       | No      | No      |
| PupPub    |         |         |         |            |       |          |         |         |


### Tech


|           | Lang | Frontend |     Backend     | Modular |  Style  |             Comments             |
|-----------|------|----------|-----------------|---------|---------|----------------------------------|
| Prose     | JS   | Backbone | Quite Stateless | Good    | Simple. | Bad code climate. Insecure deps. |
| Gitbook   |      |          |                 |         |         |                                  |
| Dillinger |      |          |                 |         |         |                                  |
| Pen Edit  |      |          |                 |         |         |                                  |
| Substance |      |          |                 |         |         |                                  |
| Realms    |      |          |                 |         |         |                                  |
| PupPub    |      |          |                 |         |         |                                  |

### Misc


|                 | Offline | Desktop | PDF | Dropbox | G Drive |         Comments         |
|-----------------|---------|---------|-----|---------|---------|--------------------------|
| Prose           |         |         |     |         | No      | Also has a table editor. |
| Gitbook         |         | Yes     | Yes |         | Yes     |                          |
| Dillinger       | Yes     |         | Yes | Yes     | Yes     |                          |
| Aloha           |         |         |     |         |         |                          |
| Pen Edit        |         |         |     |         | Yes     |                          |
| ContentEditable |         |         |     |         | Yes     |                          |


### Prose

### Dillinger

AngularJS - HTML enhanced for web apps!
Ace Editor - awesome web-based text editor
Marked - a super fast port of Markdown to JavaScript
Twitter Bootstrap - great UI boilerplate for modern web apps
node.js - evented I/O for the backend
Express - fast node.js network app framework @tjholowaychuk
Gulp - the streaming build system
keymaster.js - awesome keyboard handler lib by @thomasfuchs
jQuery - duh

### Aloha

### ...
