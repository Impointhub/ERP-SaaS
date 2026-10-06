# Detail Minute Of Meeting

## ADR-001 : Bagaimana cara user bisa mendaftar pada ERP SAAS&#x20;

#### Topic

User perlu dapat mendaftar ke platform erp saas&#x20;

#### Problem

Platform ERP SAAS hanya dapat digunakan oleh user yang diundang (invite). Diperlukan mekanisme registrasi yang tetap membatasi akses hanya untuk user yang berhak.

#### Options

**Option 1 - Invitation**

**(+)**

* Hanya user yang diundang yang dapat mengakses platform.
* User dapat langsung aktif tanpa proses verifikasi.
* Implementasi lebih sederhana.

**(-)**

* User hanya dapat bergabung melalui undangan dari Admin Personal Finance.
* Membutuhkan pembuatan akun default oleh admin.
* Password awal diketahui oleh pihak yang membuat akun.
* Email yang dimasukkan admin berpotensi tidak valid.

**Option 2 - Invitation dengan Email Verification**

**(+)**

* Memastikan alamat email yang digunakan valid.
* Password hanya diketahui oleh pemilik akun.
* Tidak memerlukan akun default yang dibuat admin.

**(-)**

* User harus melakukan proses verifikasi email sebelum akun aktif.
* Flow registrasi menjadi lebih panjang dibanding invitation biasa.

#### Decision

Menggunakan **Option 1 - Invitation**.

#### Reasoning

* Sesuai dengan ruang lingkup dan penawaran awal proyek.
* Platform hanya digunakan oleh pengguna internal sehingga risiko penggunaan email tidak valid relatif kecil.
* Proses onboarding menjadi lebih cepat karena tidak memerlukan verifikasi email.
* Implementasi lebih sederhana dan memenuhi kebutuhan bisnis saat ini.
