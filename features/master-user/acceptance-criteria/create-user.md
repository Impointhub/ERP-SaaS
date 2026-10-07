# Create User

MSR.1 – Redirect to login page

* Given I am not logged in
* When I access /master/user/create
* Then the system redirects to the login page

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

## MSR.2 - Redirect to forbidden page

* Given I already logged in
* And I dont have permission to create user
* When I access the page /master/user/1
* Then I redirect to forbidden page

<figure><img src="../../../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

## MSR.3 – Column Name Is Required (field name belum diisi)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* And I have role "admin"
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I leave the "Name" field empty

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

* And I type "aini@pointhub.co" into column email

<figure><img src="../../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

* And I select role "admin" into column role

<figure><img src="../../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

* And I click save the form

<figure><img src="../../../.gitbook/assets/image (517).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column Name Is Required"

<figure><img src="../../../.gitbook/assets/image (513).png" alt=""><figcaption></figcaption></figure>

* And the system does not create the user
* And I user should remain on the create page

## MSR.4 – Column Email Is Required (field email belum diisi)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* And I have role "admin"
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And type "Aini Rahman" into column "name"

<figure><img src="../../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

* And I leave empty email column

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* And I select "Admin" into column "role"

<figure><img src="../../../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

* And I click save

<figure><img src="../../../.gitbook/assets/image (521).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column Email Is Required"

<figure><img src="../../../.gitbook/assets/image (522).png" alt=""><figcaption></figcaption></figure>

* And the system does not create the user
* And I should remain on the create page

## MSR.5 – Email already registered (email sudah terdaftar)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* And I have role "admin"
* And The email "impointhub@gmail.com" is already registered.
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And type "Aini Rahman" into column "name"

<figure><img src="../../../.gitbook/assets/image (524).png" alt=""><figcaption></figcaption></figure>

* And I type "impointhub@gmail.com" into column "email"

<figure><img src="../../../.gitbook/assets/image (525).png" alt=""><figcaption></figcaption></figure>

* And I select "Admin" into column "role"

<figure><img src="../../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

* And I click save

<figure><img src="../../../.gitbook/assets/image (527).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Email already registered"

<figure><img src="../../../.gitbook/assets/image (528).png" alt=""><figcaption></figcaption></figure>

* And the system does not create the user
* And I should remain on the create page

## MSR.6 – Column role is required (field role belum diisi)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* And I have role "admin"
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I type "Aini Rahman" into column "name"

<figure><img src="../../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

* And I type "aini@pointhub.co" into column "email"

<figure><img src="../../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column role

<figure><img src="../../../.gitbook/assets/image (1000).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

* And I click "save"

<figure><img src="../../../.gitbook/assets/image (532).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column role is required"

<figure><img src="../../../.gitbook/assets/image (533).png" alt=""><figcaption></figcaption></figure>

* And the system does not create the user
* And I should remain on the create page

## MSR.7 – Column password Is Required (field password belum diisi)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I type "Aini Rahman" into column name

<figure><img src="../../../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure>

* And I type "aini@pointhub.co" into column email

<figure><img src="../../../.gitbook/assets/image (87).png" alt=""><figcaption></figcaption></figure>

* And I select "Admin" into column role

<figure><img src="../../../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

* And I leave empty password column

<figure><img src="../../../.gitbook/assets/image (1001).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure>

* And I click save

<figure><img src="../../../.gitbook/assets/image (536).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Column password is required".

<figure><img src="../../../.gitbook/assets/image (537).png" alt=""><figcaption></figcaption></figure>

* And the system does not create the user
* And I should remain on the create page

## MSR.8 – Passwords do not match (password dan konfirmasi password tidak sama)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I type "Aini Rahman" into column name

<figure><img src="../../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

* And I type "aini@pointhub.co" into column email

<figure><img src="../../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin" into column role

<figure><img src="../../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin12!" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (1002).png" alt=""><figcaption></figcaption></figure>

* And I click save the form

<figure><img src="../../../.gitbook/assets/image (540).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Passwords do not match"

<figure><img src="../../../.gitbook/assets/image (541).png" alt=""><figcaption></figcaption></figure>

* And the system does not create the user
* And I should remain on the create page

## MSR.9 – Success, redirect to list page (semua field valid, user berhasil dibuat)

* Given I already logged in
* And I have permission to create user
* And I on the page /master/user/
* When I click create button

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* And I type "Aini Rahman" into column name

<figure><img src="../../../.gitbook/assets/image (542).png" alt=""><figcaption></figcaption></figure>

* And I type "aini@pointhub.co" into column email

<figure><img src="../../../.gitbook/assets/image (543).png" alt=""><figcaption></figcaption></figure>

* And I select "admin" into column role

<figure><img src="../../../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password

<figure><img src="../../../.gitbook/assets/image (98).png" alt=""><figcaption></figcaption></figure>

* And I type "Admin123" into column password confirmation

<figure><img src="../../../.gitbook/assets/image (546).png" alt=""><figcaption></figcaption></figure>

* And I click save

<figure><img src="../../../.gitbook/assets/image (547).png" alt=""><figcaption></figcaption></figure>

* Then the system creates the new user record
* And the system sets "created\_at" to the current timestamp
* And the system sets "created\_by" to the ID of the logged-in user
* And the system redirects to the user list page
