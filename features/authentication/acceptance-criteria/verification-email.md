# Verification Email

## 5.1. The system display : the code field is required&#x20;

* `GIVEN` user already filled signup form

```
const users = [
  {
    _id: "69ae0dabf12cfd6a5dd090eb",
    username: "johndoe",
    email: "johndoe@example.com",
    password: "$argon2id$v=19$m=65536,t=2,p=1$7M8Lw...",
    email_verification: {
      is_verified: false,
      requested_at: "2026-03-09T00:00:42.734Z",
      code: "ae59ee4b-3221-4cbe-8fd5-144fa126a102",
      url: "https://simple-accounting.pointhub.app/verify-email"
    },
    created_at: "2026-03-09T00:00:43.411Z",
    trimmed_email: "johndoe@example.com",
    trimmed_username: "johndoe"
  }
]
```

* `AND` user already receive verify email code from email

<figure><img src="../../../.gitbook/assets/image (505).png" alt=""><figcaption></figcaption></figure>

* `AND` user visit verify email page
* `WHEN` user click "Verify Email" button

<figure><img src="../../../.gitbook/assets/image (506).png" alt=""><figcaption></figcaption></figure>

* And user type verification code into column "code"

<figure><img src="../../../.gitbook/assets/image (507).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "Your Email Has Been Verified!"

<figure><img src="../../../.gitbook/assets/image (508).png" alt=""><figcaption></figcaption></figure>



#### Note: Database Change&#x20;

* Before Sign up&#x20;

```
//const users = [
  {
    _id: "69ae0dabf12cfd6a5dd090eb",
    ...
    email_verification: {
      is_verified: false,
      requested_at: "2026-03-09T00:00:42.734Z",
      code: "ae59ee4b-3221-4cbe-8fd5-144fa126a102",
      url: "https://simple-accounting.pointhub.app/verify-email"
    },
    ...
  }
]
```

* After Sign up&#x20;

```
//const users = [
  {
    _id: "69ae0dabf12cfd6a5dd090eb",
    ...
    email_verification: {
      is_verified: true,
      verified_at: "2026-03-09T00:00:50.734Z",
    },
    ...
  }
]
```

## 5.2. The system display verification code is invalid&#x20;

* `GIVEN` user visit verify email page
* `WHEN` user click "Verify Email" button

<figure><img src="../../../.gitbook/assets/image (510).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "The code field is required."

<figure><img src="../../../.gitbook/assets/image (509).png" alt=""><figcaption></figcaption></figure>

## 5.3.Verify Email Successfully&#x20;

* `GIVEN` user visit verify email page
* `WHEN` user click "Verify Email" button

<figure><img src="../../../.gitbook/assets/image (510).png" alt=""><figcaption></figcaption></figure>

* `THEN` user see "Verification code is invalid."

<figure><img src="../../../.gitbook/assets/image (511).png" alt=""><figcaption></figcaption></figure>
