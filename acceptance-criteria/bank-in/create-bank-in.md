# Create Bank In

## BI.1.1 : Redirect to the login page

* `GIVEN` user visit `/bank-in` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## BI.1.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to create bank in
* When user type `/bank-in` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## BI.1.3 : The system displays the message "Bank account is required"

## BI.1.4 : The system displays the message "Payment form is required"

## BI.1.5 : The system displays the message "Account is required"

## BI.1.6 : The system displays the message "Amount is required"

## BI.1.7 : The system displays the message "Amount must be filled with data numbers"

## BI.1.8 : The system displays the message "Successfully created"

## Journal entry for bank in transaction
