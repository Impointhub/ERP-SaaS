# Delete Bank In

## BI.2.1 : Redirect to the login page

* `GIVEN` user visit `/bank-in` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## BI.2.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to delete bank in
* When user type `/bank-in` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## BI.2.3 : The system displays the message "Password is required"

## BI.2.4 : The system displays the message "Payment form is required"

## BI.2.5 : The system displays the message "wrong password"

## BI.2.6 : The system displays the message "Successfully delete"

## Make a reverse journal entry for cash receipt transactions
