---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
area: 
draft: "true"
cover: 
type: article
progress: <% await tp.system.suggester(["Idea", "Working", "Finished"], ["Idea", "Working", "Finished"]) %>
<%*
let title = tp.file.title;
   if (title.startsWith('Untitled')) {
      title = await tp.system.prompt('title - ');
      await tp.file.rename(`${title}`);
   }
-%>
title: <%* tR += `${title}` %>

---
# Image
# {{title}}

### Intro
*Something to introduce to users*


### Context
*When does this come into play*

## Overview
*What does this article consists of*
- [[Knowledge-base Article#Part 1]]
- [[Knowledge-base Article#Part 2]]
- [[Knowledge-base Article#Part 3]]


### Body

#### Part 1 

#### Part 2

#### Part 3



### Conclusions



### Key take away
- [ ] Key1 
- [x] Key2
- [ ] Key3
- [ ]  
 









---
# References