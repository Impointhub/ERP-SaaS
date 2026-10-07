# Approval Payment Order

## PO.6.1 : User redirect to login page

* `GIVEN` user visit /`finance/point/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.6.2 : The system does not display the approval button

* Given the user on the page /`finance/point/payment-order`
* And the user already logged in.
* And the user don't have permission approval\_ payment order
* And the user have data "PO-001"
* When the user click "PO-001"

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

* Then user can't see the approval button.

<figure><img src="../../../.gitbook/assets/image (947).png" alt=""><figcaption></figcaption></figure>

## PO.6.3 : Payment order approval status becomes approved

* Given the user on the page /`finance/point/payment-order`
* And the user already logged in.
* And the user have permission approval\_ payment order
* And the user have data "PO-001"
* When user click "PO-001"

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

* When user click button "approve"

<figure><img src="../../../.gitbook/assets/image (409).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Successfully Approved"

<figure><img src="../../../.gitbook/assets/image (1043).png" alt=""><figcaption></figcaption></figure>

* And status approval form becomes approved

<figure><img src="../../../.gitbook/assets/image (411).png" alt=""><figcaption></figcaption></figure>
