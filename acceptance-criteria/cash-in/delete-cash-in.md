# Delete Cash In

## CI.2.1 : Redirect to the login page

* `GIVEN` user visit `/cash-in` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## CI.2.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to delete cash in
* When user type `/cash-in` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CI.2.3 : The system displays the message "Password is required"

*

## CI.2.4 : The system displays the message "Payment form is required"

## CI.2.5 : The system displays the message "wrong password"

## CI.2.6 : The system displays the message "Successfully delete"

* Given user is logged in
* And user wants to delete cash in data
* And user has filled delete reason
* And user has entered password
* When user clicks delete button
* Then cash in data is deleted successfully

## Make a reverse journal entry for cash receipt transactions
