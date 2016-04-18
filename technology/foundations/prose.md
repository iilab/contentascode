---
title: Prose
stage: author
issue: 47
---

- Integrate with Gitlab backend
- Easier "Fork and Pull Request" workflow for non techies.
- Allow offline workflow
- Metadata first document creation
- Transclusion support (iilab/prose#1)
- Prosemirror integration
- Content "Integration" tests #11 (perhaps with isomorphic tests ran by prosemirror in the client)


:[Choose editor(s) as a basis for the authoring environment #5 - Comment](https://github.com/iilab/contentascode/issues/5#issuecomment-197972547)

This [issue on ProseMirror](https://github.com/ProseMirror/prosemirror/issues/9) makes a good point about separation of concern between the editor and the backend. Substance might mean a slightly stronger coupling between document authoring, document metadata and project navigation and backend. 

In that sense Prose could be a project navigation component with ProseMirror as the authoring component (there would probably need to be some integration between the two to help for instance with navigation within a project's media or link library).  Prose would manage document metadata (in the YAML frontmatter or elsewhere) and connect to various backends (including local ones for offline editing). 

This gitbook component Repofs (https://github.com/GitbookIO/repofs) is an interesting approach to integrating the project navigation (and common features currently not in Prose like moving files, creating folders or dealing with templates.  