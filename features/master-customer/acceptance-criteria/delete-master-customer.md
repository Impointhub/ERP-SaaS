# Delete Master Customer

## CUS.3.1 - User redirect to login page

* Given I am not logged in&#x20;
* &#x20;When I open the page https://test.app.point.red/master/customer/1/&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/image (432).png" alt=""><figcaption></figcaption></figure>

## CUS.3.2 - The user cannot see the delete button on the details page

* Given I already logged in&#x20;
* &#x20;And I do not have permission to delete customer&#x20;
* &#x20;When I open the page https://test.app.point.red/master/customer/1/&#x20;
* &#x20;Then I cannot see the delete button on the details page

<figure><img src="../../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

## CUS.3.3 - Cannot delete because the master customer record is referenced in other transactions

* Given I already logged in&#x20;
* And I have permission to delete customer&#x20;
* &#x20;And I am on the page https://test.app.point.red/master/customer/1/&#x20;
* And customer CUS-1 is referenced in other transactions
* When I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (682).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "This master customer record is referenced in other transactions and cannot be deleted"

<figure><img src="../../../.gitbook/assets/image (683).png" alt=""><figcaption></figcaption></figure>

## CUS.3.4 - Display message password is required

* &#x20;Given I already logged in&#x20;
* &#x20;And I have permission to delete customer&#x20;
* &#x20;And I am on the page https://test.app.point.red/master/customer/1/&#x20;
* &#x20;And customer CUS-1 is not referenced in any transaction&#x20;
* &#x20;When I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (682).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column password&#x20;

<figure><img src="../../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

* And I click OK&#x20;

<figure><img src="../../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Password is required"

<figure><img src="../../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>



## CUS.3.5 - Send notification wrong password

* Given I already logged in&#x20;
* And I have permission to delete customer&#x20;
* &#x20;And I am on the page https://test.app.point.red/master/customer/1/&#x20;
* &#x20;And customer CUS-1 is not referenced in any transaction&#x20;
* &#x20;When I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (682).png" alt=""><figcaption></figcaption></figure>

* &#x20;And I type wrong password&#x20;

<figure><img src="../../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* &#x20;And I click OK&#x20;

<figure><img src="../../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* &#x20;Then the system sends notification "Wrong password"

<figure><img src="../../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

## CUS.3.6 - Display notification successfully deleted

* Given I already logged in&#x20;
* And I have permission to delete customer&#x20;
* And I am on the page https://test.app.point.red/master/customer/1/&#x20;
* And customer CUS-1 is not referenced in any transaction&#x20;
* When I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

* And I type my correct password&#x20;

<figure><img src="../../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

* And I click OK&#x20;

<figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

* Then the system displays notification "Successfully deleted"&#x20;

<figure><img src="../../../.gitbook/assets/image (684).png" alt=""><figcaption></figcaption></figure>

* And customer CUS-1 is removed from the customer list
