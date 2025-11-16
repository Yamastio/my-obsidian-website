---
id: Membuat Unique Key
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

- Apa fungsi dari Unique Key dalam database?
- Apa perbedaan Unique Key dengan Primary Key?
- Bagaimana cara membuat Unique Key saat membuat tabel?
- Bagaimana cara menambahkan Unique Key ke tabel yang sudah ada?
- Bagaimana cara menghapus Unique Key dari tabel?

---

## Notes

### Fungsi Unique Key

-   **Unique Key** berfungsi untuk memastikan bahwa semua nilai dalam kolom tertentu adalah unik.
-   Ini berarti tidak ada dua baris yang dapat memiliki nilai yang sama di kolom yang memiliki *Unique Key*.

### Perbedaan dengan Primary Key

-   **Primary Key**:
    -   Hanya ada satu *Primary Key* per tabel.
    -   Nilainya harus unik dan tidak boleh `NULL`.
    -   Berfungsi sebagai identitas utama dan kunci referensi antar tabel.
-   **Unique Key**:
    -   Bisa ada lebih dari satu *Unique Key* per tabel.
    -   Nilainya harus unik, tetapi boleh `NULL` (hanya satu nilai `NULL` yang diizinkan).
    -   Hanya untuk menyimpan data unik, tanpa menjadi identitas utama dari suatu data.

### Cara Membuat Unique Key

#### 1. Saat Membuat Tabel

-   Anda dapat mendeklarasikan *Unique Key* langsung saat membuat tabel menggunakan perintah `CREATE TABLE`.
-   **Contoh**: Membuat tabel `penduduk` dengan `nik` sebagai *Unique Key*.
    ```sql
    CREATE TABLE penduduk (
        id INT NOT NULL AUTO_INCREMENT,
        nik VARCHAR(50) NOT NULL,
        PRIMARY KEY(id),
        UNIQUE KEY(nik)
    );
    ```

#### 2. Menambahkan Unique Key ke Tabel yang Sudah Ada

-   Jika tabel sudah ada dan Anda ingin menambahkan *Unique Key* pada kolom tertentu.
-   **Langkah 1**: Tambahkan kolom jika belum ada (misalnya `no_induk` ke tabel `siswa`).
    ```sql
    ALTER TABLE siswa
    ADD COLUMN no_induk VARCHAR(10);
    ```
-   **Langkah 2**: Tambahkan *Unique Key* pada kolom `no_induk`. Anda juga bisa membuat *Unique Key* gabungan dari beberapa kolom.
    ```sql
    ALTER TABLE siswa
    ADD UNIQUE KEY(no_induk);
    -- Contoh Unique Key gabungan:
    -- ALTER TABLE siswa ADD UNIQUE KEY(no_induk, name, id);
    ```

#### 3. Menghapus Unique Key dari Tabel

-   Untuk menghapus *Unique Key* dari tabel, Anda perlu mengetahui nama *index* yang dibuat untuk *Unique Key* tersebut. Biasanya, MySQL akan memberi nama *index* yang sama dengan nama kolom jika hanya satu kolom.
-   **Sintaks**:
    ```sql
    ALTER TABLE nama_tabel
    DROP INDEX nama_index;
    ```
-   **Contoh**: Menghapus *Unique Key* pada kolom `no_induk` dari tabel `siswa`.
    ```sql
    ALTER TABLE siswa
    DROP INDEX no_induk;
    ```

---

## Summary

Unique Key memastikan keunikan nilai dalam satu atau lebih kolom, berbeda dengan Primary Key yang juga berfungsi sebagai identitas utama tabel dan tidak boleh `NULL`. Unique Key dapat dibuat saat pembuatan tabel atau ditambahkan ke tabel yang sudah ada menggunakan `ALTER TABLE ... ADD UNIQUE KEY`. Untuk menghapusnya, digunakan `ALTER TABLE ... DROP INDEX` dengan nama *index* yang sesuai. Penggunaan Unique Key penting untuk menjaga integritas data dan validasi input.