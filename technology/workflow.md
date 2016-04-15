---
title: Workflow
---

# Content as Code Implementation Workflows

The contentascode repo should track overall framework discussions. It should use a tagging structure that helps follow the right level of interest or focus of work, for instance:
- `Meta` - Focus on organisational aspects, partnerships,...
- `Design` - Overall contentascode framework discussions such as use cases, users stories
- `API` - Discussion about shared APIs across implementations (`content update` or the `_content.yml` structures).
- `Documentation` - About the contentascode website as the main source of documentation for the effort, including onboarding, visual explanations, approach to communication.
- `Features` - Discussion and tracking of the progress of specific features across contentascode implementations. For instance `link checking` or `project scaffolding` or `automatic anchors`
- Logical grouping of `Features` or *Parity* with well known tools or stacks. Such as Blogging (or Octopress, Medium), or Wiki (or MediaWiki or Gollum), or CMSes (Drupal,...). 
> Right now I'm trying to use different tags for each "parity goals" but maybe having a `parity` tag and have several issues underneath would be better. Each issue linking to the other constituting issues, which raises the effort of linking slightly. 

I suspect there's a smart use of Pull Requests. 
 - Tracking implementations progress. Maybe implementations fork the contentascode repo inside their organisation repo (or maybe a smaller "implementation" repo?) and "check" features or compatible APIs as they progress. This way users that want to follow progress of a particular implementation at a higher level can do so by subscribing to a pull request...

## Notifications

Piggy backing on the Githb/[Gitlab notifications](http://doc.gitlab.com/ee/workflow/notifications.html) seems like the low hanging fruit. These various levels are available:
 - Watch the whole repo (an argument in favor of small modules/repos)
 - Watch an issue thread (therefore navigation in issues - through tags, milestone - is key, and should also feed into the static generation)
 - Watch a pull request (something well suited for external contributions)

## Public Chat

 - Rocket.Chat dedicated instance
 - IRC Bridge -> IRC public logs.
 - 

## RSS

It's interesting to think about how RSS could be used to track changes on the static website at various levels too.