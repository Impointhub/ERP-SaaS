# Master Customer

## Database&#x20;

| Column Name   | Frontend     | Data Type    | Rules                                                      | Sample Data              |   |
| ------------- | ------------ | ------------ | ---------------------------------------------------------- | ------------------------ | - |
| id            |              | int(10)      | Autoincreament                                             | 1                        |   |
| code          | Code         | varchar(255) | Unique, Not Null                                           | T0283                    |   |
| name          | Name         | varchar(255) | Not Null                                                   | Nur Aini                 |   |
| notes         |              | text         |                                                            |                          |   |
| created\_by   |              | int(10)      | Foreign key to user(id)                                    | 1                        |   |
| updated\_by   |              | int(10)      | Foreign key to user(id)                                    | 2                        |   |
| created\_at   |              | timestamp    | Not null, CURRENT\_TIMESTAMP                               | 22 Agustus 2025 19:00:01 |   |
| updated\_at   |              | timestamp    | Not null, CURRENT\_TIMESTAMP ON UPDATE CURRENT\_TIMESTAMP  | 23 Agustus 2025 18:00:19 |   |
| archived\_at  |              | datetime     | Not null, CURRENT\_TIMESTAMP ON ARCHIVE CURRENT\_TIMESTAMP |                          |   |
| archived\_by  |              | int(10)      | Foreign key to user(id)                                    |                          |   |
| address       | Address      | varchar(255) | Nullable                                                   | Jln Musi no 21           |   |
| city          |              | varchar(255) |                                                            |                          |   |
| state         |              | varchar(255) |                                                            |                          |   |
| country       |              | varchar(255) |                                                            |                          |   |
| zip\_code     |              | varchar(255) |                                                            |                          |   |
| latitude      |              | varchar(255) |                                                            |                          |   |
| longitude     |              | varchar(255) |                                                            |                          |   |
| phone         | phone        | varchar(255) | Nullable                                                   | 0318428239239            |   |
| phone\_cc     |              | varchar(255) |                                                            |                          |   |
| email         |              | varchar(255) |                                                            |                          |   |
| credit\_limit | credit limit | decimal(65   | Not null, Default 0                                        | 0                        |   |

