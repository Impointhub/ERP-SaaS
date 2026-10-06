# Read Payment Order

## PO.5.1 :  User redirect to login page

* `GIVEN` user visit `/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.5.2 :  Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to read a payment order
* When user type `finance/point/payment-order/1` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## PO.5.3 : Displays detail of payment order

* Given the user on the page finance/point/payment-order
* And the user already logged in.&#x20;
* And the user have permission read\_permission payment order&#x20;
* And the user have data "PO-001"
* When the user click "PO-001"

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

* Then user can data redirect to detail page payment order&#x20;

<figure><img src="../../../.gitbook/assets/image (1029).png" alt=""><figcaption></figcaption></figure>
