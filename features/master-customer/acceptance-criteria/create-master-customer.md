# Create Master Customer

## CUS.1.1 - User redirect to login page

* Given I am not logged in
* When I type https://test.app.point.red/master/customer/create on the browser
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/image (432).png" alt=""><figcaption></figcaption></figure>

## CUS.1.2 - Redirect to forbidden page

* Given I already logged in
* And I do not have permission to create customer
* When I type https://test.app.point.red/master/customer/create on the browser
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CUS.1.3 - Display message code is required

* Given I already logged in
* And I have permission to create customer
* And I am on the page https://test.app.point.red/master/customer/create
* When I leave empty column code

<figure><img src="../../../.gitbook/assets/image (646).png" alt=""><figcaption></figcaption></figure>

* And I type name Sumber Berkat Makmur

<figure><img src="../../../.gitbook/assets/image (647).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (648).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Code is required"

<figure><img src="../../../.gitbook/assets/image (649).png" alt=""><figcaption></figcaption></figure>

## CUS.1.4 - Send notification name is required

* Given I already logged in
* And I have permission to create customer
* And I am on the page https://test.app.point.red/master/customer/create
* When I type code CUS-843

<figure><img src="../../../.gitbook/assets/image (650).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column name

<figure><img src="../../../.gitbook/assets/image (651).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (652).png" alt=""><figcaption></figcaption></figure>

* Then the system sends notification "Name is required"

<figure><img src="../../../.gitbook/assets/image (653).png" alt=""><figcaption></figcaption></figure>

## CUS.1.5 - Send notification the code already exist

* Given I already logged in
* And I have permission to create customer
* And I am on the page https://test.app.point.red/master/customer/create
* And code CUS-1 is already used by another customer
* When I type code CUS-1

<figure><img src="../../../.gitbook/assets/image (654).png" alt=""><figcaption></figcaption></figure>

* And I type name Sumber Berkat Makmur

<figure><img src="../../../.gitbook/assets/image (655).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (656).png" alt=""><figcaption></figcaption></figure>

* Then the system sends notification "The code already exist"

<figure><img src="../../../.gitbook/assets/image (657).png" alt=""><figcaption></figcaption></figure>

## CUS.1.6 - Display notification successfully created

* Given I already logged in
* And I have permission to create customer
* And I am on the page https://test.app.point.red/master/customer/create
* When I type "CUS-843" into column code

<figure><img src="../../../.gitbook/assets/image (658).png" alt=""><figcaption></figcaption></figure>

* And I type "Sumber Berkat Makmur" into column name

<figure><img src="../../../.gitbook/assets/image (659).png" alt=""><figcaption></figcaption></figure>

* And I type "purchase@sbm.com" into column email

<figure><img src="../../../.gitbook/assets/image (660).png" alt=""><figcaption></figcaption></figure>

* And I type "Jln raya diponegoro" into column address

<figure><img src="../../../.gitbook/assets/image (661).png" alt=""><figcaption></figcaption></figure>

* And I type "0318428239239" into column phone

<figure><img src="../../../.gitbook/assets/image (663).png" alt=""><figcaption></figcaption></figure>

* And I type "100000" into column credit ceiling

<figure><img src="../../../.gitbook/assets/image (664).png" alt=""><figcaption></figcaption></figure>

* And I type "pic atas nama aini" into column notes

<figure><img src="../../../.gitbook/assets/image (665).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (666).png" alt=""><figcaption></figcaption></figure>

* Then the system displays notification "Successfully created"

<figure><img src="../../../.gitbook/assets/image (667).png" alt=""><figcaption></figcaption></figure>

* And the new customer CUS-843 is saved to the customer list

<figure><img src="../../../.gitbook/assets/image (668).png" alt=""><figcaption></figcaption></figure>
