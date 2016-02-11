---
title: Technology - Translation
---

* TOC
{:toc}

# How Panic Button is doing it

# Git repositories: 
## 1. [panicbutton.io](https://github.com/PanicInitiative/panicbutton.io) (jekyll site)
## 2. [PanicButton](https://github.com/PanicInitiative/PanicButton) (Android app) 

# Panicbutton.io Transifex Workflow

## Markdown source

**[Status: Existing in the panicbutton.io repository]**

The markdown files in the panicbutton.io Jekyll site's _posts directory serve as the source files for the translation process. Authors use [Prose](https://admin.panicbutton.io/) to edit the markdown source files, in English, triggering a rebuild of the site on update of a markdown post. 

Files that move from the panicbutton.io repository to the PanicButton Android app through the Transifex translation process are located in _posts/mobile and _posts/help. These relevant markdown files contain the yaml "categories" assignment "mobile" or "help". 

## Markdown -> JSON Key-Value Pair conversion

**[Status: tx_md2jsonKV.py Script in progress]**

Because the markdown files for panicbutton.io contain extensive amounts of yaml front matter, it is necessary to convert the files to JSON prior to sending them to Transifex. Transifex does not handle the mixed yaml/markdown source well. A push to the panicbutton.io repository triggers travis.yaml to launch the bash script, **tx_md2jsonKV.py**, which converts all markdown files in _posts into JSON Key-Value pairs comprising key-value pairs. **tx_md2jsonKV.py** builds these new JSON Key-Value files in the _locales directory. 

In this conversion process, there is one JSON file for each language, with each master JSON file containing yaml front-matter and content of that language's markdown files. Each item of yaml front-matter represents a new key, and the markdown content also comprises one key, "content". For example, if the folder _posts/mobile/ has ten markdown files, the resulting JSON file, **mobile.json**, will comprise all ten of the markdown files, each broken down into its yaml and markdown key-value pairs. 

## Transifex configuration

**[Status: .tx config creation in progress]**

Transifex is hooked into panicbutton.io's root in a .tx folder that contains the [Transifex config file](http://docs.transifex.com/client/config/) (**.tx/config**). The config file alerts the Transifex client to files in the repository that are subject to translation in Transifex; dictates the naming convention for the returned, translated files; and sets the file format (here, Key-Value JSON). 

## JSON -> Transifex: Registering a change

**[Status: TXGH Integration TODO]**

If the newly built JSON Key-Value files (in _locales, from **tx_md2jsonKV.py**) differ from the ones that they replace, [TXGH](https://github.com/transifex/txgh), a Sinatra-based transifex-github integration/server, registers this change to the files in _locales. It updates Transifex to show that each language's repository is no longer 100% translated. This cues translators to update each language's translations. 

## Transifex: Returning translated files to repository

**[Status: TXGH integration TODO, python script tx_jsonKV2md.py in progress]**

When a translator completes a language's translation, and the Transifex repository registers 100% completion, TXGH pushes the newly translated JSON Key-Value files into panicbutton.io's git repository at _locales/\<lang\>/, overwriting the files that exist in this repository (the old translations). 

This push triggers another bash script prompted by travis.yaml, **tx_jsonKV2md.py**, which converts the JSON Key-Value files in _locales/\<lang\>/ back into markdown. The new markdown files are placed in _posts/\<lang\>/, replacing the markdown files from the previous round of translations. 

## Pushing Markdown files to Android Panic Button App

**[Status: travis.yaml cloning and pushing to Android application TODO]**

On each push to the panicbutton.io dev branch, travis.yaml performs a process to transform and push relevant information to the PanicButton Android application repository. First, travis.yaml <code>git clones</code> the PanicButton Android application's asset repository. The script then converts all of the markdown files in \_posts/mobile and \_posts/help (including all files in the \_posts/mobile/\<lang\> and \_posts/help/\<lang\> directories) into custom, PanicButton-specific JSON following templates located in /api/help.json and /api/mobile.json. These files are named **mobile\_\<lang\>.json** and **help\_\<lang\>.json**. 

Upon creation, the files are copied into the newly cloned PanicButton App assets directory, over-writing the now-outdated, equivalently-named files. 

Next, travis.yaml calls <code>git add -A && git commit -m "Updating translations to the PanicButton Application" && git push origin dev</code>. If the newly created JSON files, mobile_\<lang\>.json, differ from the previous versions (eg if the <code>git push</code> that called the script represents an updated translation), then the changes will be committed and pushed to the PanicButton Android Application's repository. This triggers a rebuild of the app. If the JSON files, mobile_\<lang\>.json, have not changed, then the cloned directory will not register any change on <code>git add -A</code>, and so the <code>git commit && git push origin dev</code> will fail without triggering an error. 

# Panic Button Android App Additional Transifex workflow

## strings.XML

**[Status: .tx config creation in progress. TXGH integration TODO]**

The PanicButton Android app contains an additional Transifex workflow. The app has translatable material independent of the panicbutton.io source files in the **/src/main/res/values/strings.xml** file. 

Thus, the PanicButton Android Application repository also houses a .tx folder with its own config file, which dictates the translation source, resulting file names, and format for **strings.xml**.

A TXGH integration in the PanicButton app repository will register a pushed change in the **strings.xml** file, updating **strings.xml** in the Transifex repository to show that translation is no longer complete and alerting translators that an update to the translation is necessary. 

Upon completion of the translation, TXGH will return the translated files to the PanicButton repository, placing them in the directories **/src/main/res/values-\<lang\>**, with each language's file named **strings.xml**. Existing translations in each of these directories will be overwritten by this action from TXGH. The app will be rebuilt upon return of new files. 





