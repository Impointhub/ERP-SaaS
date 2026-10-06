# Invite User

## User.1.1 : Restrict Access Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "invite\_user"
* When user access the Invite User page
* Then user cannot access the page

## User.1.2 : Display Validation for Required Fields <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "invite\_user"
* And user on the Invite User form
* When user leaves one or more required fields empty
* And user click button "Invite"
* Then system does not send the invitation
* And user can view validation message "{Field Name} is required"

## User.1.3 : Display Validation for Duplicate Email <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "invite\_user"
* And user on the Invite User form
* When user input an email that already exists
* And user click button "Invite"
* Then system does not send the invitation
* And user can view validation message "Email has already been taken"

## User.1.4 : Display Validation for Duplicate Unique Fields <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "invite\_user"
* And user on the Invite User form
* When user input a value that already exists in a unique field
* And user click button "Invite"
* Then system does not send the invitation
* And user can view validation message "{Field Name} has already been taken"

## User.1.5 : Successfully Invite User <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "invite\_us er"
* And user has filled all required fields with valid data
* When user click button "Invite"
* Then system successfully creates the invitation
* And system updates the database
* And user can view notification "Invite Success"
* And user is redirected to the User list page
