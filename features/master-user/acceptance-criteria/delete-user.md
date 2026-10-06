# Delete User

DUSR.1&#x20;\- Redirect to forbidden page
-----------------------------------

* Given I already logged in&#x20;
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I dont have permission to delete user&#x20;
* When I click name "Aini Rahman"
* Then I can't view button delete&#x20;

OR&#x20;

* Given I already logged in&#x20;
* And I on the page /master/user/1/

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* And I dont have permission to delete user&#x20;
* Then I can't view button delete&#x20;

<figure><img src="../../../.gitbook/assets/image (549).png" alt=""><figcaption></figcaption></figure>

DUSR.2&#x20;\- Cannot delete because&#x20;the user already has&#x20;references.
-----------------

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user&#x20;
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (1010).png" alt=""><figcaption></figcaption></figure>

* And I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (1011).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Cannot delete because  &#x20;the user already has  &#x20;references".&#x20;

<figure><img src="../../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

DUSR.3&#x20;\- Password is required
-----------------------------

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user&#x20;
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column password&#x20;

<figure><img src="../../../.gitbook/assets/image (1012).png" alt=""><figcaption></figcaption></figure>

* And I click delete

<figure><img src="../../../.gitbook/assets/image (1014).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Password is required".&#x20;

<figure><img src="../../../.gitbook/assets/image (551).png" alt=""><figcaption></figcaption></figure>

DUSR.5&#x20;\- Wrong password
-----------------------

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user&#x20;
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

* And I type "12341234" into column password&#x20;

<figure><img src="../../../.gitbook/assets/image (1016).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Wrong Password".&#x20;

<figure><img src="../../../.gitbook/assets/image (552).png" alt=""><figcaption></figcaption></figure>

## DUSR.6 - Success Delete&#x20;

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user&#x20;
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (1017).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password&#x20;

<figure><img src="../../../.gitbook/assets/image (1018).png" alt=""><figcaption></figcaption></figure>

* And I click delete&#x20;

<figure><img src="../../../.gitbook/assets/image (1019).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Successfully deleted"

<figure><img src="../../../.gitbook/assets/image (553).png" alt=""><figcaption></figcaption></figure>
