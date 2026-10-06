# Database

## Database&#x20;

<table><thead><tr><th>Column Name (database)</th><th>Column Name (frontend)</th><th>Data Type</th><th>Rules</th><th width="224">Sample Data</th></tr></thead><tbody><tr><td>id</td><td></td><td>int(10)</td><td>Autoincreament</td><td>1</td></tr><tr><td>name</td><td>username</td><td>varchar(255)</td><td>unique, not null</td><td>nrainii</td></tr><tr><td>email</td><td>email</td><td>varchar(255)</td><td>unique</td><td>impointhub@gmail.com</td></tr><tr><td>password </td><td>password </td><td>varchar(255)</td><td>Required </td><td>Admin123!</td></tr><tr><td>password confirmation </td><td>password confirmation</td><td>varchar(255)</td><td>Required </td><td>Admin123!</td></tr><tr><td>Role id </td><td>Role </td><td>varchar(255)</td><td>Required </td><td>Administrator  </td></tr><tr><td>created_at</td><td></td><td>timestamp</td><td>Not Null, Default: CURRENT_TIMESTAMP</td><td>07/08/2025 11:46</td></tr><tr><td>updated_at</td><td></td><td>timestamp</td><td>Not Null, Default: CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP</td><td>null</td></tr><tr><td>created_by</td><td></td><td>int(10)</td><td>Not Null, Foreign Key to users(id)</td><td>1</td></tr><tr><td>updated_by</td><td></td><td>int(10)</td><td>Nullable, Foreign Key to users(id)</td><td>null</td></tr><tr><td>Deleted_at</td><td></td><td>datetime</td><td>Not Null, Default: CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP</td><td>null</td></tr><tr><td>Deleted_by</td><td></td><td>int(10)</td><td>Not Null, Foreign Key to users(id)</td><td>1</td></tr></tbody></table>

## Sample Database

| id | name (username) | email                                               | password    | password\_confirmation | role    | created\_at      | updated\_at      | created\_by | updated\_by | deleted\_at      | deleted\_by |
| -- | --------------- | --------------------------------------------------- | ----------- | ---------------------- | ------- | ---------------- | ---------------- | ----------- | ----------- | ---------------- | ----------- |
| 1  | nrainii         | [impointhub@gmail.com](mailto:impointhub@gmail.com) | Admin123!   | Admin123!              | Admin   | 07/08/2025 11:46 | null             | 1           | null        | null             | null        |
| 2  | martien         | [martien@pointhub.co](mailto:martien@pointhub.co)   | Martien123! | Martien123!            | Admin   | 08/08/2025 09:12 | 10/08/2025 14:20 | 1           | 2           | null             | null        |
| 3  | budi            | [budi@pointhub.co](mailto:budi@pointhub.co)         | Budi12345!  | Budi12345!             | Staff   | 09/08/2025 10:05 | null             | 1           | null        | null             | null        |
| 4  | aini            | [aini@pointhub.co](mailto:aini@pointhub.co)         | Aini1234!   | Aini1234!              | Manager | 10/08/2025 08:30 | 12/08/2025 16:45 | 2           | 2           | null             | null        |
| 5  | siti            | [siti@pointhub.co](mailto:siti@pointhub.co)         | Siti12345!  | Siti12345!             | Staff   | 11/08/2025 13:10 | null             | 1           | null        | 20/08/2025 09:00 | 2           |
| 6  | dedi            | [dedi@pointhub.co](mailto:dedi@pointhub.co)         | Dedi12345!  | Dedi12345!             | Manager | 12/08/2025 15:22 | null             | 1           | null        | null             | null        |

## &#x20;

