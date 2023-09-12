---
Status: "#inventory"
Quantity: 
Parts Required: 
Other Items: 
tags: []
draft: "true"
<%*
let title = tp.file.title;
   if (title.startsWith('Untitled')) {
      title = await tp.system.prompt('title - ');
      await tp.file.rename(`${title}`);
   }
-%>
title: <%* tR += `${title}` %>
---

# {{title}}



### Quantity :
*Amount of this item available now*




## Items

*List of Items used for this; You can put a link to another inventory item if needed*



| Item | Notes | Quantity | Available |
| ---- | ----- | -------- | --------- |
|      |       |          |           |
|      |       |          |           |


## Where will this be used
*Application of this inventory item: What process does it impact*




## Method
*What to do with it*





---
# References
