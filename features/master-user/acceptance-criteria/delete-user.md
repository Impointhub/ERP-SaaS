# Delete User

## DUSR.1 - Redirect to forbidden page

* Given I already logged in
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I dont have permission to delete user
* When I click name "Aini Rahman"
* Then I can't view button delete

OR

* Given I already logged in
* And I on the page /master/user/1/

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* And I dont have permission to delete user
* Then I can't view button delete

<figure><img src="../../../.gitbook/assets/image (549).png" alt=""><figcaption></figcaption></figure>

## DUSR.2 - Cannot delete because the user already has references.

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (1009).png" alt=""><figcaption></figcaption></figure>

* And I click delete

<figure><img src="../../../.gitbook/assets/image (1011).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Cannot delete because the user already has references".

<figure><img src="../../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

## DUSR.3 - Password is required

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column password

<figure><img src="../../../.gitbook/assets/image (1012).png" alt=""><figcaption></figcaption></figure>

* And I click delete

<figure><img src="../../../.gitbook/assets/image (1013).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Password is required".

<figure><img src="../../../.gitbook/assets/image (551).png" alt=""><figcaption></figcaption></figure>

## DUSR.5 - Wrong password

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I click delete

<figure><img src="../../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

* And I type "12341234" into column password

<figure><img src="../../../.gitbook/assets/image (1016).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Wrong Password".

<figure><img src="../../../.gitbook/assets/image (552).png" alt=""><figcaption></figcaption></figure>

## DUSR.6 - Success Delete

* Given I already logged in as "admin"
* And My password acccount "Admin123"
* And I on the page /master/user
* And I already have data user "Aini Rahman"
* And I have permission to delete user
* When I click name "Aini Rahman"

<figure><img src="../../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

* And I click delete

<figure><img src="../../../.gitbook/assets/image (1017).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (1018).png" alt=""><figcaption></figcaption></figure>

* And I click delete

<figure><img src="../../../.gitbook/assets/image (1019).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Successfully deleted"

<figure><img src="../../../.gitbook/assets/image (553).png" alt=""><figcaption></figcaption></figure>
