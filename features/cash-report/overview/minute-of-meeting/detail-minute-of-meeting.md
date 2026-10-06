# Detail Minute of Meeting

## ADR — Rumus Cash Report dan Bank Report

**Topic:**\
Penentuan rumus pada Cash Report dan Bank Report

#### Problem

Pada **Cash Report**, total cash saat ini direncanakan dihitung menggunakan rumus:

> **Total Cash = Ending Balance - Cash Advance**

Namun, fitur **Cash Advance** belum dikembangkan sehingga data Cash Advance belum tersedia di sistem. Kondisi ini menyebabkan rumus tersebut belum dapat diterapkan pada Cash Report.

Hal yang sama perlu dipertimbangkan pada **Bank Report**, agar development report dapat dilakukan tanpa menunggu seluruh fitur pendukung selesai dikembangkan.

#### Options

#### Option 1 — Develop Cash Advance terlebih dahulu

Mengembangkan fitur **Cash Advance** sebelum menyelesaikan Cash Report, sehingga data Cash Advance tersedia dan rumus Total Cash dapat menggunakan:

> **Total Cash = Ending Balance - Cash Advance**

**Kelebihan:**

* Rumus report dapat diterapkan sesuai kebutuhan bisnis awal.
* Data Cash Advance tersedia secara langsung dari sistem.
* Hasil report lebih lengkap dan sesuai dengan konsep perhitungan yang direncanakan.

**Kekurangan:**

* Development Cash Report menjadi bergantung pada development Cash Advance.
* Timeline development Cash Report menjadi lebih panjang.
* Fokus development ERP V1 dapat tertunda karena harus menyelesaikan fitur tambahan terlebih dahulu.

#### Option 2 — Develop Cash Report dan Bank Report V1 terlebih dahulu

Mengembangkan **Cash Report dan Bank Report versi 1** menggunakan data dan fitur yang sudah tersedia saat ini, tanpa menunggu Cash Advance selesai dikembangkan.

Rumus report akan menggunakan data transaksi yang sudah tersedia pada ERP V1. Perhitungan yang membutuhkan data Cash Advance akan disesuaikan kembali setelah fitur Cash Advance dikembangkan.

**Kelebihan:**

* Mempercepat development dan release basic product ERP V1.
* Cash Report dan Bank Report dapat segera digunakan dengan data yang sudah tersedia.
* Mengurangi dependency antar-feature dalam proses development.
* Perhitungan dapat dikembangkan lebih lanjut pada versi berikutnya setelah Cash Advance tersedia.

**Kekurangan:**

* Rumus Total Cash pada V1 belum dapat menggunakan Cash Advance.
* Hasil report V1 dapat berbeda dengan perhitungan final setelah Cash Advance dikembangkan.
* Diperlukan adjustment pada report ketika fitur Cash Advance sudah tersedia.

#### Decision

**Option 2 — Develop Cash Report dan Bank Report V1 terlebih dahulu.**

Cash Report dan Bank Report akan dikembangkan menggunakan data dan fitur yang sudah tersedia pada ERP V1. Perhitungan yang membutuhkan data Cash Advance akan dilakukan adjustment setelah fitur Cash Advance dikembangkan.

#### Reasoning

Keputusan ini diambil karena prioritas saat ini adalah **mempercepat development basic product ERP V1**.

Development report tidak perlu menunggu seluruh fitur pendukung selesai apabila fitur tersebut belum menjadi dependency utama untuk penggunaan report pada V1.

Dengan pendekatan ini:

1. Basic Cash Report dan Bank Report dapat segera selesai.
2. Development dapat berjalan secara paralel dengan fitur Cash Advance.
3. Enhancement terhadap rumus report dapat dilakukan pada development berikutnya setelah data Cash Advance tersedia.
4. Dependency antar-feature dapat diminimalkan sehingga proses development ERP V1 lebih cepat.

#### Follow-up

Setelah fitur **Cash Advance** selesai dikembangkan, lakukan review terhadap rumus Cash Report untuk memastikan perhitungan:

> **Total Cash = Ending Balance - Cash Advance**

dapat diterapkan sesuai kebutuhan bisnis.

Jika terdapat perubahan rumus, perubahan tersebut perlu dibuat sebagai enhancement pada versi berikutnya.
