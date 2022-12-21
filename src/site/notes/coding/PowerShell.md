---
{"dg-publish":true,"permalink":"/coding/power-shell/"}
---

up:: [[Home/Coding\|Coding]]

## How to enable user scripts in PowerShell

By default user execution scripts are disabled.  
To enable them, you can use this command:

```PowerShell

  Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

```
