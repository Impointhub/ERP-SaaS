# List Master group chart of account

## Group-COA 4.1 : Redirect to the login page

* `GIVEN` user visit `/chart-of-accounts` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## Group-COA 4.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to group a chart of accounts.
* When user type `/chart-of-accounts` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## Group-COA.4-3 : displays the message "you don't have any data yet."

* Given user is logged in
* And the user has permission to read the chart of accounts.&#x20;
* And users don't have data chart of accounts.&#x20;
* Then the user can view the data notification "You don't have any data yet."&#x20;

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

## Group-COA-4.4 : Displays all group chart of accounts data that have been entered.

* Given user is logged in
* And the user has permission to read the chart of accounts.&#x20;
* And users have group chart of account&#x20;
* Then the user can view the data have been entered&#x20;

<figure><img src="../../../.gitbook/assets/image (231).png" alt=""><figcaption></figcaption></figure>
