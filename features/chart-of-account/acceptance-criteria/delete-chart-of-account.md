# Delete Chart of Account

### COA3.1 redirect to the login page&#x20;

* Given user visit `/chart-of-accounts` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### COA3.2 redirect to the forbidden page&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user does not have permission to delete a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

### COA3.3.Displaying notification "can't delete, chart of accounts already has references"

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission delete the chart of account&#x20;
* And user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (986).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button "delete"

<figure><img src="../../../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Failed Delete, Unable to edit this Chart of Account\
  because it is already referenced by existing transactions or configurations."

<figure><img src="../../../.gitbook/assets/image (430).png" alt=""><figcaption></figcaption></figure>

### COA3.4 The system displays the message "This field is required"&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission delete the chart of accounts.&#x20;
* And user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (987).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button "delete".&#x20;

<figure><img src="../../../.gitbook/assets/image (169).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "password"

<figure><img src="../../../.gitbook/assets/image (170).png" alt=""><figcaption></figcaption></figure>

* And click button delete&#x20;

<figure><img src="../../../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "password is required"&#x20;

<figure><img src="../../../.gitbook/assets/image (172).png" alt=""><figcaption></figcaption></figure>

### COA3.5 Displays a wrong password notification&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission to delete the chart of accounts.&#x20;
* And password user for the account "Admin123!"
* And user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (988).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button "delete".&#x20;

<figure><img src="../../../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

* And user type  "Admin" into column password&#x20;

<figure><img src="../../../.gitbook/assets/image (173).png" alt=""><figcaption></figcaption></figure>

* And click button delete&#x20;

<figure><img src="../../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "wrong password"&#x20;

<figure><img src="../../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>

### COA3.6.The system displays the message "Successfully deleted"&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission to delete the chart of accounts.&#x20;
* And password user for the account "Admin123!"
* And user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (989).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button "delete".&#x20;

<figure><img src="../../../.gitbook/assets/image (169).png" alt=""><figcaption></figcaption></figure>

* And user type  "Admin123!" into column password&#x20;

<figure><img src="../../../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>

* And click button delete&#x20;

<figure><img src="../../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Success Delete chart of account"&#x20;

<figure><img src="../../../.gitbook/assets/image (177).png" alt=""><figcaption></figcaption></figure>
