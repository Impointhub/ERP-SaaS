# Database Cash Out

## Database Cash&#x20;

### Cash Header&#x20;

<table><thead><tr><th>Kolom</th><th>Kolom Frontend</th><th width="137.77777099609375">Requirement</th><th width="174.2222900390625">Tujuan</th><th>Sample Data</th></tr></thead><tbody><tr><td>id</td><td>— (tidak ditampilkan; digunakan secara internal sebagai key/route record)</td><td>Primary key, auto increment, unsigned integer</td><td>Pengenal unik untuk setiap header transaksi cash </td><td>1, 2, 3, 4, 5</td></tr><tr><td>formulir_id</td><td>Form Number </td><td>Wajib diisi · unsigned int · FK → formulir.id · ON UPDATE cascade · ON DELETE cascade</td><td>Menyimpan nomor form </td><td>CASH-OUT/0001/VIII/26, CASH-IN/0004/VIII/26)</td></tr><tr><td>coa_id</td><td>Cash Account</td><td>Wajib diisi · unsigned int · FK → coa.id · ON UPDATE cascade · ON DELETE cascade</td><td>Akun Chart of Account yang dipakai sebagai akun kas/bank di level header </td><td>10122, 10130</td></tr><tr><td>person_id</td><td>Payment To </td><td>Wajib diisi · unsigned int · FK → person.id (idx: point_finance_cash_person_index) · ON UPDATE restrict · ON DELETE restrict</td><td>Menyimpan data supplier </td><td>501, 502, 503, 504, 505</td></tr><tr><td>payment_flow</td><td>— (bukan field langsung; menentukan kolom List — Received atau Disbursed — tempat nominal baris ini ditampilkan)</td><td>Wajib diisi · string · nilai yang diharapkan: "in" atau "out" (divalidasi di level aplikasi — bukan enum di database)</td><td>Membedakan cash-out (uang keluar/pembayaran) dan cash-in (uang masuk/penerimaan). Menentukan apakah nominal ditampilkan di kolom Disbursed atau Received pada halaman List.</td><td>"out", "out", "in", "out", "in"</td></tr><tr><td>total</td><td>Amount </td><td>Wajib diisi · decimal(16,4)</td><td>Total nominal transaksi — jumlah di level header yang ditampilkan pada halaman List dan Detail.</td><td>310000.0000, 320100.0000, 2500000.0000, 313600.0000, 750000.0000</td></tr></tbody></table>

### Cash Detail&#x20;

<table><thead><tr><th>Kolom</th><th>Kolom Frontend</th><th width="147.5555419921875">Requirement</th><th>Sample Data</th><th>Tujuan</th><th>Catatan</th></tr></thead><tbody><tr><td>id</td><td>— (tidak ditampilkan)</td><td>Primary key, auto increment, unsigned integer</td><td>1, 2, 3, 4, 5</td><td>Pengenal unik untuk setiap baris item dalam satu transaksi cash.</td><td>Digenerate otomatis oleh sistem.</td></tr><tr><td>point_finance_cash_id</td><td>— (tidak ditampilkan langsung; mengelompokkan baris pada tabel line-item)</td><td>Wajib diisi · unsigned int · </td><td>1, 1, 1, 2, 2</td><td>Mengelompok-kan baris item ini di bawah header transaksi induknya — satu header bisa memiliki banyak baris detail (tabel akun yang tampil di halaman Detail).</td><td>Cascade delete — jika header dihapus, seluruh baris detailnya ikut terhapus. Inilah yang membuat halaman Detail bisa menampilkan "account lebih dari satu".</td></tr><tr><td>coa_id</td><td>Account</td><td>Wajib diisi · unsigned int · FK → coa.id · ON UPDATE restrict · ON DELETE restrict</td><td>53101, 53106, 53103, 41001, 53115</td><td>Akun beban/pendapatan spesifik yang dibebankan pada baris item ini (akun per baris, berbeda dari akun kas di header).</td><td>Restrict — akun yang masih dipakai oleh baris detail tidak bisa dihapus.</td></tr><tr><td>allocation_id</td><td>Allocation</td><td>Opsional· autofill dari payment order </td><td>1, 1, 2, (dalam praktiknya nullable untuk baris cash-in — lihat Catatan)</td><td>Alokasi dari setiap pembayaran </td><td>Skema mewajibkan kolom ini NOT NULL, namun pada flow/mockup ada baris cash-in tanpa alokasi ("Without allocation") — perlu dikonfirmasi ke tim backend apakah kolom ini perlu dibuat nullable, atau perlu ada baris placeholder "none" di tabel allocation.</td></tr><tr><td>notes_detail</td><td>Notes</td><td>Opsional · text</td><td>"Testing", "Bensin mobil box kiriman HB Mojokerto", "Pelunasan invoice INV-2201"</td><td>Catatan bebas yang menjelaskan peruntukan baris item ini.</td><td>Tidak ada batas panjang karakter di level database (kolom text).</td></tr><tr><td>amount</td><td>Amount</td><td>Wajib diisi · decimal(16,4)</td><td>100000.0000, 120100.0000, 200000.0000, 2500000.0000, 313600.0000</td><td>Nominal untuk baris item ini secara spesifik.</td><td>Penjumlahan seluruh baris di bawah satu header harus sama dengan point_finance_cash.total pada header tersebut.</td></tr></tbody></table>

## Sample Database&#x20;

### Sample Database Header&#x20;

| id | formulir\_id | coa\_id | person\_id | payment\_flow | total   |
| -- | ------------ | ------- | ---------- | ------------- | ------- |
| 1  | 101          | 10122   | 501        | out           | 310000  |
| 2  | 102          | 10122   | 502        | out           | 320100  |
| 3  | 103          | 10130   | 503        | in            | 2500000 |
| 4  | 104          | 10122   | 504        | out           | 313600  |
| 5  | 105          | 10130   | 505        | in            | 750000  |

### Sample Database Detail&#x20;

| id | point\_finance\_cash\_id | coa\_id | allocation\_id | notes\_detail                         | amount  |
| -- | ------------------------ | ------- | -------------- | ------------------------------------- | ------- |
| 1  | 1                        | 53101   | 1              | Testing                               | 100000  |
| 2  | 1                        | 53103   | 1              | Bensin mobil box                      | 200000  |
| 3  | 1                        | 53107   |                | Pembelian materai                     | 10000   |
| 4  | 2                        | 53106   | 1              | Kiriman HB Magetan                    | 120100  |
| 5  | 2                        | 53103   | 1              | Bensin mobil box kiriman HB Mojokerto | 200000  |
| 6  | 3                        | 41001   |                | Pelunasan invoice INV-2201            | 2500000 |
| 7  | 4                        | 53115   | 2              | Cetak banner 2 toko Lamongan          | 313600  |
| 8  | 5                        | 41001   |                | Pembayaran DP order                   | 750000  |
