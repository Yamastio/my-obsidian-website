---
id: Mengurutkan Baris Data
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

- Bagaimana cara mengurutkan data dalam SQL?
- Bagaimana cara mengurutkan data secara ascending (menaik)?
- Bagaimana cara mengurutkan data secara descending (menurun)?
- Bagaimana cara mengurutkan data berdasarkan beberapa kolom?

---

## Notes

### Penggunaan Dasar `ORDER BY`
Klausa `ORDER BY` digunakan dalam perintah `SELECT` untuk mengurutkan hasil kueri berdasarkan satu atau lebih kolom. Secara default, pengurutan dilakukan secara ascending (menaik).

### Mengurutkan Secara Ascending (ASC)
Untuk mengurutkan data dari nilai terkecil ke terbesar (atau A-Z untuk teks), Anda dapat menggunakan `ORDER BY` tanpa spesifikasi atau secara eksplisit dengan kata kunci `ASC`.

- **Contoh**: Mengurutkan pelanggan berdasarkan nama secara ascending.
  ```sql
  SELECT * FROM customers
  ORDER BY name LIMIT 20;
  ```

### Mengurutkan Secara Descending (DESC)
Untuk mengurutkan data dari nilai terbesar ke terkecil (atau Z-A untuk teks), gunakan kata kunci `DESC` setelah nama kolom.

- **Contoh**: Mengurutkan pelanggan berdasarkan nama secara descending.
  ```sql
  SELECT * FROM customers
  ORDER BY name DESC LIMIT 20;
  ```

### Mengurutkan Berdasarkan Beberapa Kolom
Anda dapat mengurutkan data berdasarkan lebih dari satu kolom. Urutan kolom dalam klausa `ORDER BY` menentukan prioritas pengurutan.

- **Contoh**: Mengurutkan pelanggan berdasarkan negara secara ascending, lalu berdasarkan nama secara descending.
  ```sql
  SELECT * FROM customers
  ORDER BY country ASC, name DESC LIMIT 50;
  ```
  Pertama, data akan diurutkan berdasarkan `country`. Jika ada beberapa pelanggan dengan negara yang sama, mereka akan diurutkan berdasarkan `name` secara descending.

---

## Summary

Klausa `ORDER BY` di SQL adalah perintah fundamental untuk mengurutkan hasil kueri. Data dapat diurutkan secara ascending (menaik) menggunakan `ASC` atau secara descending (menurun) menggunakan `DESC`. Kemampuan untuk mengurutkan berdasarkan beberapa kolom memberikan fleksibilitas tinggi dalam menyajikan data sesuai kebutuhan, dengan prioritas pengurutan ditentukan oleh urutan kolom dalam klausa `ORDER BY`.
