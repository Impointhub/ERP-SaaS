# Checklist Cash Report

## CK.1. checked checkbox

* Given I already logged in
* And I have permission to read cash report
* And I on the page "https://test.app.point.red/finance/point/report/cash"
* And the report already displays transaction data
* When I click the checkbox on the row "CASH-IN/0012/V/26"

<figure><img src="../../../.gitbook/assets/image (901).png" alt=""><figcaption></figcaption></figure>

* Then the system marks the row "CASH-IN/0012/V/26" as reconciled

<figure><img src="../../../.gitbook/assets/image (902).png" alt=""><figcaption></figcaption></figure>

* And the row displays the label "Reconciled"
