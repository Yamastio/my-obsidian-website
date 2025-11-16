---
id: 7-Memahami SQL Injection
aliases: []
tags:
  - cybersecurity
  - web_security
  - bughunting
  - jagoansiber
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[web_security]], [[bughunting]], [[jagoansiber]]

---

## Cue

- Apa itu SQL Injection (SQLi) dan bagaimana dampaknya?
- Apa itu Database dan SQL?
- Bagaimana cara kerja SQL Injection dan jenis-jenisnya?
- Bagaimana cara mendeteksi SQL Injection secara manual dan otomatis?
- Bagaimana cara mencegah SQL Injection?

---

## Notes

### 1. Aplikasi Web dan Database: Hubungan yang Penting
- Sebagian besar aplikasi web modern menggunakan database di back-end.
- Aplikasi web berinteraksi dengan database secara real-time untuk dinamis dan responsif.
- Permintaan ke database sering melibatkan informasi dari permintaan HTTP(S) pengguna.

### 2. Apa Itu SQL Injection (SQLi)?
- Kerentanan keamanan web yang memungkinkan penyerang mengganggu query (permintaan) aplikasi ke databasenya.
- Penyerang bisa memodifikasi query SQL.
- Dampak serius: Melihat data terlarang, memodifikasi/menghapus data, mengkompromikan server/infrastruktur, DoS.

### 3. Mengenal Database dan SQL
- Database Management System (DBMS): Perangkat lunak untuk membuat, mendefinisikan, meng-host, dan mengelola database.
    - Contoh: MySQL, PostgreSQL (RDBMS), MongoDB, Cassandra (NoSQL).
- Structured Query Language (SQL): Bahasa standar untuk berinteraksi dengan database relasional (RDBMS).
- SQL dapat digunakan untuk: mengambil, memperbarui, menghapus data; membuat tabel/database; menambah/menghapus pengguna; memberikan izin.

### 4. Cara SQL Injection Bekerja (dan Bagaimana Mendeteksinya)
- SQL Injection sering terjadi pada klausa `WHERE` dari query `SELECT`, tapi bisa di bagian lain.
- Jenis SQL Injection:

### Mengambil Data Tersembunyi
- Penyerang memanipulasi query untuk menampilkan semua data (contoh: `OR 1=1--`).

### Mengakali Logika Aplikasi
- Terjadi pada halaman login.
- Penyerang menggunakan komentar SQL (`--` atau `#`) untuk menghilangkan bagian query pengecekan password.
- Contoh: `administrator'--` sebagai username untuk login tanpa password.

### UNION Injection
- Jika aplikasi menampilkan hasil query, penyerang bisa menggunakan `UNION` untuk menjalankan query `SELECT` tambahan.
- Membutuhkan jumlah kolom dan tipe data yang kompatibel.
- Penyerang bisa menentukan jumlah kolom dengan `ORDER BY` atau mencoba `NULL`.

### Blind SQL Injection
- Aplikasi rentan tapi respons HTTP tidak mengandung hasil query SQL atau detail kesalahan database.
- Teknik UNION attack tidak efektif.
- Teknik berbeda:
    - Memicu Respons Kondisional: Mencari perbedaan respons berdasarkan kondisi yang disuntikkan.
    - Time-based Injection: Memicu penundaan waktu (`SLEEP(5)`) tergantung kondisi benar/salah.

### Cara Mendeteksi SQL Injection Secara Manual
- Masukkan tanda kutip tunggal (`'`) dan cari kesalahan.
- Masukkan kondisi boolean (`OR 1=1`, `OR 1=2`) dan perhatikan respons.
- Masukkan payload penundaan waktu (`sleep(5)`) dan perhatikan waktu respons.

### 5. Mengotomatisasi SQL Injection dengan SQLmap
- SQLmap: Alat penetration testing open-source (Python) untuk otomatisasi deteksi dan eksploitasi SQLi.
- Perintah dasar: `sqlmap –u “https://url/page?parameter=value”`.

### 6. Cara Mencegah SQL Injection (Mitigasi)
- Input Sanitization: Membersihkan input pengguna dari karakter berbahaya.
- Input Validation: Memastikan input pengguna sesuai format/tipe data yang diharapkan.
- User Privileges: Memberikan hak akses terendah yang dibutuhkan kepada pengguna database/aplikasi.
- Web Application Firewall (WAF): Mendeteksi dan memblokir serangan SQL Injection.
- Parameterized Queries (Prepared Statements): Cara paling efektif, memisahkan kode SQL dari input pengguna.

## Summary

SQL Injection adalah kerentanan serius yang dapat memungkinkan penyerang untuk memanipulasi database aplikasi web, mencuri data sensitif, atau bahkan mengambil alih server. Ini terjadi ketika aplikasi tidak benar dalam menangani input pengguna saat membangun query SQL. Memahami berbagai jenis serangan seperti pengambilan data tersembunyi, UNION attack, dan blind SQLi sangat penting untuk mengidentifikasi dan mencegahnya. Namun, kabar baiknya adalah SQL Injection dapat dicegah secara efektif dengan praktik pengkodean yang aman, terutama dengan menggunakan Parameterized Queries, serta kombinasi dari input validation, sanitization, dan pembatasan hak akses. Dengan langkah-langkah mitigasi yang tepat, kita bisa membuat aplikasi web jauh lebih aman dari ancaman ini.