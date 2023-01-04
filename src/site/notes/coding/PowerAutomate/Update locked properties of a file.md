---
{"title":"Update locked properties of a file","dg-publish":true,"tags":"coding/PowerAutomate","language":"en","permalink":"/coding/power-automate/update-locked-properties-of-a-file/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]


```excel
if
  (
    and
    (
      equals(outputs('Update_file_properties')?['body']?['status'],400), 
      contains(outputs('Update_file_properties')?['body']?['message'], 'locked')
    )
    ,true
    ,false
  )
  //inside Compose:
  setProperty(body('Parse_JSON_-_is_file_locked'),body('Parse_JSON_-_is_file_locked')?['IsLocked'],if(equals(outputs('Update_file_properties')?['body']?['status'],400), true, false))
  //Delay in seconds:
  if(body('Parse_JSON_-_is_file_locked')?['IsLocked'],90,1)
```
related:
[Document is locked for shared use by user](https://powerusers.microsoft.com/t5/Building-Flows/PowerAutomate-Handling-Document-is-locked-for-shared-use-by/td-p/734031)
[Power Automate: Error 400 - file locked for shared use](https://www.youtube.com/watch?v=_wLBj1UFhag)
[Add & Update Excel Data to SharePoint List using Power Automate | Excel Import using flow](https://www.youtube.com/watch?v=uEZI_b1Gs-k)
