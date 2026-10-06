# Create Master Supplier

## Master Supplier.2.1 : View Master Supplier List <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_master\_supplier"
* When user access the Master Supplier index page
* Then user can view the available Master Supplier data

## Master Supplier.2.2 : Redirect to Forbidden Page When User Has No Read Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "read\_master\_supplier"
* When user type /master-supplier url into browser
* Then user redirected to forbidden page

## Master Supplier.2.3 : View Supplier Group Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_master\_supplier"
* And user on the Master Supplier index page
* When user click tab "Group"
* Then user can view the available Supplier Group data

## Master Supplier.2.4 : Search Master Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_master\_supplier"
* And user on the Master Supplier index page
* And Master Supplier data is available
* When user input keyword into search bar
* And the keyword matches existing data
* Then system displays search results related to the keyword

## Master Supplier.2.5 : Sort Master Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_master\_supplier"
* And user on the Master Supplier index page
* When user click sort icon on any column
* Then system sorts the data in ascending order
* And user can click the sort icon again
* Then system sorts the data in descending order
