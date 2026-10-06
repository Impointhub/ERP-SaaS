# Detail User

DSR.1&#x20;\- Redirect to&#x20;login page
----------------

* Given I already logged in
* And I have permission to read user&#x20;
* When I access the page /master/user/1
* Then I redirect to login page&#x20;

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

DSR.2&#x20;\- Redirect to&#x20;forbidden page
--------------------

* Given I already logged in &#x20;
* And I dont have permission to read user&#x20;
* When I access the page /master/user/1
* Then I redirect to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

DSR.3&#x20;\- Users can view detail&#x20;data of user data
-----------------------

* Given I already logged in&#x20;
* And I have permission to read user&#x20;
* When I access the page /master/user/1
* Then the user should see the detail data of user "1"

<figure><img src="../../../.gitbook/assets/image (548).png" alt=""><figcaption></figcaption></figure>
