# Read Bank Report

## BR1: User redirect to login page

* Given I am not logged in
* When I open the page "https://test.app.point.red/finance/point/report/bank"
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## BR2: Redirect to forbidden page

* Given I already logged in
* And I do not have permission to read bank report
* When I open the page "https://test.app.point.red/finance/point/report/bank"
* Then the system redirects me to the restricted access page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## BR3: Displaying bank report data

* Given I already logged in
* And I have permission to read bank report
* And I on the page "https://test.app.point.red/finance/point"
* When I click "Bank Report"

<figure><img src="../../../.gitbook/assets/image (903).png" alt=""><figcaption></figcaption></figure>

* Then the system opens the page "https://test.app.point.red/finance/point/report/bank"

<figure><img src="../../../.gitbook/assets/image (1041).png" alt=""><figcaption></figcaption></figure>

* And the system displays the bank report page
