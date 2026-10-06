# Reset Password

## 2.1.The system displays message "The password field is required"

* `GIVEN` user receive an email
* `WHEN` user click button "reset-password"

<figure><img src="../../.gitbook/assets/image (448).png" alt=""><figcaption></figcaption></figure>

* And  user click button "reset-password"

<figure><img src="../../.gitbook/assets/image (451).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "The password field is required."

<figure><img src="../../.gitbook/assets/image (452).png" alt=""><figcaption></figcaption></figure>

## 2.2. The system display message : "password not strong enough" <a href="#id-1-6-f2-password-reset-fails-when-password-is-not-strong-enough" id="id-1-6-f2-password-reset-fails-when-password-is-not-strong-enough"></a>

* `GIVEN` user receive an email
* `WHEN` user click button "reset-password

<figure><img src="../../.gitbook/assets/image (448).png" alt=""><figcaption></figcaption></figure>

* AND user type "newpass" into input "new-password"

<figure><img src="../../.gitbook/assets/image (453).png" alt=""><figcaption></figcaption></figure>

* AND user type "newpass" into input "password-confirmation"

<figure><img src="../../.gitbook/assets/image (454).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "Use at least 8 characters".

<figure><img src="../../.gitbook/assets/image (457).png" alt=""><figcaption></figcaption></figure>

*   `AND` user see "Contain at least one uppercase letter".

    <figure><img src="../../.gitbook/assets/image (458).png" alt=""><figcaption></figcaption></figure>



* `AND` user see "Contain at least one numeric character".

<figure><img src="../../.gitbook/assets/image (460).png" alt=""><figcaption></figcaption></figure>

* `AND` user see "Contain at least one special character".

<figure><img src="../../.gitbook/assets/image (461).png" alt=""><figcaption></figcaption></figure>

## 2.3. The system display message "password doesnt match"

* `GIVEN` user receive an email
* `WHEN` user click button "reset-password"

<figure><img src="../../.gitbook/assets/image (448).png" alt=""><figcaption></figcaption></figure>

* And user type "Admin123!" into input "new-password"

<figure><img src="../../.gitbook/assets/image (462).png" alt=""><figcaption></figcaption></figure>

* And user type "Admin123@" into input "password-confirmation"

<figure><img src="../../.gitbook/assets/image (463).png" alt=""><figcaption></figcaption></figure>

* `AND` user click button "reset-password"

<figure><img src="../../.gitbook/assets/image (451).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "Confirm password doesn't match the new password."

<figure><img src="../../.gitbook/assets/image (467).png" alt=""><figcaption></figcaption></figure>

## 2.4.Success reset password

* `GIVEN` user receive an email
* `WHEN` user click button "reset-password"

<figure><img src="../../.gitbook/assets/image (448).png" alt=""><figcaption></figcaption></figure>

* And user type "Admin123!" into input "new-password"

<figure><img src="../../.gitbook/assets/image (449).png" alt=""><figcaption></figcaption></figure>

* `AND` user type "Admin123!" into input "confirm-password"

<figure><img src="../../.gitbook/assets/image (450).png" alt=""><figcaption></figcaption></figure>

* `AND` user click button "reset-password"

<figure><img src="../../.gitbook/assets/image (451).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "Reset Password Success".
* `AND` user redirected to signin page.
