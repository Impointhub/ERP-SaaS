# Delete Role

## RLD.1 - Redirect to login page when user is not logged in

* Given I have not logged in
* When I access the page /master/role/
* Then the system displays the message "Redirect to login page"

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## RLD.2 - Delete button is hidden when user has no permission to delete role

* Given I already logged in
* And I do not have permission to delete role
* When I on the page /master/role/
* Then the user should not see the delete button on the role list

<figure><img src="../../../.gitbook/assets/image (574).png" alt=""><figcaption></figcaption></figure>

## RLD.3 - Password is required

* Given I already logged in
* And I have permission to delete role
* And I on the page /master/role/
* When I click role name "ADMINISTRATOR 1" on the list page

<figure><img src="../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

* And I click button "Delete"

<figure><img src="../../../.gitbook/assets/image (576).png" alt=""><figcaption></figcaption></figure>

* And I leave the "password" field empty

<figure><img src="../../../.gitbook/assets/image (577).png" alt=""><figcaption></figcaption></figure>

* And I click "OK"

<figure><img src="../../../.gitbook/assets/image (578).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Password is required"

<figure><img src="../../../.gitbook/assets/image (579).png" alt=""><figcaption></figcaption></figure>

* And the system does not delete the role

## RLD.4 - Wrong password

* Given I already logged in
* And I have permission to delete role
* And password for my account "admin123"
* And I on the page /master/role/
* When I click role name "ADMINISTRATOR 1" on the list page

<figure><img src="../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

* And I click button "Delete"

<figure><img src="../../../.gitbook/assets/image (576).png" alt=""><figcaption></figcaption></figure>

* And I type "wrongpass" into column password

<figure><img src="../../../.gitbook/assets/image (580).png" alt=""><figcaption></figcaption></figure>

* And I click "OK"

<figure><img src="../../../.gitbook/assets/image (581).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Wrong password"

<figure><img src="../../../.gitbook/assets/image (582).png" alt=""><figcaption></figcaption></figure>

* And the system does not delete the role
* And I should remain on the pop up delete

## RLD.5 - Successfully delete role, redirect to list page

* Given I already logged in
* And I have permission to delete role
* And I on the page /master/role/
* When I click role name "ADMINISTRATOR 1" on the list page

<figure><img src="../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

* And I click button "Delete"

<figure><img src="../../../.gitbook/assets/image (576).png" alt=""><figcaption></figcaption></figure>

* And I type "admin123" into column password

<figure><img src="../../../.gitbook/assets/image (580).png" alt=""><figcaption></figcaption></figure>

* And I click "OK"

<figure><img src="../../../.gitbook/assets/image (581).png" alt=""><figcaption></figcaption></figure>

* Then the system display notification "successfully deleted"

<figure><img src="../../../.gitbook/assets/image (583).png" alt=""><figcaption></figcaption></figure>

* And the system redirects the user to the list page

<figure><img src="../../../.gitbook/assets/image (585).png" alt=""><figcaption></figcaption></figure>
