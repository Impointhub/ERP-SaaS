# Update Master Customer Group

## Master Customer Group.3.1 : Open Edit Customer Group Form <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_customer\_group"
* And user on the Customer Group details page
* When user click button "Edit"
* Then system displays the editable Customer Group form in a pop-up window

## Master Customer Group.3.2 : Display Required Field Validation on Update <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_customer\_group"
* And user on the Edit Customer Group form
* When user leaves one or more required fields empty
* And user click button "Update"
* Then system does not save the data
* And user can view validation message "{Field Name} is required"

## Master Customer Group.3.3 : Successfully Update Customer Group <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user have permission "edit\_customer\_group"
* And user has updated the Customer Group data
* When user click button "Update"
* Then system successfully saves the updated data
* And user can view notification "Update Success"

## Master Customer Group.3.4 : View Updated Customer Group Data <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user successfully updates Customer Group data
* When user access the Customer Group index page
* Then user can view the latest updated data

## Master Customer Group.3.5 : Restrict Update Access <a href="#group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page" id="group-coa-1.1-create-master-group-chart-of-account-redirect-to-the-login-page"></a>

* Given user is logged in
* And user does not have permission "edit\_customer\_group"
* When user access the Customer Group details page
* Then user cannot view button "Edit"
