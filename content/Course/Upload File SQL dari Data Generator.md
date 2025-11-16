---
id: Upload File SQL dari Data Generator
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

- Bagaimana cara menghasilkan data dummy untuk database?
- Bagaimana cara mengosongkan tabel sebelum mengimpor data baru?
- Bagaimana cara mengimpor file SQL dari command line MySQL?
- Bagaimana cara menghitung jumlah data dalam sebuah tabel?

---

## Notes

### Langkah-langkah Mengisi Tabel dengan Data Generator

Proses ini menjelaskan cara mengisi tabel database MySQL dengan data dummy yang dihasilkan dari layanan online, mengosongkan tabel terlebih dahulu, lalu mengimpor data baru.

#### 1. Hasilkan Data (Mockaroo)
- Anda dapat menggunakan data generator online seperti [Mockaroo](https://www.mockaroo.com/) untuk membuat data dummy dalam format SQL.
- Sesuaikan kolom dan tipe data, lalu unduh file `.sql` yang dihasilkan.

#### 2. Kosongkan Tabel (TRUNCATE)
- Sebelum mengimpor data baru, sebaiknya kosongkan tabel target untuk menghindari duplikasi atau konflik.
- Perintah `TRUNCATE TABLE` lebih efisien daripada `DELETE` untuk mengosongkan seluruh tabel.
- Jika tabel memiliki foreign key, Anda perlu menonaktifkan pengecekan sementara.
  ```sql
  -- Nonaktifkan pengecekan foreign key
  SET FOREIGN_KEY_CHECKS = 0;

  -- Kosongkan tabel
  TRUNCATE TABLE customers;

  -- Aktifkan kembali pengecekan foreign key
  SET FOREIGN_KEY_CHECKS = 1;
  ```

#### 3. Impor File SQL (`source`)
- Di dalam command line client MySQL, gunakan perintah `source` untuk mengeksekusi file `.sql` yang telah Anda unduh.
- Pastikan untuk menggunakan path file yang lengkap.
  ```sql
  source C:/path/to/your/file.sql;
  ```

#### 4. Verifikasi Data (`COUNT`)
- Setelah impor selesai, verifikasi bahwa data telah berhasil ditambahkan dengan menghitung jumlah baris dalam tabel.
  ```sql
  SELECT COUNT(id) FROM customers;
  ```

---

## Summary

Untuk mengisi tabel database dengan data dummy, Anda bisa menggunakan layanan seperti Mockaroo untuk menghasilkan file SQL. Sebelum mengimpor, kosongkan tabel target menggunakan `TRUNCATE TABLE`, dengan menonaktifkan `FOREIGN_KEY_CHECKS` jika perlu. Gunakan perintah `source` di command line MySQL untuk mengimpor file SQL tersebut, dan terakhir, verifikasi jumlah data menggunakan `SELECT COUNT()` untuk memastikan proses berhasil.
