# Filter General Ledger

GF1: System displays data&#x20;according to filters
--------------------------

* Given I logged in
* And I has permission to read the general ledger report
* And I on the general ledger page&#x20;

<figure><img src="../../../.gitbook/assets/image (974).png" alt=""><figcaption></figcaption></figure>

* When I selects "01-08-2026" on the column date from&#x20;

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

* And I selects "15-08-2026" on the column date to&#x20;

<figure><img src="../../../.gitbook/assets/image (971).png" alt=""><figcaption></figcaption></figure>

* And I selects "10205-BANK BCA GIRO PUSAT 1" on the column account&#x20;

<figure><img src="../../../.gitbook/assets/image (972).png" alt=""><figcaption></figcaption></figure>

* Then the system updates the table to match the selected date range and account

<figure><img src="../../../.gitbook/assets/image (975).png" alt=""><figcaption></figcaption></figure>
