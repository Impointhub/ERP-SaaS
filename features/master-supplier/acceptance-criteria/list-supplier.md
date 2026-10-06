# List Supplier

## LSP.1 - Redirect to login page

* Given I have not logged in
* When I type /master/contact/supplier/ into browser&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## LSP.2 - Redirect to forbidden page

* Given I already logged in
* And I do not have permission to read supplier
* When I open the page /master/contact/supplier/
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## LSP.3 - Show data on the list page

* Given I already logged in
* And I have permission to read supplier
* When I open the page /master/contact/supplier/
* Then the system displays the supplier list with columns "Name"&#x20;

<figure><img src="../../../.gitbook/assets/image (642).png" alt=""><figcaption></figcaption></figure>
