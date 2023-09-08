---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
  - "#obsidian"
  - "#markdown"
  - "#md"
  - "#basics"
  - how-to
area: Markdown
published: "false"
cover: https://cdn.worldvectorlogo.com/logos/markdown.svg
type: article
progress: Idea
---

![Markdown Logo SVG](https://cdn.worldvectorlogo.com/logos/markdown.svg)

# Markdown Basics

#obsidian #markdown #basics #knowledge-base #how-to 


# Markdown Basics


#### Headings

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6


#### Add tags 
#yay-tags

#### Format Text
_Italics_
*Italics*
**bold**
__bold

~~Strikethrough~~ 

==Highlights==



#### Lists

Initiate lists by using any of the symbols followed by a new line. New points are added to lists as needed

` + | - | * `

* Number
* Three
* Four

- List Item1
- List Item2

+ Stuff 1
+ Stuff 2

Numbered : 
1. Item1
2. Two

#### Checklist

Use following key combo to initiate checklists
` Ctrl + Enter `  ^dd865b

- [ ] Example 1 ^ca4996
- [x] Two ✅ 2023-09-05
- [ ] Three

#### Quotes

Add Quotes to your text by adding `>` before your text

> Good Quote 101

Nested Quotes:
> Good Quote 101
> > Good quote 202

#### Link to other parts

Double brackets to link to another page in the vault 

[[Markdown Basics]]

Add alias to linked page by adding a **` | `** in the square brackets followed by alias name 

[[Markdown Basics | How to do basic Markdowns]]

##### Links to Heading in pages, can be different pages

Add `#` after page name in linking followed by a certain heading you want to link to. This works for this page and other pages

[[Markdown Basics#Link to other parts]]

Add alias to above

[[Markdown Basics#Link to other parts|Links-to-headings]] 


##### Blocks to same page

Add `^` after page name in linking followed by a certain text block element you want to link to.

[[Markdown Basics#^dd865b | Link to Checklist]] 

##### External Links

Use the following syntax to add external links 
Enter the label under Square brackets and link under regular brackets:
` [Obsidian](obsidian.md)`
[Obsidian](Obsidian.md)

##### Embed Links, 
To embed any of the above links to a section of the page in preview mode, just add `!` before the any of the links above

`![Obsidian](obsidian.md)`
`![[Markdown Basics#External Links |External Links]]`
![[Markdown Basics#External Links |External Links]]


#### Code blocks

Add  4 `` ` 
to start a code block and end with a same, type language name after the first 4

````py
print("Hello World")
````


 


#### Footnotes

Add a footnote by adding a `^3` inside square brackets `[^3]`
replacing '3' in the above with any number, preferably the current number of footnotes on the page plus 1 

Footnotes[^1]

Add footnote description preferably in references by adding a colon at the end of the footnote square like so: `[^3]:`
[^1]: Reference to footnote 1

---
# References