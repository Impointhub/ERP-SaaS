# Payment Order - Lioni - Detail

## ADR-001 : Fungsi kolom notes pada payment order&#x20;

* **Topic** : Fungsi kolom notes pada approval payment order&#x20;
* **Problem** : pada saat approval user bisa mengisi kolom notes, akan tetapi data notes belum tampil dimanapun&#x20;
* **Option :**&#x20;
  * **Option 1 :** Data notes ditampilkan pada halaman detail&#x20;
    * Kelebihan :&#x20;
      * User bisa mengetahui alasan payment order diapprove&#x20;
      * Track history payment order&#x20;
      * Membantu proses klarifikasi jika terdapat pertanyaan di kemudian hari.
    * Kekurangan :&#x20;
      * Menambah informasi pada halaman detail sehingga tampilan menjadi lebih padat.
      * Notes dapat dilihat oleh seluruh user yang memiliki akses ke detail Payment Order, meskipun tidak selalu relevan bagi semua user.
  * **Option 2 :**&#x20;
    * Kelebihan
      * Informasi approval tersimpan pada konteks yang sesuai, yaitu riwayat approval.
      * Halaman detail Payment Order tetap bersih dan fokus pada data transaksi.
      * Memudahkan audit karena setiap catatan dapat dikaitkan dengan approver, tanggal, dan status approval.
      * Lebih scalable jika di masa depan terdapat multi-level approval.
    * Kekurangan&#x20;
      * User harus membuka menu atau section Approval History untuk melihat alasan approval.
      * Informasi alasan approval tidak langsung terlihat pada halaman utama detail Payment Order.
      * Berpotensi terlewat oleh user yang tidak terbiasa membuka riwayat approval.
* **Decision :**&#x20;
  * Data notes ditampilkan pada halaman detail payment order&#x20;
* **Reasoning :**&#x20;
  * Agar mengetahui alasan di approve dari form payment order yang diajukan&#x20;

## ADR-002 : Fungsi preview pada payment order&#x20;

* **Topic :** Fungsi preview pada payment order &#x20;
* **Problem :** payment order diajukan untuk permintaan pembayaran, untuk menjaga agar tidak sampai salah input, maka  user bisa menggunakan fitur preview untuk melihat detail dari payment order yang diajukan.&#x20;
* **Option :**&#x20;
  * Option 1 : ditambahkan fungsi preview pada payment order&#x20;
    * Kelebihan :&#x20;
      * user bisa melihat data yang akan diajukan sebelum disubmit&#x20;
      * mencegah kesalahan submit data&#x20;
      * Sesuai dengan kb retail
      * Cocok untuk transaksi yang memiliki dampak finansial
      * Memberikan kesempatan terakhir untuk melakukan koreksi
    * Kekurangan :&#x20;
      * Menambah satu langkah pada user journey.
      * Memperpanjang waktu penyelesaian transaksi.
      * Berpotensi dianggap redundant oleh user yang sudah terbiasa dengan proses Payment Order.
  * Option 2: Tidak Menambahkan Halaman Preview, Menggunakan Confirmation Modal Saat Submit
    * Kelebihan :&#x20;
      * UX lebih cepat karena tidak ada perpindahan halaman.
      * Mengurangi jumlah klik dan waktu submit.
      * Implementasi lebih sederhana dibandingkan halaman preview penuh.
      * Tetap memberikan validasi terakhir sebelum data diajukan.
    * Kekurangan&#x20;
      * Informasi yang ditampilkan terbatas karena ruang modal terbatas.
      * User tidak dapat melakukan review data secara menyeluruh.
      * Risiko kesalahan input lebih tinggi dibandingkan halaman preview.
      * Kurang sesuai untuk transaksi dengan nominal besar atau data yang kompleks
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Payment Order merupakan transaksi finansial yang memerlukan tingkat akurasi tinggi. Halaman preview memungkinkan user melakukan verifikasi menyeluruh terhadap data yang akan diajukan sehingga dapat mengurangi risiko kesalahan pembayaran. Selain itu, pendekatan ini telah sesuai dengan proses bisnis dan standar yang diterapkan pada KB Retail.

## ADR-003 : Chart of account yang bisa ditampilkan pada payment order&#x20;

* **Topic :** chart of account yang bisa ditampilkan pada payment order&#x20;
* **Problem :** pada payment order tidak semua chart of account yang ditampilkan, karna tidak semua akun bisa dilakukan pengajuan menggunakan payment order pada finance.&#x20;
* **Option :**&#x20;
  * **Option 1 : Ditampilkan akun yang tidak berhubungan dengan setting jurnal otomatis** &&#x20;
    * Kelebihan :&#x20;
      * mencegah fraud karna aku user tidak bisa menjurnal pada akun yang sudah disetting sebagai jurnal otomatis&#x20;
      * User bisa melakukan pencatatan pada finance selain akun beban saja&#x20;
    * Kekurangan :&#x20;
      * User mungkin tidak memahami alasan beberapa akun tidak muncul pada pilihan COA.
      * Membutuhkan dokumentasi atau informasi yang jelas terkait akun yang dibatasi.
