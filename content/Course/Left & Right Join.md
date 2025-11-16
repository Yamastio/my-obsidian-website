---
id: Left & Right Join
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

- Apa itu `LEFT JOIN` dan `RIGHT JOIN` dalam SQL?
- Bagaimana perbedaan prioritas tabel pada `LEFT JOIN` dan `RIGHT JOIN`?
- Kapan nilai `NULL` muncul dalam hasil `LEFT JOIN` dan `RIGHT JOIN`?

---

## Notes

### Pengertian `LEFT JOIN` dan `RIGHT JOIN`
`LEFT JOIN` (atau `LEFT OUTER JOIN`) dan `RIGHT JOIN` (atau `RIGHT OUTER JOIN`) digunakan untuk menggabungkan baris dari dua tabel atau lebih berdasarkan kolom terkait. Perbedaan utamanya terletak pada tabel mana yang diprioritaskan untuk menampilkan semua barisnya.

### `LEFT JOIN`
- **Fungsi**: Mengembalikan semua baris dari tabel "kiri" (tabel pertama dalam klausa `FROM`) dan baris yang cocok dari tabel "kanan".
- **Nilai `NULL`**: Jika tidak ada kecocokan di tabel "kanan", kolom dari tabel "kanan" akan diisi dengan nilai `NULL`.
- **Contoh**: Mengambil semua pelanggan dan data pesanan yang cocok. Jika ada pelanggan tanpa pesanan, mereka tetap akan ditampilkan dengan kolom `orders.date` bernilai `NULL`.
  ```sql
  SELECT customers.id, customers.name, orders.date
  FROM customers
  LEFT JOIN orders
  ON customers.id = orders.customer_id
  LIMIT 10;
  ```

### `RIGHT JOIN`
- **Fungsi**: Mengembalikan semua baris dari tabel "kanan" (tabel kedua dalam klausa `FROM` atau setelah `RIGHT JOIN`) dan baris yang cocok dari tabel "kiri".
- **Nilai `NULL`**: Jika tidak ada kecocokan di tabel "kiri", kolom dari tabel "kiri" akan diisi dengan nilai `NULL`.
- **Contoh**: Mengambil semua pesanan dan data pelanggan yang cocok. Jika ada pesanan tanpa pelanggan yang terdaftar (misalnya data tidak konsisten), pesanan tersebut tetap akan ditampilkan dengan kolom `customers.name` bernilai `NULL`.
  ```sql
  SELECT customers.id, customers.name, orders.date
  FROM customers
  RIGHT JOIN orders
  ON customers.id = orders.customer_id
  LIMIT 10;
  ```

---

## Summary

`LEFT JOIN` dan `RIGHT JOIN` adalah jenis `OUTER JOIN` dalam SQL yang digunakan untuk menggabungkan data dari dua tabel. `LEFT JOIN` memprioritaskan tabel kiri, mengembalikan semua barisnya dan mencocokkan baris dari tabel kanan, mengisi `NULL` jika tidak ada kecocokan. Sebaliknya, `RIGHT JOIN` memprioritaskan tabel kanan. Keduanya penting untuk analisis data di mana semua entri dari satu tabel harus dipertahankan dalam hasil.
