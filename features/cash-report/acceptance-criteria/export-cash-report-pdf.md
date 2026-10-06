# Export Cash Report (PDF)

EP1: System saves PDF&#x20;export
------------

* Given I already logged in
* And I have permission to read cash report
* And I on the page "https://test.app.point.red/finance/point/report/cash"
* And I already select filter
* When I click "Export to PDF"

<figure><img src="../../../.gitbook/assets/image (896).png" alt=""><figcaption></figcaption></figure>

* Then the system generates the PDF file
* And the system displays the message "Your PDF file for Cash Report has been generated."
* And the system should generate pdf file as a format [https://drive.google.com/file/d/1OKuPR05PM4ZAPjsg5skweDK1wgHIvc\_Y/view?usp=sharing](https://drive.google.com/file/d/1OKuPR05PM4ZAPjsg5skweDK1wgHIvc_Y/view?usp=sharing)
