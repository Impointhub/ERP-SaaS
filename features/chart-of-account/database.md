# Database

#### 1. Database

<table><thead><tr><th width="132.20001220703125">Column</th><th>Column Frontend</th><th>Rules</th><th>Sample Data</th><th width="173.5999755859375">Tujuan</th><th>Notes</th></tr></thead><tbody><tr><td>ID</td><td>-</td><td>Autoincreament</td><td>1</td><td>Memberikan ID pada chart of account</td><td></td></tr><tr><td>Main Category</td><td>Main Category</td><td>Required</td><td>Asset</td><td>Untuk Mapping chart of account pada setiap laporan akuntansi</td><td>Main category chart of account terdiri : Asset, Hutang, Modal, Pendapatan, Biaya</td></tr><tr><td>Major Group</td><td>Major Group</td><td>Required</td><td>Current Asset</td><td>Untuk mapping chart of account pada laporan akuntansi seperti : laba rugi, neraca</td><td></td></tr><tr><td>Account Number</td><td>Account Number</td><td>Required, unique</td><td>101</td><td>Memberikan kode pada chart of account dan setiap kode harus unique.</td><td></td></tr><tr><td>Account Name</td><td>Account Number</td><td>Required</td><td>Cash musi</td><td>Memberikan nama pada chart of account</td><td></td></tr><tr><td>Cash Account</td><td>Cash Account</td><td>Bolean</td><td>True</td><td>Memberikan penanda bahwa akun merupakan akun kas yang dibaca pada cashflow</td><td></td></tr><tr><td>Balance Normal</td><td>Balance Normal</td><td>Required</td><td>Debit</td><td>Memberikan informasi posisi normal balance account</td><td>Position COA : Debit, Kredit</td></tr><tr><td>Cashflow category</td><td>Balance Normal</td><td>Option</td><td>Null</td><td>Memberikan informasi category cashflow pada setiap account</td><td>Jika coa cash account maka tidak bisa memilih cash flow category</td></tr><tr><td>Ancestors</td><td></td><td></td><td>1,6,10</td><td>Jalur group dari paling atas sampai group tempat akun berada.<br></td><td><h4>Cara Membaca Ancestors di COA</h4><p>Contoh: <strong>101 Cash Besar</strong>, Ancestors <code>1,6,9</code>, COA Group ID <code>9</code>.</p><p>Dibaca dari kiri: <strong>Asset (1) → Cash &#x26; Bank (6) → Petty Cash (9)</strong>. Artinya akun Cash Besar ada di group Petty Cash, yang ada di Cash &#x26; Bank, yang ada di Asse</p></td></tr><tr><td>Coa group ID</td><td></td><td></td><td>10</td><td>untuk menampilkan relasi dengan table group coa</td><td></td></tr></tbody></table>

#### 2. Sample Database

| ID | Main Category | Major Group           | Account Number | Account Name                   | Cash Account | Balance Normal | Cashflow Category  | Ancestors | COA Group ID |
| -- | ------------- | --------------------- | -------------- | ------------------------------ | ------------ | -------------- | ------------------ | --------- | ------------ |
| 1  | Asset         | Current Asset         | 101            | Cash Besar                     | TRUE         | Debit          | NULL               | 1,6,10    | 10           |
| 2  | Asset         | Current Asset         | 102            | Bank BCA                       | TRUE         | Debit          | NULL               | 1,6,10    | 10           |
| 3  | Asset         | Current Asset         | 103            | Piutang Usaha                  | FALSE        | Debit          | Operating Activity | 1,6,11    | 11           |
| 4  | Asset         | Fixed Asset           | 201            | Kendaraan Operasional          | FALSE        | Debit          | Investing Activity | 1,7,12    | 12           |
| 5  | Asset         | Fixed Asset           | 202            | Akumulasi Penyusutan Kendaraan | FALSE        | Kredit         | NULL               | 1,7,12    | 12           |
| 6  | Hutang        | Current Liability     | 301            | Hutang Usaha                   | FALSE        | Kredit         | Operating Activity | 2,8,13    | 13           |
| 7  | Hutang        | Long Term Liability   | 302            | Hutang Bank Jangka Panjang     | FALSE        | Kredit         | Financing Activity | 2,9,14    | 14           |
| 8  | Modal         | Equity                | 401            | Modal Pemilik                  | FALSE        | Kredit         | Financing Activity | 3,15      | 15           |
| 9  | Pendapatan    | Revenue               | 501            | Pendapatan Penjualan           | FALSE        | Kredit         | Operating Activity | 4,16      | 16           |
| 10 | Pendapatan    | Other Revenue         | 502            | Pendapatan Bunga Bank          | FALSE        | Kredit         | Operating Activity | 4,17      | 17           |
| 11 | Biaya         | Operating Expense     | 601            | Biaya Gaji                     | FALSE        | Debit          | Operating Activity | 5,18      | 18           |
| 12 | Biaya         | Operating Expense     | 602            | Biaya Listrik & Air            | FALSE        | Debit          | Operating Activity | 5,18      | 18           |
| 13 | Biaya         | Non Operating Expense | 603            | Biaya Bunga Bank               | FALSE        | Debit          | Financing Activity | 5,19      | 19           |

#### List Main Category Asset

| Category Name |
| ------------- |
| Asset         |
| Liabilities   |
| Equity        |
| Income        |
| Expenses      |

#### List Major Category

| Main Category | Major Category           |
| ------------- | ------------------------ |
| Asset         | Current Asset            |
|               | Fixed Asset              |
|               | Non current Asset        |
|               | Intangible Asset         |
|               | Other Asset              |
|               | Accumulated Depreciation |
| Liability     | Current Liability        |
|               | Long Term Liability      |
|               | Tax Liability            |
|               | Other Liability          |
| Equity        | Owner Equity             |
|               | Capital                  |
|               | Retained Earnings        |
|               | Current year earnings    |
|               | Dividend                 |
| Revenue       | Operating Income         |
|               | Service Income           |
|               | Other Revenue            |
|               | Cost of good sales       |
|               | Interest revenue         |
| Expense       | Operating Expense        |
|               | Marketing Expense        |
|               | Factory Overhead         |
|               | Other Expense            |
|               | Office Expense           |
