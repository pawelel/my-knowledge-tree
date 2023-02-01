---
{"title":"Speed Up Async Tasks","dg-publish":true,"tags":["coding/CSharp"],"language":"en","permalink":"/coding/c-sharp/speed-up-async-tasks/","dgPassFrontmatter":true}
---

up:: [[coding/CSharp/CSharp\|CSharp]]

If you need to run multiple async tasks simultaneously, try to assign them to variables and then use `WhenAll()` method:

```cs
var _firstItemsTask = GetFirstItems(httpclient);
var _secondItemsTask = GetSecondItems(httpclient);
await Task.WhenAll(_firstItemsTask, _secondItemsTask);
var _firstItems = await _firstItemsTask;
var _secondItems = await _secondItemsTask;
```
