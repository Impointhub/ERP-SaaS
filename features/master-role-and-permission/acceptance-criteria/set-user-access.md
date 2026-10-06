# Set User Access

## RSP.1 - Redirect to login page when user is not logged in

* Given I have not logged in
* When I access the page /master/role
* Then the system displays the message "Redirect to login page"

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## RSP.2 - Successfully set user access&#x20;

* Given I already logged in
* And I on the page /master/role
* When I click role name "ADMINISTRATOR 1" on the list page

<figure><img src="../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

* And I click button "Set User Access"

<figure><img src="../../../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>

* And I check the checkbox for user "MARTIEN,SYSTEM,KARTIKA"

<figure><img src="../../../.gitbook/assets/image (595).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Successfully Set role to user"

<figure><img src="../../../.gitbook/assets/image (645).png" alt=""><figcaption></figcaption></figure>

* And the system assigns role "ADMINISTRATOR 1" to user "MARTIEN,SYSTEM, KARTIKA"
