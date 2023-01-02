---
{"title":"Extract Date From File Name","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/extract-date-from-file-name/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate\|PowerAutomate]]

[Solved: How to get the last 4 characters of a string? - Power Platform Community](https://powerusers.microsoft.com/t5/General-Power-Automate/How-to-get-the-last-4-characters-of-a-string/td-p/1500549)
[How to split file name for further processing in Power Automate](https://tomriha.com/how-to-split-file-name-for-further-processing-in-power-automate/)
If you need to extract number or text from the file name, you can use `substring` method:

```go
substring(outputs('Compose'),sub(length(outputs('Compose')),5),5)
```
```go
substring(triggerOutputs()?['body/{Name}'],sub(length(triggerOutputs()?['body/{Name}']),7),7)
```
