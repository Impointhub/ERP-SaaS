# Read Master Customer Group

## Master Customer Group.2.1 : View Customer Group Module <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_customer\_group"
* When user access the Master menu
* Then user can view the Customer Group module

## Master Customer Group.2.2 : View Customer Group List <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_customer\_group"
* When user access the Customer Group index page
* Then user can view Customer Group data
* And system displays a maximum of 10 records per page

## Master Customer Group.2.3 : Sort Customer Group Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_customer\_group"
* And user on the Customer Group index page
* When user click sort icon on any column
* Then system sorts the data in ascending order
* And user can click the sort icon again
* Then system sorts the data in descending order

## Master Customer Group.2.4 : View Customer Group Details <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_customer\_group"
* And user on the Customer Group index page
* When user click a Customer Group name
* Then user is directed to the Customer Group details page

## Master Customer Group.2.5 : Navigate Using Pagination <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_customer\_group"
* And user on the Customer Group index page
* When user click a specific page number on pagination
* Then system displays data for the selected page

## Master Customer Group.2.6 : Hide Customer Group Module Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "read\_customer\_group"
* When user access the Master menu
* Then user cannot view the Customer Group module

