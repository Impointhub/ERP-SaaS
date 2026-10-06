# Create Master Customer

## Master Customer.2.1 : Input Customer Information <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_customer"
* And user on the "Add Customer" form
* When user click any available information field
* Then user can input information according to the field rules

## Master Customer.2.2 : Auto Generate Customer Code <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_customer"
* When user access the "Add Customer" form
* Then system automatically generates value for the Code field based on the configured formula

