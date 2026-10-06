# Edit Master Customer

## CUS.2.1 - User redirect to login page

* Given I am not logged in&#x20;
* When I open the page https://test.app.point.red/master/customer/1/edit&#x20;
* &#x20;Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/image (432).png" alt=""><figcaption></figcaption></figure>

## CUS.2.2 - Redirect to forbidden page

* Given I already logged in&#x20;
* &#x20;And I do not have permission to edit customer&#x20;
* When I open the page https://test.app.point.red/master/customer/1/edit&#x20;
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CUS.2.3 - Send notification name is required

* Given I already logged in&#x20;
* And I have permission to edit customer&#x20;
* &#x20;And I am on the page https://test.app.point.red/master/customer/1/edit&#x20;
* And the customer code CUS-1 cannot be changed&#x20;
* &#x20;When I leave empty column name&#x20;

<figure><img src="../../../.gitbook/assets/image (671).png" alt=""><figcaption></figcaption></figure>

* &#x20;And I click submit&#x20;

<figure><img src="../../../.gitbook/assets/image (670).png" alt=""><figcaption></figcaption></figure>

* Then the system sends notification "Name is required"

<figure><img src="../../../.gitbook/assets/image (669).png" alt=""><figcaption></figcaption></figure>

## CUS.2.4 - Display notification successfully update

* Given I already logged in&#x20;
* And I have permission to edit customer&#x20;
* And I am on the page https://test.app.point.red/master/customer/1/edit&#x20;
* When I type "Sumber Berkat Makmur Sejahtera" into column name&#x20;

<figure><img src="../../../.gitbook/assets/image (672).png" alt=""><figcaption></figcaption></figure>

* And I type "Sumberberkat@makmur.com" into column email&#x20;

<figure><img src="../../../.gitbook/assets/image (673).png" alt=""><figcaption></figcaption></figure>

* And I type "Jln musi no 21 Surabaya" into column address

<figure><img src="../../../.gitbook/assets/image (674).png" alt=""><figcaption></figcaption></figure>

* And I type "082842392398 " into column phone

<figure><img src="../../../.gitbook/assets/image (675).png" alt=""><figcaption></figcaption></figure>

* And I type "100.000" into column credit ceiling

<figure><img src="../../../.gitbook/assets/image (676).png" alt=""><figcaption></figcaption></figure>

* And I type "PIC Atas nama aini" into column notes&#x20;

<figure><img src="../../../.gitbook/assets/image (677).png" alt=""><figcaption></figcaption></figure>

* &#x20;And I click submit&#x20;

<figure><img src="../../../.gitbook/assets/image (678).png" alt=""><figcaption></figcaption></figure>

* &#x20;Then the system displays notification "Successfully updated"&#x20;

<figure><img src="../../../.gitbook/assets/image (679).png" alt=""><figcaption></figcaption></figure>

* &#x20;And the updated data is shown on the page https://test.app.point.red/master/customer/1/
