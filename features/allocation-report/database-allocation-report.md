# Database Allocation Report

## Database&#x20;

* **Allocation Report**&#x20;

| Column          | Type          | Rules                           | Sample Data  | Tujuan                                 | Notes                                                       | Column Frontend |
| --------------- | ------------- | ------------------------------- | ------------ | -------------------------------------- | ----------------------------------------------------------- | --------------- |
| `id`            | INT           | PK, auto increment, unique      | 1            | Identitas unik data allocation report  | Dibuat otomatis oleh system                                 | -               |
| `formulir_id`   | INT           | Required, FK ke `formulir.id`   | 101          | Menyimpan referensi formulir transaksi | Jika formulir dihapus, data allocation report ikut terhapus | Formulir        |
| `allocation_id` | INT           | Required, FK ke `allocation.id` | 5            | Menyimpan allocation yang digunakan    | Allocation tidak dapat dihapus jika masih digunakan         | Allocation      |
| `amount`        | DECIMAL(16,4) | Required, >= 0                  | 1500000.0000 | Menyimpan nominal allocation           | Maksimal 16 digit dengan 4 angka desimal                    | Amount          |

* **Formulir**&#x20;

| Column        | Type         | Rules                      | Sample Data          | Tujuan                      | Notes                                            | Column Frontend |
| ------------- | ------------ | -------------------------- | -------------------- | --------------------------- | ------------------------------------------------ | --------------- |
| `id`          | INT          | PK, auto increment, unique | 101                  | Identitas formulir          | Digunakan sebagai referensi transaksi            | -               |
| `code`        | VARCHAR      | Required, unique           | FRM-001              | Nomor/kode formulir         | Tidak boleh duplicate                            | Form Number     |
| `date`        | DATE         | Required                   | 2026-08-20           | Menyimpan tanggal transaksi | Mengikuti tanggal transaksi                      | Date            |
| `description` | VARCHAR/TEXT | Optional                   | Pembelian bahan baku | Keterangan transaksi        | Bisa kosong jika tidak diperlukan                | Description     |
| `status`      | VARCHAR/ENUM | Required                   | Done                 | Status formulir             | Nilai mengikuti status yang tersedia pada sistem | Status          |

* Allocation&#x20;

| Column        | Type         | Rules                      | Sample Data           | Tujuan                 | Notes                                                          | Column Frontend |
| ------------- | ------------ | -------------------------- | --------------------- | ---------------------- | -------------------------------------------------------------- | --------------- |
| `id`          | INT          | PK, auto increment, unique | 5                     | Identitas allocation   | Digunakan sebagai referensi allocation                         | -               |
| `code`        | VARCHAR      | Required, unique           | AL-001                | Kode allocation        | Tidak boleh duplicate                                          | Allocation Code |
| `name`        | VARCHAR      | Required                   | Marketing             | Nama allocation        | Wajib diisi                                                    | Allocation Name |
| `description` | TEXT         | Optional                   | Budget marketing 2026 | Menjelaskan allocation | Opsional                                                       | Description     |
| `status`      | VARCHAR/ENUM | Required                   | Active                | Status allocation      | Allocation inactive tidak dapat digunakan untuk transaksi baru | Status          |

## Sample Database&#x20;

* Allocation Report&#x20;

| id | formulir\_id | allocation\_id |         amount |
| -: | -----------: | -------------: | -------------: |
|  1 |          101 |              5 | 1,500,000.0000 |
|  2 |          102 |              5 | 2,000,000.0000 |
|  3 |          103 |              8 |   750,000.0000 |
|  4 |          104 |             10 | 3,250,000.0000 |
|  5 |          105 |              8 | 1,250,000.0000 |

* Formulir&#x20;

|  id | code    | date       | description          | status |
| --: | ------- | ---------- | -------------------- | ------ |
| 101 | FRM-001 | 2026-08-01 | Pembelian bahan baku | Done   |
| 102 | FRM-002 | 2026-08-03 | Pembayaran supplier  | Done   |
| 103 | FRM-003 | 2026-08-05 | Biaya operasional    | Done   |
| 104 | FRM-004 | 2026-08-10 | Pembelian sparepart  | Done   |
| 105 | FRM-005 | 2026-08-15 | Biaya transportasi   | Done   |

* Allocation&#x20;

| id | code   | name           | description             | status |
| -: | ------ | -------------- | ----------------------- | ------ |
|  5 | AL-001 | Marketing      | Budget marketing 2026   | Active |
|  8 | AL-002 | Operational    | Budget operational 2026 | Active |
| 10 | AL-003 | Sparepart      | Budget sparepart mesin  | Active |
| 11 | AL-004 | Transportation | Budget transportasi     | Active |
| 12 | AL-005 | Office         | Budget kebutuhan kantor | Active |

