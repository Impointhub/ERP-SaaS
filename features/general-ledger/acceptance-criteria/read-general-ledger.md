# Read General Ledger

## GL1: User redirect to login page

* Given I have not logged in
* When I type `/accounting/general-ledger` into browser
* Then I should be redirected to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## GL2: Redirect to forbidden page

* Given I already logged in
* And I do not have permission to read general ledger&#x20;
* When I type `/accounting/general-ledger` create into browser&#x20;
* Then I redirect to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>



## GL3: Displaying General Ledger data

* Given I logged in
* And I has permission to read the general ledger report
* When I navigates to "/accounting/general-ledger"

<figure><img src="../../../.gitbook/assets/image (966).png" alt=""><figcaption></figcaption></figure>

* And I selects "01-08-2026" on column date from

<figure><img src="../../../.gitbook/assets/image (968).png" alt=""><figcaption></figcaption></figure>

* And I selects "31-08-2026" on column date to&#x20;

<figure><img src="../../../.gitbook/assets/image (969).png" alt=""><figcaption></figcaption></figure>

* And I selects account "10101 · Cash on hand"&#x20;

<figure><img src="../../../.gitbook/assets/image (976).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the general ledger data for the selected date range and account

<figure><img src="../../../.gitbook/assets/image (977).png" alt=""><figcaption></figcaption></figure>
