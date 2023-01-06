---
{"title":"Or function","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/or-function/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

[Power Automate Functions - Or - YouTube](https://www.youtube.com/watch?v=AKOwVnubeX0)

You can use `or` function to check if one of the parameters matches given criteria:

```powerquery
or(not(empty(item()?['invoice number'])),item()?['invoice number'],not(empty(item()?['Invoice No'])),item()?['Invoice No'])
```
This function checks if 'invoice number' column is not empty or 'Invoice No' column is not empty.
Either way it will result with a first encountered true or (if all are) false.