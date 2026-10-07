# Database

1. Database group

<table><thead><tr><th width="132.20001220703125">Column</th><th width="128">Column Frontend</th><th width="162.4000244140625">Rules</th><th>Sample Data</th><th width="289.60003662109375">Notes</th></tr></thead><tbody><tr><td>ID</td><td>-</td><td>Autoincreament</td><td>1</td><td>-</td></tr><tr><td>Main category</td><td>Main category</td><td>Required</td><td>Asset</td><td>Main category hanya memiliki 5 opsi yaitu : Asset, Liability, Equity, Income, Expense.</td></tr><tr><td>Major category</td><td>Major category</td><td>Required</td><td>Current Asset</td><td>Major Category terdiri dari :<br><br>1. Asset : current asset, fixed asset.<br>2. Liability : current liability, long term liability<br>3. Equity : Owner capital, retained earning<br>4. Expense : Operating expense, Non Operating , Cost of good sales<br>5. Income/Revenue : Operating income,Non Operating Income.<br></td></tr><tr><td>Parent id</td><td>-</td><td>-</td><td>1</td><td>menunjukkan group ini berada <strong>langsung di bawah group yang mana. contoh :</strong> <br><strong>Asset -> cash bank (parent id = asset) -> bank account (parent id = cash bank)</strong></td></tr><tr><td>Ancestors</td><td>-</td><td>-</td><td>1,6,8</td><td>menunjukkan <strong>seluruh jalur</strong> dari group paling atas sampai ke group itu. <strong>contoh :</strong> <br>Asset (1) -> cash and bank (6) -> bank account (8)</td></tr><tr><td>Group code</td><td>Group code</td><td>Required, unique</td><td>Bank</td><td>Diperoleh dari master kategori</td></tr><tr><td>Group name</td><td>Group name</td><td>Required</td><td>Bank Lioni</td><td>Unique</td></tr><tr><td>Sort order</td><td>-</td><td></td><td>3</td><td>untuk menampilkan dari subgroup berada pada level berapa</td></tr></tbody></table>

2. Sample Database

| ID | Main Category | Major Category        | Parent ID | Ancestors | Group Code | Group Name            | Sort Order |
| -- | ------------- | --------------------- | --------- | --------- | ---------- | --------------------- | ---------- |
| 1  | Asset         | Current Asset         | NULL      | 1         | AST        | Asset                 | 1          |
| 2  | Liability     | Current Liability     | NULL      | 2         | LIA        | Liability             | 1          |
| 3  | Equity        | Owner Capital         | NULL      | 3         | EQT        | Equity                | 1          |
| 4  | Income        | Operating Income      | NULL      | 4         | INC        | Income                | 1          |
| 5  | Expense       | Operating Expense     | NULL      | 5         | EXP        | Expense               | 1          |
| 6  | Asset         | Current Asset         | 1         | 1,6       | CASH       | Cash & Bank           | 2          |
| 7  | Asset         | Current Asset         | 1         | 1,7       | REC        | Account Receivable    | 2          |
| 8  | Asset         | Current Asset         | 6         | 1,6,8     | BANK       | Bank Account          | 3          |
| 9  | Asset         | Current Asset         | 6         | 1,6,9     | PETTY      | Petty Cash            | 3          |
| 10 | Asset         | Fixed Asset           | 1         | 1,10      | FIXED      | Fixed Asset           | 2          |
| 11 | Asset         | Fixed Asset           | 10        | 1,10,11   | VEH        | Vehicle               | 3          |
| 12 | Asset         | Fixed Asset           | 10        | 1,10,12   | BUILD      | Building              | 3          |
| 13 | Liability     | Current Liability     | 2         | 2,13      | AP         | Account Payable       | 2          |
| 14 | Liability     | Long Term Liability   | 2         | 2,14      | LOAN       | Bank Loan             | 2          |
| 15 | Equity        | Owner Capital         | 3         | 3,15      | CAPITAL    | Owner Capital         | 2          |
| 16 | Equity        | Retained Earnings     | 3         | 3,16      | RETAIN     | Retained Earnings     | 2          |
| 17 | Income        | Operating Income      | 4         | 4,17      | SALES      | Sales Revenue         | 2          |
| 18 | Income        | Non Operating Income  | 4         | 4,18      | OTHERINC   | Other Income          | 2          |
| 19 | Expense       | Operating Expense     | 5         | 5,19      | OPEX       | Operating Expense     | 2          |
| 20 | Expense       | Cost of Goods Sold    | 5         | 5,20      | COGS       | Cost of Goods Sold    | 2          |
| 21 | Expense       | Non Operating Expense | 5         | 5,21      | NONOPEX    | Non Operating Expense | 2          |
| 22 | Expense       | Operating Expense     | 19        | 5,19,22   | SALARY     | Salary Expense        | 3          |
| 23 | Expense       | Operating Expense     | 19        | 5,19,23   | UTIL       | Utility Expense       | 3          |
