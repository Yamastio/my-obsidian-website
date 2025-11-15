---
id: Apa Itu Database
aliases: []
tags:
  - mysql
comments: true
draft: false
---

Related: [[index|Home]], [[mysql]]

## Apa itu Database

Database adalah sekumpulan data yang disimpan dan dikelola secara elektronik dalam sebuah sistem komputer. Tujuan utama database adalah menyediakan cara yang terstruktur, efisien, dan konsisten untuk menyimpan, mengakses, dan mengelola informasi.

Istilah DMS (Data Management System) sering digunakan secara umum untuk menggambarkan sistem pengelolaan data. Namun, dalam konteks teknis, istilah yang lebih tepat adalah DBMS (Database Management System). DBMS adalah perangkat lunak yang digunakan untuk membuat, mengelola, dan menjalankan operasi pada database.

---

## Komponen Utama Database

### Tabel

Struktur utama yang digunakan untuk menyimpan data. Masing-masing tabel merepresentasikan suatu entitas.
Contoh: Customer, Manufacture, Product, Order, Order_items.

### Kolom / Field

Atribut atau properti dari data yang disimpan pada tabel. Setiap kolom memiliki nama dan tipe data.

### Baris / Record

Satu unit data dalam sebuah tabel yang merepresentasikan satu entitas lengkap.

### Tipe Data

Menentukan jenis data yang dapat disimpan pada sebuah kolom.
Contoh:

- varchar atau char untuk teks
- integer untuk angka
- date untuk tanggal

### Query

Instruksi atau perintah yang digunakan untuk berinteraksi dengan database. Query digunakan untuk menambah, mengubah, menghapus, dan mengambil data.

---

## Analogi Sederhana

Database dapat dianalogikan sebagai sebuah rak buku besar.

- Setiap rak adalah tabel.
- Setiap buku adalah record.
- Informasi di dalam buku adalah data pada kolom.
- Aturan seperti kategori atau label adalah tipe data.

---

## SQL (Structured Query Language)

SQL adalah bahasa standar untuk mengelola dan berinteraksi dengan database relasional. SQL memungkinkan pengguna untuk:

- Menyisipkan data
- Mengambil data
- Memperbarui data
- Menghapus data
- Membuat tabel dan struktur database
- Mengatur hak akses

SQL digunakan oleh berbagai DBMS seperti MySQL, PostgreSQL, MariaDB, SQLite, dan lainnya.
