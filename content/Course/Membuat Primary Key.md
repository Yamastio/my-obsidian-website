---
id: Membuat Primary Key
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

- Apa fungsi dari Primary Key dalam database?
- Bagaimana cara membuat Primary Key saat membuat tabel?
- Bagaimana cara menambahkan Primary Key ke tabel yang sudah ada?
- Bagaimana cara menghapus Primary Key dari tabel?

---

## Notes

### Fungsi Primary Key

-   **Primary Key** (Kunci Utama) berfungsi sebagai identitas unik untuk setiap baris dalam sebuah tabel.
-   Setiap nilai dalam kolom *Primary Key* harus unik dan tidak boleh `NULL`.
-   Digunakan sebagai kunci referensi untuk membuat relasi antar tabel (sebagai *Foreign Key* di tabel lain).

### Cara Membuat Primary Key

#### 1. Saat Membuat Tabel

-   Anda dapat mendeklarasikan *Primary Key* langsung saat membuat tabel menggunakan perintah `CREATE TABLE`.
-   **Contoh**: Membuat tabel `anggota` dengan `id` sebagai *Primary Key* yang otomatis bertambah (`AUTO_INCREMENT`).
    ```sql
    CREATE TABLE anggota(
        id INT NOT NULL AUTO_INCREMENT,
        nama VARCHAR(50) NOT NULL,
        PRIMARY KEY(id)
    );
    ```
-   **Verifikasi Struktur Tabel**:
    ```sql
    DESCRIBE anggota;
    ```
    Output akan menunjukkan `id` sebagai `PRI` (Primary Key) dan `Extra` sebagai `auto_increment`.

#### 2. Menambahkan Primary Key ke Tabel yang Sudah Ada

-   Jika tabel sudah ada dan belum memiliki *Primary Key*, Anda bisa menambahkannya menggunakan `ALTER TABLE`.
-   **Sintaks**:
    ```sql
    ALTER TABLE nama_tabel ADD PRIMARY KEY(nama_kolom);
    ```
-   **Contoh**: Menambahkan *Primary Key* pada kolom `id` di tabel `siswa`.
    ```sql
    ALTER TABLE siswa ADD PRIMARY KEY(id);
    ```

#### 3. Menghapus Primary Key dari Tabel

-   Untuk menghapus *Primary Key* dari tabel, gunakan perintah `ALTER TABLE` dengan klausa `DROP PRIMARY KEY`.
-   **Sintaks**:
    ```sql
    ALTER TABLE nama_tabel DROP PRIMARY KEY;
    ```
-   **Contoh**: Menghapus *Primary Key* dari tabel `siswa`.
    ```sql
    ALTER TABLE siswa DROP PRIMARY KEY;
    ```

---

## Summary

Primary Key adalah atribut penting dalam *database* relasional yang menjamin keunikan dan integritas setiap baris data, serta berfungsi sebagai titik referensi untuk relasi antar tabel. Primary Key dapat didefinisikan saat pembuatan tabel dengan `CREATE TABLE ... PRIMARY KEY(kolom)`, ditambahkan ke tabel yang sudah ada menggunakan `ALTER TABLE ... ADD PRIMARY KEY(kolom)`, atau dihapus dengan `ALTER TABLE ... DROP PRIMARY KEY`. Pengelolaan Primary Key yang tepat sangat vital untuk desain *database* yang efisien dan konsisten.
