# Create Master Allocation

## ALO.1.1: User redirect to login page

* `GIVEN` user visit url `/master/allocation` without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## ALO.1.2: redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to create allocation.
* When user type `/master/allocation` url into browser
* Then the user redirected to forbidden page

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## ALO.1.3: The system displays the message "Name is required"

* Given User on the page `/master/allocation ​`
* And the user already login
* And the user already have permission for the create\_allocation.
* When user click button "Create"

<figure><img src="../../../.gitbook/assets/image (468).png" alt=""><figcaption></figcaption></figure>

* And user leave empty column "name"

<figure><img src="../../../.gitbook/assets/image (469).png" alt=""><figcaption></figcaption></figure>

* And user click save

<figure><img src="../../../.gitbook/assets/image (470).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Name is required"

<figure><img src="../../../.gitbook/assets/image (471).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the create page

<figure><img src="../../../.gitbook/assets/image (472).png" alt=""><figcaption></figcaption></figure>

## ALO.1.4: The system Send a notification : "The name already exists."

* Given User on the page `/master/allocation` ​
* And the user already login
* And I already have allocation data "Project A"
* And the user already have permission for the create\_allocation.
* When user click button "Create"

<figure><img src="../../../.gitbook/assets/image (468).png" alt=""><figcaption></figcaption></figure>

* And user types "Project A" Into column "Name"

<figure><img src="../../../.gitbook/assets/image (474).png" alt=""><figcaption></figcaption></figure>

* And user click save

<figure><img src="../../../.gitbook/assets/image (475).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "The name already exists"

<figure><img src="../../../.gitbook/assets/image (961).png" alt=""><figcaption></figcaption></figure>

* And user should remain on the create page

<figure><img src="../../../.gitbook/assets/image (961).png" alt=""><figcaption></figcaption></figure>

## ALO.1.5: Display a notification "successfully created"

* Given User on the page `/master/allocation ​`
* And the user already logged in.
* And the user already have permission for the create\_allocation.
* When user click button "Create"

<figure><img src="../../../.gitbook/assets/image (468).png" alt=""><figcaption></figcaption></figure>

* And user types "Project F" into column "Name"

<figure><img src="../../../.gitbook/assets/image (478).png" alt=""><figcaption></figcaption></figure>

* And user click save

<figure><img src="../../../.gitbook/assets/image (480).png" alt=""><figcaption></figcaption></figure>

* Then user can view notification "Successfully created"

<figure><img src="../../../.gitbook/assets/image (481).png" alt=""><figcaption></figcaption></figure>

* And user should redirect to detail page

<figure><img src="../../../.gitbook/assets/image (483).png" alt=""><figcaption></figcaption></figure>
