# Detail Bank In

## BI.4.1 : Redirect to the login page

* `GIVEN` user visit `/bank-in` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## BI.4.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to detail bank in
* When user type `/bank-in` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## BI.4.2 : The system display detail of bank in

* Given user is logged in
* And user has permission to view bank in
* And bank in data already exists
* When user clicks form number from bank in list
* Then user can see bank in details
