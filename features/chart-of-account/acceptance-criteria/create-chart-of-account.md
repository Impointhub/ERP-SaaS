# Create chart of account

### _COA1.1 redirect to the login page_

* Given user visit `/chart-of-accounts` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### COA1.2 redirect to the forbidden page

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And the user does not have permission to create a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>



### _COA1.3. The system displays the message "This field is required"_

* Given User is logged in&#x20;
* And user have permission "create\_chart\_of\_account"
* And the user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (978).png" alt=""><figcaption></figcaption></figure>

* When user click "Create COA"&#x20;

<figure><img src="../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "Main category"&#x20;

<figure><img src="../../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "Major group"

<figure><img src="../../../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

* And user type "1000-01" into column "Account number"&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI (2).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "Account Name"&#x20;

<figure><img src="../../../.gitbook/assets/image (121).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "Balance Normal"&#x20;

<figure><img src="../../../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

* And user click save COA&#x20;

<figure><img src="../../../.gitbook/assets/image (123).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Unable to save record, Please correct the errors highlighted below"

<figure><img src="../../../.gitbook/assets/image (124).png" alt=""><figcaption></figcaption></figure>

### COA1.4 The system displays the message "account number already exists"

* Given the user is logged in&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission "create\_chart\_of\_account"
* And user have data account number "1000-01"
* And the user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (979).png" alt=""><figcaption></figcaption></figure>

* When user click "Create COA"&#x20;

<figure><img src="../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

* And user click choosen main category "Asset"

<figure><img src="../../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

* And user click choosen major group "Current Asset"

<figure><img src="../../../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

* And user type "1000-01" into column Account number&#x20;

<figure><img src="../../../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure>

* And user type "piutang usaha" into column Account name&#x20;

<figure><img src="../../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

* And user click choosen balance normal "Debit"&#x20;

<figure><img src="../../../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure>

* And user click choose cashflow category "operating"

<figure><img src="../../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

* And column "is cash account" disable&#x20;

<figure><img src="../../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

* And user click "save coa"&#x20;

<figure><img src="../../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

* Then user can view error message "Unable to save record. please correct the errors highlighted below."

<figure><img src="../../../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>

### COA1.5. The system displays the message "Successfully created"&#x20;

* Given the user is logged in&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission "create\_chart\_of\_account"
* And the user on the list page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (980).png" alt=""><figcaption></figcaption></figure>

* When user click "Create COA"&#x20;

<figure><img src="../../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

* And user click choosen main category "Asset"

<figure><img src="../../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

* And user click choosen major group "Current Asset"

<figure><img src="../../../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

* And user type "1000-02" into column Account number.&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI (2).png" alt=""><figcaption></figcaption></figure>

* And user type "piutang usaha" into the column "Account name".&#x20;

<figure><img src="../../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

* And user click choosen balance normal "Debit".&#x20;

<figure><img src="../../../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

* And user click choosen cashflow category "operating"

<figure><img src="../../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

* And column "is cash account" disable&#x20;

<figure><img src="../../../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>

* And user click "save COA".&#x20;

<figure><img src="../../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Success create chart of account"

<figure><img src="../../../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure>

* And user redirect to list page.&#x20;

<figure><img src="../../../.gitbook/assets/image (981).png" alt=""><figcaption></figcaption></figure>
