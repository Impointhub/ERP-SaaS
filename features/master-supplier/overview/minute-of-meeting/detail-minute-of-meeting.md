# Detail Minute of meeting

## ADR001: Supplier Module — Feature Scope untuk Version 1.0

### Topic

Menentukan fitur apa saja yang akan dikembangkan pada Supplier module versi 1.0.

***

### Problem Statement

Pada KB Retail PointHub, Supplier module mencakup:

* Supplier Group Management
* Master Supplier (dengan kolom PIC dan Data Bank)
* Entity relationship yang kompleks

Tidak semua fitur tersebut digunakan atau diperlukan secara langsung, sehingga muncul pertanyaan: **berapa banyak fitur yang harus diimplementasikan pada versi pertama tanpa mengorbankan fungsionalitas inti?**

***

### Options

#### Option 1: Full Feature Parity dengan KB Retail

**Deskripsi:**\
Mengimplementasikan Supplier module persis seperti KB Retail, termasuk:

* Supplier Group Management (CRUD)
* Master Supplier dengan semua kolom: Nama, Alamat, Email, Phone, Notes, PIC (Person In Charge), Data Bank (Bank Name, Account Number, Account Holder)
* Seluruh permission matrix dan akses kontrol yang ada

| Aspek               | Keterangan                                                      |
| ------------------- | --------------------------------------------------------------- |
| **Scope**           | Lengkap, mencakup semua fitur KB Retail                         |
| **Target User**     | Mendukung semua use case yang ada di KB Retail                  |
| **Database Schema** | Menggunakan schema penuh dengan FK ke bank master dan PIC table |

**Kelebihan:**

* ✅ Feature completeness — semua kebutuhan KB Retail tertampung
* ✅ Tidak perlu refactor/migration di kemudian hari jika ada request PIC/Bank
* ✅ Konsistensi dengan sistem yang sudah ada
* ✅ Single source of truth untuk data supplier di seluruh ekosistem PointHub

**Kekurangan:**

* ❌ Development time lebih lama (estimated 3-4 sprint vs 1-2 sprint)
* ❌ Testing coverage lebih luas = risk lebih tinggi
* ❌ Kompleksitas code lebih tinggi (FK validation, cascade delete, permission checks)
* ❌ PIC dan Bank data belum tentu digunakan pada fase awal — potential over-engineering
* ❌ Blocking dependency untuk module lain (HR untuk PIC, Bank Master)

***

#### Option 2: MVP — Minimal Viable Product (DIPILIH)

**Deskripsi:**\
Mengimplementasikan CRUD supplier dengan data identitas dasar saja:

* Supplier Code (unique key)
* Supplier Name (required)
* Email
* Address
* Phone Number
* Notes (optional)
* Supplier Group (reference only, minimal management)

| Aspek               | Keterangan                                                      |
| ------------------- | --------------------------------------------------------------- |
| **Scope**           | Core supplier CRUD + basic identity                             |
| **Target User**     | Procurement & Purchasing team untuk basic supplier lookup       |
| **Database Schema** | Minimal — supplier table dengan FK sederhana ke supplier\_group |

**Kelebihan:**

* ✅ Fast time-to-market — dapat diluncurkan dalam 1-2 sprint
* ✅ Reduced complexity — fokus pada core business logic saja
* ✅ Lower risk — fewer code paths, easier testing
* ✅ Independen dari module lain (HR, Bank Master) — tidak ada blocking dependency
* ✅ Mudah untuk extend ke Option 1 di fase berikutnya (backward compatible)
* ✅ Clear scope — user dan team paham persis apa yang delivered

**Kekurangan:**

* ❌ Jika di kemudian hari ada urgent request untuk PIC/Bank, perlu enhancement (add fields + migration)
* ❌ Tidak cover 100% use case KB Retail — mungkin ada resistance dari legacy users
* ❌ Perlu clear communication bahwa ini adalah MVP, bukan final product

***

### Decision

**→ OPTION 2 (MVP) dipilih**

#### Reasoning

1. **Business Velocity:** Untuk mempercepat proses development dan go-to-market, MVP memberikan value lebih cepat.
2. **Risk Mitigation:** Dengan scope yang jelas dan terbatas, risk implementasi lebih rendah, memudahkan rework jika ada discovery baru.
3. **No Blocking Dependencies:** MVP tidak memerlukan modul HR (PIC) atau Bank Master yang belum ada, sehingga dapat dijalankan independen.
4. **Agile Scalability:** Arsitektur MVP memungkinkan incremental enhancement di sprint berikutnya tanpa major refactor. Phase 2 bisa add PIC; Phase 3 bisa add Bank data.
5. **Resource Efficiency:** Tim fokus pada core CRUD + permission logic, bukan edge cases dari enterprise schema.
6. **Early Feedback:** Launching MVP lebih cepat memungkinkan user feedback lebih awal, yang bisa guide Phase 2 requirements.

