# Read Cash Report

## CR1: User redirect to login page

* Given I am not logged in
* When I type "https://test.app.point.red/finance/point/report/cash" into browser&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## CR2: Redirect to forbidden page

* Given I already logged in
* And I do not have permission to read cash report
* When I type "https://test.app.point.red/finance/point/report/cash" into browser
* Then the system redirects me to the restricted access page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## CR3: Displaying cash report data

* Given I already logged in
* And I have permission to read cash report
* When I type "https://test.app.point.red/finance/point/report/cash" into browser&#x20;
* And I select "01 May 2026" into column "period from"

<figure><img src="../../../.gitbook/assets/image (883).png" alt=""><figcaption></figcaption></figure>

* And I select "31 Aug 2026" into column "period to"

<figure><img src="../../../.gitbook/assets/image (884).png" alt=""><figcaption></figcaption></figure>

* And I select "Kas Kecil Outlet 1" into column "account"

<figure><img src="../../../.gitbook/assets/image (885).png" alt=""><figcaption></figcaption></figure>

* And I select "All" into column "subledger"

<figure><img src="../../../.gitbook/assets/image (886).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the cash report data

<figure><img src="../../../.gitbook/assets/image (1038).png" alt=""><figcaption></figcaption></figure>
