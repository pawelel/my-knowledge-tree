---
{"title":"PowerShell","dg-publish":true,"tags":"coding","language":"en","permalink":"/coding/power-shell/power-shell/","dgPassFrontmatter":true}
---

up:: [[coding/general/Coding\|Coding]]

## How to enable user scripts in PowerShell

By default user execution scripts are disabled.  
To enable them, you can use this command:

```PowerShell

  Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

```
