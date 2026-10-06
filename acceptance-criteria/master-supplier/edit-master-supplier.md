# Edit Master Supplier

## Master Supplier.4.1 : Display Edit Button on Supplier Details Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_supplier"
* And user on the supplier details page
* Then user can view button "Edit"

## Master Supplier.4.2 : Open Edit Supplier Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_supplier"
* And user on the supplier details page
* When user click button "Edit"
* Then system displays the "Edit Supplier" form in a pop-up window

## Master Supplier.4.3 : Edit Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_supplier"
* And user on the supplier details page
* When user click button "Edit"
* Then user can modify the supplier information

## Master Supplier.4.4 : Successfully Update Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_supplier"
* And user on the "Edit Supplier" form
* And user has updated the supplier information with valid data
* When user click button "Update"
* Then system successfully saves the updated supplier data
* And user can view notification "Data has been updated successfully"

## Master Supplier.4.5 : Display Required Field Validation on Update <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_supplier"
* And user on the "Edit Supplier" form
* When user leaves one or more required fields empty
* And user click button "Update"
* Then system does not save the supplier data
* And user can view validation message "{Field Name} is required" on each empty required field

## Master Supplier.4.6 : Hide Edit Button Without Edit Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "edit\_master\_supplier"
* When user access the supplier details page
* Then user cannot view button "Edit"
