# Filter Cash Report

## CF1: System displays data according to filters

* Given I already logged in
* And I have permission to read cash report
* And I type "https://test.app.point.red/finance/point/report/cash" into browser
* When I click "Filter"

<figure><img src="../../../.gitbook/assets/image (888).png" alt=""><figcaption></figcaption></figure>

* And I select "01 May 2026" into column "date from"

<figure><img src="../../../.gitbook/assets/image (889).png" alt=""><figcaption></figcaption></figure>

* And I select "31 Aug 2026" into column "date to"

<figure><img src="../../../.gitbook/assets/image (890).png" alt=""><figcaption></figcaption></figure>

* And I select "Kas Kecil Outlet 1" into column "account"

<figure><img src="../../../.gitbook/assets/image (892).png" alt=""><figcaption></figcaption></figure>

* And I select "All" into column "subledger"

<figure><img src="../../../.gitbook/assets/image (893).png" alt=""><figcaption></figcaption></figure>

* And I click "Apply filter"

<figure><img src="../../../.gitbook/assets/image (894).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the cash report data filtered by "01 May 2026", "31 Aug 2026", "Kas Kecil Outlet 1" and "All" subledger

<figure><img src="../../../.gitbook/assets/image (1039).png" alt=""><figcaption></figcaption></figure>
