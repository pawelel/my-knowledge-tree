---
{"title":"Get Excel column names","dg-publish":true,"tags":"coding/power-automate","language":"en","permalink":"/coding/get-excel-column-names/","dgPassFrontmatter":true}
---

up:: [[coding/Power Automate\|Power Automate]]


```excel

  split(string(first(outputs('List_rows_present_in_a_table')?['body/value'])),'",')

  ```
related:
[Is there any way to get the column headers from Excel file?](https://powerusers.microsoft.com/t5/Building-Flows/Is-there-any-way-to-get-the-column-headers-from-Excel-file-amp/td-p/846453)