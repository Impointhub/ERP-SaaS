---
hidden: true
---

# Verify Email

## 1.2.S1. User can verify email successfully <a href="#id-1-2-s1-user-can-verify-email-successfully" id="id-1-2-s1-user-can-verify-email-successfully"></a>

* `GIVEN` user already filled signup form
* `AND` user already receive verify email code from email
* `AND` user visit verify email page
* `WHEN` user click "Verify Email" button
* `THEN` user see "Your Email Has Been Verified!"

## 1.2.F1. Email verification fails when verification code is invalid. <a href="#id-1-2-f1-email-verification-fails-when-verification-code-is-invalid" id="id-1-2-f1-email-verification-fails-when-verification-code-is-invalid"></a>

* `GIVEN` user visit verify email page
* `WHEN` user click "Verify Email" button
* `THEN` user see "Verification code is invalid."

## 1.2.F2. Email verification fails when required fields are empty. <a href="#id-1-2-f1-email-verification-fails-when-required-fields-are-empty" id="id-1-2-f1-email-verification-fails-when-required-fields-are-empty"></a>



