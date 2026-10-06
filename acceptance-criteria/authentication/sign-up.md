---
hidden: true
---

# Sign Up

## 1.1.S1. User can sign up successfully.

* `GIVEN` user visit signup page
* `WHEN` user type "johndoe" into input "username"
* `AND` user type "[johndoe@example.com](mailto:johndoe@example.com)" into input "email"
* `AND` user type "John1234" into input "password"
* `AND` user type "John1234" into input "confirm-password"
* `AND` user click checkbox "accept-terms-and-privacy"
* `AND` user click button "sign-up"
* `THEN` user see "Please verify your email"
* `AND` user see "You're almost there! We sent an email to [johndoe@example.com](mailto:johndoe@example.com)"
* `AND` user see "Just click on the link in that email to complete your signup."
* `AND` user see "If you don't see it, you may wait a few minutes for the email to arrive or check your spam folder."

## 1.1.F1. Sign up fails when required fields are empty. <a href="#id-1-1-f1-sign-up-fails-when-required-fields-are-empty" id="id-1-1-f1-sign-up-fails-when-required-fields-are-empty"></a>

* `GIVEN` user visit signup page
* `WHEN` user click button "sign-up"
* `THEN` user see "The username field is required"
* `AND` user see "The email field is required"
* `AND` user see "The password field is required"

## 1.1.F2. Sign up fails when username already exists. <a href="#id-1-1-f2-sign-up-fails-when-username-already-exists" id="id-1-1-f2-sign-up-fails-when-username-already-exists"></a>

* `GIVEN` user visit signup page
* `WHEN` user type "admin" into input "username"
* `AND` user type "[admin2@example.com](mailto:admin2@example.com)" into input "email"
* `AND` user type "admin1234" into input "password"
* `AND` user type "admin1234" into input "confirm-password"
* `AND` user click button "sign-up"
* `THEN` user see "The username field already exists"

## 1.1.F3. Sign up fails when email already exists.

* `GIVEN` user visit signup page
* `WHEN` user type "admin2" into input "username"
* `AND` user type "[admin@example.com](mailto:admin@example.com)" into input "email"
* `AND` user type "admin1234" into input "password"
* `AND` user type "admin1234" into input "confirm-password"
* `AND` user click button "sign-up"
* `THEN` user see "The email field already exists"

## 1.1.F4. Sign up fails when password is not strong enough. <a href="#id-1-1-f4-sign-up-fails-when-password-is-not-strong-enough" id="id-1-1-f4-sign-up-fails-when-password-is-not-strong-enough"></a>

* `GIVEN` user visit signup page

<figure><img src="../../.gitbook/assets/image (431).png" alt=""><figcaption></figcaption></figure>

* `WHEN` user type "admin2" into input "username"



* `AND` user type "[admin2@example.com](mailto:admin2@example.com)" into input "email"
* `AND` user type "admin" into input "password"
* `THEN` user see "Use at least 8 characters"

## 1.1.F5. Sign up fails when password confirmation does not match. <a href="#id-1-1-f5-sign-up-fails-when-password-confirmation-does-not-match" id="id-1-1-f5-sign-up-fails-when-password-confirmation-does-not-match"></a>

* `GIVEN` user visit signup page
* `WHEN` user type "admin2" into input "username"
* `AND` user type "[admin2@example.com](mailto:admin2@example.com)" into input "email"
* `AND` user type "admin123" into input "password"
* `AND` user type "a" into input "confirm-password"
* `AND` user click button "sign-up"
* `THEN` user see "Password do not match"

## <br>



