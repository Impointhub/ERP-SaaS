# Accept Invitation

## User.2.1 : Validate Registered Email Address <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user accesses the invitation link
* When system validates the email address
* Then system checks whether the email address is already registered

## User.2.2 : Validate User Login Status <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user accesses the invitation link
* When system processes the invitation
* Then system checks whether the user is logged in

## User.2.3 : Activate User Account <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user accesses a valid invitation link
* And the invitation data is valid
* When user accepts the invitation
* Then system updates the database
* And system activates the user account

## User.2.4 : Display Welcome Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user successfully accepts the invitation
* When the account activation process is completed
* Then system displays the Welcome page
