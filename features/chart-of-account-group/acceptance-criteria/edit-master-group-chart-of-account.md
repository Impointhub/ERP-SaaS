# Edit- Master group chart of account

## Group-COA 2.1 : redirect to the login page

* `GIVEN` user visit `/chart-of-accounts` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## Group-COA 2.2 : redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to edit a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## Group-COA 2.3 : Only the group name column can be edited.

* Given user is logged in&#x20;
* And user have permission "edit\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset"&#x20;
* And user already have parent group "Cash and Bank"
* And the coa group "gpr01" already have transaction reference
* And user already have folder with "gpr01"
* And user click folder "gpr01"
* And user click button "Edit group"

<figure><img src="../../../.gitbook/assets/image (196).png" alt=""><figcaption></figcaption></figure>

* Then user redirect to edit form&#x20;
* And column "group code" should be disable

<figure><img src="../../../.gitbook/assets/image (194).png" alt=""><figcaption></figcaption></figure>

## Group-COA 2.4 : The system displays the message "This field is required."

* Given user is logged in&#x20;
* And user have permission "edit\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset".&#x20;
* And user already have parent group "Cash and Bank"
* When the user click button "edit"

<figure><img src="../../../.gitbook/assets/image (196).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column group code.&#x20;

<figure><img src="../../../.gitbook/assets/image (189).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column group name&#x20;

<figure><img src="../../../.gitbook/assets/image (189).png" alt=""><figcaption></figcaption></figure>

* And user click the button "update".&#x20;

<figure><img src="../../../.gitbook/assets/image (197).png" alt=""><figcaption></figcaption></figure>

* Then the user can view the notification "{column\_name} is required".&#x20;

<figure><img src="../../../.gitbook/assets/image (198).png" alt=""><figcaption></figcaption></figure>

## Group-COA 2.5 : Displays the error message "this fieled\_should be\_unique"

* Given user is logged in&#x20;
* And user have permission "edit\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset".&#x20;
* And user already have parent group "Cash and Bank"
* When the user click button "edit"
* And user type "101" into column "Group code"

<figure><img src="../../../.gitbook/assets/image (199).png" alt=""><figcaption></figcaption></figure>



* And user type "Ganesha park residence" into column "Group Name"

<figure><img src="../../../.gitbook/assets/image (200).png" alt=""><figcaption></figcaption></figure>

* And user click button  "update"&#x20;

<figure><img src="../../../.gitbook/assets/image (201).png" alt=""><figcaption></figcaption></figure>

* Then user can view the notification "{column\_name} is already exist"&#x20;

<figure><img src="../../../.gitbook/assets/image (202).png" alt=""><figcaption></figcaption></figure>

## Group-COA 2-6 : The system displays the message "Successfully updated"

* Given user is logged in&#x20;
* And user have permission "create\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset"&#x20;
* And user already have parent group "Cash and Bank"
* And user already have folder with code "101"
* When user click group "101"
* And user click button "edit"&#x20;
* And user type "group01" into column "Group code"

<figure><img src="../../../.gitbook/assets/image (203).png" alt=""><figcaption></figcaption></figure>

* And user type "Ganesha park residence" into column "Group Name"

<figure><img src="../../../.gitbook/assets/image (204).png" alt=""><figcaption></figcaption></figure>

* And user click the button "update".&#x20;

<figure><img src="../../../.gitbook/assets/image (205).png" alt=""><figcaption></figcaption></figure>

* Then user redirect to list page&#x20;

<figure><img src="../../../.gitbook/assets/image (207).png" alt=""><figcaption></figcaption></figure>

* And user can view notification "Successfully updated"
