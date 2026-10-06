# Index

## Master Customer.1.1 : Restrict Access to Master Customer Data Without Read Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "read\_master\_customer"
* When user navigate to the Master Customer index page
* Then user cannot view the available Master Customer data
