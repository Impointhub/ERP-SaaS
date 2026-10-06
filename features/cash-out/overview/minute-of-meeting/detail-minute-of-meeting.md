# Detail Minute of Meeting

## ADR001: Fitur apa saja yang didevelop pada erp v.1

**Topik:**&#x20;

Fitur apa saja yang di-develop pada ERP v.1

**Problem:**\
Development ERP v.1 pada Point Hijau dibuat sebagai pre-requisite dari Personal Finance.

**Opsi 1 — MVP:** \
Fitur yang di-develop hanya Create, Edit, Delete, dan Detail. \
Kelebihannya :&#x20;

* &#x20;pendekatan ini mempercepat proses development Personal Finance.&#x20;

Kekurangannya :&#x20;

* fitur print belum tersedia secara native di sistem, sehingga user harus menggunakan Ctrl+P (browser print) untuk mencetak.

**Opsi 2 — Lengkap:**&#x20;

Fitur yang di-develop mencakup Create, Edit, Delete, Detail, dan Print.&#x20;

Kelebihannya :&#x20;

* &#x20;fitur yang tersedia sudah lengkap termasuk print bawaan sistem.&#x20;

Kekurangannya: &#x20;

* proses development menjadi lebih lama&#x20;

**Keputusan:** Opsi 1 (MVP)

**Alasan:** Untuk mempercepat proses development.



## **ADR002: Requirement untuk saldo kas dan bank**

**Topik:**\
Requirement untuk saldo kas dan bank

**Problem:**\
Pada saat accounting input data, saldo kas dan bank bisa minus untuk sementara.

**Opsi 1 — Saldo kas dan bank tidak bisa minus:**

Kelebihan:

* Saldo yang ditampilkan selalu mencerminkan kondisi riil, tidak ada risiko laporan kas/bank menunjukkan angka yang secara bisnis tidak masuk akal (negatif)
* Berfungsi sebagai kontrol otomatis — mencegah user memproses pembayaran melebihi dana yang tersedia, mengurangi risiko kesalahan input atau penyalahgunaan

Kekurangan:

* Berisiko menolak transaksi yang sebenarnya sah saat terjadi input bersamaan (concurrent), karena sistem membaca saldo belum ter-update — bisa mengganggu operasional saat volume transaksi tinggi
* Menyulitkan proses pencatatan mundur (rekap harian di akhir hari, backdate entry), yang merupakan praktik umum di accounting

**Opsi 2 — Saldo kas dan bank bisa minus (sementara):**

Kelebihan:

* Mendukung alur kerja accounting yang tidak selalu real-time (rekap harian, input mundur) tanpa memblokir user
* Transaksi yang terjadi bersamaan tetap bisa diproses tanpa gagal karena validasi saldo

Kekurangan:

* Saldo bisa tampil negatif untuk sementara sebelum seluruh transaksi selesai diinput, berpotensi membingungkan user yang melihat laporan di tengah proses
* Memerlukan mekanisme tambahan (monitoring/alert/reconciliation) supaya saldo minus tidak dibiarkan permanen dan tidak terlewat dari perhatian

**Keputusan:** Opsi 2 — Saldo kas dan bank bisa minus

**Alasan:** Karena pada saat input transaksi bisa terjadi bersamaan, sehingga saldo kas dan bank bisa minus untuk sementara.
