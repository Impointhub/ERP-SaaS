# Bank Out - Lioni - Detail

## ADR-001 : Pada halaman list cash out - lioni & bank out - lioni perlu ditampilkan untuk account asal dan account tujuan&#x20;

* **Topic :** Pada halaman list cash out - lioni / bank out - lioni perlu ditambahkan kolom account asal dan account tujuan
* **Problem :** Pada saat membaca halaman list cash out - lioni dan bank out - lioni pada point ungu, user mengalami kebingungan karna akun yang menjadi lawan dari transaksi kas ditampilkan pada halaman list. namun sumber dananya belum ditampilkan pada halaman list. sehingga user perlu klik detail untuk mengetahui sumber dananya.&#x20;
* **Option**&#x20;
  * **Option 1 :** Ditampilkan data akun sumber dana pada halaman list&#x20;
    * **Kelebihan :**&#x20;
      * User dapat melihat informasi transaksi secara lebih lengkap dalam satu layar.
      * Mengurangi kebutuhan membuka halaman detail untuk setiap transaksi.
      * Mempercepat proses review dan verifikasi transaksi.
      * Memudahkan identifikasi perpindahan dana antar akun.
      * Membantu user ketika transaksi tidak dikelompokkan berdasarkan akun tertentu sehingga konteks transaksi tetap terlihat dengan jelas.
    * **Kekurangan :**&#x20;
      * Menambah jumlah kolom pada halaman list sehingga tampilan menjadi lebih padat.
      * Perlu penambahan filter atau fitur pencarian untuk menjaga kemudahan penggunaan ketika jumlah data besar.
      * Berpotensi mengurangi ruang tampilan pada perangkat dengan resolusi lebih kecil.
  * **Option 2 :** Ditampilkan data akun sumber dana melalui filter&#x20;
    * **Kelebihan :**&#x20;
      * Tampilan halaman list tetap sederhana dan tidak terlalu padat.
      * User dapat melakukan pencarian berdasarkan grouping akun tertentu.
      * Tidak memerlukan penambahan kolom pada tabel transaksi.
    * **Kekurangan :**&#x20;
      * User tidak dapat melihat informasi akun asal dan tujuan secara langsung dalam satu layar.
      * User harus melakukan filter terlebih dahulu sebelum dapat menganalisis transaksi berdasarkan akun.
      * Membutuhkan langkah tambahan untuk memperoleh informasi yang sebenarnya sering digunakan saat proses review.
      * Kurang efektif ketika user perlu membandingkan transaksi dari banyak akun sekaligus.
* **Decision :**&#x20;
  * Dipilih Option 1: Menampilkan Account Asal dan Account Tujuan pada halaman List Cash out - lioni dan Bank Out - lioni.
* **Reasoning :** &#x20;
  * Kebutuhan utama user adalah dapat memahami konteks transaksi secara cepat tanpa harus membuka halaman detail atau melakukan filter tambahan. Dengan menampilkan Account Asal dan Account Tujuan langsung pada halaman list, user dapat melakukan review, verifikasi, dan pencarian transaksi secara lebih efisien dalam satu layar. Meskipun diperlukan penambahan filter untuk menjaga keterbacaan data, manfaat yang diperoleh lebih besar dibandingkan mempertahankan informasi akun hanya melalui mekanisme filter.



## ADR-002 : Alur pembetulan data pada cash out - lioni / bank out - lioni mengikuti alur erp&#x20;

* **Topic :** Alur pembetulan data pada cash out mengikuti alur erp&#x20;
* **Problem :** Pada saat transaksi cash in dan bank in bu lioni perlu melakukan edit untuk menjagai apabila ada allocation yang tidak sesuai dengan data bu lioni. sedangkan pada cash out - lioni dan bank out - lioni, untuk setiap form cash out - lioni & bank out - lioni yang dibuat harus memiliki referensi payment order. sehingga ketika diberikan fitur untuk bu lioni bisa melakukan edit pada form cash out - lioni dan bank out - lioni, akan membuat payment order tidak berfungsi&#x20;
* **Option :**&#x20;
  * **Option 1 :** Alur untuk edit cash out - lioni / bank out - lioni mengikuti alur erp&#x20;
    * Kelebihan :&#x20;
      * Konsisten dengan standar proses ERP.
      * Menjaga fungsi Payment Order sebagai dokumen otorisasi pengeluaran dana.
      * Mencegah perubahan transaksi tanpa approval yang sah.
      * Mengurangi risiko fraud karena seluruh perubahan tetap melalui workflow persetujuan.
      * Menjaga keterkaitan (traceability) antara Payment Order dan Cash Out -lioni /Bank Out - lioni.
      * Memudahkan proses audit karena seluruh perubahan dapat ditelusuri dari dokumen sumber.
      * Menghindari ketidaksesuaian antara nilai, akun, dan allocation pada Payment Order dan transaksi pencairan dana.
    * Kekurangan :&#x20;
      * Proses koreksi menjadi lebih panjang karena harus dilakukan dari dokumen sumber.
      * Membutuhkan pembatalan atau revisi pada dokumen sebelumnya sebelum transaksi dapat diperbaiki.
      * User memerlukan pemahaman terhadap hubungan antar dokumen dalam proses ERP.
  * **Option 2** : Payment order dihapus sehingga bisa langsung membuat cash out
    * Kelebihan :&#x20;
      * Proses koreksi lebih cepat dan sederhana.
      * User dapat langsung memperbaiki transaksi tanpa harus kembali ke dokumen sebelumnya.
      * Mengurangi jumlah langkah yang diperlukan dalam proses operasional.
    * Kekurangan :&#x20;
      * Menghilangkan fungsi kontrol dan approval yang terdapat pada Payment Order.
      * Meningkatkan risiko fraud dan transaksi tanpa otorisasi.
      * Menyebabkan potensi ketidaksesuaian antara proses pengajuan dan realisasi pembayaran.
      * Menurunkan traceability antar dokumen.
      * Menyulitkan proses audit karena sumber persetujuan transaksi menjadi tidak jelas.
      * Berpotensi menimbulkan perbedaan data antara laporan pengajuan pembayaran dan laporan realisasi pembayaran.
      * Tidak sesuai dengan standar proses ERP yang telah diterapkan.
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  *   Payment Order merupakan mekanisme kontrol utama dalam proses pengeluaran dana. Memberikan kemampuan edit langsung pada Cash Out - lioni atau Bank Out - lioni berpotensi menghilangkan fungsi kontrol tersebut dan menciptakan risiko ketidaksesuaian antara dokumen pengajuan dan realisasi pembayaran.

      Meskipun proses koreksi menjadi lebih panjang, pendekatan ini menjaga integritas data, memastikan seluruh perubahan tetap melalui proses approval yang sesuai, serta mempertahankan audit trail yang lengkap. Oleh karena itu, pembetulan data harus dilakukan melalui revisi dokumen sumber sesuai dengan standar ERP yang berlaku.Mengikuti alur sop dari erp&#x20;

