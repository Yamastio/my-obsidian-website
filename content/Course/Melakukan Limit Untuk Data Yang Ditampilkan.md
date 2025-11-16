---
id: Melakukan Limit Untuk Data Yang Ditampilkan
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

- Bagaimana cara membatasi jumlah baris data yang ditampilkan oleh kueri SQL?
- Bagaimana cara melompati sejumlah baris tertentu sebelum menerapkan batasan hasil?

---

## Notes

### Menggunakan `LIMIT`
Klausa `LIMIT` digunakan dalam perintah `SELECT` untuk membatasi jumlah baris yang dikembalikan oleh kueri. Ini sangat berguna ketika Anda hanya ingin melihat sebagian kecil dari hasil yang mungkin sangat banyak.

- **Contoh**: Mengambil 10 baris pertama dari tabel `customers`.
  ```sql
  SELECT * FROM customers LIMIT 10;
  ```

### Menggunakan `LIMIT` dengan `OFFSET`
Klausa `OFFSET` digunakan bersama dengan `LIMIT` untuk melompati sejumlah baris tertentu sebelum mulai mengambil baris yang dibatasi. Ini sering digunakan untuk implementasi paginasi (halaman).

- **Contoh**: Mengambil 10 baris data, dimulai setelah melompati 20 baris pertama.
  ```sql
  SELECT * FROM customers LIMIT 10 OFFSET 20;
  ```
  (Catatan: Dalam contoh asli ada typo `OFFSET;` tanpa angka, saya asumsikan maksudnya adalah `OFFSET <jumlah_baris_yang_dilompati>`).

---

## Summary

Klausa `LIMIT` di SQL berfungsi untuk membatasi jumlah baris yang dikembalikan oleh sebuah kueri, sangat berguna untuk mengontrol ukuran hasil. Ketika dikombinasikan dengan `OFFSET`, `LIMIT` memungkinkan pengguna untuk melompati sejumlah baris tertentu sebelum mengambil data, sebuah fungsionalitas kunci untuk mengimplementasikan paginasi dalam aplikasi.
