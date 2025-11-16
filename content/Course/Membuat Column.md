---
id: Membuat Column
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

- Bagaimana cara menambahkan kolom baru ke tabel MySQL?
- Bagaimana cara menghapus kolom dari tabel MySQL?

---

## Notes

### Menambahkan Kolom ke Tabel

-   Untuk menambahkan kolom baru ke tabel yang sudah ada, gunakan perintah `ALTER TABLE` dengan klausa `ADD COLUMN`.
-   **Sintaks**:
    ```sql
    ALTER TABLE nama_tabel ADD COLUMN nama_kolom tipe_data(panjang);
    ```
-   **Contoh**: Menambahkan kolom `kelas` dengan tipe data `char` dan panjang 2 ke tabel `siswa`.
    ```sql
    ALTER TABLE siswa ADD COLUMN kelas char(2);
    ```

### Menghapus Kolom dari Tabel

-   Untuk menghapus kolom dari tabel yang sudah ada, gunakan perintah `ALTER TABLE` dengan klausa `DROP COLUMN`.
-   **Sintaks**:
    ```sql
    ALTER TABLE nama_tabel DROP COLUMN nama_kolom;
    ```
-   **Contoh**: Menghapus kolom `kelas` dari tabel `siswa`.
    ```sql
    ALTER TABLE siswa DROP COLUMN kelas;
    ```

---

## Summary

Dalam MySQL, perintah `ALTER TABLE` digunakan untuk memodifikasi struktur tabel. Untuk menambahkan kolom baru, gunakan `ALTER TABLE nama_tabel ADD COLUMN nama_kolom tipe_data`. Sedangkan untuk menghapus kolom, gunakan `ALTER TABLE nama_tabel DROP COLUMN nama_kolom`. Kedua operasi ini memungkinkan pengelolaan skema *database* yang fleksibel setelah tabel dibuat.
