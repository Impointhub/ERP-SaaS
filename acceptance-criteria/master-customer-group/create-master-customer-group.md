# Create Master Customer Group

## Master Customer Group.1.1 : Open Add Customer Group Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_customer\_group"
* When user click button "Create New" from the Customer Group selection popup
* Then system displays the "Add Customer Group" form in a pop-up window

## Master Customer Group.1.2 : Display Warning for Duplicate Code <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_customer\_group"&#x20;
* And user on the "Add Customer Group" form
* When user input an existing code
* And user click button "Save"
* Then system does not save the data
* And user can view notification "The code has already taken"

## Master Customer Group.1.3 : Successfully Create Customer Group <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_customer\_group"
* And user on the "Add Customer Group" form
* And user has filled all required fields with valid data
* When user click button "Save"
* Then system successfully saves the Customer Group data
* And user can view notification "Create Success"
* And the Customer Group data appears on the index page

## Master Customer Group.1.4 : Display Required Field Validation <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_customer\_group"
* And user on the "Add Customer Group" form
* When user leaves one or more required fields empty
* And user click button "Save"
* Then system does not save the data
* And user can view validation message "{Field Name} is required"

## Master Customer Group.1.5 : Customer Group Available as Reference <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user successfully creates a Customer Group
* When user accesses modules that use Customer Group reference
* Then the newly created Customer Group is available as reference data
