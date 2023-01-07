---
{"title":"Remove Null Values From Compose","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/remove-null-values-from-compose/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

If you need to get rid of nulls from Compose output after Apply For Each, just pass it through Filter Array.

![Pasted image 20230107224853.png](data:image/png;base64,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)

## Solution

![Pasted image 20230107225135.png](data:image/png;base64,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)