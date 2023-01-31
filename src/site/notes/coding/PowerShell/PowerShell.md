---
{"title":"PowerShell","dg-publish":true,"tags":["coding"],"language":"en","permalink":"/coding/power-shell/power-shell/","dgPassFrontmatter":true}
---

up:: [[coding/Coding\|Coding]]

## How to enable user scripts in PowerShell

By default user execution scripts are disabled.  
To enable them, you can use this command:

```PowerShell

  Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

```

## Remove driver that revents to turn on Memory integrity
run this command and copy data to txt file
```powershell
dism /online /get-drivers /format:table
```
Open Core isolation and find driver name
Then uninstall it using command:
```powershell
pnputil /delete-driver <Published Name> /uninstall /force
```
