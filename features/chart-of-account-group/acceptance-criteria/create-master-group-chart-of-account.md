# Create- Master group chart of account

### Group-COA-1.1 :  Redirect to the login page

* `GIVEN` user visit `/chart-of-accounts` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### Group-COA-1.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to create a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

### Group-COA-1.3 : The system displays the message "{Column\_name} is required"

* Given user is logged in&#x20;
* And user have permission "create\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset"&#x20;
* And user already have parent group "Cash and Bank"
* When the user click button (+) on folder icon &#x20;
* And user leave empty column group code&#x20;
* And user leave empty column group name&#x20;
* And user click button  "save"&#x20;
* Then user can view the notification "{column\_name} is required".&#x20;

<figure><img src="../../../.gitbook/assets/image (188).png" alt=""><figcaption></figcaption></figure>



### Group-COA-1.4: The system displays the message "Group already exists"

* Given user is logged in&#x20;
* And user have permission "create\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset"&#x20;
* And user already have parent group "Cash and Bank"
* And user already have folder with code "101"
* When the user click button (+) on folder icon &#x20;
* And user type "101" into column "Group code"
* And user type "Ganesha park residence" into column "Group Name"
* And user click button  "save"&#x20;
* Then user can view the notification "{column\_name} is already exist"&#x20;

<figure><img src="../../../.gitbook/assets/image (190).png" alt=""><figcaption></figcaption></figure>

### Group-COA-1.5 : The system displays the message "Successfully created group"

* Given user is logged in&#x20;
* And user have permission "create\_chart\_of\_account"
* And the user on the list page chart of account&#x20;
* And user already have major group "current asset"&#x20;
* And user already have parent group "Cash and Bank"
* And user already have folder with code "101"
* When the user click button (+) on folder icon &#x20;
* And user type "101" into column "Group code"
* And user type "Ganesha park residence" into column "Group Name"
* And user click button  "save"&#x20;

<figure><img src="../../../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>

* Then user can view the notification "Successfully created"

<figure><img src="../../../.gitbook/assets/image (192).png" alt=""><figcaption></figcaption></figure>

* And user redirect to list page group chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (193).png" alt=""><figcaption></figcaption></figure>



