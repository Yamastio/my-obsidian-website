---
id: Fungsi Utama SQL
aliases: []
tags:
  - mysql
  - sql
  - databases
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[mysql]], [[sql]], [[databases]]

---

## Cue

- Apa saja kategori utama perintah dalam SQL?
- Apa itu DDL (Data Definition Language) dan contohnya?
- Apa itu DML (Data Manipulation Language) dan contohnya?
- Apa itu DQL (Data Query Language) dan contohnya?
- Apa itu DCL (Data Control Language) dan contohnya?
- Apa itu TCL (Transaction Control Language) dan contohnya?

---

## Notes

SQL (Structured Query Language) memiliki beberapa kategori perintah utama yang digunakan untuk berinteraksi dengan database relasional. Setiap kategori memiliki fungsi spesifik, mulai dari mendefinisikan struktur hingga memanipulasi data.

### 1. DDL (Data Definition Language)
- **Fungsi**: Perintah untuk mendefinisikan, mengubah, atau menghapus struktur objek database seperti tabel, indeks, atau view.
- **Contoh Perintah**: `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`, `TRUNCATE TABLE`.

### 2. DML (Data Manipulation Language)
- **Fungsi**: Perintah untuk memanipulasi data yang ada di dalam tabel, seperti menambah, memperbarui, atau menghapus baris data.
- **Contoh Perintah**: `INSERT INTO`, `UPDATE`, `DELETE`.

### 3. DQL (Data Query Language)
- **Fungsi**: Perintah yang digunakan untuk mengambil atau melakukan kueri data dari database. Ini adalah kategori yang paling sering digunakan.
- **Contoh Perintah**: `SELECT`.

### 4. DCL (Data Control Language)
- **Fungsi**: Perintah untuk mengelola hak akses dan perizinan pengguna terhadap database.
- **Contoh Perintah**: `GRANT` (memberikan izin), `REVOKE` (mencabut izin).

### 5. TCL (Transaction Control Language)
- **Fungsi**: Perintah untuk mengelola transaksi dalam database untuk memastikan integritas data.
- **Contoh Perintah**: `COMMIT` (menyimpan transaksi), `ROLLBACK` (membatalkan transaksi), `SAVEPOINT`.

---

## Summary

Perintah SQL dikelompokkan ke dalam lima kategori utama sesuai fungsinya. Data Definition Language (DDL) digunakan untuk mengelola struktur database, sementara Data Manipulation Language (DML) untuk memanipulasi data di dalamnya. Data Query Language (DQL) berfungsi untuk mengambil data, Data Control Language (DCL) mengatur hak akses pengguna, dan Transaction Control Language (TCL) mengelola transaksi. Pemahaman kelima kategori ini adalah dasar untuk mengelola dan berinteraksi dengan database secara efektif.
