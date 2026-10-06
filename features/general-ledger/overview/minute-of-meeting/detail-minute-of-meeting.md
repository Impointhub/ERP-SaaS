# Detail Minute of Meeting

## ADR001 — General Ledger Account Selection Flow

#### **Topic :**&#x20;

Flow Pada General Ledger&#x20;

#### Problem Statement

Pada proses penyusunan fitur **General Ledger**, flow pada **Point Hijau** mengikuti flow pada **Point Ungu**.

Berdasarkan evaluasi terhadap flow pada Point Ungu, ditemukan bahwa user dapat memilih **lebih dari satu akun** dalam satu tampilan General Ledger. Kondisi tersebut menyebabkan data dari beberapa akun tercampur, khususnya pada:

* Opening Balance
* Transaction / Movement
* Ending Balance

Akibatnya, nilai opening balance dan ending balance yang ditampilkan dapat merupakan gabungan dari dua akun yang berbeda. Hal ini menyebabkan informasi yang ditampilkan tidak merepresentasikan saldo dan transaksi dari akun secara individual.

Flow existing memungkinkan user memilih dua atau lebih akun sekaligus pada General Ledger.

Contoh:

> User memilih **Account A** dan **Account B** → sistem menampilkan opening balance dan ending balance yang merupakan hasil penggabungan data kedua akun.

Hal tersebut berpotensi menimbulkan interpretasi yang salah karena user tidak dapat memastikan saldo dan transaksi tersebut berasal dari akun mana.

#### Decision

Untuk **V1 / MVP**, General Ledger akan menggunakan **single account selection**.

User hanya dapat memilih **satu akun dalam satu waktu** untuk melihat General Ledger.

Dengan demikian, seluruh informasi yang ditampilkan dalam General Ledger akan memiliki konteks akun yang jelas, meliputi:

* Opening Balance
* Transaction / Movement
* Ending Balance

Fitur untuk memilih dan menampilkan **beberapa akun sekaligus** tidak termasuk dalam scope V1 dan akan dipertimbangkan untuk **V2**.

**V1 / MVP — Included**

* User dapat memilih satu akun.
* General Ledger menampilkan data berdasarkan akun yang dipilih.
* Opening Balance dihitung berdasarkan akun yang dipilih.
* Transaction / Movement hanya berasal dari akun yang dipilih.
* Ending Balance merepresentasikan saldo akun yang dipilih.

**V2 — Future Enhancement**

* User dapat memilih beberapa akun.
* Sistem dapat menampilkan data per akun tanpa mencampurkan saldo antar-akun.
* Jika diperlukan, sistem dapat menyediakan consolidated view untuk beberapa akun dengan logic dan presentation yang secara eksplisit membedakan antara:
  * Individual Account Balance
  * Consolidated Balance

**Expected Outcome**

Dengan penerapan single account selection pada V1:

> **1 Account Selected → 1 Account Context → Accurate Opening Balance → Accurate Transactions → Accurate Ending Balance**

User dapat mengetahui kondisi General Ledger secara benar tanpa risiko data antar-akun tercampur.



## ADR002: Master pada General Ledger Menampilkan Data Customer / Supplier  yang Melakukan Transaksi

#### **Topic**&#x20;

&#x20;Master pada General Ledger Menampilkan Data Person yang Melakukan Transaksi

#### Problem&#x20;

Saat ini, kolom **Master** pada general ledger hanya menampilkan data person (pihak yang terlibat dalam transaksi, misalnya customer/supplier/ekspedisi) ketika akun yang bersangkutan disetting memiliki subledger. Jika akun tidak disetting subledger, kolom Master tidak menampilkan data person tersebut. Hal ini salah, karena user tetap perlu mengetahui siapa pihak yang terlibat dalam setiap transaksi — terlepas dari setting subledger pada akun — agar data general ledger mudah dibaca dan ditelusuri.

#### Decision

Kolom **Master** pada general ledger akan selalu menampilkan data customer/supplier yang terlibat dalam transaksi, tanpa bergantung pada setting subledger di akun.

#### Reasoning

* Mempermudah user membaca data pada general ledger.
* Mengikuti standard accounting, di mana setiap entri jurnal idealnya bisa ditelusuri ke pihak yang terlibat (customer, supplier, ekspedisi, karyawan, dsb).
