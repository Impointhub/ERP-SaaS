# Read Allocation report

## AR1: User redirect to login page

* Given I am not logged in
* When I type "/finance/point/allocation-report" into browser&#x20;
* Then the system redirects me to the login page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## AR2: Redirect to forbidden page

* Given I already logged in
* And I do not have permission to read allocation report&#x20;
* When I type "/finance/point/allocation-report" into browser
* Then the system redirects me to the restricted access page

<figure><img src="../../../.gitbook/assets/Forbidden.png" alt=""><figcaption></figcaption></figure>

## AR3: Displaying allocation report data

* Given I already logged in
* And I have permission to read allocation report &#x20;
* When I type "/finance/point/allocation-report" into browser
* And I select "01-08-2026" into column date from&#x20;

<figure><img src="../../../.gitbook/assets/image (925).png" alt=""><figcaption></figcaption></figure>

* And I select "22-08-2019" into column date to&#x20;

<figure><img src="../../../.gitbook/assets/image (926).png" alt=""><figcaption></figcaption></figure>

* And I select "Borongan gersik" Into column allocation

<figure><img src="../../../.gitbook/assets/image (927).png" alt=""><figcaption></figcaption></figure>

* Then the system Display data based on filters

<figure><img src="../../../.gitbook/assets/image (1042).png" alt=""><figcaption></figcaption></figure>

