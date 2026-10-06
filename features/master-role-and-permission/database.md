# Database

## Database

### Table: `roles`

| Column       | Column Frontend | Requirement                                                                  | Sample Data      | Notes                                                           |
| ------------ | --------------- | ---------------------------------------------------------------------------- | ---------------- | --------------------------------------------------------------- |
| id           | —               | int(10), PK, Autoincrement                                                   | 1                | Primary key, tidak ditampilkan/diedit di UI                     |
| name         | NAME            | varchar(255), unique, not null                                               | ADMINISTRATOR 1  | Ditampilkan di List, Create, Edit, dan Detail Role              |
| created\_at  | —               | timestamp, not null, default CURRENT\_TIMESTAMP                              | 05/08/2025 09:00 | Diisi otomatis oleh sistem saat role dibuat                     |
| updated\_at  | —               | timestamp, nullable, default CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP | null             | Terisi otomatis saat role diedit; null jika belum pernah diedit |
| created\_by  | —               | int(10), not null, FK to users(id)                                           | 1                | Mencatat user yang membuat role                                 |
| updated\_by  | —               | int(10), nullable, FK to users(id)                                           | null             | Mencatat user yang terakhir mengedit role                       |
| archived\_at | —               | datetime, nullable                                                           | null             | Timestamp soft-delete; terisi saat role dihapus (RLD.5)         |
| archived\_by | —               | int(10), nullable, FK to users(id)                                           | null             | Mencatat user yang menghapus role                               |

***

### Table: `permissions`

| Column      | Column (Frontend) | Requirement                                     | Sample Data      | Notes                                                                                    |
| ----------- | ----------------- | ----------------------------------------------- | ---------------- | ---------------------------------------------------------------------------------------- |
| id          | —                 | int(10), PK, Autoincrement                      | 1                | Primary key, tidak ditampilkan/diedit di UI                                              |
| name        | PERMISSION NAME   | varchar(255), unique, not null                  | MENU ACCOUNTING  | Ditampilkan sebagai baris checkbox di halaman Set Permission                             |
| created\_at | —                 | timestamp, not null, default CURRENT\_TIMESTAMP | 01/08/2025 08:00 | Diisi otomatis saat data permission dibuat (biasanya seed data/master, bukan input user) |
| updated\_at | —                 | timestamp, nullable                             | null             | Terisi jika nama permission pernah diubah                                                |

***

### Table: `role_has_permissions` (pivot)

| Column         | Column (Frontend) | Requirement                                     | Sample Data      | Notes                                                         |
| -------------- | ----------------- | ----------------------------------------------- | ---------------- | ------------------------------------------------------------- |
| id             | —                 | int(10), PK, Autoincrement                      | 1                | Primary key, tidak ditampilkan/diedit di UI                   |
| role\_id       | —                 | int(10), not null, FK to roles(id)              | 1                | Menentukan role mana yang memiliki permission ini             |
| permission\_id | —                 | int(10), not null, FK to permissions(id)        | 1                | Menentukan permission mana yang dimiliki role                 |
| created\_at    | —                 | timestamp, not null, default CURRENT\_TIMESTAMP | 05/08/2025 09:05 | Diisi saat checkbox permission dicentang dan disimpan (RSP.2) |

## Sample Database&#x20;

Karena `permissions` di role itu **array of string**, secara relasional ini butuh 3 tabel: `roles`, `permissions`, dan tabel pivot `role_has_permissions` (many-to-many) — bukan satu kolom array, supaya konsisten dengan flow **Set Permission** yang sudah kita buat sebelumnya (checkbox per menu).

### Struktur Database

#### Table: `roles`

| Column       | Data Type    | Rules                                                              |
| ------------ | ------------ | ------------------------------------------------------------------ |
| id           | int(10)      | PK, Autoincrement                                                  |
| name         | varchar(255) | unique, not null                                                   |
| created\_at  | timestamp    | Not Null, Default: CURRENT\_TIMESTAMP                              |
| updated\_at  | timestamp    | Nullable, Default: CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP |
| created\_by  | int(10)      | Not Null, Foreign Key to users(id)                                 |
| updated\_by  | int(10)      | Nullable, Foreign Key to users(id)                                 |
| archived\_at | datetime     | Nullable                                                           |
| archived\_by | int(10)      | Nullable, Foreign Key to users(id)                                 |

#### Table: `permissions`

| Column      | Data Type    | Rules                                                              |
| ----------- | ------------ | ------------------------------------------------------------------ |
| id          | int(10)      | PK, Autoincrement                                                  |
| name        | varchar(255) | unique, not null                                                   |
| created\_at | timestamp    | Not Null, Default: CURRENT\_TIMESTAMP                              |
| updated\_at | timestamp    | Nullable, Default: CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP |

#### Table: `role_has_permissions` (pivot)

