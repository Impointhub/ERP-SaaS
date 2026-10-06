# User List

## User.3.1 : Restrict Access Without Authorization <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is not authorized
* When user access the User List page
* Then user cannot access the page

## User.3.2 : Restrict Access Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "read\_user"
* When user access the User List page
* Then user cannot access the page

## User.3.3 : Search User Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_user"
* And user on the User List page
* When user fill the search input with a keyword
* Then system displays filtered user data that matches the keyword

## User.3.4 : Navigate User List Using Pagination <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_user"
* And user on the User List page
* When user select a page from pagination
* Then system displays the data for the selected page

## User.3.5 : Display Sorted User Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "read\_user"
* And user on the User List page
* When system displays filtered data
* Then system displays the data according to the applied sorting order
