# Export General Ledger

EG.1: System saves in excel&#x20;format
------------

* Given I logged in
* And I has permission to read the general ledger report
* And I is on the general ledger page
* And a date range and account filter are already applied
* When the user clicks "Export to Excel"

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* Then the system generates an Excel file of the filtered general ledger
* And the system show notifications "Successfully export general ledger"&#x20;

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

* And the system downloads the file to the user's device as a format&#x20;
  * [https://docs.google.com/spreadsheets/d/1VUdbz1JDIsrJBVvUWEQJuiYKEEDit95K/edit?usp=sharing\&ouid=100441136837797679779\&rtpof=true\&sd=true](https://docs.google.com/spreadsheets/d/1VUdbz1JDIsrJBVvUWEQJuiYKEEDit95K/edit?usp=sharing\&ouid=100441136837797679779\&rtpof=true\&sd=true)
