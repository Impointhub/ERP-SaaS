# Delete Master Allocation

## ALO.3.1 : User redirect to login page

* `GIVEN` user visit url `/master/allocation/1` without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## ALO.3.2 : redirect to the forbidden page

* Given user is logged in
* And user on the page `/master/allocation/1`
* And user does not have permission to delete allocation
* When user click button delete

<figure><img src="../../../.gitbook/assets/image (100).png" alt=""><figcaption></figcaption></figure>

* Then user redirected to forbidden page

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## ALO.3.3 : The system Displays a notification "allocation cannot be deleted because the data is already referenced"

* Given user already logged in.
* And user on the page `/master/allocation/1`
* And the user already has permission for the delete\_allocation
* And the allocation data already have a reference
* When user click button "delete" on the detail page

<figure><img src="../../../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

* And the system display message is "allocation cannot be deleted because the data is already referenced."

<figure><img src="../../../.gitbook/assets/image (956).png" alt=""><figcaption></figcaption></figure>

## ALO.3.4 : The system displays the message "password is required"

* Given user already logged in
* And user on the page /master/allocation/1
* And user already has permission to delete the allocation.
* The data allocation does not have a transaction reference.
* When user click button "delete" on the detail page

<figure><img src="../../../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

* And the user leaves the password column empty.

<figure><img src="../../../.gitbook/assets/image (104).png" alt=""><figcaption></figcaption></figure>

* And user click button delete

<figure><img src="../../../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "This field is required"

<figure><img src="../../../.gitbook/assets/image (106).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the delete confirmation pop up

<figure><img src="../../../.gitbook/assets/image (107).png" alt=""><figcaption></figcaption></figure>

## ALO.3.5 : The system displaying notification "wrong password"

* Given the user on the page /master/allocation/1
* And the user already logged in.
* And the password of user "12345678"
* And the user already has permission for the delete\_allocation.
* And the allocation data doesn't have a reference.
* When user click button "delete" on the detail page

<figure><img src="../../../.gitbook/assets/image (957).png" alt=""><figcaption></figcaption></figure>

* And the user types "1234" into column "password" on the pop-up delete

<figure><img src="../../../.gitbook/assets/image (958).png" alt=""><figcaption></figcaption></figure>

* And the user click delete on the pop-up delete

<figure><img src="../../../.gitbook/assets/image (959).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "wrong password"

<figure><img src="../../../.gitbook/assets/image (960).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the pop-up delete

## ALO.3.6 : Display a notification "successfully deleted"

* Given the user on the page /master/allocation/1
* And the user already logged in.
* And the password of user "12345678"
* And the user already has permission for the delete\_payment\_order.
* And the payment order form does not yet have a reference.
* When user click button "delete" on the detail page

<figure><img src="../../../.gitbook/assets/image (109).png" alt=""><figcaption></figcaption></figure>

* And the user type "12345678" into the password column.

<figure><img src="../../../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

* And the user click "delete"

<figure><img src="../../../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

* Then The system displays the message "Successfully deleted"

<figure><img src="../../../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>

* And the allocation data will be deleted
* And user redirect to list page

<figure><img src="../../../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>
