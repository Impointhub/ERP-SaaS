# Delete- Master group chart of account

## Group-coa 3.1 : Redirect to the login page

* `GIVEN` user visit `/chart-of-accounts` url without signin
* `THEN` user redirected to `Sign In` page<br>

<figure><img src="../../../.gitbook/assets/image (210).png" alt=""><figcaption></figcaption></figure>

## Group-coa 3.2 : Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to delete a chart of accounts.
* When user type `/chart-of-accounts` url into browser
* Then user redirected to forbidden page

<figure><img src="../../../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

## Group-coa 3.3 : The system displays the message "This field is required"

* Given user is logged in
* And users have permission to delete the chart of accounts.
* And password user for the account "Admin123"!
* And user on the list page chart of account
* When user click group "101 GPR"
* And the user clicks the delete button.

<figure><img src="../../../.gitbook/assets/image (219).png" alt=""><figcaption></figcaption></figure>

* And user leave empty password confirmation empty.

<figure><img src="../../../.gitbook/assets/image (218).png" alt=""><figcaption></figcaption></figure>

* And user click button delete

<figure><img src="../../../.gitbook/assets/image (214).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Password is required".

<figure><img src="../../../.gitbook/assets/image (215).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the delete form.

<figure><img src="../../../.gitbook/assets/image (216).png" alt=""><figcaption></figcaption></figure>

## Group-coa 3.4 : Displays the message "wrong password"

* Given user is logged in
* And users have permission to delete the chart of accounts.
* And password user for the account "Admin123"!
* And user on the list page chart of account
* When user click group "101 GPR"
* And the user clicks the delete button.

<figure><img src="../../../.gitbook/assets/image (219).png" alt=""><figcaption></figcaption></figure>

* And user type "Admin12" into column

<figure><img src="../../../.gitbook/assets/image (221).png" alt=""><figcaption></figcaption></figure>

* And user click button delete

<figure><img src="../../../.gitbook/assets/image (222).png" alt=""><figcaption></figcaption></figure>

* Then user can view the notification "wrong password"

<figure><img src="../../../.gitbook/assets/image (223).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the delete form.

<figure><img src="../../../.gitbook/assets/image (224).png" alt=""><figcaption></figcaption></figure>

## Group-coa 3.5 : Group data will be deleted

* Given user is logged in
* And users have permission to delete the chart of accounts.
* And password user for the account "Admin123"!
* And user on the list page chart of account
* When user click group "101 GPR"
* And the user clicks the delete button.

<figure><img src="../../../.gitbook/assets/image (229).png" alt=""><figcaption></figcaption></figure>

* And user type "Admin123" into the column.

<figure><img src="../../../.gitbook/assets/image (228).png" alt=""><figcaption></figcaption></figure>

* And user click button delete

<figure><img src="../../../.gitbook/assets/image (226).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "successfully deleted "

<figure><img src="../../../.gitbook/assets/image (230).png" alt=""><figcaption></figcaption></figure>

* And subgroup within this group will be move to the parent level. Sample Data  :&#x20;
  * Data before deletion :
    * Asset&#x20;
      * Kas & Bank&#x20;
        * Kas Setara kas (deletion by user)
          * Petty cash&#x20;
        * Bank&#x20;
  * Data after deletion :&#x20;
    * Asset&#x20;
      * Kas & Bank&#x20;
        * Petty Cash (Petty cash increases at the parent level)
        * Bank&#x20;

## Group-coa 3.6 : Archive data chart of account&#x20;

* Given user is logged in
* And users have permission to delete the chart of accounts.
* And password user for the account "Admin123"!
* And user on the list page chart of account
* And group "101 GPR" already have transaction&#x20;
* When user click group "101 GPR"

<figure><img src="../../../.gitbook/assets/image (105).png" alt=""><figcaption></figcaption></figure>

* And the user clicks the delete button.

<figure><img src="../../../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

* And user type "Admin123" into the column.

<figure><img src="../../../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>

* And user click button delete

<figure><img src="../../../.gitbook/assets/image (226).png" alt=""><figcaption></figcaption></figure>

* Then I can view notification "successfully archived "

<figure><img src="../../../.gitbook/assets/Successfully Archived Notification.png" alt=""><figcaption></figcaption></figure>

* And subgroup within this group will be move to the parent level. Sample Data  :&#x20;
  * Data before deletion :
    * Asset&#x20;
      * Kas & Bank&#x20;
        * Kas Setara kas (archived by user)
          * Petty cash&#x20;
          * Bank&#x20;
  * Data after deletion :&#x20;
    * Asset&#x20;
      * Kas & Bank&#x20;
        * Petty Cash (Petty cash increases at the parent level)
          * Bank&#x20;
