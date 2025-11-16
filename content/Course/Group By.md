---
id: Group By
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

- Apa itu klausa `GROUP BY` di SQL?
- Bagaimana cara menghitung jumlah record per grup menggunakan `GROUP BY`?
- Bagaimana cara menggunakan alias dengan `GROUP BY`?
- Bagaimana cara menghitung nilai rata-rata dan maksimum per grup?

---

## Notes

### Penggunaan Dasar `GROUP BY`
Klausa `GROUP BY` digunakan dalam SQL untuk mengelompokkan baris yang memiliki nilai yang sama dalam satu atau lebih kolom menjadi satu baris ringkasan. Ini sering digunakan bersama dengan fungsi agregat (seperti `COUNT()`, `AVG()`, `SUM()`, `MAX()`, `MIN()`) untuk melakukan perhitungan pada setiap grup.

### Menghitung Jumlah Data per Grup
- **Contoh**: Menghitung jumlah pelanggan (`id`) untuk setiap negara.
  ```sql
  SELECT COUNT(id), country FROM customers
  GROUP BY country;
  ```
  Hasilnya akan menampilkan jumlah pelanggan untuk setiap negara yang berbeda.

### Menggunakan Alias dengan `GROUP BY`
Anda dapat menggunakan alias untuk memberikan nama yang lebih deskriptif pada kolom hasil dari fungsi agregat.

- **Contoh**: Menghitung jumlah pelanggan per negara dengan alias "Jumlah Customers".
  ```sql
  SELECT COUNT(id) AS `Jumlah Customers`, country
  FROM customers
  GROUP BY country;
  ```

### Fungsi Agregat Lainnya dengan `GROUP BY`
Selain `COUNT()`, Anda juga dapat menggunakan fungsi agregat lain untuk mendapatkan informasi ringkasan per grup.

- **Rata-rata (AVG)**: Menghitung rata-rata usia pelanggan per negara.
  ```sql
  SELECT AVG(age), country
  FROM customers
  GROUP BY country;
  ```
- **Nilai Maksimal (MAX)**: Menemukan usia tertua pelanggan per negara.
  ```sql
  SELECT MAX(age) AS `Usia Tertua`, country
  FROM customers
  GROUP BY country;
  ```

---

## Summary

Klausa `GROUP BY` di SQL adalah alat yang ampuh untuk mengelompokkan baris data berdasarkan nilai yang sama dalam satu atau lebih kolom. Ini sering digunakan bersama dengan fungsi agregat seperti `COUNT()`, `AVG()`, dan `MAX()` untuk melakukan perhitungan ringkasan pada setiap grup. Penggunaan alias juga dapat meningkatkan keterbacaan hasil kueri yang kompleks.
