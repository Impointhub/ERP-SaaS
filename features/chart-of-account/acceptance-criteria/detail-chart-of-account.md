# Detail Chart of Account

### COA5.1 redirect to the login page&#x20;

* Given user visit `/chart-of-accounts` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### COA5.2 redirect to the forbidden page&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user dont have permission to read a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

### COA5.3.Displays detail chart of account&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user  have permission to read a chart of accounts.
* And user on the list page chart of accounts&#x20;

<figure><img src="../../../.gitbook/assets/image (991).png" alt=""><figcaption></figcaption></figure>

* And user have account number "1000-02"

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* When user click "1000-02" on the column number&#x20;

<figure><img src="../../../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

* Then user can view detail page chart of account&#x20;

<figure><img src="../../../.gitbook/assets/image (992).png" alt=""><figcaption></figcaption></figure>
