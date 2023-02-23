---
{"title":"Extract Date From File Name","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/extract-date-from-file-name/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

[Solved: How to get the last 4 characters of a string? - Power Platform Community](https://powerusers.microsoft.com/t5/General-Power-Automate/How-to-get-the-last-4-characters-of-a-string/td-p/1500549)
[How to split file name for further processing in Power Automate](https://tomriha.com/how-to-split-file-name-for-further-processing-in-power-automate/)
If you need to extract number or text from the file name, you can use `substring` method:

`invoices_01.2023.xlsx`
```go
substring(outputs('Compose'),sub(length(outputs('Compose')),5),5)
```
```go
substring(triggerOutputs()?['body/{Name}'],sub(length(triggerOutputs()?['body/{Name}']),7),7)
```
And if there is a date in the end, you can also use `split` method:

```go
split(substring(triggerOutputs()?['body/{Name}'],sub(length(triggerOutputs()?['body/{Name}']),7),7),'.')
```
In one Parse Json Action:
```json
{
"file month": "@{split(substring(triggerOutputs()?['body/{Name}'],sub(length(triggerOutputs()?['body/{Name}']),7),7),'.')?[0]}",
"file year": "@{split(substring(triggerOutputs()?['body/{Name}'],sub(length(triggerOutputs()?['body/{Name}']),7),7),'.')?[1]}"
}

{
    "type": "object",
    "properties": {
        "file month": {
            "type": "string"
        },
        "file year": {
            "type": "string"
        }
    }
}
```
Result:

![Pasted image 20230102195850.png](/img/user/attachments/Pasted%20image%2020230102195850.png)
