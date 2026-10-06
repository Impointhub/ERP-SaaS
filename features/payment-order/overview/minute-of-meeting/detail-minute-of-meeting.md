# Detail Minute of Meeting

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
  * **Option 2 :** Membuat Halaman/Section Khusus Approval History
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
* **Problem :** Pada proses pengajuan Payment Order, nominal maupun detail pembayaran sering mengalami perubahan sebelum diajukan. Dalam kondisi tersebut, user cenderung langsung melakukan submit tanpa melakukan verifikasi akhir terhadap data yang telah diinput. Hal ini meningkatkan risiko terjadinya kesalahan pembayaran yang akan berdampak pada transaksi Cash Out atau Bank Out serta memerlukan proses koreksi setelah transaksi diproses. Oleh karena itu, diperlukan mekanisme yang memungkinkan user melakukan pemeriksaan kembali terhadap seluruh informasi sebelum Payment Order diajukan&#x20;
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
* **Problem :** pada payment order tidak semua chart of account yang ditampilkan, karena tidak semua akun bisa dilakukan pengajuan menggunakan payment order pada finance.&#x20;
* **Option :**&#x20;
  * **Option 1 : Ditampilkan akun yang tidak berhubungan dengan setting jurnal otomatis**&#x20;
    * Kelebihan :&#x20;
      * mencegah fraud karena aku user tidak bisa menjurnal pada akun yang sudah disetting sebagai jurnal otomatis&#x20;
      * User bisa melakukan pencatatan pada finance selain akun beban saja&#x20;
    * Kekurangan :&#x20;
      * User mungkin tidak memahami alasan beberapa akun tidak muncul pada pilihan COA.
      * Membutuhkan dokumentasi atau informasi yang jelas terkait akun yang dibatasi.
* **Decision :**
  * Option 1&#x20;
* **Reasoning :**&#x20;
  * Agar user bisa membuat transaksi pada akun selain yang digunakan pada setting jurnal&#x20;

