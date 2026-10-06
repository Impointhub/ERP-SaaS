# Export Master Customer

## Master Customer.6.1 : Restrict Access to Master Customer Data Without Read Permission <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the Customer index page
* When user click button "Export"
* Then system exports the customer data
* And user receives the exported data in an Excel file
