# Import Supplier

## Master Supplier.8.1 : Open Import Supplier Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "import\_supplier"
* And user on the Master Supplier page
* When user click button "Import" beside search bar
* Then user is directed to the Import Supplier page

## Master Supplier.8.2 : Select Import File <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* And user on the Import Supplier page
* When user click button "Import"
* Then system opens file explorer
* And user can select a file to import

## Master Supplier.8.3 : Successfully Import Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the Import Supplier page
* And user has selected an import file
* And user has mapped or adjusted the imported data according to available options
* When user click button "Save"
* Then system successfully imports the supplier data
* And user can view notification "Import Success"

## Master Supplier.8.4 : Display Validation for Incomplete Import Mapping <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the Import Supplier page
* And user has selected an import file
* When user does not complete the required data mapping
* And user click button "Save"
* Then system does not import the supplier data
* And user can view a warning message



