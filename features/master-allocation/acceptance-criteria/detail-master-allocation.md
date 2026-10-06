# Detail Master Allocation

## ALO.4.1: User redirect to login page

* `GIVEN` user visit `/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## ALO.4.2: redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to read allocation&#x20;
* When user type [https://test.app.point.red/master/allocation/1](https://test.app.point.red/master/allocation/1)  url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## ALO.4.3: The system show detail allocation

* Given the user on the page `/master/allocation/1`
* And the user already logged in.&#x20;
* And the user have permission read\_allocation&#x20;
* And the user have data allocation "Project A"
* When the user click "Project A"

<figure><img src="../../../.gitbook/assets/image (501).png" alt=""><figcaption></figcaption></figure>

* Then user can data redirect to detail Allocation&#x20;

<figure><img src="../../../.gitbook/assets/image (500).png" alt=""><figcaption></figcaption></figure>
