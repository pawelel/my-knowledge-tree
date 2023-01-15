---
{"title":"Xpath Snippets","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/xpath-snippets/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

[How to merge arrays in Power Automate](https://www.tachytelic.net/2022/07/power-automate-merge-array/)
[How to merge two arrays in Power Automate by a common property using the xpath expression. - YouTube](https://www.youtube.com/watch?v=QSF6dNkSKSA)


Xpath select text from node where name starts with "Title" or "Description"
```xml
//Array[starts-with(local-name(), "Description")] | //Array[starts-with(local-name(), "Title")]/text()
```
