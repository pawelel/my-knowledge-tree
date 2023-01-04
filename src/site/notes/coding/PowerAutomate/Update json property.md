---
{"title":"Update json property","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/update-json-property/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

You can use `SetProperty()` function:
```excel

setProperty(body('Parse_JSON_-_is_file_locked')?['IsLocked'],false)

```
related:
[Power Automate Expressions How To: setProperty](https://www.youtube.com/watch?v=MnnkNjrNKHk)