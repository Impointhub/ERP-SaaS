# Edit Role

## RLE.1 - Redirect to login page when user is not logged in

* Given I have not logged in
* When I access the page /master/role/1/edit
* Then the system displays the message "Redirect to login page"

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## RLE.2 - Redirect to forbidden page when user has no permission to edit role

* Given I already logged in
* And I do not have permission to edit role
* And I on the page /master/role/1/edit
* When I click submit
* Then the system displays the message "Redirect to forbidden page"

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## RLE.3 - Column Name Is Required

* Given I already logged in
* And I have permission to edit role
* And I on the page /master/role/1/edit
* When I leave the "Name" field empty

<figure><img src="../../../.gitbook/assets/image (568).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (567).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column Name Is Required"

<figure><img src="../../../.gitbook/assets/image (566).png" alt=""><figcaption></figcaption></figure>

* And I should remain on the edit page&#x20;

## RLE.4 - Column Name Is already exist

* Given I already logged in
* And I have permission to edit role
* And I on the page /master/role/1/edit
* When I type "AUDIT KAS BESAR" into column name

<figure><img src="../../../.gitbook/assets/image (569).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (570).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column Name Is already exist"

<figure><img src="../../../.gitbook/assets/image (571).png" alt=""><figcaption></figcaption></figure>

* And the system does not update the role

## RLE.5 - Successfully update role, redirect to detail page

* Given I already logged in
* And I have permission to edit role
* And I on the page /master/role/1/edit
* When I type "ADMINISTRATOR SENIOR" into column name

<figure><img src="../../../.gitbook/assets/image (572).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (573).png" alt=""><figcaption></figcaption></figure>

* Then the system show notification success update role&#x20;
* And I redirects to detail page&#x20;

