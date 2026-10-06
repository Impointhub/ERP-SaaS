# Detail Role

## RDL.1 - Redirect to login page when user is not logged in

* Given I have not logged in
* When I access the page /master/role/1
* Then the system displays the message "Redirect to login page"

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## RDL.2 - Redirect to forbidden page when user has no permission to read role

* Given I already logged in
* And I do not have permission to read role
* When I access the page /master/role/1
* Then the system displays the message "Redirect to forbidden page"

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## RDL.3 - Successfully view role detail

* Given I already logged in
* And I have permission to read role
* When I access the page /master/role/1
* Then the system displays the message "Show detail data"
* And the user should see the detail data of "ADMINISTRATOR 1"

<figure><img src="../../../.gitbook/assets/image (588).png" alt=""><figcaption></figcaption></figure>
