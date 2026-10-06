# Read Master Supplier Group

## Master Supplier Group.2.1 : View Supplier Group Module <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_supplier\_group"
* When user access the Master menu
* Then user can view the Supplier Group module

## Master Supplier Group.2.2 : View Supplier Group List <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_supplier\_group"
* When user access the Supplier Group index page
* Then user can view Supplier Group data
* And system displays a maximum of 10 records per page

## Master Supplier Group.2.3 : Sort Supplier Group Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_supplier\_group"
* And user on the Supplier Group index page
* When user click sort icon on any column
* Then system sorts the data in ascending order
* And user can click the sort icon again
* Then system sorts the data in descending order

## Master Supplier Group.2.4 : View Supplier Group Details <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_supplier\_group"
* And user on the Supplier Group index page
* When user click a Supplier Group name
* Then user is directed to the Supplier Group details page

## Master Supplier Group.2.5 : Navigate Using Pagination <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_supplier\_group"
* And user on the Supplier Group index page
* When user click a specific page number on pagination
* Then system displays data for the selected page

## Master Supplier Group.2.6 : Hide Supplier Group Module Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "read\_supplier\_group"
* When user access the Master menu
* Then user cannot view the Supplier Group module

