---
id: Update
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

- Bagaimana cara menggunakan perintah `UPDATE` di SQL?
- Bagaimana cara memperbarui satu baris data spesifik?
- Mengapa klausa `WHERE` sangat penting saat melakukan `UPDATE`?

---

## Notes

### Sintaks Dasar UPDATE
Perintah `UPDATE` digunakan untuk memodifikasi data yang sudah ada di dalam sebuah tabel. Sintaks dasarnya adalah:
```sql
UPDATE nama_tabel
SET kolom1 = nilai1, kolom2 = nilai2, ...
WHERE kondisi;
```

### Memperbarui Satu Baris
Untuk memperbarui satu baris data yang spesifik, gunakan klausa `WHERE` dengan kunci unik (seperti `id`). Ini memastikan hanya satu baris yang terpengaruh.

- **Contoh**: Mengubah nama, kota, dan negara untuk pelanggan dengan `id = 3`.
  ```sql
  UPDATE customers
  SET name="Miku", city="Tokyo", country="Japan"
  WHERE id = 3;
  ```

### Memperbarui Beberapa Baris (Peringatan)
Klausa `WHERE` sangat krusial karena jika kondisinya cocok dengan beberapa baris, semua baris tersebut akan diperbarui. Jika klausa `WHERE` dihilangkan, **semua baris** dalam tabel akan diubah.

- **Contoh**: Mengubah `city` menjadi "Kyoto" untuk semua pelanggan yang negaranya "Japan".
  ```sql
  UPDATE customers
  SET city="Kyoto"
  WHERE country = "Japan";
  ```
- Perintah di atas akan mengubah kolom `city` untuk semua baris yang memenuhi kondisi `country = "Japan"`. Gunakan dengan hati-hati.

---

## Summary

Perintah `UPDATE` dalam SQL berfungsi untuk memodifikasi data yang sudah ada dalam tabel. Sangat penting untuk menggunakan klausa `WHERE` secara hati-hati untuk menargetkan baris yang benar. Jika `WHERE` menargetkan kunci unik, hanya satu baris yang akan berubah, tetapi jika kondisinya lebih umum, beberapa baris bisa terpengaruh secara bersamaan.
