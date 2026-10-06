# Database

## Database&#x20;

| Database    | Column Frontend | Rules              | Sample database    | Tujuan                                                               |
| ----------- | --------------- | ------------------ | ------------------ | -------------------------------------------------------------------- |
| Id          | -               | Auto increament    | 1                  | Memberikan id pada data allocation                                   |
| Name        | Name            | Required, unique   | Project A          | Memberikan nama alokasi yang akan dipanggil pada laporan alokasi     |
| Created by  |                 | foreign key {user} | Aini               | Memberikan informasi nama user yang membuat data allocation          |
| Updated by  |                 | foreign key {user} | kartika            | Memberikan informasi nama user yang update data allocation           |
| Deleted by  |                 | foreign key {user} | kartika            | Memberikan infromasi nama user yang delete data allocation           |
| Created at  |                 | Timestamp          | 07 July 2026 17:00 | Menampilkan tanggal dan waktu user melakukan create                  |
| Updated at  |                 | Timestamp          | 07 July 2026 19:00 | Menampilkan tanggal dan waktu user melakukan update data allocation  |
| Deleted at  |                 | Timestamp          | 07 July 2026 20:00 | Menampilkan tanggal dan waktu user melakukan delete data allocation  |

## Sample Database&#x20;



| Id | Name                   | Created by | Updated by | Deleted by | Created at         | Updated at         | Deleted at         |
| -: | ---------------------- | ---------- | ---------- | ---------- | ------------------ | ------------------ | ------------------ |
|  1 | Project A              | Aini       | Aini       | -          | 07 July 2026 09:00 | 07 July 2026 09:00 | -                  |
|  2 | Project B              | Kartika    | Aini       | -          | 07 July 2026 10:15 | 07 July 2026 13:20 | -                  |
|  3 | Operational            | User A     | Kartika    | -          | 07 July 2026 11:30 | 08 July 2026 09:10 | -                  |
|  4 | Marketing Campaign     | Aini       | Kartika    | -          | 08 July 2026 08:45 | 08 July 2026 14:30 | -                  |
|  5 | Development Product    | Kartika    | Kartika    | -          | 08 July 2026 10:00 | 09 July 2026 16:15 | -                  |
|  6 | Event Internal         | User A     | Aini       | Aini       | 09 July 2026 09:20 | 09 July 2026 12:10 | 10 July 2026 08:30 |
|  7 | Customer Project       | Aini       | Aini       | -          | 10 July 2026 10:00 | 10 July 2026 10:00 | -                  |
|  8 | Research & Development | Kartika    | Freidy     | -          | 10 July 2026 13:45 | 11 July 2026 15:20 | -                  |
