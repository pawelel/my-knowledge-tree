---
{"title":"Nested Flow - Child Flow","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/nested-flow-child-flow/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate\|PowerAutomate]]

[Create Power Automate Reusable Flow with Child Flow](https://www.youtube.com/watch?v=PMYWUKF3TLA)
[Call Child Flows - Power Automate | Microsoft Learn](https://learn.microsoft.com/en-us/power-automate/create-child-flows)
[Power Automate Child Flow using Solution Packages - YouTube](https://www.youtube.com/watch?v=DLhwnZ5JRvE)

Child flow:
- needs to have proper connection (Run only users->Edit->Connections used and assign your connection instead of Provided by run-only user) - this condition might be obsolete - I couldn't find this option inside of Manage run-only permissions.
- have to be in the same solution as parent flow
- must send response to parent flow
Without it you will not be able to save parent flow - there will be an error.
