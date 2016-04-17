---
title: git
stage: source
---

# Git

One of the most fundamental components of the content as code approach is the use of the distributed version control system git. It provides low level facilities for tracking changes and backing up ~~code~~ content in large file structures, create new versions (branches) as well as ways to deal with conflicts and merging different versions.

But one of the emerging practices that both Github and Gitlab have been focusing on have added a number of buildinb blocks to the low-level mechanics of git. Some of these are:
 - forks and tracking the "fork graph",
 - pull requests as a first class concept,
 - continuous integration reporting back at various levels (release, branches, pull requests) 
 - issue tracking deeply integrated with commits,
 - code review tools,
 - collaboration with @mentions and #issue references across repos.

It is really these emerging tools that offer the most promise in applying "code management" concepts to "content management".

One of the strategies of content as code is, in addition to having a author-centric approach to prioritising features and improving user experience, to follow a somewhat bottom-up, tech-centric approach simultaneously which aims to iterate on the above building blocks to see how well they can be assembled to provide new useful functionalities for content management.

Some of these ideas are currently being explored in the following issues on the content as code repo:
 - [Use of continuous integration to provide content verification and testing (#11)](https://github.com/iilab/contentascode/issues/11)
 - [Reporting of these tests, such as link checking, in pull requests (#11)](https://github.com/iilab/contentascode/issues/11#issuecomment-196234329)
 - [Implement github issues as a page discussion feature (#24)](https://github.com/iilab/contentascode/issues/24)
 - [Integration with waffle.io (#35)](https://github.com/iilab/contentascode/issues/35)
 - [Integration with kanban.leanlabs.io (#36)](https://github.com/iilab/contentascode/issues/36)
