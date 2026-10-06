# Create Role

## RL.1 - Redirect to login page when user is not logged in

* Given I have not logged in
* When I access the page /master/role/create
* Then the system displays the message "Redirect to login page"

<figure><img src="../../../.gitbook/assets/image (210).png" alt=""><figcaption></figcaption></figure>

## RL.2 - Redirect to forbidden page when user has no permission to create role

* Given I already logged in
* And I do not have permission to create role
* When I type  /master/role/create into browser&#x20;
* Then the system displays the message "Redirect to forbidden page"

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## RL.3 - Column Name Is Required

* Given I already logged in
* And I have permission to create role
* And I on the page /master/role/create
* When I leave the "Name" field empty

<figure><img src="../../../.gitbook/assets/image (558).png" alt=""><figcaption></figcaption></figure>

* And I click submit the form

<figure><img src="../../../.gitbook/assets/image (557).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column Name Is Required"

<figure><img src="../../../.gitbook/assets/image (556).png" alt=""><figcaption></figcaption></figure>

* And I should remain on the create page&#x20;



## RL.4 - Column Name Is already exist

* Given I already logged in
* And I have permission to create role
* And I on the page /master/role/create
* When I type "ADMINISTRATOR 1" into column name

<figure><img src="../../../.gitbook/assets/image (559).png" alt=""><figcaption></figcaption></figure>

* And I click submit the form

<figure><img src="../../../.gitbook/assets/image (560).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column Name Is already exist"

<figure><img src="../../../.gitbook/assets/image (561).png" alt=""><figcaption></figcaption></figure>

* And I should remain on the create page&#x20;

## RL.5 - Successfully create role, redirect to list page

* Given I already logged in
* And I have permission to create role
* And I on the page /master/role/create
* When I type "ROLE BARU" into column name

<figure><img src="../../../.gitbook/assets/image (562).png" alt=""><figcaption></figcaption></figure>

* And I click submit the form

<figure><img src="../../../.gitbook/assets/image (564).png" alt=""><figcaption></figcaption></figure>

* Then the system succes creates the role
* And the system redirects the user to the list page

<figure><img src="../../../.gitbook/assets/image (565).png" alt=""><figcaption></figcaption></figure>
