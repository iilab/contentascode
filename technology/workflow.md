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

## Progress

I suspect there's a smart use of Pull Requests. 
 - Tracking implementations progress. Maybe implementations fork the contentascode repo inside their organisation repo (or maybe a smaller "implementation" repo?) and "check" features or compatible APIs as they progress. This way users that want to follow progress of a particular implementation at a higher level can do so by subscribing to a pull request...

With the waffle approach, we might be able, and have an incentive to for display purposes on the board, to have another mechanism to group issues which is more task driven. This needs more thinking.

## Notifications

Piggy backing on the Githb/[Gitlab notifications](http://doc.gitlab.com/ee/workflow/notifications.html) seems like the low hanging fruit. These various levels are available:

*Participating* notifications are those in which you are directly involved in a conversation. You will automatically receive these notifications when:

- Someone mentions you or a team you're a member of
- You are assigned to an issue or pull request
- Someone makes a comment in a conversation you're subscribed to

*Watching* notifications are those in which you are actively watching a repository, but aren't necessarily participating. You will automatically receive these notifications for:

- Opened issues and their comments
- Opened pull requests and their comments
- Comments on any commits
- Published releases

Thoughts:
 - Watching the whole repo is an argument in favor of small modules/repos, but if so it might make subscription to a master repo harder.
 - Watching an issue thread, therefore navigation in issues - through tags, milestone - is key, and should also feed into the static generation
 - Watch a pull request, something well suited for external contributions.

## Public Chat

 - Rocket.Chat dedicated instance
 - IRC Bridge -> IRC public logs.
 - 

## RSS

It's interesting to think about how RSS could be used to track changes on the static website at various levels too.

## Notes

Semantics
 - Watch/Subscribe
    - Item
    - Group
 - Participate/Mentions
 - Configure Delivery
   - Channels
     - Email
     - RSS
     - IRC/Chat
     - Third party platform (Github/Gitlab/...)
   - Frequency
     - Immediately
     - Batch

The first step is to depend on an external service for notifications (despite the need to register/login). Good candidates are the Github/Gitlab issue trackers (Gitlab self-hosted allowing to avoid third party authentication dependencies). 

In that case there should be mappings of content items to issues (#24) and notifications can be managed through the issue subscription mechanism. Here are possible approaches:

#### Approach A
> Example for one master repo

Repo: https://github.com/iilab/contentascode
Issues: https://github.com/iilab/contentascode/issues

One issue could be mapped to one page.
 - PROS: The issue can be used as a discussion page. 
 - CONS: Lots of issues. 

Implementation:
 - At first an `issue` metadata key could be added with the issue number.
 - Later an issue could be created automatically via the issue tracker's API.
 - Commits could be checked and amended with the proper issue number so that they appear in the issue thread.

#### Approach B
> One master repo, issues are orthogonal to the content (a more classical setup between code and issue tracking or documentation and issues)

Repo: https://github.com/iilab/openmentoring-mobile
Issues: https://github.com/iilab/openmentoring-mobile/issues

#### Approach C
> Multiple subrepos, corresponding to "areas of interest"

Repo: https://code.iilab.org/openintegrity/openintegrity.org
Subrepos:
 - https://code.iilab.org/openintegrity/framework
 - https://code.iilab.org/openintegrity/design
 - https://code.iilab.org/openintegrity/practices
 - https://code.iilab.org/openintegrity/impact

