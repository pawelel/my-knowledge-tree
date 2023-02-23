---
{"title":"Projects","dg-publish":true,"tags":["coding/projects"],"language":"en","permalink":"/coding/my-projects/","dgPassFrontmatter":true}
---

up:: [[My Knowledge Tree\|My Knowledge Tree]]

## Asset Management Demo

![sc3.gif](/img/user/attachments/sc3.gif)

The project, built using Blazor Server and the [MudBlazor - Blazor Component Library](https://mudblazor.com/) aimed to enable asset configuration for indexing. 
Main features:

- List all assets
- Relational CRUD for plant, area, line, coordinate, device type, device, asset name...
- Customizable views
- Import data from Excel using [GitHub - mganss/ExcelMapper: Map POCO objects to Excel files](https://github.com/mganss/ExcelMapper)
- Notifications
- Enforce unique asset name
- Permission levels
- JWT token support
- Material design
- Mark as "removed"
- Only admin could delete from database
- Localization based on user browser settings (PL/EN)

Additionally, a separate Chrome extension application was developed to utilize data provided by the server's API.

## SC3 Chrome Plugin

![Pasted image 20230129095426.png](/img/user/attachments/Pasted%20image%2020230129095426.png)
The purpose of this plugin was to improve the efficiency of the first line of support in creating tickets and to standardize ticket naming for future business reporting. Another benefit of using the plugin was to reduce the number of typos. A table is displayed thanks to the [Tabulator](https://tabulator.info/) - JavaScript table and DataGrid library.
The main features of the plugin include the ability to:

-   Fill out a form
-   Filter by certain conditions
-   Locate assets based on various parameters
-   Automatic localization of the interface (Polish/English) based on browser settings
-   Export filtered data to the xlsx format
-   Export all data
