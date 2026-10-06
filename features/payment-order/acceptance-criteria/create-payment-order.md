# Create Payment Order

## PO.1.1 :  User redirect to login page

* `GIVEN` user visit `/finance/point/payment-order` url without signin
* `THEN` user redirected to `Sign In` page

<figure><img src="../../../.gitbook/assets/▶ COA Form Plan for CRUD UI.png" alt=""><figcaption></figcaption></figure>

## PO.1.2 :  Redirect to the forbidden page

* Given user is logged in
* And the user does not have permission to create a payment order
* When user type `/finance/point/payment-order` url into browser&#x20;
* Then user redirected to forbidden page&#x20;

<figure><img src="../../../.gitbook/assets/image (932).png" alt=""><figcaption></figcaption></figure>

## PO.1.3 : The system displays the message "Payment to is required"

* Given User on the page `/finance/point/payment-order`
* And the user already login&#x20;
* And the user already have permission for the create\_payment\_order.&#x20;
* When user click button "Create"

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (260).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "Payment to"

<figure><img src="../../../.gitbook/assets/image (261).png" alt=""><figcaption></figcaption></figure>

* And the user choose "cash" on column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (262).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into column "Form Notes"

<figure><img src="../../../.gitbook/assets/image (952).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban Ekspedisi" into column "account"

<figure><img src="../../../.gitbook/assets/image (264).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"&#x20;

<figure><img src="../../../.gitbook/assets/image (953).png" alt=""><figcaption></figcaption></figure>

* And the user type "Rp.100.000" into column "Amount"&#x20;

<figure><img src="../../../.gitbook/assets/image (266).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" Into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (423).png" alt=""><figcaption></figcaption></figure>

* And the user choose "kartika" into column "Approved By"

<figure><img src="../../../.gitbook/assets/image (267).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (268).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Payment To} is required"

<figure><img src="../../../.gitbook/assets/image (242).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the create page&#x20;

## PO.1.4 : The system displays the message "Payment method is required"

* Given User on the page `/finance/point/payment-order`
* And the user already login&#x20;
* And the user already have permission for the create\_payment\_order.&#x20;
* When user click button "Create"
* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (271).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "Payment method"

<figure><img src="../../../.gitbook/assets/image (272).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into column "Form Notes"

<figure><img src="../../../.gitbook/assets/image (954).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban Ekspedisi" into column "account"

<figure><img src="../../../.gitbook/assets/image (275).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"&#x20;

<figure><img src="../../../.gitbook/assets/image (955).png" alt=""><figcaption></figcaption></figure>

* And the user type "Rp.100.000" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (276).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" Into column " Allocation"

<figure><img src="../../../.gitbook/assets/image (424).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Martien" into column "Approved by"

<figure><img src="../../../.gitbook/assets/image (277).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (278).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Payment Method} is required"

<figure><img src="../../../.gitbook/assets/image (243).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the create page&#x20;

## PO.1.5 : The system displays the message "Account is required"

* Given User on the page `/finance/point/payment-order`
* And the user already login&#x20;
* And the user already has permission for create\_payment\_order.&#x20;
* When user click button "Create"
* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (280).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment method"

<figure><img src="../../../.gitbook/assets/image (281).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "Account"

<figure><img src="../../../.gitbook/assets/image (282).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (283).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Account} is required"

<figure><img src="../../../.gitbook/assets/image (240).png" alt=""><figcaption></figcaption></figure>

* And column transaction notes, amount, and allocation will be disable&#x20;

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the create page&#x20;

## PO.1.6 : The system displays the message "Amount is required"

