# List Cash In

## CI.3.1 : Redirect to the login page

* `GIVEN` user visit `/cash-in` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## CI.3.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to list cash in
* When user type `/cash-in` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CI.3.3 : Displays the message "You don't have any data yet"

## CI.3.4 : Displays cash in data that has been input by the user

* Given user is logged in
* And user has permission to view cash in
* And cash in data already exists
* When user clicks form number from cash in list
* Then user can see cash in details
