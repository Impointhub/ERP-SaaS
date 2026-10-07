# List Chart of Account

### COA4.1 redirect to the login page

* Given user visit `/chart-of-accounts` url without signin
* Then user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

### COA4.2 redirect to the forbidden page

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user dont have permission to read a chart of accounts.
* When user type `/chart-of-accounts` url into browser
* Then user redirected to forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

### COA4.3 displays the message "you don't have any data yet"

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission to read chart of accounts.
* And user don't have data chart of accounts.
* Then user can view data notification "you don't have any data yet."

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

### COA4.4.Displays all chart of accounts data that has been entered.

* Given user is logged in

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

* And user have permission to read chart of accounts.
* And user have data chart account
* Then user can view all chart of account data that has been entered

<figure><img src="../../../.gitbook/assets/image (990).png" alt=""><figcaption></figcaption></figure>

* And chart of account data sort based on account number

<figure><img src="../../../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>
