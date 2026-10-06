# Set Permission Access

## RSU.1 - Redirect to login page when user is not logged in

* Given I have not logged in
* When I access the page /master/role
* Then the system displays the message "Redirect to login page"

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## RSU.2 - Successfully set permission access&#x20;

* Given I already logged in
* And I on the page /master/role
* When I click role name "ADMINISTRATOR 1" on the list page

<figure><img src="../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

* And I click button "Set Permission"

<figure><img src="../../../.gitbook/assets/image (589).png" alt=""><figcaption></figcaption></figure>

* And I check the checkbox permission for role "MENU ACCOUNTING"

<figure><img src="../../../.gitbook/assets/image (591).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Successfully Set permission "

<figure><img src="../../../.gitbook/assets/image (644).png" alt=""><figcaption></figcaption></figure>

* And the system saves the selected permission for role "ADMINISTRATOR 1"
