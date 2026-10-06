# Edit Master Supplier

## ESP.1 - Redirect to login page

* Given I have not logged in
* When I type /master/contact/supplier/create into browser&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## ESP.2 - Can't be changed because supplier already referenced&#x20;

* Given I already logged in&#x20;
* And I have permission to edit supplier&#x20;
* And I have data supplier "Bumi Lautan Kopi," which already has references&#x20;
* And I On the list page&#x20;
* When I click "\[sup-1] Bumi Lautan Kopi"

<figure><img src="../../../.gitbook/assets/image (1020).png" alt=""><figcaption></figcaption></figure>

* And I click edit&#x20;

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "Can't be changed because supplier already referenced"&#x20;

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

## ESP.3 - Redirect to forbidden page

* Given I already logged in
* And I do not have permission to edit supplier
* When I  type /master/contact/supplier/edit/1 into browser&#x20;
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## ESP.4 - Displaying notification name column is required

* Given I already logged in
* And I have permission to edit supplier
* And code column cannot be edited.
* And I on the page /master/contact/supplier/1/edit
* When I leave empty column name&#x20;

<figure><img src="../../../.gitbook/assets/image (617).png" alt=""><figcaption></figcaption></figure>

* And I type "supplier@gmail.com" into column email&#x20;

<figure><img src="../../../.gitbook/assets/image (618).png" alt=""><figcaption></figcaption></figure>

* And I type "Jln musi no 21"  into column address&#x20;

<figure><img src="../../../.gitbook/assets/image (619).png" alt=""><figcaption></figcaption></figure>

* And I type "4293293839" into column phone&#x20;

<figure><img src="../../../.gitbook/assets/image (620).png" alt=""><figcaption></figcaption></figure>

* And I type "testing" into column notes&#x20;

<figure><img src="../../../.gitbook/assets/image (621).png" alt=""><figcaption></figcaption></figure>

* And I click submit
* Then the system displays the message "Name is required"

<figure><img src="../../../.gitbook/assets/image (622).png" alt=""><figcaption></figcaption></figure>

## ESP.5 - Show notification "Success update supplier" and redirect to detail page

* Given I already logged in
* And I have permission to edit supplier
* And code column cannot be edited.
* And I on the page /master/contact/supplier/1/edit
* When I type "Dua Burung Updated" into column name

<figure><img src="../../../.gitbook/assets/image (623).png" alt=""><figcaption></figcaption></figure>

* And I type "Duaburung@gmail.com" into column email&#x20;

<figure><img src="../../../.gitbook/assets/image (624).png" alt=""><figcaption></figcaption></figure>

* And I type "DELTA HARMONI 52 WARU, DELTASARI BARU" into column address&#x20;

<figure><img src="../../../.gitbook/assets/image (625).png" alt=""><figcaption></figcaption></figure>

* And I type "031 - 8550694" into column phone&#x20;

<figure><img src="../../../.gitbook/assets/image (626).png" alt=""><figcaption></figcaption></figure>

* And I type "Testing" into column notes&#x20;

<figure><img src="../../../.gitbook/assets/image (627).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (628).png" alt=""><figcaption></figcaption></figure>

* Then the system updates the supplier
* And the system displays the message "Success update supplier"
* And the system redirects me to the detail page

<figure><img src="../../../.gitbook/assets/image (629).png" alt=""><figcaption></figcaption></figure>
