---
id: Insert
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

- Bagaimana cara menggunakan perintah `INSERT INTO` di SQL?
- Bagaimana cara memasukkan data ke kolom-kolom tertentu dalam sebuah tabel?

---

## Notes

### Sintaks Dasar `INSERT INTO`
Perintah `INSERT INTO` digunakan untuk menambahkan baris data baru ke dalam sebuah tabel di database. Anda dapat memilih untuk memasukkan data ke semua kolom atau hanya ke kolom-kolom tertentu.

#### Memasukkan Data ke Kolom Tertentu
- Anda dapat menentukan kolom mana saja yang ingin Anda isi datanya. Ini berguna jika Anda tidak ingin mengisi semua kolom atau jika beberapa kolom memiliki nilai default.
- **Sintaks**:
  ```sql
  INSERT INTO nama_tabel (kolom1, kolom2, ...)
  VALUES (nilai1, nilai2, ...);
  ```

### Contoh Penggunaan
- **Contoh**: Memasukkan data ke tabel `products` untuk kolom `name` dan `price`.
  ```sql
  INSERT INTO products (name, price)
  VALUES ('Kursus Hacker', 12000000);
  ```
- Pastikan urutan nilai dalam klausa `VALUES` sesuai dengan urutan kolom yang ditentukan.

---

## Summary

Perintah `INSERT INTO` dalam SQL adalah fundamental untuk menambahkan baris data baru ke dalam tabel database. Anda dapat secara spesifik menentukan kolom mana yang akan diisi datanya, diikuti dengan nilai-nilai yang sesuai. Ini memungkinkan fleksibilitas dalam mengelola data, terutama ketika tidak semua kolom perlu diisi atau ketika kolom memiliki nilai default.
