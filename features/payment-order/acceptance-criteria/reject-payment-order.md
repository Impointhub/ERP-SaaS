# Reject Payment Order

## PO.7.1 :  User redirect to login page

* `GIVEN` user visit /`finance/point/payment-order`  url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.7.2 :  The system does not display the approval button

* Given the user on the page /`finance/point/payment-order`&#x20;
* And the user already logged in.&#x20;
* And the user don't have permission approval\_ payment order&#x20;
* And the user have data "PO-001"

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

* Then user can't see button approval&#x20;

<figure><img src="../../../.gitbook/assets/image (951).png" alt=""><figcaption></figcaption></figure>

## PO.7.3 : Payment order approval status becomes rejected

* Given the user on the page /`finance/point/payment-order`&#x20;
* And the user already logged in.&#x20;
* And the user have permission approval\_ payment order&#x20;
* And the user have data "PO-001"
* When the user click data "PO-001"

<figure><img src="../../../.gitbook/assets/image (405).png" alt=""><figcaption></figcaption></figure>

* And the user type "Biaya Terlalu Besar "  into column "Approval Notes"

<figure><img src="../../../.gitbook/assets/image (950).png" alt=""><figcaption></figcaption></figure>

* And the user click button "Reject"&#x20;

<figure><img src="../../../.gitbook/assets/image (412).png" alt=""><figcaption></figcaption></figure>





* Then user can view notification "Success Rejected"&#x20;

<figure><img src="../../../.gitbook/assets/image (1044).png" alt=""><figcaption></figcaption></figure>

* And status approval form becomes rejected.&#x20;

<figure><img src="../../../.gitbook/assets/image (415).png" alt=""><figcaption></figcaption></figure>

* And reason reject show on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (416).png" alt=""><figcaption></figcaption></figure>
