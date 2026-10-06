# Discussion History

**Topic**\
Menentukan data user yang dapat diubah melalui fitur Edit User.

**Problem**\
User perlu dapat mengubah data profil. Namun, perubahan **name** yang telah digunakan dalam transaksi dapat menyebabkan inkonsistensi atau kerancuan pada data transaksi yang sudah tersimpan.

#### Option 1: Name dan Email Tidak Dapat Diedit

Kolom **name** dan **email** tidak dapat diubah setelah user terdaftar karena data tersebut telah digunakan sebagai referensi pada transaksi.

**Kelebihan:**

* Tidak memerlukan proses verifikasi email ulang.
* Email yang tersimpan telah dipastikan valid melalui proses verifikasi.
* Tidak mengubah existing flow pada KB Retail.

**Kekurangan:**

* Name tidak dapat diperbaiki jika terjadi kesalahan input.
* Email yang terdaftar tidak dapat diubah.

#### Option 2: Menambahkan Name Alias dan Mengizinkan Edit Email

Menambahkan kolom **name alias** untuk mengakomodasi perubahan nama setelah user memiliki transaksi. Email juga dapat diubah apabila terjadi kesalahan input, dengan menambahkan proses verifikasi email ulang.

**Kelebihan:**

* User dapat memperbaiki data apabila terjadi kesalahan input.
* Memungkinkan pengembangan flow dari KB Retail.

**Kekurangan:**

* Memerlukan penambahan kolom **name alias**.
* Memerlukan fitur verifikasi email ulang.

#### Decision

**Option 1: Name dan Email Tidak Dapat Diedit**

#### Reasoning

Keputusan ini dipilih untuk mempertahankan struktur dan flow user yang telah berjalan pada **KB Retail**, serta memastikan email yang tersimpan merupakan email yang telah tervalidasi.
