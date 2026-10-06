# Edit Master Allocation

## ALO.2.1: User redirect to login page

* `GIVEN` user visit url `/master/allocation` without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## ALO.2.2: redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to edit allocation.&#x20;
* When user type _`/master/allocation`_ url into browser&#x20;
* And user already have allocation data "Project A"&#x20;
* When user click data "Project A"&#x20;
* And user click button "edit"&#x20;
* Then the user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## ALO.2.3: The system Displays a notification "allocation cannot be changed because the data is already referenced"

* Given User on the page `/master/allocation`&#x20;
* And user already logged in&#x20;
* And user already have permission to edit allocation&#x20;
* And user have data allocation "Project A"
* And data allocation have reference&#x20;
* When user click button "edit" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (485).png" alt=""><figcaption></figcaption></figure>

* And the system display message "Unable to edit this form because it is already used in another transaction."

<figure><img src="../../../.gitbook/assets/image (484).png" alt=""><figcaption></figcaption></figure>

## ALO.2.4: The system displays the message "Name is required"

* Given User on the page `/master/allocation/1  ​`
* And the user already logged in.&#x20;
* And the user already have data allocation "Project B"
* And the user already have permission to edit allocation&#x20;
* When user click button "Edit"

<figure><img src="../../../.gitbook/assets/image (486).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "name"&#x20;

<figure><img src="../../../.gitbook/assets/image (487).png" alt=""><figcaption></figcaption></figure>

* And user click save

<figure><img src="../../../.gitbook/assets/image (488).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Name is required"&#x20;

<figure><img src="../../../.gitbook/assets/image (489).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the edit page&#x20;

<figure><img src="../../../.gitbook/assets/image (490).png" alt=""><figcaption></figcaption></figure>

ALO.2.5: The system Send a notification&#x20;"the name  already exists."
---------------------------------

* Given User on the page `/master/allocation/1`&#x20;
* And user already logged in.
* And user already have allocation data "Project A"
* And the data allocation does not yet have a reference.
* And user already have permission for the edit allocation
* When user click button "Edit"

<figure><img src="../../../.gitbook/assets/image (491).png" alt=""><figcaption></figcaption></figure>

* And user types "Project A" Into column "Name"

<figure><img src="../../../.gitbook/assets/image (492).png" alt=""><figcaption></figcaption></figure>

* And user click save

<figure><img src="../../../.gitbook/assets/image (493).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "The name already exist."

<figure><img src="../../../.gitbook/assets/image (961).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the edit page&#x20;

<figure><img src="../../../.gitbook/assets/image (961).png" alt=""><figcaption></figcaption></figure>

ALO.2.6: Display a notification"successfully updated"
----------------------

* Given User on the page `/master/allocation/1 ​`
* And the user already logged in.
* And user already have allocation data "Project A"
* And the data allocation does not yet have a reference.
* And user already have permission for the edit allocation
* When user click button "Edit"

<figure><img src="../../../.gitbook/assets/image (491).png" alt=""><figcaption></figcaption></figure>

* And user types "Project F" into column "Name"

<figure><img src="../../../.gitbook/assets/image (496).png" alt=""><figcaption></figcaption></figure>

* And user click save

<figure><img src="../../../.gitbook/assets/image (497).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Successfully updated"

<figure><img src="../../../.gitbook/assets/image (498).png" alt=""><figcaption></figcaption></figure>

* And user should redirect to detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (499).png" alt=""><figcaption></figcaption></figure>