* **Decision :**
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Agar user bisa membuat transaksi pada akun selain yang digunakan pada setting jurnal&#x20;



## ADR-004 : Kapan chart of account lioni bisa dibaca pada payment order&#x20;

* **Topic** : Kapan chart of account lioni bisa dibaca pada payment order&#x20;
* **Problem** : Payment order perlu membaca akun lioni yang tujuannya agar admin lain bisa membuatkan transaksi dengan akun atas nama lioni. akan tetapi user tidak bisa melihat semua transaksi atas account lioni yang tidak dibuat oleh user itu sendiri.&#x20;
*   **Option :**&#x20;

    * **Option 1 :** Penambahan permission "Full access & Transaction only" pada setiap modul finance&#x20;
      * Kelebihan :&#x20;
        * Account lioni bisa tampil secara dinamis sesuai dengan permission yang diberikan pada user&#x20;
        * system lebih mundah mencocokan antara akses modul, dan user dengan account lioni
        * Memudahkan sistem dalam melakukan mapping antara user, modul, dan COA yang dapat digunakan.&#x20;
      * Kekurangan :&#x20;
        * Menambah kompleksitas konfigurasi role dan akses.
        * Memerlukan pengujian menyeluruh untuk memastikan tidak terjadi privilege escalation
    * **Option 2 :** Menambahkan PIC/Owner pada COA Lioni dan Membatasi Akses Berdasarkan Kepemilikan Transaksi
      * Kelebihan :&#x20;
        * Implementasi lebih sederhana karena tidak perlu mengubah struktur permission seluruh modul finance.
        * User lain tetap dapat membuat transaksi menggunakan COA Lioni sesuai kebutuhan operasional.
        * Visibilitas transaksi dapat dibatasi berdasarkan pembuat transaksi (created by) atau PIC transaksi.
        * Cocok untuk kebutuhan jangka pendek dengan perubahan sistem yang minimal
      * Kekurangan : &#x20;
        * Rule akses menjadi tersebar di berbagai modul dan transaksi.
        * Sulit dipelihara ketika jumlah user, COA, dan skenario bisnis bertambah.
        * Berpotensi menimbulkan inkonsistensi antar modul finance.
        * Membutuhkan custom logic tambahan pada setiap fitur yang menggunakan COA Lioni


* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning**&#x20;
  * Pendekatan permission-based lebih scalable dan konsisten untuk jangka panjang. Sistem dapat menentukan visibilitas COA dan transaksi berdasarkan hak akses yang dimiliki user tanpa bergantung pada aturan khusus per transaksi atau per COA. Selain itu, mekanisme ini memudahkan pengelolaan akses pada seluruh modul finance dan memberikan fondasi yang lebih kuat untuk kebutuhan ekspansi fitur di masa mendatang

## ADR-005 : Perbedaan antara modul payment order lioni dan payment order&#x20;

* **Topic :** Apa perbedaan antara modul payment order lioni dan payment order&#x20;
* **Problem :** Bu lioni ingin menyatukan antara hasil input dari ce fei fei dengan bu lioni. Dalam implementasinya memiliki aturan seperti dibawah ini :&#x20;

<figure><img src="../../../.gitbook/assets/image (232).png" alt=""><figcaption></figcaption></figure>

