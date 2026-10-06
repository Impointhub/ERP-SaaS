# Import Master Customer

## Master Customer.5.1 : Open Import Customer Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "import\_master\_customer"
* And user on the Master Customer page
* When user click button "Import" beside search bar
* Then user is directed to the Import Customer page

## Master Customer.5.2 : Select Import File <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the Import Customer page
* When user click button "Import"
* Then system opens file explorer
* And user can select a file to import

## Master Customer.5.3 : Successfully Import Customer Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the Import Customer page
* And user has selected an import file
* And user has adjusted the imported data according to available options
* When user click button "Save"
* Then system successfully imports the customer data
* And user can view notification "Import Success"

## Master Customer.5.4 : Display Validation for Incomplete Import Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the Import Customer page
* And user has selected an import file
* When user does not complete the required data adjustment
* And user click button "Save"
* Then system does not import the customer data
* And user can view a warning message
