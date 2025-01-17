---
title: "Page Parameters"
id: ""
sidebar_label: "Page Parameters"
---
Page parameters is an important concept. It helps passing data across pages.

---
Pass data from one page to another page within an app by defining the **Page Params**. This applies to pages and partial pages. There can be many scenarios where you will need to pass data to a specific page. For example: 

- displaying the employee details working in a selected department,
- displaying profile for a specific user based on some dynamic constraint, or
- loading a personalized page like for activation links etc..

## How parameters work

A typical page URL for a given app would be like this: https://www.app.com/#pagename Once the Page Param has been defined the URL changes to https://www.app.com/#pagename?param1=1&param2=abc This URL format will allow the data to be retained on browser refresh and reload. As is evident from the above example, multiple parameters are also supported.

## Steps to adding Page Params

There are two aspects to adding Page Params.



1. **Parameterized Page**: Page needing input to render the data on the page needs to _define_ page-level parameters to hold this input and _access_ the param value within the page.
2. **Calling Page**: Page calling the above parameterized-page needs a way to _pass the value_ to the parameter

For example, `test_page` needs an id to render the data and it has to be invoked from Main Page with the needed value for id.

### Parameterised Page
- Add the parameter fields to the parameterized page (in this case, _test\_page_) by giving it a Name and specifying the Type. Currently, the supported types for page param are string, integer, boolean and date.⁣ 

[![](/learn/assets/pp_params.png)](/learn/assets/pp_params.png)

- Page Params are available on the page/partial scope and can be used in the same. These parameters can be accessed from the Page Param tab on the binding dialog. 

[![](/learn/assets/pp_bind.png)](/learn/assets/pp_bind.png)

### Calling Page
- The Application-scoped Navigation Action generated by default by WaveMaker for test\_page can be used to bind a value for the id field from the Main Page. The param will be available in the data tab of the Actions (goToPage\_test\_page). You can also create another Navigation Action and use it in a different navigation flow. 

[![](/learn/assets/pp_navvar.png)](/learn/assets/pp_navvar.png)

We have seen how a page can be added to WaveMaker app, it's title and layout set. We also saw how page parameters can be used to pass information to pages. Learn more about [Partial Pages](/learn/app-development/ui-design/page-concepts/partial-pages/), [Page Layouts](/learn/app-development/ui-design/page-concepts/page-layouts/), and [Page Templates](/learn/app-development/ui-design/page-concepts/page-templates/).

