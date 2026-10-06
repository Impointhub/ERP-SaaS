# Authentication

## Database&#x20;

| Column                            | Column Frontend | Requirement      | Type Data             |
| --------------------------------- | --------------- | ---------------- | --------------------- |
| \_id                              |                 | Required         | String                |
| username                          | username        | Required, unique | String                |
| email                             | email           | Required, unique | String                |
| password                          | Password        | Required         | String                |
| trimmed\_username                 |                 | Required         | String                |
| trimmed\_email                    |                 | Required         | String                |
| email\_verification.code          |                 | Required         | String                |
| email\_verification.url           |                 | Required         | String                |
| email\_verification.is\_verified  |                 | Required         | Boolean               |
| email\_verification.requested\_at |                 | Required         | String (ISO DateTime) |
| email\_verification.verified\_at  |                 | Required         | String (ISO DateTime) |
| created\_at                       |                 | Required         | String (ISO DateTime) |

## Sample database&#x20;

| \_id      | username      | email                                                         | password   | trimmed\_username | trimmed\_email                                                | email\_verification.code | email\_verification.url                                                                            | email\_verification.is\_verified | email\_verification.requested\_at | email\_verification.verified\_at | created\_at          |
| --------- | ------------- | ------------------------------------------------------------- | ---------- | ----------------- | ------------------------------------------------------------- | ------------------------ | -------------------------------------------------------------------------------------------------- | -------------------------------- | --------------------------------- | -------------------------------- | -------------------- |
| USR000001 | john.doe      | [john.doe@example.com](mailto:john.doe@example.com)           | John@12345 | johndoe           | [john.doe@example.com](mailto:john.doe@example.com)           | VER-8F2A91               | [https://app.example.com/verify-email/VER-8F2A91](https://app.example.com/verify-email/VER-8F2A91) | TRUE                             | 2026-07-01T08:30:00Z              | 2026-07-01T08:35:42Z             | 2026-07-01T08:25:10Z |
| USR000002 | jane.smith    | [jane.smith@example.com](mailto:jane.smith@example.com)       | Jane#2026  | janesmith         | [jane.smith@example.com](mailto:jane.smith@example.com)       | VER-5BC931               | [https://app.example.com/verify-email/VER-5BC931](https://app.example.com/verify-email/VER-5BC931) | FALSE                            | 2026-07-02T09:15:00Z              | NULL                             | 2026-07-02T09:10:23Z |
| USR000003 | michael.lee   | [michael.lee@example.com](mailto:michael.lee@example.com)     | Mike@9876  | michaellee        | [michael.lee@example.com](mailto:michael.lee@example.com)     | VER-9AE442               | [https://app.example.com/verify-email/VER-9AE442](https://app.example.com/verify-email/VER-9AE442) | TRUE                             | 2026-07-03T10:05:00Z              | 2026-07-03T10:07:11Z             | 2026-07-03T10:00:00Z |
| USR000004 | olivia.wilson | [olivia.wilson@example.com](mailto:olivia.wilson@example.com) | Olivia!456 | oliviawilson      | [olivia.wilson@example.com](mailto:olivia.wilson@example.com) | VER-CD129A               | [https://app.example.com/verify-email/VER-CD129A](https://app.example.com/verify-email/VER-CD129A) | FALSE                            | 2026-07-04T13:40:00Z              | NULL                             | 2026-07-04T13:35:48Z |
| USR000005 | david.brown   | [david.brown@example.com](mailto:david.brown@example.com)     | David$2026 | davidbrown        | [david.brown@example.com](mailto:david.brown@example.com)     | VER-EF7612               | [https://app.example.com/verify-email/VER-EF7612](https://app.example.com/verify-email/VER-EF7612) | TRUE                             | 2026-07-05T15:00:00Z              | 2026-07-05T15:04:18Z             | 2026-07-05T14:55:27Z |
