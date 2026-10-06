# Detail Master Supplier

## VSP.1 - Redirect to login page

* Given I have not logged in
* When I type /master/contact/supplier/1 into browser&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## VSP.2 - Redirect to forbidden page

* Given I already logged in
* And I do not have permission to read supplier
* When I type /master/contact/supplier/1 into browser&#x20;
* Then the system redirects me to the forbidden page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## VSP.3 - Show detail page

* Given I already logged in
* And I have permission to read supplier
* When I type /master/contact/supplier/1 into browser
* Then the system displays the supplier detail page

<figure><img src="../../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>
