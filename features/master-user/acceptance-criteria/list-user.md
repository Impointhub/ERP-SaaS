# List User

LUSR.1&#x20;\- Redirect to login page&#x20;
-------------------------------------

* Given I am not logged in&#x20;
* When I access the page /master/user/
* Then I redirect to login page&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

LUSR.2&#x20;\- Redirect to&#x20;forbidden page
--------------------

* Given I already logged in
* And I do not have permission to read user&#x20;
* When I access the page /master/user/
* Then the system displays the message "Redirect to forbidden page"

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

LUSR.3&#x20;\- Users can view detail&#x20;data of user data
-----------------------

* Given I already logged in
* And I have permission to read user&#x20;
* And I have data user with name "martien" on the list page
* When I access the page /master/user/
* Then the user should see the list of users on the page

<figure><img src="../../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>
