# Edit User

## UMSR.1 - Redirect to login page&#x20;

* Given I am not logged in
* When I access /master/user/create
* Then the system redirects to the login page

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## UMSR.2 - Redirect to forbidden page&#x20;

* Given I already logged in &#x20;
* And I dont have permission to edit user&#x20;
* When I access the page /master/user/1
* Then I redirect to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

## UMSR.3 - Role is required

* Given I already logged in&#x20;
* And I have permission to edit user&#x20;
* When I access the page /master/user/1/edit

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column role

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

* And I click save&#x20;

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Role is required"

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

## UMSR.4. Successfully Updated user

* Given I already logged in&#x20;
* And I have permission to edit user&#x20;
* When I access the page /master/user/1/edit

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* And I select "Admin" into column role&#x20;

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

* And I click save&#x20;

<figure><img src="../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

* Then I redirect to detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (555).png" alt=""><figcaption></figcaption></figure>

* And I can view notification "Successfully Updated user"

<figure><img src="../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>
