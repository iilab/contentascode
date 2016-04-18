---
layout: page
title: Technology
---

> Also see the [status page](../status) and [roadmap](../status#roadmap)

The following sub-pages describe the various technology related aspect of the content as code project

* Workflow Components
  * [Authoring](authoring)
  * [Translation](translation)
  * [Collaboration]()
  * [Management]()
  * [Reuse]()
* [Implementation](implementation)
* [Existing Approaches](existing) : Descriptions of existing approaches among project partners. 
* [Inspiration](inspiration) from other projects


<!-- MarkdownTOC -->

- [Technical Goals](#technical-goals)
    - [CMS Parity](#cms-parity)
    - [Flexible structure](#flexible-structure)
    - [Interoperable and extensible](#interoperable-and-extensible)
    - [Streamlined and extensible](#streamlined-and-extensible)
- [Components / Stack](#components--stack)
    - [Source](#source)
    - [Author](#author)
    - [Generate](#generate)
    - [Collaborate](#collaborate)
    - [Integrate](#integrate)
    - [Publish](#publish)

<!-- /MarkdownTOC -->

## Technical Goals

### CMS Parity

> Having usable solutions for commonly available features in CMSes is a design goal.

Have clear, integrated and open source solutions to deal with comments, visit statistics, search, forms and other features traditionally managed with a database backend.

### Flexible structure

> Allowing completely free form content structures or complex content structures is a design goal.  

### Interoperable and extensible

> Allowing mixed workflows that allow importing/exporting/synchronising content across systems and adding software components is a design goal.

### Streamlined and extensible

> Simplicity and ease of use and understanding are design goals.

Composed of many different software parts, the workflow is nonetheless streamlined and integrated. When deployed with default settings, it can be used immediately. Authors, editors, translators as well as software and systems engineer can understand how the pieces fit together.

## Components / Stack

This table aims to represent which components affect which stages of the content as code framework.
 - Key          : means that this component is a key component for this stage.
 - Change       : means that this component modifies or applies to this stage.
 - + component : means that this component works better with the specified component.
 - = component : means that this component only works with the specified component.
 - - component : means that this component doesn't work with the specified component.

| Component \ Stack |  Source  | Author |  Integrate  | Collaborate | Generate | Translate |  Publish   |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| github            | Key      |        | + travis    |             |          |           | + gh-pages |
| gitlab            | Key      |        | + gitlab-ci |             |          |           |            |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| prose             | + github | Key    |             |             | + jekyll |           |            |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| travis            |          |        | Key         |             |          |           |            |
| gitlab-ci         | - github |        | Key         |             |          |           |            |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| validate          |          |        | Change      |             |          |           |            |
| validate links    |          |        | Change      |             |          |           |            |
| validate style    |          |        | Change      |             |          |           |            |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| jekyll            |          |        |             |             | Key      |           |            |
| metalsmith        |          |        |             |             | Key      |           |            |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| transifex         |          |        |             |             |          | Key       |            |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|
| gh-pages          | + github |        |             |             |          |           | Key        |
|-------------------|----------|--------|-------------|-------------|----------|-----------|------------|

### Source

Source repositories which contain the sources for the current project. 

Note: These are not upstream dependencies which will be managed with metadata inside and alongside the source files.


### Author

This is where the content is edited, manipulated and so on. Different authoring environment will have different capabilities (for instance for validation without a server round-trip or workflow aspects...). 

### Generate

The static site generator used.

### Collaborate

Collaborating on the planning, authoring, editing, reviewing, commenting of content.

### Integrate

These are the tools used to prepare and validate content and give feedback to authors and editors, including presenting staging or testing environments/artifacts of various versions that are being worked on.
Note: Maybe this should be included in the publish component.

### Publish

These are the various channels where published versions will be available from.
