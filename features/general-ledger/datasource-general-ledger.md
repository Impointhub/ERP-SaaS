# Datasource General ledger

### Database General Ledger&#x20;

| Column Frontend  | Type          | Rules                          | Sample Data                                                                        | Tujuan                                                                   |
| ---------------- | ------------- | ------------------------------ | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Date             | DATE          | Autofill dari form refrence    | 02-08-2026                                                                         | Tanggal transaksi terjadi                                                |
| Reference        | VARCHAR(20)   | Autofill dari form reference   | JV-0090                                                                            | Nomor referensi jurnal, untuk ditelusuri ke dokumen sumber               |
| Master           | VARCHAR(10)   | Autofill dari form refrence    | <p>CUST-001 <br>SUP-003<br></p>                                                    | Menampilkan master customer / supplier / expedition dari form reference  |
| Description      | VARCHAR(255)  | Autofill dari form reference   | Customer payment received                                                          | Keterangan transaksi                                                     |
| Debit            | DECIMAL(18,2) | Autofill, dari form refrence.  | 12500000.00                                                                        | Nilai debit transaksi                                                    |
| Credit           | DECIMAL(18,2) | Autofill dari form reference   | 0.00                                                                               | Nilai kredit transaksi                                                   |
| Balance          | —             | —                              | <p><em>Dihitung otomatis =</em> <br><em>Opening balance + Debit - kredit</em> </p> | Saldo berjalan setelah transaksi ini                                     |
| Opening Balance  | -             | -                              | _Dihitung Otomatis_                                                                | Saldo akhir dari tanggal sebelum "Date from"                             |

### Sample Database&#x20;

| Date           | Reference | Master   | Description                |         Debit |        Credit |           Balance |
| -------------- | --------- | -------- | -------------------------- | ------------: | ------------: | ----------------: |
| **01-08-2026** | —         | —        | **Opening Balance**        |             — |             — | **50.000.000,00** |
| 02-08-2026     | JV-0090   | CUST-001 | Customer payment received  | 12.500.000,00 |          0,00 |     62.500.000,00 |
| 03-08-2026     | JV-0091   | SUP-003  | Payment to supplier        |          0,00 |  8.000.000,00 |     54.500.000,00 |
| 04-08-2026     | JV-0092   | CUST-005 | Customer payment received  |  7.500.000,00 |          0,00 |     62.000.000,00 |
| 05-08-2026     | JV-0093   | EXP-002  | Expedition service payment |          0,00 |  2.500.000,00 |     59.500.000,00 |
| 06-08-2026     | JV-0094   | CUST-008 | Customer payment received  | 15.000.000,00 |          0,00 |     74.500.000,00 |
| 08-08-2026     | JV-0095   | SUP-007  | Payment to supplier        |          0,00 | 10.000.000,00 | **64.500.000,00** |
