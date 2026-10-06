# Delete Master Supplier Group

## Master Supplier Group.4.1 : Display Delete Button <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* When user access the Supplier Group details page
* Then user can view button "Delete"

## Master Supplier Group.4.2 : Open Delete Reason Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user on the Supplier Group details page
* When user click button "Delete"
* Then system displays the delete reason form

## Master Supplier Group.4.3 : Display Required Validation on Delete Reason <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user on the delete reason form
* When user leaves the Reason field empty
* And user click button "Delete"
* Then user can view validation message "This field is required"

## Master Supplier Group.4.4 : Validate Maximum Characters for Delete Reason <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user on the delete reason form
* When user input more than 255 characters in the Reason field
* Then user can view validation message "Max 255 chars"

## Master Supplier Group.4.5 : Open Delete Confirmation Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user has filled the Reason field with less than 255 characters
* When user click button "Delete"
* Then system displays delete confirmation pop-up
* And password field is required

## Master Supplier Group.4.6 : Display Required Validation for Password <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user on the delete confirmation pop-up
* When user leaves Password field empty
* And user click button "Delete"
* Then user can view validation message "This field is required"

## Master Supplier Group.4.7 : Display Warning for Incorrect Password <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user on the delete confirmation pop-up
* When user input incorrect password
* And user click button "Delete"
* Then system does not delete the data
* And user can view notification "Wrong Password"

## Master Supplier Group.4.8 : Successfully Delete Supplier Group <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_supplier\_group"
* And user on the delete confirmation pop-up
* When user input correct password
* And user click button "Delete"
* Then system successfully deletes the data
* And user can view notification "Delete Success"
* And the data is removed from the system

## Master Supplier Group.4.9 : Display Request Delete Button <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "delete\_supplier\_group"
* When user access the Supplier Group details page
* Then user can view button "Request Delete"

## Master Supplier Group.4.10 : Open Request Delete Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "delete\_supplier\_group"
* When user click button "Request Delete"
* Then system displays request delete form
* And system displays field "Reason"
* And system displays field "Select User"

## Master Supplier Group.4.11 : Display Required Validation on Request Delete <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the request delete form
* When user leaves Reason field empty
* And user does not select a user
* And user click button "Submit"
* Then user can view validation message "{Field Name} is required"

## Master Supplier Group.4.12 : Validate Maximum Characters for Request Delete Reason <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the request delete form
* When user input more than 255 characters in the Reason field
* Then user can view validation message "Max 255 chars"

## Master Supplier Group.4.13 : Successfully Submit Delete Request <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the request delete form
* And user has selected a recipient
* And user has filled the Reason field correctly
* When user click button "Submit"
* Then system successfully sends the delete request
* And user can view notification "Request Delete Success"
