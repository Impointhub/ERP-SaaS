# List Chart of Account

### COA4.1 redirect to the login page&#x20;

* Given user visit `/chart-of-accounts` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### COA4.2 redirect to the forbidden page&#x20;

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user dont have permission to read a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

### COA4.3 displays the message "you don't have any data yet"&#x20;

* Given user is logged in&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission to read chart of accounts.&#x20;
* And user don't have data chart of accounts.&#x20;
* Then user can view data notification "you don't have any data yet."&#x20;

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

### COA4.4.Displays all chart of accounts data that has been entered.

* Given user is logged in&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission to read chart of accounts.&#x20;
* And user have data chart account&#x20;
* Then user can view all chart of account data that has been entered&#x20;

<figure><img src="../../../.gitbook/assets/image (990).png" alt=""><figcaption></figcaption></figure>

* And chart of account data sort based on account number&#x20;

<figure><img src="../../../.gitbook/assets/image (158).png" alt=""><figcaption></figcaption></figure>
