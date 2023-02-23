---
{"title":"Trigger Flow On Column Value Change","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/trigger-flow-on-column-value-change/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

[PowerAutomate - Trigger Flow on Column Value Condition - YouTube](https://www.youtube.com/watch?v=HLxZ_lGhEg8)
[Trigger Conditions in Power Automate - EnjoySharePoint](https://www.enjoysharepoint.com/trigger-conditions-in-power-automate/)

In case you need to triger flow when spesific requirements are met, you can use Instant flow with Trigger conditions available through settings:
![Pasted image 20230102134832.png](/img/user/attachments/Pasted%20image%2020230102134832.png)
If you have columns like  Status (Choice with New option), Deadline (DateTime),
adding a following line:

```go
@and(equals(triggerOutputs()?['body/Status/Value'], 'New'), not(empty(triggerOutputs()?['body/Deadline'])))
```
will trigger a flow only if the Status is New and Deadline is not empty.

```go
@and(equals(triggerBody()?['Status']?['Value'], 'Nowy'), not(equals(triggerBody()?['Deadline'], null)))
```
