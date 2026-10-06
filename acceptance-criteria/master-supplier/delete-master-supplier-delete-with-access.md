# Delete Master Supplier (Delete With Access)

## Master Supplier.5.1 : Display Delete Button on Supplier Details Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_master\_supplier"
* And user on the supplier details page
* Then user can view button "Delete"

## Master Supplier.5.2 : Successfully Delete Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_master\_supplier"
* And user on the supplier details page
* When user click button "Delete"
* And system displays delete confirmation pop-up
* And user input correct password
* And user click button "Confirm"
* Then system successfully deletes the supplier data
* And user can view notification "Data has been deleted successfully"

## Master Supplier.5.3 : Deny Delete Action with Invalid Password <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_master\_supplier"
* And user on the supplier details page
* When user click button "Delete"
* And system displays delete confirmation pop-up
* And user input incorrect password
* And user click button "Confirm"
* Then system does not delete the supplier data
* And user can view notification "Invalid password"
