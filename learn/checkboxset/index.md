---
title: "CheckboxSet"
id: "checkboxset"
---

allows you to group a set of checkboxes under a common heading. You need to bind to a dataset to display a checkbox for each value.

[![](../assets/checkboxset_struct.jpg)](../assets/checkboxset_struct.jpg)

the Group By property you can group the items together under a heading. The Show Count property will show the number of items within a group.

[![](../assets/checkboxset_group.png)](../assets/checkboxset_group.png)

name is a unique identifier for the button. Special characters and spaces are not allowed in widget name.

Index

tab index attribute specifies the tab order of an element. You can use this property to change the default tabbing order for widget access using the tab key. The value can range from 0 to 32767. The default is 0 and -1 makes the element non-focusable.

NOTE: In Safari browsers, by default, Tab highlights only text fields. To enable Tab functionality, in Safari Browser from Preferences -> Advanced -> Accessibility set the option "Press Tab to highlight each item on a webpage".

width of your widget can be specified in _, pt, px_ or _% (_ _50px, 75%)._

height of your widget can be specified in _, pt, px_ or _% (_ _50px, 75%)._

property controls how contained widgets are displayed within this widget container.

this property to a variable to populate the list of values to display.

Keys

the keys of the live variable object as checkbox set options.

field

property sets the dataValue to be returned by a select editor when the list is populated using the dataSet property.

Field

property sets the displayValue to show in the select editor when the list is populated using the dataSet property.

Expression

is an advanced property that gives more control over what is displayed in the drop-down select list. A Display Expression uses a Javascript expression to format exactly what is shown.

by

property allows for grouping the items in the variable bound to the checkboxset dataset by selecting one of the field names from the drop-down list.

as

property allows for groups to be displayed under categories.

by

allows for multiple selections for ordering the display of rows based on fields in asc or desc order - up arrow for asc and down arrow for desc.

**Value**

is the default value to display value for an editor widget. Note that the display value is just what the user sees initially, and is not always the dataValue returned by the widget.

only

this checkbox property prevents the user from being able to change the data value of a widget.

determines whether or not a component is visible. It is a bindable property.

on Demand (visible only when show property is bound to a variable)

this property is set and show property is bound, the initialization of the widget will be deferred till the widget becomes visible. This behavior improves the load time. Use this feature with caution, as it has a downside (as we will not be able to interact with the widget through script until the widget is initialized). When show property is not bound the widget will be initialized immediately.

the disabled property is true (checked) the widget becomes display-only and user input will not be accepted. It can also set programmatically by binding it to a boolean type variable.

control for collapsing and expanding the group.

Count

display the number of items within the group.

event handler is called each time your element's value changes.

**Events**

click

is an HTML button. It is used to generate a click event. For example, save button.

mouse enter

event handler is called whenever the mouse enters the widget.

mouse leave

event handler is called whenever the mouse leaves the widget.

**Events**

tap

event handler is called whenever the widget is tapped.

**Events**

ready

event handler is called when the container is loaded.

# Cases

- [with Selection Widgets](/learn/how-tos/selection-widgets-use-case/)
- [to use CheckboxSet widget to filter a List](/learn/how-tos/checkboxset-filter-list-data/)

[3\. Form Widgets](/learn/app-development/widgets/widget-library/#form)

- [3.1 Button](/learn/app-development/widgets/form/button/)
- [3.2 Button Group](/learn/app-development/widgets/form/button-group/)
- [3.3 Calendar](/learn/app-development/widgets/form/calendar/)
- [3.4 Checkbox](/learn/app-development/widgets/form/checkbox/)
- [3.5 CheckboxSet](#)
    - [Properties](#properties)
    - [Events](#events)
    - [Use Cases](#use-cases)
- [3.6 Chips](/learn/app-development/widgets/form-widgets/chips/)
- [3.7 Color Picker](/learn/app-development/widgets/form/color-picker/)
- [3.8 Currency](/learn/app-development/widgets/form/currency/)
- [3.9 Date](/learn/app-development/widgets/form/date/)
- [3.10 Datetime](/learn/app-development/widgets/form-widgets/date-time-datetime/)
- [3.11 FileUpload](/learn/app-development/widgets/form/file-upload/)
- [3.12 Number](/learn/app-development/widgets/form-widgets/number/)
- [3.13 Radioset](/learn/app-development/widgets/form/radioset/)
- [3.14 Rating](/learn/app-development/widgets/form/rating/)
- [3.15 Select](/learn/app-development/widgets/form/select/)
- [3.16 Select Locale](/learn/app-development/widgets/form/select-locale/)
- [3.17 Slider](/learn/app-development/widgets/form/slider/)
- [3.18 Switch](/learn/app-development/widgets/form/switch/)
- [3.19 Text](/learn/app-development/widgets/form/text/)
- [3.20 Textarea](/learn/app-development/widgets/form/textarea/)
- [3.21 Time](/learn/app-development/widgets/form-widgets/date-time-datetime/)
- [3.22 Toggle](/learn/app-development/widgets/form/toggle/)