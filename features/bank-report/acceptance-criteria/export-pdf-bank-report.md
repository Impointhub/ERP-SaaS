# Export PDF Bank Report

EP1: System saves PDF&#x20;export
------------

* Given I already logged in
* And I have permission to read bank report
* And I on the page "/finance/point/report/bank"

<figure><img src="../../../.gitbook/assets/image (911).png" alt=""><figcaption></figcaption></figure>

* And I already select filter

<figure><img src="../../../.gitbook/assets/image (912).png" alt=""><figcaption></figcaption></figure>

* When I click "Export to PDF"

<figure><img src="../../../.gitbook/assets/image (913).png" alt=""><figcaption></figcaption></figure>

* Then the system generates the PDF file
* And the system displays the message "Your PDF file for Bank Report has been generated."
* And the system generates PDF File as a format : [https://drive.google.com/file/d/1OKuPR05PM4ZAPjsg5skweDK1wgHIvc\_Y/view?usp=sharing](https://drive.google.com/file/d/1OKuPR05PM4ZAPjsg5skweDK1wgHIvc_Y/view?usp=sharing)&#x20;
