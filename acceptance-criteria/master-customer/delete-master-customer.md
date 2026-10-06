# Delete Master Customer

## Master Customer.4.1 : Successfully Delete Customer Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_master\_customer"
* And user click button "Delete"
* And system displays delete confirmation pop-up
* When user input correct password
* And user click button "Confirm"
* Then system successfully deletes the customer data
* And user can view notification "Delete Success"