***

### Implementation Scope (Version 1.0)

#### Fitur yang INCLUDED:

* **Master Supplier CRUD**
  * Create: Code (auto-generated, editable), Name (required), Email, Address, Phone, Notes
  * Read: List dan Detail view
  * Update: Edit supplier details
  * Delete: Soft delete with password confirmation
* **Access Control**
  * Read, Create, Edit, Delete permissions
  * Role-based access matrix
  * Logged-in validation
* **Validation & Error Handling**
  * Code uniqueness
  * Required field validation
  * Email format (basic)
  * Password confirmation untuk delete

#### Fitur yang EXCLUDED (untuk Phase 2+):

* ❌ PIC (Person In Charge) — memerlukan HR module terlebih dahulu
* ❌ Bank Account data — memerlukan Bank Master module

***

## ADR002: Penyusunan Database Master Contact pada Point Hijau

### Topic

Penyusunan struktur database untuk Master Contact pada Point Hijau, khususnya untuk **Customer, Supplier, dan Ekspedisi**.

### Problem

Point Hijau diharapkan memiliki struktur dan behavior yang menyerupai Point Ungu. Pada Point Ungu, data **Customer, Supplier, dan Ekspedisi** menggunakan satu database contact karena kebutuhan data dan struktur informasinya dianggap memiliki kesamaan.

Sementara itu, pada Point Hitam, setiap master contact memiliki database yang terpisah karena kebutuhan dan atribut data masing-masing master berbeda.

Terdapat kebutuhan pada fitur **Payment Order** untuk menampilkan seluruh data person yang dapat berasal dari Customer, Supplier, maupun Ekspedisi. Oleh karena itu, diperlukan keputusan mengenai struktur database yang akan digunakan pada Point Hijau.

### Options

#### Option 1 — Menggunakan Satu Database Contact

Customer, Supplier, dan Ekspedisi disimpan dalam satu database contact dan dibedakan berdasarkan **type**.

Contoh:

* `type = customer`
* `type = supplier`
* `type = expedition`

Pendekatan ini mengikuti implementasi yang digunakan pada Point Ungu dan Point KB Retail.

**Kelebihan**

1. **Struktur database lebih sederhana**\
   Hanya membutuhkan satu database atau tabel utama untuk menyimpan seluruh data contact.
2. **Memudahkan kebutuhan Payment Order**\
   Seluruh data person sudah berada dalam satu sumber data sehingga Payment Order dapat mengambil Customer, Supplier, dan Ekspedisi secara langsung tanpa perlu menggabungkan data dari beberapa database.
3. **Mengurangi duplikasi data umum**\
   Field yang sama seperti nama, alamat, nomor telepon, email, dan informasi contact lainnya dapat disimpan dalam satu struktur.
4. **Lebih mudah untuk menampilkan seluruh person**\
   Sistem dapat melakukan filter berdasarkan `type` atau menampilkan seluruh data tanpa perlu melakukan integrasi antar-database.
5. **Konsisten dengan Point Ungu dan Point KB Retail**\
   Pendekatan ini dapat meningkatkan kesamaan arsitektur dengan produk yang sudah menggunakan konsep unified contact.

**Kekurangan**

1. **Struktur database harus mengakomodasi kebutuhan seluruh master**\
   Karena Customer, Supplier, dan Ekspedisi memiliki kebutuhan yang berbeda, database harus dirancang untuk menampung atribut yang spesifik untuk masing-masing type.
2. **Berpotensi memiliki banyak nullable field**\
   Field yang hanya dibutuhkan oleh Customer mungkin tidak relevan untuk Supplier atau Ekspedisi, sehingga dapat menyebabkan banyak field yang tidak terisi.
3. **Pengembangan Customer dapat memengaruhi struktur umum**\
   Jika Customer membutuhkan atribut atau relasi baru yang kompleks, perubahan pada database contact dapat berdampak pada struktur yang digunakan oleh Supplier dan Ekspedisi.
4. **Business logic menjadi lebih kompleks**\
   Sistem harus memiliki validasi berdasarkan `type` untuk menentukan field mana yang wajib diisi dan aturan bisnis mana yang berlaku.