| Column         | Data Type | Rules                                    |
| -------------- | --------- | ---------------------------------------- |
| id             | int(10)   | PK, Autoincrement                        |
| role\_id       | int(10)   | Not Null, Foreign Key to roles(id)       |
| permission\_id | int(10)   | Not Null, Foreign Key to permissions(id) |
| created\_at    | timestamp | Not Null, Default: CURRENT\_TIMESTAMP    |

***

### Sample Data

**`roles`**

| id | name                  | created\_at      | updated\_at      | created\_by | updated\_by | archived\_at | archived\_by |
| -- | --------------------- | ---------------- | ---------------- | ----------- | ----------- | ------------ | ------------ |
| 1  | ADMINISTRATOR 1       | 05/08/2025 09:00 | null             | 1           | null        | null         | null         |
| 2  | AUDIT KAS BESAR       | 06/08/2025 10:30 | null             | 1           | null        | null         | null         |
| 3  | ROLE MIRNA            | 07/08/2025 11:15 | 12/08/2025 14:00 | 1           | 2           | null         | null         |
| 4  | VIEWER AND APPROVE SO | 08/08/2025 13:20 | null             | 2           | null        | null         | null         |

**`permissions`**

| id | name            | created\_at      | updated\_at |
| -- | --------------- | ---------------- | ----------- |
| 1  | MENU ACCOUNTING | 01/08/2025 08:00 | null        |
| 2  | MENU FACILITY   | 01/08/2025 08:00 | null        |
| 3  | MENU INVENTORY  | 01/08/2025 08:00 | null        |
| 4  | MENU MASTER     | 01/08/2025 08:00 | null        |
| 5  | MENU SALES      | 01/08/2025 08:00 | null        |

**Permission yang dibutuhkan :**&#x20;

| Module         | Feature                | Permission                                   |
| -------------- | ---------------------- | -------------------------------------------- |
| Authentication | Sign In                | Access                                       |
| Authentication | Reset Password         | Access                                       |
| Authentication | Forgot Password        | Access                                       |
| Authentication | Sign Out               | Access                                       |
| Authentication | Verification Email     | Access                                       |
| Master         | User                   | Access, Create, Read, Edit, Delete           |
| Master         | Role                   | Access, Create, Read, Edit, Delete           |
| Master         | Permission             | Access, Create, Read, Edit, Delete           |
| Master         | Supplier               | Access, Create, Read, Edit, Delete           |
| Master         | Supplier Group         | Access, Create, Read, Edit, Delete           |
| Master         | Customer               | Access, Create, Read, Edit, Delete           |
| Master         | Customer Group         | Access, Create, Read, Edit, Delete           |
| Master         | Employee               | Access, Create, Read, Edit, Delete           |
| Master         | Expedition             | Access, Create, Read, Edit, Delete           |
| Master         | Chart of Account       | Access, Create, Read, Edit, Delete           |
| Master         | Group Chart of Account | Access, Create, Read, Edit, Delete           |
| Master         | Allocation             | Access, Create, Read, Edit, Delete           |
| Finance        | Payment Order          | Access, Create, Read, Edit, Delete, Approval |
| Finance        | Cash                   | Access                                       |
| Finance        | Cash In                | Access, Create, Read, Delete                 |
| Finance        | Cash Out               | Access, Create, Read, Delete                 |
| Finance        | Bank                   | Access                                       |
| Finance        | Bank In                | Access, Create, Read, Delete                 |
| Finance        | Bank Out               | Access, Create, Read,Delete                  |
| Finance        | Allocation Report      | Access, Read, Export                         |
| Finance        | Bank Report            | Access, Read, Export                         |
| Finance        | Cash Report            | Access, Read, Export                         |
| Finance        | Subledger              | Access, Read, Export                         |
| Finance        | General Ledger         | Access, Read, Export                         |





**`role_has_permissions`**

| id | role\_id                  | permission\_id      | created\_at      |
| -- | ------------------------- | ------------------- | ---------------- |
| 1  | 1 (ADMINISTRATOR 1)       | 1 (MENU ACCOUNTING) | 05/08/2025 09:05 |
| 2  | 1 (ADMINISTRATOR 1)       | 2 (MENU FACILITY)   | 05/08/2025 09:05 |
| 3  | 1 (ADMINISTRATOR 1)       | 3 (MENU INVENTORY)  | 05/08/2025 09:05 |
| 4  | 1 (ADMINISTRATOR 1)       | 4 (MENU MASTER)     | 05/08/2025 09:05 |
| 5  | 1 (ADMINISTRATOR 1)       | 5 (MENU SALES)      | 05/08/2025 09:05 |
| 6  | 2 (AUDIT KAS BESAR)       | 1 (MENU ACCOUNTING) | 06/08/2025 10:35 |
| 7  | 3 (ROLE MIRNA)            | 4 (MENU MASTER)     | 07/08/2025 11:20 |
| 8  | 4 (VIEWER AND APPROVE SO) | 5 (MENU SALES)      | 08/08/2025 13:25 |
