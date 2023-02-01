---
{"title":"Speed Up Async Tasks","dg-publish":true,"tags":["coding/CSharp"],"language":"en","permalink":"/coding/c-sharp/speed-up-async-tasks/","dgPassFrontmatter":true}
---

up:: [[coding/CSharp/CSharp\|CSharp]]

[Making async code run faster in C# - YouTube](https://www.youtube.com/watch?v=gW19LaAYczI)

If you need to run multiple async tasks simultaneously, try to assign them to variables and then use `WhenAll()` method:

```cs
var _firstItemsTask = GetFirstItems(httpclient);
var _secondItemsTask = GetSecondItems(httpclient);
await Task.WhenAll(_firstItemsTask, _secondItemsTask);
var _firstItems = await _firstItemsTask;
var _secondItems = await _secondItemsTask;
```
This solution will provide only the first occured error unless you create an extension:

```cs
public class TaskExt
{
public static async Task<IEnumerable<T>> WhenAll<T>(params Task<T>[] tasks)
	{
		var allTasks = Task.WhenAll(tasks);
	}

	try
	{
		return await allTasks;
	}
	catch (Exception)
	{
	//ignore
	}
	throw allTasks.Exception ?? throw new Exception("In case a try catch didn't work")

}
```

Then you can use insstead:

```cs
await TaskExt.WhenAll(_firstItemsTask, _secondItemsTask);
```
It will provide a list of all errors.