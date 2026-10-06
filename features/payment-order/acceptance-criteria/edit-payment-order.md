# Edit Payment Order

## PO.2.1 :  User redirect to login page

* `GIVEN` user visit `/finance/point/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.2.2 :  Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to edit a payment order
* When user type `/finance/point/payment-order` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## PO.2.3 : Unable to edit this form because it is already used in another transaction.

* Given User on the page `/finance/point/payment-order/1`&#x20;
* And the user already login&#x20;
* And the user already have permission for the edit\_payment\_order.&#x20;
* And the form have a reference cash out or bank out&#x20;
* When user click button "edit" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the system display message "Unable to edit this form because it is already used in another transaction"

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the detail page&#x20;

## PO.2.4 : The system displays the message "Payment to is required"

* Given User on the page `/finance/point/payment-order/1`&#x20;
* And the user already login&#x20;
* And the user already have permission for the edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "edit" on the detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (321).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "Payment to"

<figure><img src="../../../.gitbook/assets/image (322).png" alt=""><figcaption></figcaption></figure>

* And the user choose "cash" on column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (323).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into column "Form Notes"

<figure><img src="../../../.gitbook/assets/image (935).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban Ekspedisi" into column "account"

<figure><img src="../../../.gitbook/assets/image (325).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"&#x20;

<figure><img src="../../../.gitbook/assets/image (936).png" alt=""><figcaption></figcaption></figure>

* And the user type "Rp.100.000" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (327).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A " into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (429).png" alt=""><figcaption></figcaption></figure>

* And the user choose "kartika" into column "approved by"

<figure><img src="../../../.gitbook/assets/image (328).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (329).png" alt=""><figcaption></figcaption></figure>

* And the user click "save"
* Then user can view message "{Payment To} is required"

<figure><img src="../../../.gitbook/assets/image (330).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the edit page&#x20;

## PO.2.5 : The system displays the message "Payment method is required"

* Given User on the page `/finance/point/payment-order/1`&#x20;
* And the user already login&#x20;
* And the user already have permission for the edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "edit"

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (331).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (332).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "Payment method"

<figure><img src="../../../.gitbook/assets/image (333).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into column "Form Notes"

<figure><img src="../../../.gitbook/assets/image (937).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban Ekspedisi" into column "account"

<figure><img src="../../../.gitbook/assets/image (335).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"&#x20;

<figure><img src="../../../.gitbook/assets/image (938).png" alt=""><figcaption></figcaption></figure>

* And the user type "Rp.100.000" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (337).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" Into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (429).png" alt=""><figcaption></figcaption></figure>

* And the user choose "martien" into column "approved by"

<figure><img src="../../../.gitbook/assets/image (338).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (339).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Payment Method} is required"

<figure><img src="../../../.gitbook/assets/image (341).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the edit page&#x20;

## PO.2.6 : The system displays the message "Account is required"

* Given User on the page `/finance/point/payment-order`
* And the user already login&#x20;
* And the user already has permission for edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "Edit"

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (1026).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (345).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment method"

<figure><img src="../../../.gitbook/assets/image (344).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "Account"

<figure><img src="../../../.gitbook/assets/image (346).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (347).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Account} is required"

<figure><img src="../../../.gitbook/assets/image (348).png" alt=""><figcaption></figcaption></figure>

* And column notes, amount, and allocation will be disable&#x20;

<figure><img src="../../../.gitbook/assets/image (349).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the edit page&#x20;

## PO.2.7 : The system displays the message "Amount is required"

* Given User on the page `/finance/point/payment-order/1`
* And the user already login&#x20;
* And the user already has permission for edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "Edit"

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (350).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (351).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (352).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into "Form Notes"

<figure><img src="../../../.gitbook/assets/image (939).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban ekspedisi" on the column "Account"

<figure><img src="../../../.gitbook/assets/image (1032).png" alt=""><figcaption></figcaption></figure>

* And the user type "Reimburse biaya ekspedisi" into column "Transaction notes"

<figure><img src="../../../.gitbook/assets/image (940).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "amount"

<figure><img src="../../../.gitbook/assets/image (355).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" Into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (429).png" alt=""><figcaption></figcaption></figure>

* And the user choose approved by "Kartika"

<figure><img src="../../../.gitbook/assets/image (356).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (357).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Amount} is required"

<figure><img src="../../../.gitbook/assets/image (358).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the edit page&#x20;

## PO.2.8 : The system displays the message "Please enter a valid amount using numbers only"

* Given User on the page `/finance/point/payment-order/1`
* And the user already logged in.&#x20;
* And the user already has permission for edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "Edit"

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (359).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (360).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (361).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into "Form Notes"

<figure><img src="../../../.gitbook/assets/image (941).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban ekspedisi" on the column "Account"

<figure><img src="../../../.gitbook/assets/image (1033).png" alt=""><figcaption></figcaption></figure>

* And the user type "Reimburse biaya ekspedisi" into column "Transaction notes"

<figure><img src="../../../.gitbook/assets/image (942).png" alt=""><figcaption></figcaption></figure>

* And the user Type "Test" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (364).png" alt=""><figcaption></figcaption></figure>

* Then the cursor will stop at the "Amount" column&#x20;
* And display the message "Please enter a valid quantity using only numbers."

<figure><img src="../../../.gitbook/assets/image (365).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the edit page&#x20;

## PO.2.9 : The system displays the message "Amount must be greater than zero"

* Given User on the page `/finance/point/payment-order/1`
* And the user already login&#x20;
* And the user already has permission for edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "edit"

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (1027).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (367).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (368).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into "Form Notes"

<figure><img src="../../../.gitbook/assets/image (943).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban ekspedisi" on the column "Account"

<figure><img src="../../../.gitbook/assets/image (1034).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "transaction notes"

<figure><img src="../../../.gitbook/assets/image (944).png" alt=""><figcaption></figcaption></figure>

* And the user type "zero" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (371).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (429).png" alt=""><figcaption></figcaption></figure>

* And the user choose approved by "Kartika"

<figure><img src="../../../.gitbook/assets/image (372).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (373).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "Amount must be greater than zero"

<figure><img src="../../../.gitbook/assets/image (1031).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the edit page&#x20;

## PO.2.10 : The system displays the message "Successfully updated"

* Given User on the page `/finance/point/payment-order/1`
* And the user already login&#x20;
* And the user already have permission for the edit\_payment\_order.&#x20;
* and the user has a form that does not yet have a cash-out or bank out reference
* When user click button "edit"

<figure><img src="../../../.gitbook/assets/image (379).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (1028).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[CUS-100] nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (367).png" alt=""><figcaption></figcaption></figure>

* And the user choose "cash" on column "Payment method"

<figure><img src="../../../.gitbook/assets/image (368).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into column "Form Notes"

<figure><img src="../../../.gitbook/assets/image (945).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban Ekspedisi" into column "account"

<figure><img src="../../../.gitbook/assets/image (1035).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column " Transaction Notes"&#x20;

<figure><img src="../../../.gitbook/assets/image (946).png" alt=""><figcaption></figcaption></figure>



* And the user type "Rp.100.000" into column "Amount"&#x20;

<figure><img src="../../../.gitbook/assets/image (385).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (429).png" alt=""><figcaption></figcaption></figure>

* And the user choose "martien" into column "approved by"

<figure><img src="../../../.gitbook/assets/image (386).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (1036).png" alt=""><figcaption></figcaption></figure>

* And the user click "save"

<figure><img src="../../../.gitbook/assets/image (387).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "Successfully updated"

<figure><img src="../../../.gitbook/assets/image (1045).png" alt=""><figcaption></figcaption></figure>

* And the user should redirect to detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (947).png" alt=""><figcaption></figcaption></figure>

* And approval status payment order should be pending&#x20;

<figure><img src="../../../.gitbook/assets/image (391).png" alt=""><figcaption></figcaption></figure>

* And form status payment order should be pending&#x20;

<figure><img src="../../../.gitbook/assets/image (390).png" alt=""><figcaption></figcaption></figure>

* And the system sent approval to user "Kartika".

<figure><img src="../../../.gitbook/assets/image (393).png" alt=""><figcaption></figcaption></figure>
