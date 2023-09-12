---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
  - "#obsidian"
  - "#markdown"
  - "#how-to"
area: obsidian
draft: "false"
cover: https://www.dmuth.org/wp-content/uploads/2021/03/obsidian-logo.png
type: article
progress: Idea
title: Obsidian
---
![Obsidian icon Logo](https://obsidian.md/images/2023-06-logo.png)
![Obsidian Full Logo](https://www.dmuth.org/wp-content/uploads/2021/03/obsidian-logo.png)
# Obsidian

#knowledge-base #obsidian #markdown #basics #how-to

## Overview
*What does this article consists of*
- [[Obsidian#What is it]]
- [[Obsidian#How it works|How it Works]]
- [[Obsidian#Theming|Theming]]
- [[Obsidian#Keys|Hotkeys]]
- [[#Workflow]]



# What is it

Obsidian is a note taking application with its main feature being working how 'you' want it to work. It is highly adaptive and extensive with customization, themes, extensions( both community and core{built-in})

Inside Obsidian, everything is contained in a 'Vault' {basically a folder}
- A vault can contain multiple nested folders and notes residing in any level of this vault hierarchy 
	- A vault contains '.obsidian': a hidden folder in the vault that contains obsidian related files, themes, settings, etc. Things that are used to make a vault unique and working
- Obsidian cannot access folders or files outside the Vault
- All notes can be connected to one another depending on their unique relations
- 'Tags' and Folders can help better organize notes
- Notes can be filtered by projects, tags, dates and more

## How it works

Basically works as a wrapper over your regular folders and files
- Saves its files as .md (markdown) a popular way to store textual information with ways to make the text 'richer' with images, pdf, content, links, etc.
- .md is also used by github to provide 'readme' among other things
- Since it is .md, it is easily read and edited by any text editor and can be used for other things. We will use ours to create a Knowledge-base and an Inventory system. We also use some other technologies to serve these markdown files on the web to be accessed by others, we make this happen by using either Next.js(or something similar) or use hugo to publish this markdown. It can be served using github pages and other services, and from there can be served on custom domain.
- **Structure and Zettelkasten:**
	- We do not impose a folder structure from top-down planning approach, most of the content of the vault are created and put in a single page, and an ordered structure is emerged naturally by files and content linking with each other
		- All atomic ideas or individual notes live in the Zettelkasten folder. All ideas live here.
		- Reference notes: Notes jotted down on lectures, books, articles, videos, notes that you will revisit some other time to refer to previous thoughts. Dont contain actual information, although provide a fast way to insert into ideas where a certain reference/idea comes from. For example, an atomic idea note can contain a reference note about a video to provide more context and information for the idea note.
		- Files/Attachments: Contains all images, pdfs, audio files etc to be used in notes.
		- Templates: To easily create a type of notes or a task, For example template for an atomic idea or a reference note or a Knowledge-base item or an Inventory item
	- Other than just the Zettelkasten approach, other folders can be added based on what you are using Obsidian for. These are completely separate from the Zettelkasten system
- The best part and the fundamental feature of Obsidian is the '**Linking**' aspect of the app. What this allows you do is form connections between your notes by referencing other notes or concepts to the note you are working on. Add links to a current note by adding double '[]' {square brackets} to initiate linking and selecting the note you want to link to. 
	- If there is no note to the note you are linking, you can use the empty link as a 'Node' to connect your other notes. For example, a 'Node':  'Programming Languages' might not contain any content of its own, but 'Notes': 'Java', 'C++', 'JavaScript' etc. might have 'Programming Languages' in its tag section, and be connected to each other as they all are programming languages, This is how we could use tags.
		- These hubs or 'Nodes' can be important recurring theme in your notes, and can be deemed **'Map of Content(MOC)'** Which is basically a note which contains an overview of the things it connects to. In the earlier example, a MOC for Programming Languages could contain info about when programming languages emerged, how we could create one, what layers of abstractions could be needed for different languages, how languages connect and work together and so on. Then We can refer other specific language Notes in here.
- **'Graph view'** allows you to view your notes and links in an overview mode in which you can see what edges(notes) connect to what nodes(tags) in an organic fashion and how they all come together or where you can expand on next.
- Adjust system to your needs
	- Once in the flow of basic things, don't be afraid to change things make this application work for you, how you like things. 
	- Start from small changes, and ramp it up as needed

## Theming

In general, Obsidian provides minimal little tweaks to customize how it looks and funcitons.

- You can drag and drop most tabs and plugins to either the left or right bars at either end of workspace, in the panels provided 
- You can choose to stack the plugins on top of each other or adjacent to each other (in different tabs) in the allotted panels
- In settings you can customize basic visual settings like accent color, light and dark mode, text sizes and so on.
- There is a plethora of themes available to download and use from the obsidian store in settings

####  CSS Theming
The best part about Obsidian is that it is basically a JavaScript Electron Application that works almost the same on all platforms. Given this information, it isn't too hard to understand that most of its theming comes from CSS. 

So, If you know your way around CSS, you can theme how things look in Obsidian, how the Titles are rendered, colors of panels,  shading and so on. World is your oyster when it comes to theme customizing in Obsidian. 


## Keys

- ` Alt + T `  to add a template to a new note you created
- ` Ctrl + P ` Open command palette for most commands
- ` Ctrl + O ` Create or fuzzy search for a note (If a note idea is already created, you may expand on that rather than creating a new note)
- ` Ctrl + Shift + N ` Create Note in a different pane (new tab)
- ` Ctrl + E ` Switch between 'Edit' and 'View' mode

## Workflow

- Create a new note
- Apply a template
- Explain idea in your own words
- Under references, let it be known where this idea came from, and if someone wants to follow up with the source or other resources
- You can be in edit or view mode, view mode to read, interact with notes as a user, such as clicking external links to be redirected to them, looking at embedded files and content from other notes, etc. 
- Any Notes in the 'Template folder' acts as a template that can be used in other notes. Templates can be a structure for a full note or it can be partial to be used within some part of the created note.
- You can add Excalidraw, Excalibrain or Canvas content to any note, not just this, but embed any website with iframe, add videos from internet and local media, add any audio content from the (Attachment) folder, create voice recordings to accompany your notes and so on
- 