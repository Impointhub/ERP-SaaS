# Checklist bank report

## BK.1. checked checkbox

* Given I already logged in
* And I have permission to read bank report
* And I on the page "/finance/point/report/bank"
* And the report already displays transaction data

<figure><img src="../../../.gitbook/assets/image (921).png" alt=""><figcaption></figcaption></figure>

* When I click the checkbox on the row "BANK-IN/0017/V/26"

<figure><img src="../../../.gitbook/assets/image (922).png" alt=""><figcaption></figcaption></figure>

* Then the system marks the row "BANK-IN/0017/V/26" as reconciled

<figure><img src="../../../.gitbook/assets/image (923).png" alt=""><figcaption></figcaption></figure>

* And the row displays the label "Reconciled"

<figure><img src="../../../.gitbook/assets/image (924).png" alt=""><figcaption></figcaption></figure>

