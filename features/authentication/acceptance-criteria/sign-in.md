# Sign In

## 1.1.1. Displays a "wrong username or password" notification.

* `GIVEN` user visit `/signin`
* `AND` the correct user password "Admin123!"
* `WHEN` user type "admin" into input "username"

<figure><img src="../../../.gitbook/assets/image (433).png" alt=""><figcaption></figcaption></figure>

* `AND` user type "12345678" into input "password"

<figure><img src="../../../.gitbook/assets/image (436).png" alt=""><figcaption></figcaption></figure>

* `AND` user click button "sign-in"

<figure><img src="../../../.gitbook/assets/image (435).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "wrong username or password" on sign in page&#x20;

## 1.1.2 User can sign successfully

* `GIVEN` user visit `/signin`
* `WHEN` user type "admin" into input "username"

<figure><img src="../../../.gitbook/assets/image (433).png" alt=""><figcaption></figcaption></figure>

* `AND` user type "Admin123!" into input "password"

<figure><img src="../../../.gitbook/assets/image (434).png" alt=""><figcaption></figcaption></figure>

* `AND` user click button "sign-in"

<figure><img src="../../../.gitbook/assets/image (435).png" alt=""><figcaption></figcaption></figure>

* `THEN` user redirected to home page.

<figure><img src="../../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>