5. **Kurang fleksibel untuk pengembangan domain yang berbeda**\
   Jika Customer, Supplier, atau Ekspedisi berkembang menjadi domain yang lebih kompleks, struktur unified contact dapat menjadi semakin sulit untuk dipelihara.

***

#### Option 2 — Menggunakan Database Terpisah

Customer, Supplier, dan Ekspedisi disimpan pada database atau tabel yang berbeda, masing-masing memiliki struktur dan atribut sesuai kebutuhan domain masing-masing.

Pendekatan ini mengikuti implementasi yang digunakan pada Point Hitam.

**Kelebihan**

1. **Struktur database dapat disesuaikan dengan kebutuhan masing-masing master**\
   Customer, Supplier, dan Ekspedisi dapat memiliki atribut dan relasi yang berbeda sesuai kebutuhan bisnisnya.
2. **Mendukung pengembangan Customer di masa depan**\
   Customer dapat dikembangkan secara lebih fleksibel tanpa harus menyesuaikan struktur Supplier dan Ekspedisi.
3. **Mengurangi coupling antar-master**\
   Perubahan pada struktur atau business logic Customer tidak secara langsung berdampak pada Supplier atau Ekspedisi.
4. **Business logic lebih terisolasi**\
   Validasi dan aturan bisnis dapat dibuat secara spesifik untuk masing-masing master sehingga lebih mudah dikelola.
5. **Struktur database lebih merepresentasikan domain bisnis**\
   Setiap master memiliki domain yang jelas dan dapat berkembang secara independen.
6. **Lebih mudah melakukan scaling berdasarkan kebutuhan domain**\
   Jika salah satu master memiliki kebutuhan performa atau volume data yang lebih tinggi, pengembangan dapat dilakukan secara lebih spesifik terhadap master tersebut.

**Kekurangan**

1. **Payment Order membutuhkan integrasi beberapa sumber data**\
   Karena data Customer, Supplier, dan Ekspedisi berada pada database yang berbeda, sistem membutuhkan mekanisme untuk menggabungkan data ketika Payment Order perlu menampilkan seluruh person.
2. **Query menjadi lebih kompleks**\
   Pengambilan seluruh person membutuhkan proses penggabungan data dari beberapa tabel atau service.
3. **Berpotensi terjadi duplikasi field umum**\
   Field seperti nama, alamat, email, dan nomor telepon dapat muncul pada beberapa database sehingga perlu dilakukan standardisasi struktur.
4. **Membutuhkan mekanisme unified data pada application layer**\
   Untuk kebutuhan seperti Payment Order, sistem perlu memiliki service atau abstraction layer yang dapat mengembalikan data Customer, Supplier, dan Ekspedisi dalam format yang konsisten.
5. **Pengelolaan data lintas master lebih kompleks**\
   Jika terdapat kebutuhan bisnis yang menggunakan data dari beberapa master sekaligus, diperlukan mekanisme integrasi tambahan.

### Decision

Memilih **Option 2 — Setiap Master Contact Menggunakan Database yang Terpisah**, mengikuti pendekatan yang digunakan pada Point Hitam.

Dengan keputusan ini, database untuk:

* Customer
* Supplier
* Ekspedisi

akan dikelola secara terpisah sesuai dengan kebutuhan dan domain masing-masing master.

### Reasoning

Keputusan ini diambil dengan pertimbangan sebagai berikut:

1. **Kebutuhan data setiap master berbeda**\
   Customer, Supplier, dan Ekspedisi memiliki kebutuhan informasi dan atribut yang berbeda sehingga lebih tepat jika masing-masing memiliki struktur database yang disesuaikan dengan kebutuhan masing-masing.
2. **Mendukung pengembangan fitur Customer di masa depan**\
   Customer direncanakan memiliki pengembangan dan kebutuhan bisnis yang lebih kompleks. Dengan database yang terpisah, pengembangan struktur dan atribut Customer dapat dilakukan secara lebih fleksibel tanpa berdampak langsung pada Supplier atau Ekspedisi.
3. **Mengurangi coupling antar-master**\
   Pemisahan database memungkinkan masing-masing master memiliki business logic dan struktur data yang dapat berkembang secara independen.
4. **Struktur database lebih sesuai dengan domain bisnis**\
   Setiap master memiliki karakteristik dan business requirement yang berbeda. Pemisahan database memungkinkan setiap domain direpresentasikan secara lebih spesifik.
5. **Kebutuhan Payment Order tetap dapat dipenuhi**\
   Walaupun database Customer, Supplier, dan Ekspedisi terpisah, kebutuhan Payment Order untuk menampilkan seluruh data person tetap dapat dipenuhi melalui service layer atau unified data layer.



