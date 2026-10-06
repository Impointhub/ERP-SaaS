# Export Supplier

## Master Supplier.9.1 : Export Supplier Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "export\_supplier"
* And user on the Master Supplier index page
* When user click button "Export"
* Then system exports the supplier data
* And system downloads the data in ".xls" format
