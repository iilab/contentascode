---
title: Existing Approaches
---

* TOC
{:toc}

## Overview

|              | Content Format | Content Authoring |     Content Publication      |         Content Delivery         |
|--------------|----------------|-------------------|------------------------------|----------------------------------|
| SIAB         | Wyswiwyg       | Drupal            | Drupal                       | Drupal Web                       |
| Umbrella     | Markdown       | Manual            | SQL -> SQlite DB             | Native Android                   |
| Story Maker  | YAML           | Git / tx          | YAML -> Zipped JSON (Python) | Native Android (StoryPath/Liger) |
| SSD          | ?              | Drupal            | Drupal                       | Drupal Web                       |
| Panic Button | Markdown       | Prose / tx        | md -> JSON (Jekyll)          | Native Android (custom)          |

 - SIAB uses Drupal and aims to publish or manage content as markdown files. Possibly evolving towards a static Markdown files, possibly evolving to provide a Content API. https://github.com/securityinabox/siabguide
 - Umbrella is a native Android app, the content is generated from csv files into an asset database (probably sqlite) in the APK. https://github.com/securityfirst/Umbrella_android
 - Story Maker is an Android app using the StoryPath (formerly liger) library to load content packs stored as YAML files. There is a transifex workflow but I'm not sure about how the content is authored. https://github.com/StoryMaker/content-packs https://github.com/StoryMaker/storypath
 - EFF uses Drupal. The repo doesn't seem to have the content of the guide. https://github.com/EFForg/ssd 
 - Panic Button is a native Android app using a custom made JSON file parser to generate its interface (similar but less mature concept than StoryPath). Content is authored in Prose as Markdown and Jekyll generates the JSON files. There's an ongoing effort to interop with Transifex.
 - Digital First Aid Kit's source is a git repository of markdown files. Not sure about how the website and printed versions are generated. https://github.com/RaReNet/DFAK
 - Level Up uses Drupal. No source code or content I could find.

## Interoperability approaches


|                       | Interop Maturity |               Rationale                |
|-----------------------|------------------|----------------------------------------|
| SIAB                  | ++               | Markdown in Git / Close to Content API |
| Umbrella              | -                | CSV / Not Git                          |
| Story Maker           | +++              | Spec and Library                       |
| SSD                   | -                | No content source ?                    |
| Panic Button          | +                | Markdown in Git                        |
| Digital First Aid Kit | +                | Markdown in Git                        |
| Level Up              | --               | No content source / No repo            |

### Security in a Box.

Export from SIAB:

 - Ideally access Drupal Nodes through a granular API (at the level of sections, community snippets), keep track of upstream last modified date and translation dependencies to flag downstream update needs and generate/transform into static source for content packs.

Import in SIAB:

 - Drupal Remote Entity or Web Service Data module consuming a statically generated 

Integration Path

 - Possible to reuse Open Mentoring/StoryPath approach to generate content packs from SIAB to create a SIAB Mobile App.

### Umbrella. 

Export from Umbrella:

 - Directly by transforming source csv files

Import in Umbrella:

 - Exporting Open Mentoring Content Packs as Umbrella compatible CSV

Integration Path

 - Umbrella could reuse a Content Pack approach and propose to StoryPath to integrate Checklist in the spec

### Story Maker

Export/Import from Story Maker

 - Compatibility with OBB Content Pack binaries should mean that they can just be an additional source to download from.

Integration Path

 - Working with StoryPath to upstream different approaches to content management and developing NativeScript/Cordova plugins might pay off.

### Panic Button

To be discussed but if the Panic Button help section was rewritten to allow loading StoryPath content packs that would probably be a good thing. 

### TOTEM

Interop with practical tests is a strong lead.

### Open Mentoring 

#### Content Requirements

 - Git managed static content approach
 - Transifex workflow
 - Known interop path with *all* content ecosystem

#### Tech Options

Format

 - Markdown with YAML Frontmatter in smaller chunks than StoryMaker Content Packs (to allow markdown bodies in cards)

Authoring

 - Prose

Publication

 - Maybe Liger content pack interop?

Delivery

 - Native Android with StoryPath/Liger and different git static content publication scripts.
 - NativeScript App with StoryPath/Liger 
 - NativeScript App with StoryPath/Liger compatible approach
 - Corbova App with StoryPath/Liger
 - Corbova App with StoryPath/Liger compatible approach

See [Technical Research Wiki Page](https://github.com/openmentoring-content/wiki) for more about platform choice.
