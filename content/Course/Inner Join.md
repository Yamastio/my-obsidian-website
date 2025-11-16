---
id: Inner Join
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

- Apa itu `INNER JOIN` dalam SQL?
- Bagaimana `INNER JOIN` menggabungkan data dari dua tabel?
- Apa perbedaan `INNER JOIN` dengan `CROSS JOIN` atau `STRAIGHT JOIN`?

---

## Notes

### Pengertian `INNER JOIN`
`INNER JOIN` adalah klausa dalam SQL yang digunakan untuk menggabungkan baris dari dua atau lebih tabel berdasarkan kolom yang memiliki hubungan di antara mereka. `INNER JOIN` hanya akan mengembalikan baris di mana ada kecocokan di kedua tabel yang digabungkan.

### Perbedaan dengan `CROSS JOIN` atau `STRAIGHT JOIN`
Berbeda dengan `CROSS JOIN` atau `STRAIGHT JOIN` yang menggabungkan setiap baris dari satu tabel dengan setiap baris dari tabel lain (menghasilkan produk Cartesian), `INNER JOIN` secara spesifik menggabungkan baris berdasarkan kondisi yang ditentukan, biasanya melibatkan *primary key* dan *foreign key*.

### Contoh Penggunaan
- **Skenario**: Menggabungkan data pelanggan dari tabel `customers` dengan data pesanan dari tabel `orders` berdasarkan `customer_id` yang sama.
  ```sql
  SELECT * FROM customers
  INNER JOIN orders
  ON customers.id = orders.customer_id;
  ```
- Dalam contoh ini, `customers.id` adalah *primary key* di tabel `customers`, dan `orders.customer_id` adalah *foreign key* di tabel `orders` yang merujuk ke `customers.id`. Hasilnya akan menampilkan semua kolom dari kedua tabel untuk setiap baris di mana `id` pelanggan cocok dengan `customer_id` pesanan.

---

## Summary

`INNER JOIN` dalam SQL adalah perintah fundamental untuk menggabungkan baris dari dua atau lebih tabel berdasarkan kecocokan nilai di kolom yang terkait. Berbeda dengan jenis join lain yang mungkin menghasilkan kombinasi yang tidak relevan, `INNER JOIN` secara spesifik hanya mengembalikan baris di mana ada kecocokan di kedua tabel, menjadikannya sangat berguna untuk menghubungkan data yang relevan berdasarkan kunci primer dan asing.
