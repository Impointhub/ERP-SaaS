# Delete Request Master Supplier (Requestor)

## Master Supplier.6.1 : Open Delete Request Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "delete\_master\_supplier"
* And user on the supplier details page
* When user click button "Delete"
* Then system displays the "Request Delete" form in a pop-up window

## Master Supplier.6.2 : Select Delete Request Recipient <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the "Request Delete" form
* When user click dropdown "Select User"
* Then system displays users who have permission "delete\_master\_supplier"
* And user can select one recipient

## Master Supplier.6.3 : Input Delete Request Reason <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the "Request Delete" form
* When user click field "Reason"
* Then user can input the reason for deletion request

## Master Supplier.6.4 : Successfully Send Delete Request <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the "Request Delete" form
* And user has selected a request recipient
* And user has filled the Reason field
* When user click button "Delete"
* Then system successfully sends the deletion request
* And user can view notification "Delete request has been sent successfully"

## Master Supplier.6.5 : Display Required Field Validation on Delete Request <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user on the "Request Delete" form
* When user leaves one or more required fields empty
* And user click button "Delete"
* Then system does not send the deletion request
* And user can view validation message "{Field Name} is required"



