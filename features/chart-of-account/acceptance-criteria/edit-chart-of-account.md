# Edit Chart of Account

### COA2.1 redirect to the login page

* Given user visit `/chart-of-accounts` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### COA2.2 redirect to the forbidden page

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And the user does not have permission to edit a chart of accounts.
* When user type `/chart-of-accounts` url into browser
* Then user redirected to forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

### COA2.3.Displaying notification "can't edit, chart of accounts already has references"

* Given the user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission "edit\_chart\_of\_account"
* And the user on the list page chart of account

<figure><img src="../../../.gitbook/assets/image (982).png" alt=""><figcaption></figcaption></figure>

* And account 1000-01 already has a reference.
* And the user clicks the account number "1000-01"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button update

<figure><img src="../../../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Failed Update, Unable to edit this Chart of Account\
  because it is already referenced by existing transactions or configurations."

<figure><img src="../../../.gitbook/assets/image (141).png" alt=""><figcaption></figcaption></figure>

### COA2.4 The system displays the message "This field is required"

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission "edit\_chart\_of\_account"
* And user on the list page chart of account

<figure><img src="../../../.gitbook/assets/image (983).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button update

<figure><img src="../../../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "main category"

<figure><img src="../../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "major group"

<figure><img src="../../../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

* And user type "1000-02" into column account number

<figure><img src="../../../.gitbook/assets/image (160).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "Account name"

<figure><img src="../../../.gitbook/assets/image (121).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "balance normal"

<figure><img src="../../../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "cashflow category"

<figure><img src="../../../.gitbook/assets/image (161).png" alt=""><figcaption></figcaption></figure>

* And user toggle checkbox "is cash account"

<figure><img src="../../../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>

* And user click save coa

<figure><img src="../../../.gitbook/assets/image (163).png" alt=""><figcaption></figcaption></figure>

* Then I can view "Unable to save record, Please correct the errors highlighted below"

### COA2.5 The system displays the message "account number already exists"

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission "edit\_chart\_of\_account"
* And user on the list page chart of account

<figure><img src="../../../.gitbook/assets/image (983).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button update

<figure><img src="../../../.gitbook/assets/image (159).png" alt=""><figcaption></figcaption></figure>

* And I choosen main category "Asset".

<figure><img src="../../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

* And I choosen major group "Current Asset"

<figure><img src="../../../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

* And I type "1000-01" into column "Account Number"

<figure><img src="../../../.gitbook/assets/image (180).png" alt=""><figcaption></figcaption></figure>

* And I type "Sewa Dibayar Dimuka" into column "Account Name"

<figure><img src="../../../.gitbook/assets/image (180).png" alt=""><figcaption></figcaption></figure>

* And I choosen balance normal "Debit"

<figure><img src="../../../.gitbook/assets/image (182).png" alt=""><figcaption></figcaption></figure>

* And I choosen cashflow category "operating"

<figure><img src="../../../.gitbook/assets/image (183).png" alt=""><figcaption></figcaption></figure>

* And Cash account disable

<figure><img src="../../../.gitbook/assets/image (184).png" alt=""><figcaption></figcaption></figure>

* And I click save coa

<figure><img src="../../../.gitbook/assets/image (186).png" alt=""><figcaption></figcaption></figure>

* Then I should view notification "Unable to save record, Please correct the errors highlighted below"

<figure><img src="../../../.gitbook/assets/image (187).png" alt=""><figcaption></figcaption></figure>

### COA2.6.The system displays the message "Successfully updated"

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission "edit\_chart\_of\_account"
* And user on the list page chart of account

<figure><img src="../../../.gitbook/assets/image (985).png" alt=""><figcaption></figcaption></figure>

* When user click account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* And user click button update

<figure><img src="../../../.gitbook/assets/image (179).png" alt=""><figcaption></figcaption></figure>

* And I choosen main category "Asset".

<figure><img src="../../../.gitbook/assets/image (125).png" alt=""><figcaption></figcaption></figure>

* And I choosen major group "Current Asset"

<figure><img src="../../../.gitbook/assets/image (126).png" alt=""><figcaption></figcaption></figure>

* And I type "1000-02" into column "Account Number"

<figure><img src="../../../.gitbook/assets/image (993).png" alt=""><figcaption></figcaption></figure>

* And I type "Sewa Dibayar Dimuka" into column "Account Name"

<figure><img src="../../../.gitbook/assets/image (994).png" alt=""><figcaption></figcaption></figure>

* And I choosen balance normal "Debit"

<figure><img src="../../../.gitbook/assets/image (995).png" alt=""><figcaption></figcaption></figure>

* And I choosen cashflow category "operating"

<figure><img src="../../../.gitbook/assets/image (996).png" alt=""><figcaption></figcaption></figure>

* And Cash account disable

<figure><img src="../../../.gitbook/assets/image (997).png" alt=""><figcaption></figcaption></figure>

* And I click save coa

<figure><img src="../../../.gitbook/assets/image (998).png" alt=""><figcaption></figcaption></figure>

* Then I should view notification "Success update chart of account"

<figure><img src="../../../.gitbook/assets/image (999).png" alt=""><figcaption></figcaption></figure>

* And I redirect to list page
