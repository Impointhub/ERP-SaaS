# Detail Master Customer

## CUS.5.1 - User redirect to login page

* Given I am not logged in&#x20;
* When I open the page https://test.app.point.red/master/customer/1/&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/image (432).png" alt=""><figcaption></figcaption></figure>

## CUS.5.2 - Redirect to forbidden page

* Given I already logged in&#x20;
* &#x20;And I do not have permission to read customer&#x20;
* &#x20;When I type https://test.app.point.red/master/customer/1/ into browser
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CUS.5.3- Display detail data of customer

* Given I already logged in&#x20;
* And I have permission to read customer&#x20;
* &#x20;When I type the page https://test.app.point.red/master/customer/1/  into browser&#x20;
*   Then the system displays the detail data of customer CUS-1

    <figure><img src="../../../.gitbook/assets/image (680).png" alt=""><figcaption></figcaption></figure>



