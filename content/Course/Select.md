---
id: Select
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

- Apa fungsi dari perintah `SELECT` dalam SQL?
- Bagaimana cara memilih kolom-kolom tertentu dari sebuah tabel?
- Bagaimana cara memilih semua kolom dari sebuah tabel?

---

## Notes

### Penggunaan Dasar `SELECT`
Perintah `SELECT` adalah perintah yang paling umum digunakan dalam SQL. Fungsinya adalah untuk mengambil atau melakukan kueri data dari satu atau lebih tabel dalam database.

#### Memilih Kolom Tertentu
- Anda dapat menentukan kolom mana saja yang ingin Anda tampilkan dengan menuliskannya setelah kata kunci `SELECT`.
- **Contoh**: Mengambil kolom `name`, `city`, dan `country` dari tabel `customers`.
  ```sql
  SELECT name, city, country FROM customers;
  ```

#### Memilih Semua Kolom
- Untuk mengambil semua kolom dari sebuah tabel tanpa harus menuliskannya satu per satu, gunakan karakter wildcard `*`.
- **Contoh**: Mengambil semua kolom dari tabel `customers`.
  ```sql
  SELECT * FROM customers;
  ```

---

## Summary

Perintah `SELECT` adalah inti dari Data Query Language (DQL) dalam SQL, yang digunakan untuk mengambil data dari tabel database. Anda dapat memilih kolom-kolom spesifik dengan menyebutkan namanya secara eksplisit, atau menggunakan wildcard (`*`) untuk mengambil semua kolom sekaligus. Ini adalah perintah fundamental untuk semua operasi pembacaan data.
