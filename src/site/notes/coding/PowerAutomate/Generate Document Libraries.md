---
{"title":"Generate Document Libraries","dg-publish":true,"tags":["coding/PowerAutomate"],"language":"en","permalink":"/coding/power-automate/generate-document-libraries/","dgPassFrontmatter":true}
---

up:: [[coding/PowerAutomate/PowerAutomate\|PowerAutomate]]

Let's say that you need to create folders for each customer and store documents inside based on the Excel file content. Later on, there will be some additional needs like the Library name or guid, so you need to store this information somewhere. In this case, use SharePoint list.

## Create a SharePoint list - Companies

Create a SharePoint list with the following columns:

* Title - default column to store the company name
* LibraryGuid - single line of text for the library created from the Title column
* FolderName - single line of text for the library folder created from the Title column

![Starting list - Companies](/img/user/attachments/2023-01-20-13-45-16.png)

Above you can see the list with the default Title column and two additional columns. The GUID and folder name will be used in Power Automate flows, e.g. to create a file for specific customer.

## Create Power Automate flow - Generate Document Libraries

Create a new flow and select SharePoint as a trigger - "When an item is created". Select the list you created in the previous step. The flow will be triggered when a new item is added to the list. Additionally, you can add a condition to check if the item is not empty:

```powerquery
@not(equals(true, empty(item()?['Title']))
```

![Pasted image 20230120160025.png](/img/user/attachments/Pasted%20image%2020230120160025.png)
