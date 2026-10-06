# Index

## Master Supplier.1.1 : Open Add Supplier Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the Master Supplier index page
* When user click button (+) beside search bar
* Then system displays the "Add Supplier" form in a pop-up window

## Master Supplier.1.2 : Input Supplier Information <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Add Supplier" form
* When user click any available information field
* Then user can input information according to the field rules

## Master Supplier.1.3 : Auto Generate Supplier Code <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* When user access the "Add Supplier" form
* Then system automatically generates value for the Code field based on the configured formula

## Master Supplier.1.4 : Edit Auto Generated Supplier Code <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Add Supplier" form
* When user click pencil icon beside the Code field
* Then user can edit the Code field manually

## Master Supplier.1.5 : Display Warning for Duplicate Supplier Code <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Add Supplier" form
* And supplier code already exists
* When user input an existing supplier code into the Code field
* And user click button "Save"
* Then system does not save the supplier data
* And user can view notification "Code already exists"

## Master Supplier.1.6 : Select Supplier Group <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Add Supplier" form
* When user click button "Select" in Supplier Group section
* Then system displays the available Supplier Group list in a pop-up window
* And user can select a Supplier Group

## Master Supplier.1.7 : Create New Supplier Group from Selection Popu <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Select Supplier Group" pop-up window
* When user click button "Create New"
* Then system displays the "Add Supplier Group" form in a pop-up window
* And user can create a new Supplier Group

## Master Supplier.1.8 : Successfully Create Supplier <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Add Supplier" form
* And user has filled all required fields with valid data
* When user click button "Save"
* Then system successfully saves the supplier data
* And user can view notification "Data has been saved successfully"

## Master Supplier.1.9 : Display Required Field Validation <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the "Add Supplier" form
* When user leaves one or more required fields empty
* And user click button "Save"
* Then system does not save the supplier data
* And user can view validation message "{Field Name} is required" on each empty required field
