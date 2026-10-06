# Update Master Supplier Group

## Master Supplier Group.3.1 : Open Edit Supplier Group Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_supplier\_group"
* And user on the Supplier Group details page
* When user click button "Edit"
* Then system displays the "Edit Supplier Group" form in a pop-up window

## Master Supplier Group.3.2 : Display Required Field Validation on Update <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_supplier\_group"
* And user on the "Edit Supplier Group" form
* When user leaves one or more required fields empty
* And user click button "Update"
* Then system does not save the data
* And user can view validation message "{Field Name} is required"

## Master Supplier Group.3.3 : Successfully Update Supplier Group <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_supplier\_group"
* And user on the "Edit Supplier Group" form
* And user has updated the data with valid information
* When user click button "Update"
* Then system successfully updates the data
* And user can view notification "Update Success"

## Master Supplier Group.3.4 : View Updated Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user successfully updates Supplier Group data
* When user access the Supplier Group index page
* Then user can view the latest updated data

## Master Supplier Group.3.5 : Hide Edit Button Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "edit\_supplier\_group"
* When user access the Supplier Group details page
* Then user cannot view button "Edit"

