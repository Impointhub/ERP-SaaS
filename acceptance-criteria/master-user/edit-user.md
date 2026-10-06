# Edit User

## User.4.1 : Restrict Access Without Authorization <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is not authorized
* When user access the Edit User page
* Then user cannot access the page

## User.4.2 : Restrict Access Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "edit\_user"
* When user access the Edit User page
* Then user cannot access the page

## User.4.3 : Display Validation for Duplicate Username <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_user"
* And user on the Edit User form
* When user input a username that already exists
* And user click button "Update"
* Then system does not save the data
* And user can view validation message "Username has already been taken"

## User.4.4 : Display Validation for Required Fields <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_user"
* And user on the Edit User form
* When user leaves one or more required fields empty
* And user click button "Update"
* Then system does not save the data
* And user can view validation message "{Field Name} is required"

## User.4.5 : Display Validation for Duplicate Email <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_user"
* And user on the Edit User form
* When user input an email address that already exists
* And user click button "Update"
* Then system does not save the data
* And user can view validation message "Email has already been taken"

## User.4.6 : Successfully Update User Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_user"
* And user has filled all required fields with valid data
* When user click button "Update"
* Then system updates the user data in the database
* And user can view notification "Update Success"

## User.4.7 : Send Invitation Email After Successful Update <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user successfully updates user data
* When the update process is completed
* Then system sends an invitation email to the user
