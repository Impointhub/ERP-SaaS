# Read Master Supplier

## Master Supplier.3.1 : View Supplier Details <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_master\_supplier"
* And user on the Master Supplier index page
* When user click any available supplier data
* Then system displays the details page of the selected supplier
* And user can view the supplier information details

## Master Supplier.3.2 : Navigate to Supplier Details Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_master\_supplier"
* And user on the Master Supplier index page
* When user click any supplier data available on the index page
* Then user is directed to the details page of the selected supplier

## Master Supplier.3.3 : Restrict Access to Supplier Details Without Read Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "read\_master\_supplier"
* When user navigate to Master Supplier
* Then user cannot view the available Master Supplier data
* And user cannot access the details page of any supplier data

## Master Supplier.3.4 : Create New Supplier from Details Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "create\_master\_supplier"
* And user on the supplier details page
* When user click button "Create"
* Then system displays the "Add Supplier" form
* And user can create a new supplier data
