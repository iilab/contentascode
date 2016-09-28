---
layout: page
title: Status
---

## Current

> [Contribute your ideas and discuss the approach of Content as Code #1](https://github.com/iilab/contentascode/issues/1)

> [Contribute your ideas and follow the discussion about the choice of authoring environment #5](https://github.com/iilab/contentascode/issues/5)

> [Help develop the proof of concept #7](https://github.com/iilab/contentascode/issues/7)

<!-- MarkdownTOC -->

- [Strategies](#strategies)
- [Implementations](#implementations)
- [Roadmap](#roadmap)
    - [Blog](#blog)
    - [Wiki](#wiki)
    - [Knowledge Base](#knowledge-base)
    - [Project Management](#project-management)
    - [CMS](#cms)
- [Milestones](#milestones)
    - [Proof of Concept - v0.0.1](#proof-of-concept---v001)
    - [Prototype - v0.1.0](#prototype---v010)
    - [Minimum Viable Implementation - v1.0.0](#minimum-viable-implementation---v100)
- [Follow](#follow)

<!-- /MarkdownTOC -->


## Strategies

The below roadmap is only loosely enforced and what drives progress on Content as Code is engagement from projects which are implementing such approaches and will help:
 - Develop building blocks with other development stacks
 - Extend features of existing building blocks (such as docsmith)
 - Participate in the user experience and technology design

## Implementations

 - Summary

|        Name       |            Description            |                        Repo URL                        |
|-------------------|-----------------------------------|--------------------------------------------------------|
| Content as Code   | Reference Implementation          | iilab/contentascode                                    |
| Open Integrity    | Data Framework                    | https://code.iilab.org/openintegrity/openintegrity.org |
| Open Mentoring    | Mobile Education                  | iilab/openmentoring                                    |
| Panic Button      | Simple CMS for Mobile App         | PanicInitiative/PanicButton                            |
| Using TBB         | Semantic Documentation experiment | elationfoundation/using-tor-browser-bundle             |
| Security in a Box | Work in Progress                  | coming soon                                            |
| Level Up          | Work in Progress                  | levelupcc/level-up                                     |
| TOTEM             | Work in Progress                  | coming soon                                            |
| Advocacy Assembly | Work in Progress                  | coming soon                                            |

 - Components / Stages

|        Name       | Source |         Author        | Generator  |  Build   | Integration |  Publishing |
|-------------------|--------|-----------------------|------------|----------|-------------|-------------|
| Content as Code   | Github | Markdown/Pandoc       | Metalsmith | npm      | Travis      | Gh-pages    |
| Open Integrity    | Gitlab | Prose/Markdown/Pandoc | Metalsmith | Sighjs   | Gitlab CI   | Self-hosted |
| Open Mentoring    | Github | Markdown/Marked       | Metalsmith | make     | Travis      | Gh-pages    |
| Panic Button      | Github | Prose/Markdown        | Jekyll     | gh-pages |             | Self-hosted |
| Using TBB         | Github | Markdown              | Jekyll     |          |             |             |
| Security in a Box | Gitlab | Markdown              |            |          |             |             |
| Level Up          | Github | Markdown              | Jekyll     | gh-pages |             | Self-hosted |
| TOTEM             | Gitlab |                       |            |          |             |             |
| Advocacy Assembly | Github |                       |            |          |             |             |

 - Publishing Channels

|        Name       | Web | Mobile | Book | Interactive |
|-------------------|-----|--------|------|-------------|
| Content as Code   | Yes | No     | No   | No          |
| Open Integrity    | Yes |        |      | Yes         |
| Open Mentoring    | Yes | Yes    | Soon | Some        |
| Panic Button      | Yes | Yes    | No   | Some        |
| Using TBB         | Yes |        |      |             |
| Security in a Box |     |        |      |             |
| Level Up          | Yes |        |      |             |
| TOTEM             |     |        |      |             |
| Advocacy Assembly |     |        |      |             |

## Roadmap

* TOC
{:toc}


### Blog
> In progress

 - [x] Initialise an empty project (`docsmith init metalsmith` (default) or `docsmith init jekyll`)
 - [ ] Assist in creating posts (a la Octopress or Docpad)
 - [ ] Authoring environment (a la Prose or Gitbook) [#5](https://github.com/iilab/contentascode/issues/5)
 - [ ] Validate/Check
 - [ ] Preview
 - [ ] Publish

### Wiki
> In progress

Some features of a wiki such as the 
 - [x] Submit page edits
 - [ ] Submit anonymous page edits
 - [x] View page history
 - [ ] Create new pages
 - [ ] Semantic features (a la Wagn or Semantic MediaWiki)
 - [ ] Federation (a la Smallest Federated Wiki)

### Knowledge Base
> Collective Intelligence. See [Open Integrity Framework](https://code.iilab.org/openintegrity/framework)

 - [ ] User Feedback mechanisms
     - [ ] Line/Section content review [#37](https://github.com/iilab/contentascode/issues/37) [#38](https://github.com/iilab/contentascode/issues/38)
     - 

### Project Management
> In progress

 - [x] Create tasks (via Github/Gitlab issue)
 - [ ] Follow tasks
     - [x] Via github/gitlab mentions *(for free)*
     - [ ] Via client side widget
     - [ ] With a smart notification [#46](https://github.com/iilab/contentascode/issues/46)
 - [ ] Update linked task status [#45](https://github.com/iilab/contentascode/issues/45)
 - [ ] Link tasks to pages [#24](https://github.com/iilab/contentascode/issues/37) [#38](https://github.com/iilab/contentascode/issues/24)
 - [x] See tasks in Kanban view [Leanlabs Kanban #35](https://github.com/iilab/contentascode/issues/35) [Waffle #36](https://github.com/iilab/contentascode/issues/36)

### CMS

 - [ ] Content review workflows
    - [ ] External review workflows [#20](https://github.com/iilab/contentascode/issues/20)
 - [ ] Translation [#4](https://github.com/iilab/contentascode/issues/4)
 - [ ] ...


## Milestones

### Proof of Concept - v0.0.1

In the run up to the IFF the proposed tasks to help get the partnership off the ground are:

#### Design

- ~~[Iterate on the ecosystem design document #1](https://github.com/iilab/contentascode/issues/1)~~
- ~~[Document translation workflow #2](https://github.com/iilab/contentascode/issues/2)~~
- [Implement translation workflow scripts #3](https://github.com/iilab/contentascode/issues/3)~~
- ~~[Document possible legacy technology constraints and requirements #4](https://github.com/iilab/contentascode/issues/4)~~
- ~~[Choose editor(s) as a basis for the authoring environment #5](https://github.com/iilab/contentascode/issues/5)~~
- ~~[Discuss Roadmap #6](https://github.com/iilab/contentascode/issues/6)~~

#### Implementation

- ~~[Implement Proof of Concept #7](https://github.com/iilab/contentascode/issues/7)~~

> ~~Milestone [Lift off](https://github.com/iilab/contentascode/milestones/Lift%20off)~~
> ~~Version [v0.0.1](https://github.com/iilab/contentascode/issues/7)~~ - https://github.com/iilab/contentascode/issues/7

 -  Authoring
     + [x] Github
     + [x] Jekyll
     + [x] Prose
 - Translation
     + [x] Transifex

 - Collaboration
     + [x] Github - Fork and pull request

 - Management
     + [x] Waffle 

 - CMS Parity
     + [ ] Comments - Github issues?
     + [ ] Stats - Piwik

 - Deployment
     + [ ] Single repo and one click deploy 


### Prototype - v0.1.0

Prototype should allow to do demos and showcase how key functionalities will work and improve existing content workflows.

> Milestone [Prototype](https://github.com/iilab/contentascode/milestones/Prototype) - https://github.com/iilab/contentascode/milestones/Prototype
> Version [v0.1.0](https://github.com/iilab/contentascode/issues/9) - https://github.com/iilab/contentascode/issues/9

### Minimum Viable Implementation - v1.0.0

Minimum viable implementation which would allow partners to adopt the workflow and technology in production.

> Milestone [Minimum Viable Implementation](https://github.com/iilab/contentascode/milestones/Minimum%20Viable%20Implementation%20) - https://github.com/iilab/contentascode/milestones/Minimum%20Viable%20Implementation%20
> Version [v1.0.0](https://github.com/iilab/contentascode/issues/8) - https://github.com/iilab/contentascode/issues/8

## Follow

Follow the progress of the Content as Code partnership and contribute:

 - By [commenting and creating github issues](https://github.com/iilab/contentascode/issues) 
 - By [watching the github repository](https://github.com/iilab/contentascode/subscription)
 - By joining us at the [Internet Freedom Festival](https://internetfreedomfestival.org/) content re-use session.

