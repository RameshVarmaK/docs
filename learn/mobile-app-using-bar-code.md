---
title: "Mobile App using Bar code"
id: ""
---

Learn to create a **simple mobile application** that will scan an employee id barcode and display the corresponding _Employee Profile_. We will be using the sample hrdb shipped with WaveMaker.

Through this mobile application, you will learn about the following functionalities:

- Creation of a **Hybrid Mobile** app
- Importing a **Sample Database**
- Usage of **LList** widgets
- Creation of **Device** and **Live** variables

The following steps will help you to build a simple mobile app with the above-mentioned functionalities.

Login to WaveMaker using your credentials. You will be directed to Projects Dashboard page.

## Create Mobile App

Creating an app involves the following steps:

1. Click **Create App**, from the project dashboard page. **NOTE**: If you have not created any projects, you will be directed to **Sample Apps**. Select the **Apps** tab to see the Create App option.
2. Choose **Mobile**, from **Select your platform** dialog. **[![Selecting_mobile_app](/learn/assets/Selecting_mobile_app.png)](/learn/assets/Selecting_mobile_app.png)**
3. On **Create Mobile Application** dialog, enter the **Project Name** and **Description** for the project in their respective fields and set the **project avatar** (project image) if required and click **CREATE**. [![Name_Description](/learn/assets/Name_Description.png)](/learn/assets/Name_Description.png)
4. A **project settings** dialog will be displayed. [![settings](/learn/assets/settings.png)](/learn/assets/settings.png) You can modify the following (optional):

- **package prefix** – Package prefix defines the default package for the generated code across all services. This can be modified as per your requirements.
- **copyright** information – created by default, which can be modified.
- set the **default language** for the project, this can be used in conjunction with [Localization](/learn/howtos-select-locale) to set the language for the application.
- Click **SAVE**.
- The **Main Page** is created by default, with a _Two Column layout with top navbar and tabbar_.

## Adding Datasource - Database

We will Import a database to add data source to our application

1. From the Main Menu, click on **Import** and select **Database **from the drop-down list. This will enable us to include a data source (database) into our application. [![Import_DB](/learn/assets/Import_DB.png)](/learn/assets/Import_DB.png)
2. You need to choose the Database Provider of the database being imported. For this tutorial, we will use the inbuilt sample database that ships with WaveMaker. Click **sample database** link. [![bs_dbimport](/learn/assets/bs_dbimport.png)](/learn/assets/bs_dbimport.png)
3. **Select tables** that you want to import from the chosen database. Here we will go with the default setting and import all the tables by clicking **NEXT**. [![bs_dbtables](/learn/assets/bs_dbtables.png)](/learn/assets/bs_dbtables.png)
4. Upon successful import, you can choose to work with the data model generated or use the DB widgets created or go back to the canvas you are working on. Click **CLOSE** to get back to the project workspace. [![bs_dbfinal](/learn/assets/bs_dbfinal.png)](/learn/assets/bs_dbfinal.png)

## UI Design

Drag and drop following widgets

<table><tbody><tr><td width="312"><u>Widget</u></td><td width="312"><u>Usage</u></td></tr><tr><td width="312">Barcode scanner</td><td width="312">Used to scan product id</td></tr><tr><td width="312">Button</td><td width="312">To search the fetched product</td></tr><tr><td width="312">Textbox(text1)</td><td width="312">To view the scanned barcode value(Employee id)</td></tr><tr><td width="312">Textbox(text2)</td><td width="312">To view fetched Employee Name</td></tr><tr><td width="312">Textbox(text3)</td><td width="312">To view fetched Employee Designation</td></tr><tr><td width="312">Picture(picture1)</td><td width="312">To view fetched Employee image</td></tr></tbody></table>

## Variable Creation

Select the Variable option from the Create Menu. From the variable dialog:

1. Select variable type as live variable
2. Create a variable (say, empSearchVariable) with Employee table as the Type [![bs_empvar](/learn/assets/bs_empvar.png)](/learn/assets/bs_empvar.png)
3. The next steps will help in filtering data based on the output of QRCode /Barcode widget.
4. Click on data tab and select eid field binding icon. [![bs_empvar_data](/learn/assets/bs_empvar_data.png)](/learn/assets/bs_empvar_data.png)
5. Navigate to use expression tab as per the below screenshot and search for the widget with name text1 in the search box and bind its data value to the eid field. [![bs_empvar_databind](/learn/assets/bs_empvar_databind-1024x531.png)](/learn/assets/bs_empvar_databind.png)
6. Click on Save and Close button [![bs_empvar_data2](/learn/assets/bs_empvar_data2.png)](/learn/assets/bs_empvar_data2.png)

## Widget Bindings

For the various widgets dropped in the UI Design step, do the following:

1. For text1 set value from barcode data value. This would display the barcode value and we are passing the same value to the above variable [![bs_text1_bind](/learn/assets/bs_text1_bind-1024x325.png)](/learn/assets/bs_text1_bind.png) [![bs_text1_bind2](/learn/assets/bs_text1_bind2.png)](/learn/assets/bs_text1_bind2.png)
2. For text2 set value from empSearchVariable variable->firstname. This would display name of the product as per the filter. [![bs_text2_bind](/learn/assets/bs_text2_bind.png)](/learn/assets/bs_text2_bind.png)
3. Similarly for text3 set value from empSearchVariable variable->jobtitle and for picture1 set Source value from empSearchVariable variable->picurl

## Widget Events

For the various widgets dropped in the UI Design step, do the following:

1. For button1 set On tap event value as empSearchVariable. Hence, on click of the button, the variable would be called. [![bs_but_event](/learn/assets/bs_but_event-1024x371.png)](/learn/assets/bs_but_event.png)

- Save and run the project. Based on the Barcode generated the Employee name, job title and image changes in UI.
- Generate APK file for using the App in mobile
- Working with generated APK. Click [here](https://drive.google.com/file/d/0Bwk0Hs1G2nOgRDZ2c1ZueFRPX0U/view?usp=sharing) for Demo Apk file generated for the application. **Note**: For demo purpose, we have used Employee ids as 1,2,3... You can create a QR code for numbers and scan it for the respective product name, description etc. Sample QR Code generators online: http://www.qr-code-generator.com/

[Mobile App Tutorials](/learn/tutorials/#tab-mob-tutorials)

- [1\. First Mobile App](/learn/hybrid-mobile/first-mobile-app/)
- [2\. Mobile App Integrated with Database](/learn/hybrid-mobile/mobile-app-integrated-database/)
- [3\. Mobile App using Bar Code Scanner](/learn/hybrid-mobile/mobile-app-using-bar-code/)
    - [i. App Creation](#creation)
    - [ii. Integrating Datasource](#datasource)
    - [iii. UI Design](#ui-design)
    - [iv. Variable Creation](#variables)
    - [v. Widget Binding](#binding)
