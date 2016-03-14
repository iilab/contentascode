---
layout: page
title: Technology
---

> Also see the [status page](status) and [roadmap](../status#roadmap)

The following sub-pages describe the various technology related aspect of the content as code project

* Workflow Components
  * [Authoring](authoring)
  * [Translation](translation)
  * [Collaboration](collaboration)
  * [Management](management)
  * [Reuse](reuse)
* [Implementation](implementation)
* [Existing Approaches](existing) : Descriptions of existing approaches among project partners. 
* [Inspiration](inspiration) from other projects

## Technical Goals

* TOC
{:toc}

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

## Previous Architecture

In the below diagram the following approach is proposed:

 - Content Partners : Adhere to content guidelines in order to facilitate interoperability at the editorial level (adaptation of content to various audience - profile, region... - and learning situations - training, self-paced, mobile,...).
 - Curation Layer: A content catalogue helps to understand and coordinate where content is available and where it is missing. It will also aim at collecting feedback metrics from publication partners (aggregated and anonymized).
   - Curation Tools: Will help draw from the Content Ecosystem to generate content ready for publication (for Open Mentoring this would generate StoryPath compatible Content Packs, alongside Markdown files ready for publication on the wen and generation as a printed guide / for others it might mean importing content into a CMS)
 - Publication Layer: Will consist of the layer which presents and makes the content accessible to the Learning End User.

![](architecture.png)


