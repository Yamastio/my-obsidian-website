---
id: Pencarian Data Tertentu
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

- Bagaimana cara memfilter data di SQL menggunakan klausa `WHERE`?
- Bagaimana cara menggunakan operator perbandingan (misalnya `<`) dalam klausa `WHERE`?
- Bagaimana cara menggunakan operator `NOT` dalam klausa `WHERE`?
- Bagaimana cara menggunakan operator `IN` untuk memfilter berdasarkan beberapa nilai?
- Bagaimana cara menggunakan operator `LIKE` untuk pencocokan pola?

---

## Notes

### Memfilter Data dengan `WHERE`
Klausa `WHERE` digunakan dalam perintah `SELECT` untuk memfilter baris data yang ingin diambil berdasarkan kondisi tertentu. Ini memungkinkan Anda untuk mengambil hanya data yang relevan dari sebuah tabel.

### Menggunakan Operator Perbandingan
Anda dapat menggunakan operator perbandingan seperti `=`, `<`, `>`, `<=`, `>=`, `<>` (tidak sama dengan) untuk memfilter data.

- **Contoh**: Mencari pelanggan dari negara "Indonesia".
  ```sql
  SELECT * FROM customers
  WHERE country = "Indonesia";
  ```
- **Contoh**: Mencari pelanggan dengan `id` kurang dari 5.
  ```sql
  SELECT * FROM customers
  WHERE id < 5;
  ```

### Menggunakan Operator Logika (`NOT`)
Operator `NOT` digunakan untuk membalikkan kondisi. Jika kondisi aslinya benar, `NOT` akan membuatnya salah, dan sebaliknya.

- **Contoh**: Mencari pelanggan yang *bukan* dari negara "Indonesia".
  ```sql
  SELECT * FROM customers
  WHERE NOT country = "Indonesia" LIMIT 10;
  ```

### Menggunakan Operator `IN`
Operator `IN` digunakan untuk menentukan beberapa nilai yang mungkin untuk sebuah kolom dalam klausa `WHERE`. Ini adalah cara singkat untuk menulis beberapa kondisi `OR`.

- **Contoh**: Mencari pelanggan dari "Indonesia", "Russia", "German", atau "Japan".
  ```sql
  SELECT * FROM customers
  WHERE country IN ("Indonesia", "Russia", "German", "Japan") LIMIT 10;
  ```

### Menggunakan Operator `LIKE` (Pencocokan Pola)
Operator `LIKE` digunakan untuk mencari pola tertentu dalam sebuah kolom. Ini sering digunakan bersama dengan wildcard:
- `%`: Mewakili nol atau lebih karakter.
- `_`: Mewakili satu karakter tunggal.

- **Contoh**: Mencari kota yang dimulai dengan "ber".
  ```sql
  SELECT * FROM customers
  WHERE city LIKE "ber%";
  ```
- **Contoh**: Mencari kota yang diakhiri dengan "lin".
  ```sql
  SELECT * FROM customers
  WHERE city LIKE "%lin";
  ```
- **Contoh**: Mencari kota yang mengandung "ne" di mana saja.
  ```sql
  SELECT * FROM customers
  WHERE city LIKE "%ne%";
  ```

---

## Summary

Klausa `WHERE` di SQL adalah fundamental untuk memfilter data berdasarkan kondisi yang ditentukan. Ini mendukung berbagai operator, termasuk perbandingan (`=`, `<`, `>`), logika (`NOT`), `IN` untuk mencocokkan beberapa nilai, dan `LIKE` untuk pencocokan pola menggunakan wildcard (`%`, `_`). Dengan kombinasi operator ini, pengguna dapat mengambil subset data yang sangat spesifik dari database.
