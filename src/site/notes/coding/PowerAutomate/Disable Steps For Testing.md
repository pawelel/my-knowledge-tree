---
{"title":"Disable Steps For Testing","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/disable-steps-for-testing/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]
[Solved: Disabling steps for testing - Power Platform Community](https://powerusers.microsoft.com/t5/Building-Flows/Disabling-steps-for-testing/td-p/441632)

If you need to skip steps during testing, you can insert them into the condition 1=1, where the result is false. In this way, they will not be executed, but they will not block the execution of the remaining steps. After the test is completed, you can insert them into the condition 1=1, where the result is true, and the steps will be executed.
