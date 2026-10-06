# Detail Minute of meeting

## ADR-001: Customer & Supplier Module — Separate Master Data Architecture

#### Topic

Menentukan arsitektur penyimpanan data Customer dan Supplier pada ERP PointHub, apakah menggunakan satu tabel master seperti KB Retail atau dipisahkan menjadi dua master data yang independen.

***

#### Problem Statement

Pada KB Retail (Point Ungu), data **Customer** dan **Supplier** disimpan dalam satu master data (shared master). Pendekatan ini cukup untuk kebutuhan sistem saat ini.

Namun pada ERP PointHub (Point Hijau), terdapat kebutuhan bisnis yang berbeda, antara lain:

* Customer memiliki atribut khusus seperti **Credit Ceiling** yang tidak dimiliki Supplier.
* Pada roadmap berikutnya akan dikembangkan **Sales Visitation Module** yang membutuhkan informasi customer yang lebih kompleks, seperti area, territory, sales assignment, dan histori kunjungan.
* Kemungkinan perkembangan atribut Customer dan Supplier akan semakin berbeda sehingga penggunaan satu tabel akan meningkatkan kompleksitas dan jumlah kolom yang tidak relevan.

Project Owner menginginkan struktur aplikasi semirip mungkin dengan KB Retail, namun terdapat perbedaan kebutuhan bisnis dan desain database yang perlu dipertimbangkan.

***

#### Options

#### Option 1: Shared Master Data (Sama seperti KB Retail)

#### Deskripsi

Menggunakan satu tabel master untuk menyimpan Customer dan Supplier seperti implementasi pada KB Retail.

Perbedaan data diakomodasi dengan penambahan kolom khusus (custom fields) dan penanda tipe data (Customer/Supplier).

#### Scope

* Satu tabel master untuk Customer & Supplier
* Menambahkan kolom khusus sesuai kebutuhan masing-masing
* Menggunakan field type/category sebagai pembeda data

#### Target User

Seluruh modul yang membutuhkan master Customer maupun Supplier.

#### Database Schema

Single Master Table

```
master_partner- id- type (customer/supplier)- code- name- address- phone- email- credit_ceiling- ...
```

#### Kelebihan

✅ Konsisten dengan arsitektur KB Retail

✅ Migrasi data dari sistem lama lebih mudah

✅ Reuse logic CRUD lebih tinggi

✅ Jumlah tabel lebih sedikit

#### Kekurangan

❌ Banyak kolom yang hanya digunakan salah satu tipe data

❌ Banyak nilai NULL pada database

❌ Business rule Customer dan Supplier menjadi bercampur

❌ Sulit dikembangkan ketika kebutuhan Customer semakin kompleks

❌ Menambah kompleksitas validasi dan maintenance

***

#### Option 2: Separate Master Data (DIPILIH)

#### Deskripsi

Membuat master Customer dan Supplier sebagai dua entitas yang terpisah dengan struktur database masing-masing.

Masing-masing master hanya menyimpan atribut yang memang dibutuhkan oleh domain bisnisnya.

#### Scope

* Master Customer
* Master Supplier
* CRUD masing-masing module
* Relationship dan business rule dipisahkan

#### Target User

* Sales
* Procurement
* Finance
* Sales Visitation
* CRM (future)

#### Database Schema

Customer

```
customers- id- customer_code- customer_name- credit_ceiling- area_id- ...
```

Supplier

```
suppliers- id- supplier_code- supplier_name- ...
```

#### Kelebihan

✅ Database lebih terstruktur sesuai domain bisnis

✅ Mendukung kebutuhan Sales Visitation di masa depan

✅ Credit Ceiling hanya dimiliki Customer sehingga schema lebih bersih

✅ Business rule Customer dan Supplier menjadi lebih jelas

✅ Lebih scalable ketika masing-masing module berkembang

✅ Mengurangi kompleksitas validasi dan query

#### Kekurangan

❌ Tidak identik dengan implementasi KB Retail

❌ Beberapa logic CRUD perlu dibuat terpisah

❌ Membutuhkan effort lebih ketika membuat fitur yang digunakan oleh kedua master

***

#### Decision

→ **OPTION 2 (Separate Master Data)** dipilih.

***

#### Reasoning

#### Domain Driven Design

Customer dan Supplier merupakan dua domain bisnis yang memiliki lifecycle, atribut, dan business rule yang berbeda sehingga lebih tepat dipisahkan menjadi dua aggregate yang independen.

#### Future Scalability

Roadmap ERP PointHub mencakup pengembangan Sales Visitation, CRM, Territory Management, dan fitur Customer Management yang membutuhkan atribut khusus Customer. Dengan pemisahan master data, pengembangan tersebut dapat dilakukan tanpa memengaruhi Supplier.

#### Database Maintainability

Memisahkan tabel mengurangi banyaknya kolom yang tidak digunakan (NULL fields), membuat schema lebih sederhana, mudah dipahami, dan lebih mudah dipelihara.

#### Business Flexibility

Perubahan kebutuhan Customer maupun Supplier dapat dilakukan secara independen tanpa menimbulkan dampak pada entitas lainnya.

#### Cleaner Business Logic

Validasi, permission, relasi, serta business process Customer dan Supplier menjadi lebih jelas karena masing-masing memiliki model dan aturan tersendiri.

#### Long-Term Architecture

Meskipun berbeda dengan KB Retail, pendekatan ini memberikan arsitektur yang lebih scalable dan lebih sesuai dengan roadmap pengembangan ERP PointHub dalam jangka panjang.

***
