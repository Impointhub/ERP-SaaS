# List Master Customer

## CUS.4.1 - User redirect to login page

* Given I am not logged in&#x20;
* &#x20;When I open the page https://test.app.point.red/master/customer&#x20;
* &#x20;Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/image (432).png" alt=""><figcaption></figcaption></figure>

## CUS.4.2 - Redirect to forbidden page

* Given I already logged in&#x20;
* &#x20;And I do not have permission to read customer&#x20;
* When I type the page https://test.app.point.red/master/customer into browser&#x20;
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CUS.4.3 - Displaying all the data that has been entered

* Given I already logged in&#x20;
* And I have permission to read customer&#x20;
* When I type https://test.app.point.red/master/customer&#x20;
* Then the system displays all the customer data that has been entered

<figure><img src="../../../.gitbook/assets/image (681).png" alt=""><figcaption></figcaption></figure>
