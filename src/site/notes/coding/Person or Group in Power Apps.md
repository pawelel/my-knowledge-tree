---
{"dg-publish":true,"permalink":"/coding/person-or-group-in-power-apps/"}
---

up:: [[coding/Power Apps\|Power Apps]]

In order to change Person or Group in Power Apps, you should use record data in **DefaultSelectedItems** (JSON syntax):
  
```json
  {
  Claims: "i:0#.f|membership|"&person.Email,
  DisplayName: person.DisplayName
  }
  ```

  [How to update Single or Multi person field in SharePoint from Power Apps Canvas apps](https://debajmecrm.com/how-to-update-single-or-multi-person-field-in-sharepoint-from-power-apps-canvas-apps/)

  [Default values for complex SharePoint types](https://powerapps.microsoft.com/en-us/blog/default-values-for-complex-sharepoint-types/)

  ```json
  {
  'Created by'.Claims = "i:0#.f|membership|"&User().Email
  }
  ```

