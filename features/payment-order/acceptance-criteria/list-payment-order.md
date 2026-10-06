# List Payment Order

## PO.4.1 :  User redirect to login page

* `GIVEN` user visit `/finance/point/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.4.2 :  Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to list a payment order
* When user type `/finance/point/payment-order` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## PO.4.3 : Displays the message "You dont have any data yet"

* Given the user on the page `/finance/point/payment-order`
* And the user already logged in.&#x20;
* And the user have permission read\_permission payment order&#x20;
* And the user dont have any data yet&#x20;
* When the user click modul "Payment Order"

<figure><img src="../../../.gitbook/assets/image (403).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "You dont have any data yet"

<figure><img src="../../../.gitbook/assets/image (404).png" alt=""><figcaption></figcaption></figure>

## PO.4.4 : Displays all payment order data that has been entered.

* Given the user on the page `/finance/point/payment-order`
* And the user already logged in.&#x20;
* And the user have permission read\_permission payment order&#x20;
* And the user have data "PO-001"
* When the user click modul "Payment Order"

<figure><img src="../../../.gitbook/assets/image (403).png" alt=""><figcaption></figcaption></figure>

* Then user can view data "PO-001" on the list payment order&#x20;

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

* Data is sorted from newest to oldest date&#x20;

<figure><img src="../../../.gitbook/assets/image (406).png" alt=""><figcaption></figcaption></figure>
