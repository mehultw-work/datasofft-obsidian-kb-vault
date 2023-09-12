---
Status: "#idea"
tags: []
title: 
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







---
# References