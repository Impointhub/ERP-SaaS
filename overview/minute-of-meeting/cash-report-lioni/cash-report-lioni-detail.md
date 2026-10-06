# Cash Report - Lioni - Detail

## ADR-001 : Bu lioni perlu melakukan checking untuk hasil input transaksi oleh bu lioni sendiri ataupun dari ce fei fei melalui cash / bank report&#x20;

* **Topic :** Perlu fitur untuk checking transaksi melalui cash / bank report&#x20;
* **Problem :** karna yang input data pada personal finance ada dua orang, sehingga bu lioni perlu melakukan checking atas transaksi yang diinput. dan perlu penanda bahwa transaksi telah dicek oleh bu lioni&#x20;
* **Option :**&#x20;
  * **Option 1 : Menggunakan fitur checkbox pada cash / bank report**&#x20;
    * Kelebihan :&#x20;
      * Mengikuti standar ERP yang saat ini telah tersedia.
      * Biaya development relatif rendah.
      * Implementasi lebih cepat dibandingkan membuat workflow baru.
      * User dapat langsung mengetahui transaksi yang sudah dan belum diperiksa.
      * Tidak mengubah alur transaksi maupun proses akuntansi yang sudah berjalan.
      * Mengurangi risiko transaksi terlewat saat proses pengecekan berkala.
      * Mudah digunakan oleh user karena hanya membutuhkan satu aksi centang
      * Mengikuti standard ERP saat ini &#x20;
      * Mengurangi biaya development&#x20;
    * Kekurangan :&#x20;
      * Hanya menunjukkan status sudah diperiksa atau belum diperiksa.
      * Tidak menjelaskan hasil pengecekan atau catatan yang ditemukan.
      * Tidak menyediakan proses approval atau reject transaksi.
      * Berpotensi terjadi kesalahan centang apabila tidak terdapat audit trail yang memadai.
  * **Option 2: Menambahkan Workflow Review dan Approval pada Cash / Bank Report**
    * Kelebihan :&#x20;
      * Menyediakan kontrol yang lebih formal terhadap proses verifikasi.
      * Dapat menyimpan catatan hasil review.
      * Memiliki histori review yang lebih lengkap.
      * Memudahkan proses audit dan pelacakan temuan.
    * Kekurangan :&#x20;
      * Membutuhkan effort development yang lebih besar.
      * Menambah kompleksitas sistem dan proses operasional.
      * Berpotensi memperlambat proses pengecekan harian.
      * Tidak sesuai dengan kebutuhan saat ini yang hanya membutuhkan penanda transaksi telah diperiksa.
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Kebutuhan utama bisnis saat ini adalah memberikan penanda bahwa suatu transaksi telah diperiksa oleh Bu Lioni, bukan menambahkan proses approval baru. Fitur checkbox sudah cukup untuk memenuhi kebutuhan tersebut dengan biaya development yang minimal serta tetap mengikuti standar ERP yang telah digunakan saat ini.
  * Pendekatan ini memberikan keseimbangan antara kebutuhan kontrol operasional dan kompleksitas sistem, sehingga proses pengecekan dapat dilakukan secara sederhana, cepat, dan mudah dipahami oleh seluruh user.

## ADR-002 : Ada perbedaan Data yang ditampilkan pada cash report & cash report lioni

* **Topic :** Perbedaan data yang ditampilkan pada cash report dan cash report lioni&#x20;
* **Problem :** Perbedaan hak akses menyebabkan data yang ditampilkan pada Cash Report dan Cash Report Lioni tidak selalu sama. Kondisi ini berpotensi menimbulkan pertanyaan dari user karena jumlah transaksi, saldo, maupun detail transaksi yang terlihat berbeda antar pengguna.
* **Option :**&#x20;
  * **Option 1 :** Penambahan permission "Full access & Transaction only" pada setiap modul finance untuk menampilkan perbedaan data&#x20;
    * Kelebihan :&#x20;
      * Menjaga keamanan data atas transaksi bu lioni&#x20;
      * Menjaga keamanan dan kerahasiaan transaksi Bu Lioni.
      * Mengurangi risiko akses data oleh pihak yang tidak berwenang.
      * Lebih scalable untuk kebutuhan pengembangan di masa depan.
      * Mekanisme akses dapat digunakan kembali pada modul Finance lainnya.
      * Konsisten dengan konsep role dan permission yang berlaku pada sistem.
      * Mempermudah pengelolaan akses tanpa perlu membuat rule khusus per user.
    * Kekurangan :&#x20;
      * Data yang berbeda sehingga membuat user bingung
      * Data yang ditampilkan dapat berbeda antar user.
      * Berpotensi menimbulkan kebingungan apabila user tidak memahami perbedaan hak akses yang dimiliki.
      * Membutuhkan sosialisasi dan dokumentasi terkait perbedaan visibilitas data.
      * Membutuhkan pengujian tambahan untuk memastikan seluruh permission berjalan sesuai aturan.&#x20;
  * **Option 2 :** Menampilkan Data yang Sama untuk Semua User
    * Kelebihan :&#x20;
      * Tidak ada perbedaan data antar user.
      * Mengurangi potensi kebingungan karena seluruh user melihat informasi yang sama.
      * Proses implementasi relatif lebih sederhana.
    * Kekurangan&#x20;
      * Data transaksi Bu Lioni dapat diakses oleh user lain.
      * Tidak memenuhi kebutuhan bisnis terkait kerahasiaan data.
      * Meningkatkan risiko kebocoran informasi keuangan.
      * Tidak sesuai dengan prinsip least privilege dan data security.
      * Sulit diterapkan apabila kebutuhan pembatasan akses semakin kompleks di masa depan.
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Kebutuhan utama bisnis adalah menjaga kerahasiaan transaksi Bu Lioni sehingga hanya dapat diakses oleh pihak yang berwenang. Pendekatan berbasis permission memberikan mekanisme yang lebih aman, fleksibel, dan scalable dibandingkan menampilkan seluruh data kepada semua user. Meskipun terdapat konsekuensi berupa perbedaan data yang terlihat antar user, risiko tersebut dapat diminimalkan melalui dokumentasi, pelatihan, dan penjelasan hak akses yang jelas. Manfaat keamanan data yang diperoleh jauh lebih besar dibandingkan risiko kebingungan yang mungkin terjadi.
