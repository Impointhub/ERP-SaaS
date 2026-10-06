# Filter Bank Report

BF1: System displays data&#x20;according to filters
--------------------------

* Given I already logged in
* And I have permission to read bank report
* And I on the page "https://test.app.point.red/finance/point/report/bank"
* When I click "Filter"

<figure><img src="../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

* And I select "01 May 2026" into column "date from"

<figure><img src="../../../.gitbook/assets/image (905).png" alt=""><figcaption></figcaption></figure>

* And I select "31 Aug 2026" into column "date to"

<figure><img src="../../../.gitbook/assets/image (906).png" alt=""><figcaption></figcaption></figure>

* And I select "Bank BCA Giro KE-4 2588807881" into column "account"

<figure><img src="../../../.gitbook/assets/image (907).png" alt=""><figcaption></figcaption></figure>

* And I select "All" into column "subledger"

<figure><img src="../../../.gitbook/assets/image (908).png" alt=""><figcaption></figcaption></figure>

* And I click "Apply filter"

<figure><img src="../../../.gitbook/assets/image (909).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the bank report data filtered by "01 May 2026", "31 Aug 2026", "Bank BCA Giro KE-4 2588807881" and "All" subledger.&#x20;

<figure><img src="../../../.gitbook/assets/image (1040).png" alt=""><figcaption></figcaption></figure>
