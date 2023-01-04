---
{"title":"Handle Null In JSON","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/handle-null-in-json/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]
[Solved: Parse JSON, accept null values to schema - Power Platform Community](https://powerusers.microsoft.com/t5/General-Power-Automate/Parse-JSON-accept-null-values-to-schema/td-p/1483701)

If you need to allow nulls in JSON file, add null to schema:

```json
{
"type": ["string","null"]
}
```
