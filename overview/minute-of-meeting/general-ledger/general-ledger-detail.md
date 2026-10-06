# General Ledger Detail

## ADR-001 : Pada General Ledger Perlu ditampilkan Account debit dan account credit&#x20;

* **Topic :** Pada General Ledger perlu ditampilkan account debit dan account credit&#x20;
* **Problem :** Pada KB Retail Saat ini, General ledger hanya menampilkan data form number, form date, description, master, debit, credit, balance. Sehingga user tidak bisa mengetahui data akun yang digunakan pada transaksi di kb retail.&#x20;
* **Option**&#x20;
  * **Option 1 :** Menampilkan Account Debit dan Account Credit pada General Ledger
    * **Kelebihan :**&#x20;
      * User dapat langsung mengetahui akun yang digunakan dalam transaksi.
      * Mempercepat proses analisis dan investigasi transaksi.
      * Mengurangi kebutuhan membuka dokumen sumber atau laporan lain.
      * Mempermudah proses audit dan rekonsiliasi.
      * Lebih mudah dipahami oleh user finance dan accounting.
      * Perubahan relatif sederhana dari sisi development karena hanya menambahkan informasi yang sudah tersedia pada jurnal.
      * Mengurangi risiko salah interpretasi transaksi.
    * **Kekurangan :**&#x20;
      * Menambah jumlah kolom pada halaman General Ledger.
      * Tampilan tabel menjadi lebih lebar terutama pada perangkat dengan resolusi kecil.
      * Perlu penyesuaian export report apabila format export saat ini memiliki keterbatasan lebar kolom.
  * **Option 2 :** Menampilkan Akun Lawan (Contra Account) Saja pada General Ledger
    * Kelebihan :&#x20;
      * Tampilan laporan lebih ringkas.
      * Mengurangi jumlah kolom pada tabel.
      * Lebih sederhana dari sisi tampilan pengguna.
    * Kekurangan : &#x20;
      * Tidak menampilkan informasi jurnal secara lengkap.
      * User masih perlu melakukan analisis tambahan untuk memahami transaksi secara utuh.
      * Tidak memenuhi kebutuhan Bu Lioni untuk mengetahui akun yang digunakan pada transaksi.
      * Berpotensi menimbulkan interpretasi yang berbeda terhadap transaksi yang kompleks.
      * Kurang membantu dalam proses audit dan investigasi transaksi.
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Kebutuhan utama user adalah memahami transaksi akuntansi secara cepat tanpa harus membuka dokumen referensi lainnya. Dengan menampilkan Account Debit dan Account Credit secara langsung pada General Ledger, user dapat memperoleh konteks transaksi yang lebih lengkap dalam satu layar.

