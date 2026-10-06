# Create Cash Out

## CO.1.1 : Redirect to the login page

* `GIVEN` user visit `/cash-out` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## CO.1.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to create cash out
* When user type `/cash-out` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CO.1.3 : Redirect to the forbidden page
