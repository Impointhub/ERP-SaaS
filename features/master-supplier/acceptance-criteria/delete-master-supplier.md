# Delete Master Supplier

## DSP.1 - Redirect to login page

* Given I have not logged in
* When I open the page /master/contact/supplier
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## DSP.2 - User cannot see delete button

* Given I already logged in
* And I do not have permission to delete supplier
* When I open the page /master/contact/supplier/1
* Then the system does not display the delete button

<figure><img src="../../../.gitbook/assets/image (1021).png" alt=""><figcaption></figcaption></figure>

DSP.3&#x20;\- Display notification&#x20;"Can't deleted&#x20;supplier, because is referenced"
--------------------------------------

* Given I already logged in&#x20;
* And I have permission to delete supplier&#x20;
* And I on the page /master/contact/supplier/1
* When I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Can't deleted  &#x20;supplier, because is referenced"&#x20;

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

## DSP.4 - Password is required

* Given I already logged in
* And I have permission to delete supplier
* And I on the page /master/contact/supplier/1
* When I click delete

<figure><img src="../../../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

* And I leave the password field empty

<figure><img src="../../../.gitbook/assets/image (632).png" alt=""><figcaption></figcaption></figure>

* And I click OK

<figure><img src="../../../.gitbook/assets/image (634).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Password is required"

<figure><img src="../../../.gitbook/assets/image (633).png" alt=""><figcaption></figcaption></figure>

## DSP.5 - Wrong password

* Given I already logged in
* And I have permission to delete supplier
* And I on the page /master/contact/supplier/1
* And I click delete

<figure><img src="../../../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

* When I type an incorrect password into the password field

<figure><img src="../../../.gitbook/assets/image (636).png" alt=""><figcaption></figcaption></figure>



* And I click OK

<figure><img src="../../../.gitbook/assets/image (637).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Wrong password"

<figure><img src="../../../.gitbook/assets/image (638).png" alt=""><figcaption></figcaption></figure>

## DSP.6 - Show notification "Success delete" and redirect to list page

* Given I already logged in
* And I have permission to delete supplier
* And I on the page /master/contact/supplier/1
* And I click delete

<figure><img src="../../../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

* When I type my correct password into the password field

<figure><img src="../../../.gitbook/assets/image (639).png" alt=""><figcaption></figcaption></figure>

* And I click OK

<figure><img src="../../../.gitbook/assets/image (640).png" alt=""><figcaption></figcaption></figure>

* Then the system deletes the supplier
* And the system displays the message "Success delete"
* And the system redirects me to the list page

<figure><img src="../../../.gitbook/assets/image (641).png" alt=""><figcaption></figcaption></figure>
