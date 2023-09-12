---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
  - obsidian
  - markdown
  - quartz
  - hugo
  - deploy
area: 
draft: "false"
cover: 
type: article
progress: Idea
title: Quartz KB Hosting and Setup
---

# Using Quartz to Host KB online on GithubPages
#obsidian #quartz #markdown #deploy 


### Intro
Uses Quartz 4.0 by Jacky Zhao to create a Static site that hosts Obsidian Vault Content


### Context
Follow Quartz guide to set up static pages. It contains ways to use most plugins and document content in your vault. Comes with Dark/Light mode, wiki-links, search etc.

Quartz is highly extensible and customizable for your usecase. 


## Overview
*What does this article consists of*
- [[#Using Quartz]]
- [[#Host it online]]
- [[#Private content]]
- [[#EARLIER VARIANT DEPRECATED|Deprecated Earlier Variant; DO NOT USE]]
- [[#References|Reference links]]

# Using Quartz

- Github: [Jacky Zhao Quartz Github](https://github.com/jackyzha0/quartz/)
- Quartz 4.0 Website(Built with quartz and obsidian): [Quartz 4.0](https://four.quartz.jzhao.xyz/)  
### Set up

Visit Quartz website: [Quartz 4.0](https://four.quartz.jzhao.xyz/)
Here are the steps to get started
- Clone Quartz repo, 
- `cd` into this directory
- `npm i` to install dependencies
- `npx quartz create` to initiate build process, specify docs etc.
- Update Frontmatter
	- set `draft` as `false` to publish that specific content
	- set `title` to your page's title
	- Any other frontmatter changes relevant to it

### Host it online 

You can use any static site hosting solution to host your content, some good options are
- Netlify
- Github Pages
- Cloudflare Pages
- Repl.it
For steps, visit 
[Quartz: Hosting Static Sites](https://four.quartz.jzhao.xyz/hosting)



### Private content

Taking content from quartz website: 
![Quartz Private Pages- Built in feature](https://four.quartz.jzhao.xyz/features/private-pages)

##### Basically
- Edit `quartz.config.ts`  to include `ignorePatterns` 
- OR
- add frontmatter tag `draft` to `true`
#


# EARLIER VARIANT : DEPRECATED

### ~~How It Works:~~

Quarts is a pseudo-app that sits on top of Hugo (Go based Static Site Generator) that creates a static site based on the files passed to it using Obsidian Export. 

Obsidian Export is a CLI tool that lets user export a subset of Obsidian Vault in a Quartz/Hugo friendly  manner (has the correct frontmatter; namely `title`) to make sure your private content in the vault remains private and is not passed to Quartz to convert to a static site. A certain fork of Obsidian Export adds in the frontmatter `title` based on the name of the document. 

### ~~Scripts:~~
~~We have 2 scripts to make the process easy:~~

- ~~Watch Script~~
	- Makes sure we start with our quartz directory. 
	- Uses nodemon to watch certain folders to detect any changes; changes can be in folders containing content or folders that quarts uses, e.g. styles, layouts etc.
	- Executes Compile script when changes are detected for any of the extensions we monitor (md, html, js, scss, xml)
	  
	  Here is the script
	  ```bash
	  #!/bin/bash

cd ~/Sites/quartz; nodemon -w ~/Library/Mobile\ Documents/iCloud~md~obsidian/Documents/bkb -w ~/Sites/quartz/assets/js -w ~/Sites/quartz/assets/styles -w ~/Sites/quartz/layouts -w ~/Sites/quartz/config.toml -w ~/Sites/quartz/data/config.yaml -x "~/Sites/quartz/compile.sh" -e md,html,js,scss,xml
```
**Please make sure your folders and structures are in order according to the script**
- ~~Compile Script~~
	- Is Called when the above script is run
	- Is run when you want to compile your current documents to obsidian-export and then to quartz and hugo
	- Here are the steps it performs
		- Initially it clears out the content folder
		- Runs obsidian-export with add-titles to frontmatter, we pass  in our obsidian vault to it, and exports the output to `content` folder in quartz
		- Then we run hugo-obsidian and give our new quartz content as the input. hugo-obsidian generates an output
	  ```bash
	  #!/bin/bash

cd ~/Sites/hugo-obsidian; rm -fr ~/Sites/quartz/content/*; rm -rf ~/Sites/quartz/public/*; ~/Sites/obsidian-export/target/debug/obsidian-export --add-titles --frontmatter=always ~/Library/Mobile\ Documents/iCloud~md~obsidian/Documents/bkb ~/Sites/quartz/content; go run ~/Sites/hugo-obsidian -input=/Users/brandonkboswell/Sites/quartz/content -output=/Users/brandonkboswell/Sites/quartz/assets/indices -index -root=/Users/brandonkboswell/Sites/quartz; (cd ~/Sites/quartz && hugo --minify)
```

#### Resources: 
- [Brandon Boswell Hugo Obsidian-export Quartz3 Video](https://www.youtube.com/watch?v=ITiiuBNVue0)
- [Blog Brandon ^](https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/)
- Github
	- [Obsidian-export fork Brandon](https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/)
	- [Jacky Zhao Quartz](https://github.com/jackyzha0/quartz)
	- [Jacky Zhao Hugo-Obsidian](https://github.com/jackyzha0/hugo-obsidian)








---
# References

- Github: [Jacky Zhao Quartz Github](https://github.com/jackyzha0/quartz/)
- Quartz 4.0 Website(Built with quartz and obsidian): [Quartz 4.0](https://four.quartz.jzhao.xyz/)  
- [Quartz: Hosting Static Sites](https://four.quartz.jzhao.xyz/hosting)
- [Quartz Private Pages- Built in feature](https://four.quartz.jzhao.xyz/features/private-pages)


- ==DEPRECATED==
	- [Brandon Boswell Hugo Obsidian-export Quartz3 Video](https://www.youtube.com/watch?v=ITiiuBNVue0)
	- [Blog Brandon ^](https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/)
	- Github
		- [Obsidian-export fork Brandon](https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/)
		- [Jacky Zhao Quartz](https://github.com/jackyzha0/quartz)
		- [Jacky Zhao Hugo-Obsidian](https://github.com/jackyzha0/hugo-obsidian)



