# Export Cash Report (Excel)

EE1: System saves&#x20;export in Excel format
----------------------------

* Given I already logged in
* And I have permission to read cash report
* And I on the page "https://test.app.point.red/finance/point/report/cash"
* And I already select filter
* When I click "Export to Excel"

<figure><img src="../../../.gitbook/assets/image (897).png" alt=""><figcaption></figcaption></figure>

* Then the system generates the Excel file
* And the system displays the message "Your Excel file for Cash Report has been generated."

<figure><img src="../../../.gitbook/assets/image (898).png" alt=""><figcaption></figcaption></figure>

* And the system generate excel as format [https://docs.google.com/spreadsheets/d/1a\_J0AHqpnn39AqlGJGcThcYIcQKZzNjx/edit?usp=sharing\&ouid=100441136837797679779\&rtpof=true\&sd=true](https://docs.google.com/spreadsheets/d/1a_J0AHqpnn39AqlGJGcThcYIcQKZzNjx/edit?usp=sharing\&ouid=100441136837797679779\&rtpof=true\&sd=true)
