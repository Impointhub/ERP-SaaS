# List Master Allocation

## ALO.5.1 : redirect to the login page

* `GIVEN` user visit url `/master/allocation` without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## ALO.5.2: redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to read allocation&#x20;
* When user type `/master/allocation` url into browser&#x20;
* Then the user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## ALO.5.3: displays the message "you don't have any data yet"

* Given the user on the page `/master/allocation/`&#x20;
* And the user already logged in.&#x20;
* And the user have permission to read allocation.&#x20;
* And the user dont have any data yet&#x20;
* When the user click modul "Allocation"

<figure><img src="../../../.gitbook/assets/image (502).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "You dont have any data yet"

<figure><img src="../../../.gitbook/assets/image (962).png" alt=""><figcaption></figcaption></figure>

## ALO.5.4: Displays all Allocation data that has been entered.

* Given the user on the page `/master/allocation/`&#x20;
* And the user already logged in.&#x20;
* And the user have permission read\_allocation&#x20;
* And the user have data "Project A"
* When the user click modul "Allocation"

<figure><img src="../../../.gitbook/assets/image (502).png" alt=""><figcaption></figcaption></figure>

* Then user can view data "Project A" on the list allocation&#x20;

<figure><img src="../../../.gitbook/assets/image (504).png" alt=""><figcaption></figcaption></figure>

