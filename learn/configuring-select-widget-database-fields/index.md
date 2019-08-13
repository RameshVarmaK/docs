---
title: "Configuring Select Widget from Database Fields"
id: "configuring-select-widget-database-fields"
---

A Select widget can be used in various ways based on the source of data. Each type of data source needs a different approach. WaveMaker Select widget works in any one of the following ways:

- [static list of values](/learn/how-tos/configuring-select-widget-static-list-values/)
- [variable data](/learn/how-tos/configuring-select-widget-variable/)
- [display and data value fields from a Variable](/learn/how-tos/configuring-select-widget-display-data-fields/)
- database fields

The options displayed in the Select drop-down can come from a database, too. For example, you want the user to select department id based on the department they belong to.

1. and drop a Select and Label widget onto the canvas.
2. the Select widget to a database. Here we are using the Department table from the hrdb, [the sample db](http://[supsystic-show-popup id=106]) that comes shipped with Studio and has been imported earlier and [Database CRUD Variable](http://[supsystic-show-popup id=105]) [![](../assets/sel_db_var.png)](../assets/sel_db_var.png)
3. the Datafield property to the deptid field and Display Field property to the name field of the Live Variable corresponding to Department dataset [![](../assets/sel_db_props.png)](../assets/sel_db_props.png)
4. selection made by the user is displayed in a Label widget, by binding the select datavalue to it. [![](../assets/sel_list_res.png)](../assets/sel_list_res.png)
5. the app and see the selected item from the Select widget displayed in the label.

[Use Cases](/learn/app-development/widgets/form-widgets/select-use-cases/)

- [1\. How to use list of values for select widget configuration](/learn/how-tos/configuring-select-widget-static-list-values/)
- [2\. How to use variable for select widget configuration](/learn/how-tos/configuring-select-widget-variable/)
- [3\. How to use display and data value fields for select widget configuration](/learn/how-tos/configuring-select-widget-display-data-fields/)
- [4\. How to use database fields for select widget configuration](/learn/how-tos/configuring-select-widget-database-fields/)
- [5\. How to configure cascading select](/learn/how-tos/configuring-cascading-select/)