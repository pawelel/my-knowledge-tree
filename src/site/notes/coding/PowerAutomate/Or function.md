---
{"title":"Or function","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/or-function/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

If you need to use first matching criteria, there is `or` function:

```powerquery
or(not(empty(item()?['invoice number'])),item()?['invoice number'],not(empty(item()?['Invoice No'])),item()?['Invoice No'])
```
This function checks if 'invoice number' column is not empty or 'Invoice No' column is not empty.
Either way it will result with a first encountered value.