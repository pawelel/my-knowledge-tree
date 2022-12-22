---
{"title":"Update json property","dg-publish":true,"tags":"coding/power-automate","language":"en","permalink":"/coding/update-json-property/","dgPassFrontmatter":true}
---

up:: [[coding/Power Automate\|Power Automate]]

You can use `SetProperty()` function:
```excel

setProperty(body('Parse_JSON_-_is_file_locked')?['IsLocked'],false)

```
related:
[Power Automate Expressions How To: setProperty](https://www.youtube.com/watch?v=MnnkNjrNKHk)