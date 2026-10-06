# Create Master Supplier

## CSP.1 - Redirect to login page

* Given I have not logged in
* When I type /master/contact/supplier/create into browser&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## CSP.2 - Redirect to forbidden page

* Given I already logged in
* And I do not have permission to create supplier
* When I  type /master/contact/supplier/create into browser&#x20;
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CSP.3 - Code is required

* Given I already logged in
* And I have permission to create supplier
* And I on the page /master/contact/supplier/create
* When I leave empty code column&#x20;

<figure><img src="../../../.gitbook/assets/image (597).png" alt=""><figcaption></figcaption></figure>

* And I type "Aini" Into column name&#x20;

<figure><img src="../../../.gitbook/assets/image (598).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (599).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Code is required"



## CSP.4 - Code already exists

* Given I already logged in
* And I have permission to create supplier
* And I on the page /master/contact/supplier/create
* When I type "SUP-2" into column code

<figure><img src="../../../.gitbook/assets/image (600).png" alt=""><figcaption></figcaption></figure>

* And I type "New Supplier" into column name

<figure><img src="../../../.gitbook/assets/image (601).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (603).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Code already exists"

<figure><img src="../../../.gitbook/assets/image (602).png" alt=""><figcaption></figcaption></figure>

## CSP.5 - Name is required

* Given I already logged in
* And I have permission to create supplier
* And I on the page /master/contact/supplier/create
* When I type supplier 654

<figure><img src="../../../.gitbook/assets/image (605).png" alt=""><figcaption></figcaption></figure>

* And I leave empty column name&#x20;

<figure><img src="../../../.gitbook/assets/image (606).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (607).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the message "Name is required"

<figure><img src="../../../.gitbook/assets/image (608).png" alt=""><figcaption></figcaption></figure>



## CSP.6 - Show notification "Success create supplier" and redirect to detail page

* Given I already logged in
* And I have permission to create supplier
* And I on the page /master/contact/supplier/create
* When I type "SUP-654" into column code

<figure><img src="../../../.gitbook/assets/image (609).png" alt=""><figcaption></figcaption></figure>

* And I type "New Supplier" into column name

<figure><img src="../../../.gitbook/assets/image (610).png" alt=""><figcaption></figcaption></figure>

* And I type "supplier@gmail.com" into column&#x20;

<figure><img src="../../../.gitbook/assets/image (611).png" alt=""><figcaption></figcaption></figure>

* And I type "Jln musi no 21" into column "address"

<figure><img src="../../../.gitbook/assets/image (612).png" alt=""><figcaption></figcaption></figure>

* And I type "4293293839" into column "phone"

<figure><img src="../../../.gitbook/assets/image (613).png" alt=""><figcaption></figcaption></figure>

* And I type "testing" into column "notes"

<figure><img src="../../../.gitbook/assets/image (614).png" alt=""><figcaption></figcaption></figure>

* And I click submit

<figure><img src="../../../.gitbook/assets/image (615).png" alt=""><figcaption></figcaption></figure>

* Then the system creates the supplier
* And the system displays the message "Success create supplier"
* And the system redirects me to the detail page

<figure><img src="../../../.gitbook/assets/image (616).png" alt=""><figcaption></figcaption></figure>
