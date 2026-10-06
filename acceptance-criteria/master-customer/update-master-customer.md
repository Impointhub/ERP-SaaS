# Update Master Customer

## Master Customer.3.1 : Open Edit Customer Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_customer"
* And user on the customer details page
* When user click button "Edit"
* Then system displays the editable customer form in a pop-up window

## Master Customer.3.2 : Successfully Update Customer Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_master\_customer"
* And user on the editable customer form
* And user has updated the customer information
* When user click button "Update"
* Then system successfully saves the updated customer data
* And user can view notification "Update Success"
