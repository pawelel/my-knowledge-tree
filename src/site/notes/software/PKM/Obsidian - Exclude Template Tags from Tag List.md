---
{"title":"Obsidian - Exclude Template Tags from Tag List","dg-publish":true,"tags":["software/PKM"],"language":"en","permalink":"/software/pkm/obsidian-exclude-template-tags-from-tag-list/","dgPassFrontmatter":true}
---

up:: [[software/PKM/PKM\|PKM]]

You can exclude templates folder from graph view and hide from search view by default:
![Pasted image 20230104112744.png](/img/user/attachments/Pasted%20image%2020230104112744.png)
But it doesn't work on Tag view:
![Pasted image 20230104112941.png](/img/user/attachments/Pasted%20image%2020230104112941.png)
In order to do it, wrap `tags:` with Templater syntax:
```js
<% "tags:" %> <% tp.file.folder(true) %>
```
