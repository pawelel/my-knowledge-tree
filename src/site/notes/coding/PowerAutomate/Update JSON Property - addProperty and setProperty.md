---
{"title":"Update json property","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/update-json-property-add-property-and-set-property/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

[Power Automate Expressions How To: setProperty](https://www.youtube.com/watch?v=MnnkNjrNKHk)
[How to Add/ Remove property from a JSON object dynamically using Power Automate - Debajit's Power Apps & Dynamics 365 Blog](https://debajmecrm.com/how-to-add-remove-property-from-a-json-object-dynamically-using-power-automate/)

In order to add new property to JSON, you can use `SetProperty()` function:
```powerquery
setProperty(body('Parse_JSON_-_is_file_locked')?['IsLocked'],false)
```
A property also can be nested inside of existing JSON object:

```powerquery
addProperty(json('{ "Address": { "City": "Milpitas", "State": "CA" } }')['Address'], 'ZipCode', '750321')
```

If there is a need of adding an object to JSON, you can parse multiple JSON files and then combine results.



This works:
```powerquery
// Parse_JSON
{
"Condition": "Good"
}
```
```powerquery
// Parse_JSON_-_Status_array
[
	{
	"Status": "Doing"
	},
	{"Status": "Done"
	}
]
```
```powerquery
// final input
addProperty(body('Parse_JSON'), 'Status', body('Parse_JSON_-_Status_array')[0])
```

>[!BUG] This won't work due non existing property:
>  
> ```powerquery
> addProperty(json('{ "Address": { "City": "Milpitas", "State": "CA" } }')['Location'], 'Country', 'USA')
> ```

But this one does:
```powerquery
addProperty(json('{ "Address": { "City": "Milpitas", "State": "CA" } }'), 'Location', json('{"Country": "USA"}'))
```
And outputs:
```json
{
  "Address": {
    "City": "Milpitas",
    "State": "CA"
  },
  "Location": {
    "Country": "USA"
  }
}
```
