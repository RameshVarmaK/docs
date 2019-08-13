---
title: "How Tos: Form"
id: "how-tos-form"
---

Using Form to trigger an Insert QueryWe will be seeing how to use a Form to insert values into a Employee table of hrdb database using Insert Query:

1. a query in database designer with input params
    
     INTO EMPLOYEE 
    (FIRSTNAME, LASTNAME, STREET, CITY, STATE, ZIP, BIRTHDATE, PICURL, JOBTITLE, TENANTID)
    VALUES (:firstname, :lastname, :street, :city, :state, :zip, :birthdate, :picurl, :jobtitle, :tenantid)
    
2. test values and run and save the query (as InsertEmp).
3. a variable by dragging and dropping Form widget and using Create new functionality or by using this query operation from variable dialog. [![form_query_var](../assets/form_query_var.png)](../assets/form_query_var.png)
4. Layout and Configure Fields changing the display name and widget type if needed. Note that if the Service Variable undelying the Form, has to have some input fields the same should be done using the Data tab of the Service Variable.
5. page will look like this in design mode [![form_query_design](../assets/form_query_design.png)](../assets/form_query_design.png)
6. the app, enter the values and SAVE [![form_query_run](../assets/form_query_run.png)](../assets/form_query_run.png)

Using Form as Filter Form can be used as filter for GET type of API’s. Below example is for filtering the data using a query. We will be using the Employee table of hrdb database to filter on city field.

1. a query in database designer with input params
    
     \* FROM EMPLOYEE WHERE CITY = :city
    
2. test values and run and save the query (as EmpByCity).
3. a variable using this query operation from variable dialog or dragging and dropping Form widget and using Create new functionality. [![form_filter_var](../assets/form_filter_var.png)](../assets/form_filter_var.png)
4. Layout and Configure Fields changing the display name and widget type if needed.
5. and drop a Data Table onto the canvas and bind it to the Service Variable created when configuring Form. Your page will look like this in design mode Note: We have changed the name of the SAVE button to FILTER [![form_filter_design](../assets/form_filter_design.png)](../assets/form_filter_design.png)
6. the app, enter the values and FILTER, see the content of the Data Table change. [![form_filter_run](../assets/form_filter_run.png)](../assets/form_filter_run.png)

Using Form EventsFollowing events can be used to modify the behaviour of Form:

- **before submit**: This event will be called before submitting the form.  validation checks can be performed here. Returning false from the script will stop the form submit. _Example_:
    
    $scope.form1Beforesubmit = function ($event, $isolateScope, $data) { 
    //$isolateScope: $isolateScope of the form
    //$data has the data of the all widgets inside the form. This data can be modified and validated before sending the request 
    
            function isValidData(data) {
                /\*restrict password to be minimum of 6 characters\*/
                if (data.password) {
                    if (data.password.length < 6) {
                        return {
                            'error': "Password too small"
                        };
                    }
                } else {
                    return {
                        'error': "Password field required"
                    };
                }
            }
            return isValidData($data)
    };
    
- **submit**: This event will be called on submitting the form. Note: This is called after ‘on before submit’. If on before submit returns false, this function will not be called. _Example_:
    
    $scope.form1Submit = function ($event, $isolateScope, $formdata) { 
    //$isolateScope: $isolateScope of the form
    //$formData has the data of the all widgets inside the form.
    console.log(“Form data:”, $formdata);
    };
    
- **restult**: This event will be called after form is submitted and API returns a response. Event is triggered in both success and failure cases. _Example_:
    
    $scope.form1Result = function ($event, $isolateScope, $data) { 
    //$isolateScope: $isolateScope of the form
    //$data has the response returned from the API.
    console.log(“server response:”, $data);
    };
    
- **success**: This event will be called after form is submitted and API returns a success response. _Example_:
    
    $scope.form1Success = function ($event, $isolateScope, $data) { 
    //$isolateScope: $isolateScope of the form
    //$data has the response returned from the API.
    console.log(“The inserted data:”, $data);
    };
    
- **error**: This event will be called after form is submitted and API returns a failure response. _Example_:
    
    $scope.form1Error = function ($event, $isolateScope, $data) { 
    //$isolateScope: $isolateScope of the form
    //$data has the error message returned from the API.
    console.log(“Error returned from server:”, $data);
    };
    

Accessing Form MethodsLive Form has few methods exposed on widget scope to Edit, Delete, Add record and trigger actions like reset and cancel.

For the following script samples, we are considering the table. is bound to the SelectedItem of a Data Grid corresponding to Employee Live Variable.

- delete a record:
    
    $scope.Widgets.EmployeeForm.delete(); //Deletes the current record that is bound to EmployeeForm.
    
- update a record:
    
    $scope.Widgets.EmployeeForm.save(); //Updates the current record bound
    
- add a new record:
    
    $scope.Widgets.EmployeeForm.new(); //Adds a new record to dataset that is bound to EmployeeForm.
    
- reset a form:
    
    $scope.Widgets.EmployeeForm.reset(); //Resets the form to initial state.
    
- cancel an edit operation:
    
    $scope.Widgets.EmployeeForm.cancel(); //Cancels the form edit.