# Detail MOM

### Hierarchy Chart of Account yang Sesuai Standar

#### Problem

Dari 3 pengguna ERP, diketahui bahwa hierarchy Chart of Account (CoA) yang digunakan hanya terdiri dari 3 level, yaitu:

1. Asset
2. Category Account (Aktiva Lancar)
3. Chart of Account

Sementara itu, Personal Finance membutuhkan hierarchy CoA hingga 4–6 level untuk dapat menampilkan laporan sesuai dengan kebutuhan pengguna.

#### Option

**1. Menggunakan maksimal 3 level**

**Kelebihan:**

* Lebih mudah dalam melakukan mapping rumus pada laporan.
* Mengurangi potensi error pada rumus karena kompleksitas CoA lebih rendah.
* Tidak memerlukan perubahan pada desain PRD saat ini.

**Kekurangan:**

* Belum dapat mengakomodasi kebutuhan perusahaan yang memiliki hierarchy CoA hingga 4–6 level.
* Kebutuhan hierarchy CoA hingga 6 level pada Bu Lioni dianggap sebagai kebutuhan custom tambahan.

**2. Mendukung hierarchy hingga 4–6 level**

**Kelebihan:**

* Dapat mengakomodasi kebutuhan Bu Lioni dan pengguna lain yang memiliki hierarchy CoA hingga 4–6 level.
* Struktur CoA menjadi lebih fleksibel untuk berbagai kebutuhan perusahaan.

**Kekurangan:**

* Memerlukan perubahan pada desain PRD.
* Menambah kompleksitas pada pengelolaan CoA sehingga diperlukan mapping yang lebih detail untuk meminimalkan potensi error pada laporan.

#### Decision

Menggunakan **hierarchy CoA hingga 4–6 level**.

#### Reasoning

Keputusan ini diambil karena kebutuhan hierarchy hingga 6 level telah ditetapkan sebagai bagian dari **point hijau** dan diperlukan untuk mengakomodasi kebutuhan Bu Lioni. Selain itu, struktur hingga 4–6 level dapat mendukung kebutuhan pengguna lain yang memiliki struktur CoA yang lebih kompleks.
