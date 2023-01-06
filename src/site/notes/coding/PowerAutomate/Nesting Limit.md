---
{"title":"Nesting Limit","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/nesting-limit/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

In PowerAutomate you can use maximum eight nesting's. Exceeding this limit causes information:

```powerquery
The power flow's logic app flow template was invalid. The template actions 'Create_item_-_A, Create_item_-_A_-_Coordinator, Parse_JSON_-_A_with_new_Status, Append_to_array_variable_-_A, Create_item_-_B, Create_item_-_B_-_Coordinator, Append_to_array_variable_-_B' are nested at level '9' which exceeds the maximum nesting limit of '8'.
```
The only way to extend this limit is to create [[coding/PowerAutomate/Nested Flow - Child Flow\|Nested Flow - Child Flow]].
