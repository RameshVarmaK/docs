---
title: "Chips"
id: ""
---

**Chips** represent complex entities in small blocks, such as a contact. Contact chips may represent contact information in a compact way. Chips can be used for various types of entities, including free-form text, predefined text, rules, or contacts. Chips may also contain icons.

[![](/learn/assets/chips_design.png)](/learn/assets/chips_design.png)

**When to use this widget: **Using Chips widget is a growing trend across social and communication-related apps. This can afford recipient selection using tokenized auto-completing text fields. This kind of UI is more concise than list-based interfaces and more visually rich, intuitive and directly manipulable (manage recipients by touching their token).

**Where can Chips Widget be used in WaveMaker**

Chips Widget is one of the Form Widgets. It is available to be used as a standalone widget or as a part of Live Forms, Data Entry Dialogs etc.

# Features

1. The Chips widget **Value** property can be bound to a dataset of valid values for eg – Email Addresses, Hobbies, Skillset, Categories etc.. User can add new values but these new values will not be added to the dataset.
2. It acts as **search/autocomplete** widget. When the user starts typing in the Chips widget, it triggers the selection of values from the dataset and shows the corresponding values for the character pressed.
3. **Allow Only Select** (Default: false) - If Allow Only Select is set to true, Chips will restrict adding values other than in the selection. By default, there is no restriction. But note that these new values will not be added to the dataset.
4. **Max Size** (Default: 0) - By default, there is no limit on the number of chips to add. If it set to true, after Max Size is reached the input box to add more will be hidden and will be shown again after some of the elements are deleted.
5. **Enable reorder** property can be used to allow the user to reorder the Chip Elements at runtime, using a simple drag and drop operation.
6. Runtime Functionality: User can **navigate** between the chip items using the keyboard right and left keys. Also using the delete/backspace keys the Chip item can be **Deleted**.
7. **Chip item class name** property from styles tab can be used to apply styles for individual items of the Chip:
    1. a class can be added conditionally when bound to an expression ([see below for use case example](#ex3)), or
    2. class names can be entered (without any condition), these classes will be applied to all the chips.

**The difference between Search and Chips widget:**

1. In Search, you can select only one element, whereas in Chips multiple elements can be selected.
2. In Search, you cannot edit or remove selected items, whereas Chips support these features.

## Adding a Chip

1. Search for a field by typing it in the input box. Select the required chip and by clicking on to it or enter key press
2. Enter add chip other than listed items and hit enter that will add to existing list
3. If you want to add an item which is not there in the populated list, type the item and press enter. It will be added to the chips list but it will not be added to the dataset.

## Deleting a Chip

1. Click on to the cross button of each Chip element.
2. User can also select a Chip element and press DELETE button
3. Hitting backspace in the input will select the last Chips element and later deletes it.

## Edit a Chip

1. The user can double click on the Chip element and edit it.
2. On double click, you will see a format like: “displayField < dataField >”
3. Make the changes and hit the enter key. Changes will be persisted.

## Reorder Chip Elements

1. The user can drag and drop the element in the required place.

# Properties

| **Property** | **Description** |
| --- | --- |
| Name | The name is a unique identifier for the chips. Special characters and spaces are not allowed in widget name. |
| Placeholder | A placeholder is a text to show in the editor when there is no value. A common use of this is a search box that says in faint gray italicized text "Search..." which disappears as soon as the user starts to edit the text box. This is a useful alternative to a caption if you are constrained in space and asking for something simple of the user. |
| **Accessibility** |
| Tab Index | The tab index attribute specifies the tab order of an element. You can use this property to change the default tabbing order for widget access using the tab key. The value can range from 0 to 32767. The default is 0 and -1 makes the element non-focusable.
NOTE: In Safari browsers, by default, Tab highlights only text fields. To enable Tab functionality, in Safari Browser from Preferences -> Advanced -> Accessibility set the option "Press Tab to highlight each item on a webpage". |
| **Layout** |
| Width | The width of Chip widget can be specified in em, pt, px or % (i.e 50px, 75%). |
| Height | The height of Chip widget can be specified in em, pt, px or % (i.e 50px, 75%). |
| Input Width | Use this property to set the width of the chip item input box.

You can select from:

- Default – which is the normal Chip widget size, 170px, or
- Full – 100% width of the container

 |
| **Dataset** |
| Value | Set this property to a variable to populate the list of values to display. Can be bound to a Variable. |
| Search Key | The field from the above Value dataset based on which the search needs to be performed for fetching Chip Elements for user selection. |
| Picture Source | This property sets the image to be displayed in the search results. Pick from the fields from the above Dataset Value. |
| Data field | This property is useful when the dataSet is an array of objects. It decides the dataValue to be returned by the widget. If set to "All Fields", the whole object is returned against user selection. If set to a particular field, the returned value will be the value of that field in the selected object. In the case of multi-selection, the returned dataValue will also be an array. |
| Display Field | This property sets the displayValue to show in the select editor when the list is populated using the dataSet property. |
| Display Expression | This is an advanced property that gives more control over what is displayed in the drop-down select list. A Display Expression uses a Javascript expression to format exactly what is shown. |
| Order by | This allows for multiple selections for ordering the display of rows based on fields in asc or desc order - up arrow for asc and down arrow for desc. |
| **Default Value** |
| Value | This is the default value to display value for an editor widget. Note that the display value is just what the user sees initially, and is not the dataValue returned by the widget. |
| **Behavior** |
| Auto Focus | This property makes the Chip to get focus automatically when the page loads. |
| Read only | Selecting this property prevents the user from being able to change the data value of a widget. This property can be bound to a boolean value. |
| Max Size | If max size is set, chips will restrict adding more than max size. |
| Input Position | Use this property to change the position of the newly added chip item as

- _First_ - The input box appears in the beginning followed by the selected chips
- _Last_ – The input box appears at the end of the chip item list, this is the default setting

 |
| Allow Only Select | If Allow Only Select is set to true, chips will restrict adding values other than in the selection. By default, there is no restriction. |
| Enable Reorder | This property will allow users to reorder the Chip Elements at runtime. This is a bindable property. |
| Show | Showing determines whether or not a component is visible. It is a bindable property. |
| Load on Demand (visible only when show property is bound to a variable) | When this property is set and show property is bound, the initialization of the widget will be deferred until the widget becomes visible. This behavior improves the load time. Use this feature with caution, as it has a downside (as we will not be able to interact with the widget through script until the widget is initialized). When show property is not bound the widget will be initialized immediately. |
| Disabled | If the disabled property is true (checked) the widget becomes display-only and user input will not be accepted. It can also set programmatically by binding it to a boolean type variable. |
| Min Chars | The minimum number of characters to be entered by the user before the search query is triggered. The value should be greater than 0. The default value is 1. |

# Events

| Event | Description |
| --- | --- |
| Change | This event handler is called each time the chip item value changes. |
| **Mouse Events** |
| On Chip Click | This event handler is called each time the chip item is clicked. |
| **Callback Events** |
| On Before Add | This event gives handle to user whether to continue or abort to add current chip item
1. If the function does not return anything the chip item will be added
2. If the function returns false, then chip item will not be added
3. If the function returns anything other than false, chip item will be added

 |
| On Add | This event gives a handle on the successful addition of the Chip item. |
| On Before Remove | This event gives handle to user whether to continue or abort removing current chip item

1. If the function does not return anything the chip item will be removed
2. If the function returns false, then chip item will not be removed
3. If the function returns anything other than false, chip item will be removed

 |
| On Remove | This event gives handle to user on successful removal |
| On Chip Select | This event handler is called each time the chip item is selected. |
| On Before Service Call | This event is triggered before sending the service call for fetching the search results. |
| On Before Reorder | This event gives handle to user whether to continue or abort reordering current chip item

1. If the function does not return anything the chip item will be reordered
2. If the function returns false, then chip item will not be reordered
3. If the function returns anything other than false, chip item will be reordered

 |
| On Reorder | This event gives a handle on successful reordered in the following form:

Page.chips1Reorder = function($event, widget, $data, $changedItem)

where

- _$data_ - is the object containing the current chip item data,
- _$changedItem - _gives _newIndex_ and _oldIndex_ specifying the position of the chip item

 |

# Use Cases

**Example 1: Adding contacts and sending Emails**:  In this use case, you will be using the chips widget as email recipients and create a UI of Composing an Email.

[![](/learn/assets/chips_ex1.png)](/learn/assets/chips_ex1.png)

- Have a database called ProfileDB and a table named Profile with basic fields like first name, last name, job title, email.
- **Steps:**
    1. Drag and drop the chips widget onto the canvas.
    2. Create a variable based on the database CRUD APIs that is bound to Profile Table. [Know more from here](/learn/app-development/variables/database-crud/#).
    3. Bind this variable to the dataset value property.
    4. Choose Data Field as email
    5. Choose Display Field as FirstName
    6. Drag and Drop a TextArea Field for composing messages
    7. Create a [Java Service for Sending Email](/learn/app-development/services/3rd-party-libraries/using-3rd-party-jar-files/).
    8. Create a variable based on the APIs auto-generated for the methods from the Java service. [Know more from here](/learn/app-development/variables/java-services/).
    9. From the Data tab, bind the values to those returned by the Chips widget.
    10. Drag and Drop a button – Give the caption as Send. On Click of that button trigger the service variable for Java service.

**Example 2: Use in Live Form**:

1. Create two more tables in Profile DB namely Hobbies and Skillsets. Have ID and Name as fields in both.
2. Create a one-to-many relationship between id -  HobbyID
3. Create a Live Form based on a data source – ProfileDB.
4. From Advanced Settings and set the widget property for the fields Hobbies and Skillset to chips and also display expression as Hobbies and Skillset respectively.
5. Now Save and Run the App. You will observe for the Hobbies and Skillsets you are able to enter multiple values.
6. The multiple values will have to be delimited before you save the date in live form. This can be done through scripting. 
    1. Go to the Live Form events tab and for the "On before service call" event
    2. Select JavaScript from the drop down and in the script tab  add the code as below
        
        Page.liveform1Beforeservicecall = function($event, $operation, $data) { 
                  $data.<field\_name> = $data.<field\_name>.join(','); 
           };
        

**Example 3: Use a conditional class**:

1. Import sample hrdb and create a CRUD Variable for the Employee table.
2. Drag and drop Chips widget and bind the Dataset Value property to the HRDB employee variable
3. Set Data field property to All Fields,
4. From the Styles tab bind Chip item class name to the following expression: bind: item.datavalue.department.name === 'Engineering'? 'skyblue' : 'mustard' This will check if employee's department name is engineering applies "skyblue" class else applies "mustard" class (note: here "item" denotes the chip object.) [![](/learn/assets/chips_ex3_1.png)](/learn/assets/chips_ex3_1.png)[![](/learn/assets/chips_ex3_2.png)](/learn/assets/chips_ex3_2.png)
5. Add the following class to the app using the Style tab – for skyblue and mustard
    
    .nav.app-chips > li.skyblue .app-chip {
        background-color: #50b4dd;
        color: white;
        font-weight: normal;
    }
    .nav.app-chips > li.mustard .app-chip {
        background-color: #dda950;
        color: white;
        font-weight: normal;
    }
    
    [![](/learn/assets/chips_ex3_3.png)](/learn/assets/chips_ex3_3.png)
6. Preview the page [![](/learn/assets/chips_ex3_4.png)](/learn/assets/chips_ex3_4.png)
7. Setting the chip item class name (or Class Name property) as skyblue, will apply skyblue class to all the chips at runtime. [![](/learn/assets/chips_ex3_5.png)](/learn/assets/chips_ex3_5.png)

[3\. Form Widgets](/learn/app-development/widgets/widget-library/#form)

- [3.1 Button](/learn/app-development/widgets/form/button/)
- [3.2 Button Group](/learn/app-development/widgets/form/button-group/)
- [3.3 Calendar](/learn/app-development/widgets/form/calendar/)
- [3.4 Checkbox](/learn/app-development/widgets/form/checkbox/)
- [3.5 CheckboxSet](/learn/app-development/widgets/form/checkboxset/)
- [3.6 Chips](/learn/app-development/widgets/form/chips/)
    - [i. Features](#features)
    - [ii. Properties](#properties)
    - [iii. Events](#events)
    - [iv. Use Cases](#use-cases)
- [3.7 Color Picker](/learn/app-development/widgets/form/color-picker/)
- [3.8 Currency](/learn/app-development/widgets/form/currency/)
- [3.9 Date](/learn/app-development/widgets/form-widgets/date-time-datetime/)
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
