---
Status: "#MOC"
tags: []
<%*
let title = tp.file.title;
   if (title.startsWith('Untitled')) {
      title = await tp.system.prompt('title - ');
      await tp.file.rename(`${title}`);
   }
-%>
title: <%* tR += `${title}` %>
draft: "true"
---

# {{title}}: Map of Content(MOC)


__Consolidate your atomic ideas here__




---
# References