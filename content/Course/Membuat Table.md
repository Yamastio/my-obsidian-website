---
id: Membuat Table
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

- Bagaimana cara membuat tabel baru di MySQL?
- Bagaimana cara melihat daftar tabel yang ada dalam database?
- Bagaimana cara menghapus tabel dari database?
- Bagaimana cara mengubah nama tabel di MySQL?

---

## Notes

### Membuat Tabel Baru

-   Anda dapat membuat tabel baru di MySQL menggunakan perintah `CREATE TABLE`.
-   **Sintaks Dasar**:
    ```sql
    CREATE TABLE nama_tabel (
        nama_kolom1 tipe_data,
        nama_kolom2 tipe_data,
        ...
    );
    ```
-   **Contoh**: Membuat tabel `anggota` dengan kolom `id` (integer) dan `nama` (varchar).
    ```sql
    CREATE TABLE anggota (
        id INT,
        nama VARCHAR(254)
    );
    ```

### Menampilkan Tabel

-   Untuk melihat daftar semua tabel yang ada dalam *database* yang sedang aktif, gunakan perintah `SHOW TABLES;`.
    ```sql
    SHOW TABLES;
    ```

### Menghapus Tabel

-   Untuk menghapus tabel dari *database*, gunakan perintah `DROP TABLE`. **Hati-hati**, operasi ini akan menghapus tabel beserta semua datanya secara permanen.
    ```sql
    DROP TABLE anggota;
    ```

### Mengubah Nama Tabel

-   Untuk mengubah nama tabel yang sudah ada, gunakan perintah `ALTER TABLE` dengan klausa `RENAME TO`.
    ```sql
    ALTER TABLE nama_tabel_lama
    RENAME TO nama_tabel_baru;
    ```
-   **Contoh**: Mengubah nama tabel `anggota` menjadi `siswa`.
    ```sql
    ALTER TABLE anggota
    RENAME TO siswa;
    ```

---

## Summary

Dalam MySQL, pengelolaan tabel melibatkan beberapa perintah SQL dasar. Tabel baru dibuat dengan `CREATE TABLE`, memungkinkan definisi kolom dan tipe datanya. Untuk melihat tabel yang ada, gunakan `SHOW TABLES`. Tabel dapat dihapus secara permanen dengan `DROP TABLE`, dan namanya dapat diubah menggunakan `ALTER TABLE ... RENAME TO`. Perintah-perintah ini fundamental untuk strukturisasi dan pemeliharaan *database*.