---
title: Implementation
---

> Also see the [status page](status) and [roadmap](status#roadmap)

## Developer Experience

Focus on allowing user to start from a project scaffold:

  - a Blog (Jekyll compatible) with added "Contribute to this page" links.
  - a Wiki (Gollum compatible)
  - a Resource website
  - a Software documentation site 

We could create repos (```contentascode-blog```, ```contentascode-wiki```, ```contentascode-website```, ```contentascode-doc```) that are ready to clone with some sensible defaults. 

The default pipelines would have a travis.yml that push to a ```gh-pages``` branch.  

We could also look into Grunt-init or Yeoman Project Scaffolding tools to allow configuration of various options such as:

 - Choice of templating language and other frontend framework choices
 - Choice of integration backend (Jekyll/Metalsmith/...)
 - Choice of a theme (Bootstrap and variants, Foundation, GH Pages themes...)
 - Adoption of metadata schemas (SPAR, Provenance, DigiSec Taxonomy).
 - Configuration of tools like Prose with good usable defaults.
 - Enabling of other CI backends (Gitlab CI, Jenkins, Thoughtworks Go,...)
 - Configuration, integration and deployment (Heroku button style) of micro-services (like commenting, stats,...)

We also need to think about migration and various options to use [integrations](https://github.com/iilab/contentascode/labels/integration) to facilitate a progressive transition process from CMSes to the content as code approach.

## Reference Implementation Matrix

|                Name               |               Description                |  Repo  |    Editor    | Generator  |    Build     |   Hosting   |     Services     |
|-----------------------------------|------------------------------------------|--------|--------------|------------|--------------|-------------|------------------|
| scaffold-github-pages             | Fork and play.                           | Github | Prose        | Jekyll     | Github Pages | Github      |                  |
| scaffold-github-jekyll-travis     | With Jekyll and Travis CI                | Github | Prose        | Jekyll     | Travis       | Github      |                  |
| scaffold-github-metalsmith-travis | With Metalsmith and Travis CI            | Github | Prose        | Metalsmith | Travis       | Github      |                  |
| scaffold-jekyll-jenkins           | Open souce stack                         | Gitlab | Hosted Prose | Jekyll     | Jenkins      | Self-Hosted |                  |
| scaffold-metalsmith-gitlabci      | Open souce stack with metalsmith         | Gitlab | Hosted Prose | Jekyll     | Gitlab CI    | Self-Hosted |                  |
| infra-heroku                      | Push to deploy micro-service infra       | Gitlab | Hosted Prose | Jekyll     | Jenkins      | Heroku      | Single container |
| infra-docker                      | Docker single server micro-service infra |        |              |            |              |             | Multi-container  |
| infra-ansible                     | Distributed micro-service infra          |        |              |            |              |             | Multi-server     |

## Modularity

Scaffold and infrastructure repos might make some choices with regards to lower level implementation approaches (make vs bash vs gulp...) and it would be good to allow this to be plug and play. i.e. Content as Code should be opinionated with regards to concepts and architecture (and maybe its pivot data format, metadata description and other declarative things about workflow configuration), but not with regards to implementation.

