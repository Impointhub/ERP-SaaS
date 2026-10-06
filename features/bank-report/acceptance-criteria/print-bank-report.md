# Print Bank Report

## BP.1.Then system show pop up print

* Given I already logged in
* And I have permission to read bank report
* And I on the page "/finance/point/report/bank"

<figure><img src="../../../.gitbook/assets/image (917).png" alt=""><figcaption></figcaption></figure>

* And the report already displays transaction data

<figure><img src="../../../.gitbook/assets/image (918).png" alt=""><figcaption></figcaption></figure>

* When I click "Print" on the row "BANK-IN/0017/V/26"

<figure><img src="../../../.gitbook/assets/image (920).png" alt=""><figcaption></figcaption></figure>

* Then the system displays the print preview for "BANK-IN/0017/V/26"
* And the print preview shows the form date, person, account, notes, received, and disbursed amount
* And the system displays a "Print" button and a "Close" button
