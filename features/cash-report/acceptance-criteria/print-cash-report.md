# Print Cash Report

## CP.1. the system show pop up print

* Given I already logged in
* And I have permission to read cash report
* And I on the page "https://test.app.point.red/finance/point/report/cash"
* And the report already displays transaction data
* When I click "Print" on the row "CASH-IN/0012/V/26"

<figure><img src="../../../.gitbook/assets/image (899).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the print preview for "CASH-IN/0012/V/26"

<figure><img src="../../../.gitbook/assets/image (900).png" alt=""><figcaption></figcaption></figure>

* And the print preview shows the form date, person, account, notes, received, and disbursed amount
* And the system displays a "Print" button and a "Close" button
