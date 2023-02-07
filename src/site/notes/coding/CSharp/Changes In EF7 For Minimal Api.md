---
{"title":"Changes In EF7","dg-publish":true,"tags":["coding/CSharp"],"language":"en","permalink":"/coding/c-sharp/changes-in-ef-7-for-minimal-api/","dgPassFrontmatter":true}
---

up:: [[coding/CSharp/CSharp\|CSharp]]

## Delete

If you need to delete a record from the SQL DB using EF7 and get optimized result like:

```sql
DELETE FROM [Users]
WHERE [Id] = @p0;
```
You can use this syntax:

```cs
app.MapPut("delete", async (Guid id)=>
{
	await db.Users
	.Where(u => u.Id == id)
	.ExecuteDeleteAsync();
});
```
This method doesn't need `SaveChangesAsync()`.

## Bulk Update

It is also possible to update multiple records without downloading them before:

```sql
UPDATE [Users]
SET [Generations] = @p0
WHERE [BirthDate] > @p1
```

```cs
app.MapPut("update", async (AppDbContext db)=>
{
	await db.Users
	.Where(u => u.BirthDate > new DateTime(1980, 12, 13))
	.ExecuteUpdateAsync(
	s => s.SetProperty(c => c.Generations => "Gen X")
	);
});
```
