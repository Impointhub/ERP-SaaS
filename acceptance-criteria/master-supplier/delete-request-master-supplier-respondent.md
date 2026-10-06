# Delete Request Master Supplier (Respondent)

## Master Supplier.7.1 : View Delete Request Information <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_master\_supplier"
* And user has been selected as deletion request recipient
* When user access the supplier details page
* Then user can view the delete request information
* And user can view button "Approve"
* And user can view button "Reject"

## Master Supplier.7.2 : Approve Delete Request from Details Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "delete\_master\_supplier"
* And user has been selected as deletion request recipient
* And user on the supplier details page
* When user click button "Approve"
* Then system successfully deletes the supplier data

## Master Supplier.7.3 : Reject Delete Request from Details Page <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

(ini di merge krn goalsnya sama?\
GIVEN the request delete information, WHEN I click on the Reject button, THEN the data will not be deleted and it will remain available.\
GIVEN the request delete information within the view page of the selected data, WHEN I click on the Reject button, THEN the data will not be deleted and it will remain available.)

* Given user is logged in
* And user have permission "delete\_master\_supplier"
* And user has been selected as deletion request recipient
* And user on the supplier details page
* When user click button "Reject"
* Then system does not delete the supplier data
* And the supplier data remains available

## Master Supplier.7.4 : Receive Delete Request Email Notification <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user have permission "delete\_master\_supplier"
* And user has been selected as deletion request recipient
* When deletion request is submitted
* Then system sends a delete request notification email to the user

## Master Supplier.7.5 : Open Delete Request from Email <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user receives a delete request email
* When user click option "Check"
* Then system redirects user to the Login page

## Master Supplier.7.6 : Redirect to Supplier Details After Login <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is registered
* And user accesses the Login page from delete request email
* When user successfully login
* Then system redirects user to the supplier details page related to the deletion request

## Master Supplier.7.7 : Approve Delete Request from Email <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user receives a delete request email
* And user have permission "delete\_master\_supplier"
* When user click button "Approve"
* Then system successfully deletes the supplier data

## Master Supplier.7.8 : Reject Delete Request from Email <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user receives a delete request email
* And user have permission "delete\_master\_supplier"
* When user click button "Reject"
* Then system does not delete the supplier data
* And the supplier data remains available
