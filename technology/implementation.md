---
title: Implementation
---

> See the **work in progress for the [docsmith](docsmith) reference implementation**

> Also see the [status page](../../status) and [roadmap](../../status#roadmap)

## Developer Experience

Focus on allowing user to start from a project scaffold:

  - a Blog (Jekyll compatible) with added "Contribute to this page" links.
  - a Wiki (Gollum compatible)
  - a Resource website
  - a Software documentation site 

We could create repos (```contentascode-blog```, ```contentascode-wiki```, ```contentascode-site```, ```contentascode-doc```) that are ready to clone with some sensible defaults. 

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
| scaffold-jekyll-jenkins           | Open source stack                        | Gitlab | Hosted Prose | Jekyll     | Jenkins      | Self-Hosted |                  |
| scaffold-metalsmith-gitlabci      | Open source stack with metalsmith        | Gitlab | Hosted Prose | Jekyll     | Gitlab CI    | Self-Hosted |                  |
| infra-heroku                      | Push to deploy micro-service infra       | Gitlab | Hosted Prose | Jekyll     | Jenkins      | Heroku      | Single container |
| infra-docker                      | Docker single server micro-service infra |        |              |            |              |             | Multi-container  |
| infra-ansible                     | Distributed micro-service infra          |        |              |            |              |             | Multi-server     |

## Modularity

Scaffold and infrastructure repos might make some choices with regards to lower level implementation approaches (make vs bash vs gulp...) and it would be good to allow this to be plug and play. i.e. Content as Code should be opinionated with regards to concepts and architecture (and maybe its pivot data format, metadata description and other declarative things about workflow configuration), but not with regards to implementation.

This table aims to represent which components affect which stages of the content as code framework.
 - Key          : means that this component is a key component for this stage.
 - Change       : means that this component modifies or applies to this stage.
 - +1 component : means that this component works better with another component.
 - -1 component : means that this component doesn't work with another component.

| Component \ Stage |   Source  | Author |   Build   |  Integrate   | Translate |   Publish   |
|-------------------|-----------|--------|-----------|--------------|-----------|-------------|
| github            | Key       |        |           | +1 travis    |           | +1 gh-pages |
| gitlab            | Key       |        |           | +1 gitlab-ci |           |             |
| prose             | +1 github | Key    | +1 jekyll |              |           |             |
| jekyll            |           |        | Key       |              |           |             |
| metalsmith        |           |        | Key       |              |           |             |
| travis            |           |        |           | Key          |           |             |
| gitlab-ci         | -1 github |        |           | Key          |           |             |
| linkchecker       |           |        |           | Change       |           |             |
| transifex         |           |        |           |              | Key       |             |
| gh-pages          | +1 github |        |           |              |           | Key         |

| Components \ Worfklow | Store | Edit | Share | Check | Translate | Publish |
|-----------------------|-------|------|-------|-------|-----------|---------|


