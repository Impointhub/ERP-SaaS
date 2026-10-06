# Delete Payment Order

## PO.3.1 :  User redirect to login page

* `GIVEN` user visit `/finance/point/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.3.2 :  Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to delete a payment order
* When user type `/finance/point/payment-order`url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## PO.3.3 : Unable to delete this form because it is already used in another transaction

* Given the user on the page `/finance/point/payment-order/1`&#x20;
* And the user already logged in.&#x20;
* And the user already has permission for the delete\_payment\_order.&#x20;
* And the form already have a reference cash out / bank out&#x20;
* When user click button "delete" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (394).png" alt=""><figcaption></figcaption></figure>

* And the system display message is "Unable to delete this form because it is already used in another transaction."

<figure><img src="../../../.gitbook/assets/image (395).png" alt=""><figcaption></figcaption></figure>



* And the user should remain on the detail page&#x20;

## PO.3.4 : The system displays the message "This field is required"

* Given the user on the page `/finance/point/payment-order/1`&#x20;
* And the user already logged in.&#x20;
* And the user already has permission for the delete\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank transfer reference
* When user click button "delete" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (394).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty password column on the pop up delete&#x20;

<figure><img src="../../../.gitbook/assets/image (396).png" alt=""><figcaption></figcaption></figure>

* And the user click delete on the pop up delete&#x20;

<figure><img src="../../../.gitbook/assets/image (397).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "This field is required"&#x20;

<figure><img src="../../../.gitbook/assets/image (398).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the pop up delete&#x20;

## PO.3.5 : Displays a wrong password notification

* Given the user on the page `/finance/point/payment-order/1`&#x20;
* And the user already logged in.&#x20;
* And the password of user "12345678"
* And the user already has permission for the delete\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank transfer reference
* When user click button "delete" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (394).png" alt=""><figcaption></figcaption></figure>

* And the user type "1234" into column "password" on the pop up delete&#x20;

<figure><img src="../../../.gitbook/assets/image (399).png" alt=""><figcaption></figcaption></figure>

* And the user click delete on the pop up delete&#x20;

<figure><img src="../../../.gitbook/assets/image (401).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "wrong password"&#x20;

<figure><img src="../../../.gitbook/assets/image (402).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the pop up delete&#x20;

## PO.3.6 -The system displays the message "Successfully deleted"

* Given the user on the page `/finance/point/payment-order/1`&#x20;
* And the user already logged in.&#x20;
* And the password of user "12345678"
* And the user already has permission for the delete\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank transfer reference
* When user click button "delete" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (394).png" alt=""><figcaption></figcaption></figure>

<br>
----

* And the user type "12345678" into the password column.

<figure><img src="../../../.gitbook/assets/image (417).png" alt=""><figcaption></figcaption></figure>

* And the user click "delete"&#x20;

<figure><img src="../../../.gitbook/assets/image (418).png" alt=""><figcaption></figcaption></figure>

* Then The system displays the message "Successfully deleted"

<figure><img src="../../../.gitbook/assets/image (1046).png" alt=""><figcaption></figcaption></figure>

* And the payment order status becomes "Cancelled".&#x20;

<figure><img src="../../../.gitbook/assets/image (421).png" alt=""><figcaption></figcaption></figure>

* And the payment order cannot serve as a reference for a cash-out or bank-out transaction.
* And the user can't view button delete&#x20;

