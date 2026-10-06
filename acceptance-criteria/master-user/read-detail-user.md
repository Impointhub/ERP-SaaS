# Read Detail User

### User.5.1 : Restrict Access Without Authorization <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is not authorized
* When user access the User Detail page
* Then user cannot access the page

### User.5.2 : Restrict Access Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-1" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-1"></a>

* Given user is logged in
* And user does not have permission "read\_user"
* When user access the User Detail page
* Then user cannot access the page

### User.5.3 : View User Information <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-2" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-2"></a>

* Given user is logged in
* And user have permission "read\_user"
* When user access the User Detail page
* Then system displays the user information page

### User.5.4 : Open Delete Confirmation Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-3" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-3"></a>

* Given user is logged in
* And user have permission "delete\_user"
* And user on the User Detail page
* When user click button "Delete"
* Then system displays password confirmation form

### User.5.5 : Validate Password Confirmation <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-4" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-4"></a>

* Given user is logged in
* And user have permission "delete\_user"
* And user on the password confirmation form
* When user input password
* Then system validates whether the password matches the current user password

### User.5.6 : Restrict Delete Action Without Authorization <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-5" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-5"></a>

* Given user is not authorized
* When user attempts to delete a user
* Then user cannot perform the delete action

### User.5.7 : Restrict Delete Action Without Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-6" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page-6"></a>

* Given user is logged in
* And user does not have permission "delete\_user"
* When user attempts to delete a user
* Then user cannot perform the delete action<br>
