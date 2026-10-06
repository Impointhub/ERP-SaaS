# Create Master Supplier Group

## Master Supplier Group.1.1 : Open Add Supplier Group Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_supplier\_group"
* When user click button "Create New" from the "Select Supplier Group" pop-up window
* Then system displays the "Add Supplier Group" form in a pop-up window

## Master Supplier Group.1.2 : Display Warning for Duplicate Code <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_supplier\_group"
* And user on the "Add Supplier Group" form
* When user input an existing code
* And user click button "Save"
* Then system does not save the data
* And user can view notification "The code has already taken"

## Master Supplier Group.1.3 : Successfully Create Supplier Group <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_supplier\_group"
* And user on the "Add Supplier Group" form
* And user has filled all required fields with valid data
* When user click button "Save"
* Then system successfully saves the Supplier Group data
* And user can view notification "Create Success"
* And the Supplier Group data appears on the index page

## Supplier Group - 1.4 : Display Required Field Validation <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_supplier\_group"
* And user on the "Add Supplier Group" form
* When user leaves one or more required fields empty
* And user click button "Save"
* Then system does not save the data
* And user can view validation message "{Field Name} is required"

## Supplier Group - 1.5 : Supplier Group Available as Reference <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user successfully creates a Supplier Group
* When user accesses related modules that use Supplier Group reference
* Then the newly created Supplier Group is available as reference data

