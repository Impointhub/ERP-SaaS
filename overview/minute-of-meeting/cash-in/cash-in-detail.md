# Cash In Detail

## ADR-001 : Pada Cash In / Bank In perlu ada fitur edit&#x20;

* **Topic :** Pada Cash In / Bank In perlu ada fitur edit&#x20;
* **Problem :** pada saat ini secara standard erp untuk cash in & bank ini belum memiliki fitur edit. dan bu lioni memerlukan adanya fitur edit untuk mengkoreksi pengelompokan yang diinput oleh ce fei fei.&#x20;
* **Option**&#x20;
  * Option 1 : Diberikan fitur pada cash in dan bank in&#x20;
    * Kelebihan
      * User dapat melakukan koreksi data alokasi sebelum transaksi di-approve.
      * Mempercepat proses perbaikan data tanpa bergantung pada admin finance.
      * Mengurangi komunikasi manual antara user dan admin finance.
      * Menjaga kerahasiaan informasi alokasi karena koreksi dilakukan langsung oleh pihak yang berwenang.
      * Meningkatkan efisiensi operasional dan akurasi pencatatan.
    * Kekurangan
      * Memerlukan perubahan flow Cash In dan Bank In yang saat ini langsung menghasilkan jurnal.
      * Jurnal transaksi perlu diakui setelah proses approval, bukan saat transaksi dibuat.
      * Memerlukan penambahan field dan mekanisme Approval Status pada Cash In dan Bank In.
      * Membutuhkan pengujian tambahan untuk memastikan integritas jurnal dan saldo akun.
  * Option 2 : Diatur menggunakan SOP Lapangan&#x20;
    * Kelebihan :&#x20;
      * Tidak memerlukan perubahan sistem.
      * Tidak ada biaya development tambahan.
      * Tidak memerlukan perubahan pada flow jurnal yang sudah berjalan saat ini.
    * Kekurangan :&#x20;
      * User harus berkoordinasi dengan admin finance setiap kali terjadi kesalahan alokasi.
      * Proses koreksi menjadi lebih lambat.
      * Menambah beban kerja admin finance.
      * Informasi alokasi perlu dibagikan kepada pihak lain untuk proses koreksi.
      * Berpotensi menimbulkan bottleneck pada proses operasional.
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Penambahan fitur Edit memberikan fleksibilitas bagi user untuk melakukan koreksi data alokasi secara mandiri sebelum proses approval. Solusi ini membantu menjaga kerahasiaan informasi alokasi, mengurangi ketergantungan pada admin finance, serta mempercepat proses koreksi ketika terjadi kesalahan input. Meskipun memerlukan perubahan pada flow approval dan pencatatan jurnal, manfaat yang diperoleh lebih besar dibandingkan mempertahankan proses manual melalui SOP operasional.

## ADR-002 : Pada halaman list cash in / bank in perlu ditambahkan kolom account asal dan account tujuan

* **Topic :** Pada halaman list cash in / bank in perlu ditambahkan kolom account asal dan account tujuan
* **Problem :** Pada saat membaca halaman list cash in dan bank in pada point ungu, user mengalami kebingungan karna akun yang menjadi lawan dari transaksi kas ditampilkan pada halaman list. namun sumber dananya belum ditampilkan pada halaman list. sehingga user perlu klik detail untuk mengetahui sumber dananya.&#x20;
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
  * Dipilih Option 1: Menampilkan Account Asal dan Account Tujuan pada halaman List Cash In dan Bank In.
* **Reasoning :** &#x20;
  * Kebutuhan utama user adalah dapat memahami konteks transaksi secara cepat tanpa harus membuka halaman detail atau melakukan filter tambahan. Dengan menampilkan Account Asal dan Account Tujuan langsung pada halaman list, user dapat melakukan review, verifikasi, dan pencarian transaksi secara lebih efisien dalam satu layar. Meskipun diperlukan penambahan filter untuk menjaga keterbacaan data, manfaat yang diperoleh lebih besar dibandingkan mempertahankan informasi akun hanya melalui mekanisme filter.

## ADR-003 : Pada Cash In / Bank in perlu memiliki fitur approval&#x20;

* **Topic :** Pada Cash In / Bank in perlu memiliki fitur approval&#x20;
* **Problem :** Fitur approval diperlukan pada menu cash in / bank in karna bu lioni perlu memastikan data yang diinput oleh ce fei fei sudah benar. Jika ada kesalahan pada saat input maka dari bu lioni bisa mereject atau bisa membantu edit secara langsung.&#x20;
* **Option :**&#x20;
  * **Option 1 :** Menambahkan fitur approval untuk cash in dan bank in&#x20;
    * **Kelebihan :**&#x20;
      * Mencegah kesalahan pencatatan sejak awal proses.
      * Memberikan lapisan kontrol tambahan terhadap transaksi keuangan.
      * Approver dapat melakukan reject apabila terdapat kesalahan data.
      * Approver dapat melakukan koreksi sebelum transaksi disetujui.
      * Mengurangi risiko kesalahan akun, nominal, maupun alokasi transaksi.
      * Meningkatkan akurasi dan kualitas data keuangan.
    * **Kekurangan :**&#x20;
      * Menambah tahapan proses bisnis sebelum transaksi dianggap final.
      * Berpotensi terjadi perbedaan sementara antara kondisi lapangan dan data sistem apabila transaksi belum di-approve.
      * Dana yang sudah diterima secara fisik dapat belum tercatat pada laporan keuangan selama proses approval masih berlangsung.
      * Membutuhkan penambahan status transaksi seperti Draft, Pending, Approved, dan Rejected.
      * Memerlukan perubahan pada mekanisme pembentukan jurnal agar jurnal dibuat setelah approval.
  * **Option 2 :** Tetap Menggunakan Proses Saat Ini dan Mengandalkan Koreksi Setelah Transaksi Disimpan
    * **Kelebihan :**&#x20;
      * Tidak memerlukan perubahan sistem.
      * Proses pencatatan transaksi lebih cepat.
      * Dana yang diterima langsung tercermin pada laporan keuangan.
      * Tidak memerlukan tambahan konfigurasi approval dan role.
    * Kekurangan :&#x20;
      * Risiko kesalahan pencatatan lebih tinggi.
      * Kesalahan baru diketahui setelah transaksi tercatat.
      * Membutuhkan proses koreksi atau jurnal penyesuaian apabila terjadi kesalahan.
      * Mengurangi kontrol terhadap kualitas data yang masuk ke sistem.
      * Berpotensi menimbulkan perbedaan interpretasi dan audit finding di kemudian hari.
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning**&#x20;
  * Tujuan utama dari proses approval adalah mencegah kesalahan pencatatan sejak awal sebelum transaksi menjadi bagian dari data keuangan yang valid. Dengan adanya approval, Bu Lioni dapat melakukan verifikasi, koreksi, maupun penolakan terhadap transaksi yang diinput oleh user sehingga kualitas dan akurasi data keuangan dapat terjaga. Meskipun terdapat konsekuensi berupa tambahan proses dan kemungkinan perbedaan sementara antara kondisi lapangan dan sistem, manfaat pengendalian internal yang diperoleh lebih besar dibandingkan risiko yang ditimbulkan.