* Given User on the page [https://test.app.point.red/finance/point/payment-order](https://test.app.point.red/finance/point/payment-order)
* And the user already login&#x20;
* And the user already has permission for create\_payment\_order.&#x20;
* When user click button "Create"
* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (285).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (286).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (287).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into "Form Notes"

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban ekspedisi" on the column "Account"

<figure><img src="../../../.gitbook/assets/image (289).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column " Transaction Notes"

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* And the user leave empty column "amount"

<figure><img src="../../../.gitbook/assets/image (290).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" on the "Allocation" column&#x20;

<figure><img src="../../../.gitbook/assets/image (425).png" alt=""><figcaption></figcaption></figure>

* And the user choose approved by "Kartika"

<figure><img src="../../../.gitbook/assets/image (291).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (292).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "{Amount} is required"

<figure><img src="../../../.gitbook/assets/image (245).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the create page&#x20;

## PO.1.7 : The system displays the message "Please enter a valid amount using numbers only"

* Given User on the page `/finance/point/payment-order`
* And the user already logged in.&#x20;
* And the user already has permission for create\_payment\_order.&#x20;
* When user click button "Create"
* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (294).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (295).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (296).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into " Form Notes"

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban ekspedisi" on the column "Account"

<figure><img src="../../../.gitbook/assets/image (298).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

* And the user Type "Test" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (299).png" alt=""><figcaption></figcaption></figure>

* Then the cursor will stop at the "Amount" column&#x20;
* And display the message "Please enter a valid quantity using only numbers."

<figure><img src="../../../.gitbook/assets/image (246).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the create page&#x20;

## PO.1.8 : The system displays the message "Amount must be greater than zero"

* Given User on the page `/finance/point/payment-order`
* And the user already login&#x20;
* And the user already has permission for create\_payment\_order.&#x20;
* When user click button "Create"
* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[Cust-100]-Nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (301).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Cash" on the column "Payment Method"

<figure><img src="../../../.gitbook/assets/image (302).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into " Form Notes"

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban ekspedisi" on the column "Account"

<figure><img src="../../../.gitbook/assets/image (304).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

* And the user type "zero" into column "Amount"

<figure><img src="../../../.gitbook/assets/image (305).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" on the column "Allocation"

<figure><img src="../../../.gitbook/assets/image (427).png" alt=""><figcaption></figcaption></figure>

* And the user choose approved by "Kartika"

<figure><img src="../../../.gitbook/assets/image (306).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (307).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "Amount must be greater than zero"

<figure><img src="../../../.gitbook/assets/image (1030).png" alt=""><figcaption></figcaption></figure>

* And the user should remain on the create page&#x20;

## PO.1.9 : The system displays the message "Successfully created"

* Given User on the page `/finance/point/payment-order`
* And the user already login&#x20;
* And the user already have permission for the create\_payment\_order.&#x20;
* When user click button "Create"
* And the user type "2026-06-25" into "Payment Date"

<figure><img src="../../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>

* And the user choose "\[CUS-100] nganjuk" on the column "Payment To"

<figure><img src="../../../.gitbook/assets/image (309).png" alt=""><figcaption></figcaption></figure>

* And the user choose "cash" on column "Payment type"

<figure><img src="../../../.gitbook/assets/image (310).png" alt=""><figcaption></figcaption></figure>

* And the user type "Pembayaran customer" into column "Form Notes"

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Beban Ekspedisi" into column "account"

<figure><img src="../../../.gitbook/assets/image (312).png" alt=""><figcaption></figcaption></figure>

* And the user type "reimburse biaya ekspedisi" into column "Transaction Notes"&#x20;

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

* And the user type "Rp.100.000" into column "Amount"&#x20;

<figure><img src="../../../.gitbook/assets/image (314).png" alt=""><figcaption></figcaption></figure>

* And the user choose "Project A" into column "Allocation"

<figure><img src="../../../.gitbook/assets/image (429).png" alt=""><figcaption></figcaption></figure>

* And the user choose "kartika" into column "approved by"

<figure><img src="../../../.gitbook/assets/image (315).png" alt=""><figcaption></figcaption></figure>

* And the user click "review"&#x20;

<figure><img src="../../../.gitbook/assets/image (249).png" alt=""><figcaption></figcaption></figure>

* And the user click "save"

<figure><img src="../../../.gitbook/assets/image (933).png" alt=""><figcaption></figcaption></figure>

* Then user can view message "Successfully created"

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

* And the user should redirect to detail page&#x20;

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* And approval status payment order should be pending&#x20;

<figure><img src="../../../.gitbook/assets/image (318).png" alt=""><figcaption></figcaption></figure>

* And form status payment order should be pending&#x20;

<figure><img src="../../../.gitbook/assets/image (319).png" alt=""><figcaption></figcaption></figure>

* And the system sent approval to user "kartika"

<figure><img src="../../../.gitbook/assets/image (320).png" alt=""><figcaption></figcaption></figure>





