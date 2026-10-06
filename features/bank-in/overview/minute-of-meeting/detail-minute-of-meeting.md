# Detail Minute of meeting

## ADR-001 — Flow Input Cash In dan Bank In

**Topic:** Flow Input Cash In dan Bank In

#### Problem

Cash In dan Bank In memiliki kebutuhan input transaksi yang sama, yaitu:

1. Input transaksi menggunakan **referensi Payment Collection**.
2. Input transaksi secara langsung melalui **Create Cash In / Create Bank In tanpa referensi Payment Collection**.

Perlu ditentukan flow yang digunakan untuk Cash In dan Bank In agar kebutuhan bisnis dapat segera dipenuhi, sekaligus mempertimbangkan dependency terhadap fitur Payment Collection.

#### Options

#### Option 1 — Membuat Cash In dan Bank In Lengkap

Membuat Cash In dan Bank In dengan seluruh skenario input, baik menggunakan referensi Payment Collection maupun tanpa referensi Payment Collection.

**Kelebihan:**

* Flow Cash In dan Bank In sudah lengkap sejak awal.
* User dapat menggunakan referensi Payment Collection maupun membuat transaksi secara langsung.
* Tidak perlu melakukan perubahan flow utama ketika Payment Collection sudah tersedia.

**Kekurangan:**

* Scope development lebih besar dan lebih kompleks.
* Cash In dan Bank In menjadi memiliki dependency terhadap kesiapan Payment Collection.
* Berpotensi memperlambat delivery karena perlu menunggu flow Payment Collection selesai.

#### Option 2 — Membuat Cash In dan Bank In V1 Tanpa Referensi Payment Collection

Membuat Cash In dan Bank In versi awal yang hanya mendukung **Create Cash In / Create Bank In tanpa referensi Payment Collection**.

**Kelebihan:**

* Scope development lebih sederhana.
* Cash In dan Bank In dapat segera digunakan untuk memenuhi kebutuhan bisnis.
* Tidak perlu menunggu Payment Collection selesai.
* Mengurangi dependency antar fitur.

**Kekurangan:**

* Cash In dan Bank In belum mendukung referensi Payment Collection pada V1.
* Akan membutuhkan enhancement setelah Payment Collection siap.
* User belum dapat menghubungkan transaksi Cash In/Bank In dengan Payment Collection pada versi awal.

#### Decision

**Memilih Option 2 — Membuat Cash In dan Bank In V1 tanpa referensi Payment Collection.**

#### Reasoning

Option 2 dipilih untuk **mengejar kebutuhan bisnis Bu Lioni** dan mempercepat penggunaan Cash In dan Bank In.

Jika menggunakan Option 1, development Cash In dan Bank In perlu menunggu kesiapan Payment Collection. Hal tersebut dapat menyebabkan kebutuhan bisnis tertunda.

Dengan Option 2, Cash In dan Bank In dapat **delivered terlebih dahulu sebagai V1** tanpa dependency terhadap Payment Collection. Setelah Payment Collection sudah tersedia dan siap digunakan, fitur referensi Payment Collection dapat ditambahkan melalui enhancement.

#### Impact

* Cash In V1 mendukung create transaksi tanpa referensi Payment Collection.
* Bank In V1 mendukung create transaksi tanpa referensi Payment Collection.
* Referensi Payment Collection menjadi **future enhancement** untuk Cash In dan Bank In.
* Struktur data dan flow V1 perlu dibuat dengan mempertimbangkan kemungkinan penambahan referensi Payment Collection di kemudian hari.
