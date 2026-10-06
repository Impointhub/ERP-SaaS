# Master Supplier

## Database&#x20;

| Column Name  | Column Frontend | Data Type    | Rules                                                              | Sample                                                                                        | Keterangan                                  |
| ------------ | --------------- | ------------ | ------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- | ------------------------------------------- |
| id           |                 | int(10)      | Autoincrement, Primary Key                                         | 1                                                                                             | Untuk menambahkan id atas data supplier     |
| code         | Code            | varchar(191) | Nullable, Unique                                                   | "SUP-001"                                                                                     | Untuk menambahkan kode unique atas supplier |
| name         | Name            | varchar(191) | Not Null                                                           | "PT. Sumber Makmur"                                                                           | Untuk menambahkan nama supplier             |
| address      | Address         | varchar(191) | Nullable                                                           | "Jl. Sudirman No.10"                                                                          | Untuk menambahkan alamat supplier           |
| phone        | Phone           | varchar(50)  | Nullable                                                           | "021-12345678"                                                                                | Untuk menambahkan nomor telp supplier       |
| email        | Email           | varchar(191) | Nullable                                                           | ["](mailto:info@sumbermakmur.co.id)[info@sumbermakmur.co.id](mailto:info@sumbermakmur.co.id)" | Untuk menambahkan email supplier            |
| notes        |                 | text         | Nullable                                                           | "Supplier utama untuk bahan baku"                                                             | Untuk menambahkan keterangan supplier       |
| created\_by  |                 | int(10)      | Foreign Key → users(id), Nullable, onDelete: restrict              | 1                                                                                             |                                             |
| updated\_by  |                 | int(10)      | Foreign Key → users(id), Nullable, onDelete: restrict              | 2                                                                                             |                                             |
| archived\_by |                 | int(10)      | Foreign Key → users(id), Nullable, onDelete: restrict              | 3                                                                                             |                                             |
| created\_at  |                 | timestamp    | Not Null, Default: CURRENT\_TIMESTAMP                              | 2025-08-19 19:00                                                                              |                                             |
| updated\_at  |                 | timestamp    | Not Null, Default: CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP | 2025-08-19 19:05                                                                              |                                             |
| archived\_at |                 | timestamp    | Nullable                                                           | 2025-08-20 10:00                                                                              |                                             |

## Sample Database&#x20;

| id | code    | name              | address                       | phone        | email                                                     | notes                     | created\_by | updated\_by | archived\_by | created\_at         | updated\_at         | archived\_at        |
| -- | ------- | ----------------- | ----------------------------- | ------------ | --------------------------------------------------------- | ------------------------- | ----------- | ----------- | ------------ | ------------------- | ------------------- | ------------------- |
| 1  | SUP-001 | PT. Sumber Makmur | Jl. Sudirman No.10 Surabaya   | 021-12345678 | [info@sumbermakmur.co.id](mailto:info@sumbermakmur.co.id) | Supplier utama bahan baku | 1           | 1           | NULL         | 2025-08-19 19:00:00 | 2025-08-19 19:00:00 | NULL                |
| 2  | SUP-002 | PT. Berkah Abadi  | Jl. Pemuda No.15 Surabaya     | 031-888777   | [sales@berkahabadi.com](mailto:sales@berkahabadi.com)     | Supplier kemasan produk   | 1           | 2           | NULL         | 2025-08-19 19:10:00 | 2025-08-19 19:20:00 | NULL                |
| 3  | SUP-003 | CV. Jaya Sentosa  | Jl. Ahmad Yani No.25 Sidoarjo | 031-777666   | [admin@jayasentosa.co.id](mailto:admin@jayasentosa.co.id) | Supplier cadangan         | 1           | 2           | 3            | 2025-08-19 19:30:00 | 2025-08-19 19:40:00 | 2025-08-20 10:00:00 |
