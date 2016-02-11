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
| -------------------------------------------------------- | -------- | ------ | ------- | ------ |
| [Prose](https://prose.io)                                | Yes      | github | No      | No     |
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

|                 | Offline | Desktop | PDF | Dropbox | G Drive | Distraction free |
| --------------- | ------- | ------- | --- | ------- | ------- | ---------------- |
| Prose           |         |         |     |         | No      | Yes              |
| Gitbook         |         | Yes     | Yes |         | Yes     |                  |
| Dillinger       | Yes     |         | Yes | Yes     | Yes     | Yes              |
| Aloha           |         |         |     |         |         |                  |
| Pen Edit        |         |         |     |         | Yes     |                  |
| ContentEditable |         |         |     |         | Yes     |                  |


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