* **Option**&#x20;
  * **Option 1 :** Membuat dua modul yaitu payment order dan payment order lioni.&#x20;
    * **Kelebihan :**&#x20;
      * Mempermudah pelacakan (traceability) transaksi berdasarkan area bisnis.
      * Mempermudah proses troubleshooting dan investigasi ketika terjadi error.
      * Lebih scalable untuk pengembangan fitur di masa depan.
      * Rule akses menjadi lebih jelas dan tidak bercampur dalam satu modul.
      * Modul Payment Order Lioni dapat menampilkan seluruh transaksi dan COA yang berkaitan dengan Lioni.
      * Modul Payment Order Finance dapat menampilkan COA selain Lioni serta transaksi Lioni yang dibuat oleh user itu sendiri.
      * Mengurangi kompleksitas conditional logic pada level transaksi.
    * **Kekurangan :**&#x20;
      * Membutuhkan effort development yang lebih besar dibandingkan pendekatan hardcode.
      * Terdapat duplikasi beberapa komponen UI dan flow yang perlu dikelola dengan baik.
      * User yang memiliki akses ke kedua modul perlu berpindah modul untuk melihat data yang berbeda.
  * **Option 2 :** Menggunakan hard code "jika lioni, bisa melihat account dan transaksi atas seluruh chart of account lioni&#x20;
    * **Kelebihan :**&#x20;
      * Implementasi lebih cepat.
      * Perubahan sistem relatif kecil.
      * Tidak memerlukan penambahan modul baru.
      * Mengurangi kebutuhan migrasi atau perubahan menu.
    * **Kekurangan :**&#x20;
      * Business rule tersimpan dalam hardcode sehingga sulit dipelihara.
      * Semakin banyak pengecualian di masa depan akan meningkatkan kompleksitas kode.
      * Menyulitkan proses debugging dan root cause analysis ketika terjadi masalah akses.
      * Tidak fleksibel apabila terdapat entitas baru selain Lioni yang membutuhkan perlakuan serupa.
      * Berpotensi menimbulkan technical debt karena akses ditentukan oleh logic khusus, bukan konfigurasi sistem.
      * Sulit diintegrasikan dengan mekanisme role dan permission yang lebih umum.
* **Decision**&#x20;
  * Option 1&#x20;
* **Reasoning**&#x20;
  * Pemisahan modul memberikan struktur yang lebih jelas antara transaksi Finance dan transaksi Lioni. Selain mempermudah pelacakan transaksi dan investigasi error, pendekatan ini juga lebih scalable karena aturan akses tidak bergantung pada hardcode khusus untuk satu entitas. Jika di masa depan terdapat kebutuhan serupa untuk entitas lain, sistem dapat dikembangkan menggunakan pola yang sama tanpa menambah kompleksitas business rule pada modul yang sudah ada

## ADR-006 : List payment order lioni&#x20;

* **Topic :** Halaman List payment order lioni&#x20;
* **Problem :** karna user selain bu lioni tidak bisa melihat seluruh transaksi akan tetapi bu lioni bisa melihat seluruh transaksi. sehingga ada perbedaan data yang ditampilkan pada payment order lioni dan payment order&#x20;
* **Option :**&#x20;
  * **Option 1 :** Data yang ditampilkan pada payment order lioni dan payment order berbeda.
    * Kelebihan :&#x20;
      * Menjaga kerahasiaan transaksi Lioni dari user yang tidak berwenang.
      * Memenuhi kebutuhan bisnis terkait pembatasan akses data.
      * Mengurangi risiko kebocoran informasi finansial.
      * Data yang ditampilkan sesuai dengan hak akses masing-masing user.
      * Lebih mudah dikontrol melalui mekanisme permission.&#x20;
    * Kekurangan :&#x20;
      * Berpotensi menimbulkan kebingungan karena jumlah data yang ditampilkan berbeda antar user atau antar modul.
      * Membutuhkan sosialisasi dan dokumentasi terkait perbedaan akses.
      * User dapat menganggap ada data yang hilang atau tidak sinkron apabila tidak memahami aturan akses yang berlaku
  * **Option 2 :** Menampilkan Data yang Sama pada Kedua Modul, namun Detail Transaksi Dibatasi Berdasarkan Permission
    * Kelebihan :&#x20;
      * Jumlah transaksi yang terlihat lebih konsisten antar user.
      * Mengurangi persepsi bahwa terdapat data yang hilang.
      * Mempermudah rekonsiliasi jumlah transaksi antar modul.
    * Kekurangan :&#x20;
      * Informasi keberadaan transaksi Lioni tetap dapat diketahui oleh user lain meskipun detailnya disembunyikan.
      * Tidak sepenuhnya memenuhi kebutuhan privasi transaksi Lioni.
      * Menambah kompleksitas pada pengaturan visibilitas kolom dan detail transaksi.
      * Berpotensi menimbulkan pertanyaan atau permintaan akses dari user yang melihat transaksi tetapi tidak dapat membuka detailnya
* **Decision :**&#x20;
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Kebutuhan utama adalah menjaga kerahasiaan transaksi Lioni sehingga hanya dapat diakses oleh pihak yang berwenang. Oleh karena itu, transaksi yang berkaitan dengan Lioni tidak ditampilkan kepada user lain. Meskipun terdapat risiko perbedaan jumlah data yang terlihat antar modul atau user, pendekatan ini lebih sesuai dengan kebutuhan bisnis dan prinsip akses berbasis otorisasi (need-to-know access), sehingga privasi dan keamanan data tetap terjaga.

## ADR-007 : Perlu diskusi ketika create payment order ketika coa private dan coa publik dalam satu form&#x20;

* saran chat gpt untuk diseragamkan dalam 1 sifat coa&#x20;





