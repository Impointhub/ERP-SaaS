# Forgot Password

## 3.1.The system displays message "The password field is required"

* `GIVEN` user visit `/signin`
* `WHEN` user click button "forgot-password"

<figure><img src="../../.gitbook/assets/image (441).png" alt=""><figcaption></figcaption></figure>

* And  user click button "request-reset-password"

<figure><img src="../../.gitbook/assets/image (443).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "The email field is required."

<figure><img src="../../.gitbook/assets/image (444).png" alt=""><figcaption></figcaption></figure>

## 3.2. The system display message "Email is invalid"

* `GIVEN` user visit `/signin`
* `WHEN` user click button "forgot-password"

<figure><img src="../../.gitbook/assets/image (441).png" alt=""><figcaption></figcaption></figure>

* &#x20;And user type "[random-email@example.com](mailto:random-email@example.com)" into input "email"

<figure><img src="../../.gitbook/assets/image (446).png" alt=""><figcaption></figcaption></figure>

* `AND` user click button "request-reset-password"

<figure><img src="../../.gitbook/assets/image (447).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "Email is invalid".

<figure><img src="../../.gitbook/assets/image (445).png" alt=""><figcaption></figcaption></figure>

## 3.3.The user redirect to login page <a href="#id-1-5-s1-user-can-request-password-reset-successfully" id="id-1-5-s1-user-can-request-password-reset-successfully"></a>

* `GIVEN` user visit `/signin`
* `WHEN` user click button "forgot-password"

<figure><img src="../../.gitbook/assets/image (441).png" alt=""><figcaption></figcaption></figure>

* And user type "[admin@example.com](mailto:admin@example.com)" into input "email"

<figure><img src="../../.gitbook/assets/image (442).png" alt=""><figcaption></figcaption></figure>

* `AND` user click button "request-reset-password"

<figure><img src="../../.gitbook/assets/image (443).png" alt=""><figcaption></figcaption></figure>

* `THEN` user redirected to home page.
