# Detail Minute of Meeting

## ADR-001: Editable User Data

**Topic**\
Menentukan data user yang dapat diubah melalui fitur Edit User.

**Problem**\
User perlu dapat mengubah data profil. Namun, perubahan **name** yang telah digunakan dalam transaksi dapat menyebabkan inkonsistensi atau kerancuan pada data transaksi yang sudah tersimpan.

#### Decision

**Option 1: Name dan Email Tidak Dapat Diedit**

#### Reasoning

Keputusan ini dipilih untuk mempertahankan struktur dan flow user yang telah berjalan pada **KB Retail**, serta memastikan email yang tersimpan merupakan email yang telah tervalidasi.

#### Discussion history&#x20;

| MOM                                                                                                           | Date         | Person            |
| ------------------------------------------------------------------------------------------------------------- | ------------ | ----------------- |
| <p><br><a href="./#discussion-history">Menentukan data user yang dapat diubah melalui fitur Edit User</a></p> | 21 July 2026 | Bu kartika, Aini  |
