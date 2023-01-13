---
{"title":"Compare Arrays Without Apply To Each","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/join-arrays-without-apply-to-each-or-union/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

[Solved: Is there a way to concatenate arrays (not Union() ... - Power Platform Community](https://powerusers.microsoft.com/t5/Building-Flows/Is-there-a-way-to-concatenate-arrays-not-Union-I-don-t-want-to/td-p/1594186)

```powerquery
slice(string(body('Select_invoices_from_a_list')), 1, -1)
```

```powerquery
slice(string(body('Select_new_invoices')), 1, -1)
```

```powerquery
concat('[', outputs('Compose_-_convert_to_string_invoices_from_a_file'), ',' , outputs('Compose_-_convert_to_string_invoices_from_a_list'), ']')
```
```powerquery
json(outputs('Compose_Concat'))
```
