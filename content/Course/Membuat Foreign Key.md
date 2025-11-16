---
id: Membuat Foreign Key
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

- Apa fungsi dari Foreign Key dalam database?
- Bagaimana cara membuat Foreign Key di MySQL?
- Bagaimana Foreign Key digunakan untuk relasi antar tabel?

---

## Notes

### Fungsi Foreign Key

-   **Foreign Key** (Kunci Asing) berfungsi sebagai kolom referensi yang digunakan untuk membuat relasi antar tabel dalam sebuah *database*.
-   Ini memastikan integritas referensial, yaitu data di satu tabel yang merujuk ke data di tabel lain harus konsisten.
-   **Contoh**: Dalam skenario data kelas yang memiliki beberapa data siswa, `kelas_id` di tabel siswa akan menjadi *Foreign Key* yang merujuk ke `id` di tabel kelas.

### Langkah-langkah Membuat Foreign Key

1.  **Buat Tabel Utama (Parent Table)**:
    -   Misalnya, membuat tabel `kelas` dengan `id` sebagai *Primary Key*.
    ```sql
    CREATE TABLE kelas(
        id INT NOT NULL AUTO_INCREMENT,
        nama VARCHAR(2),
        PRIMARY KEY(id)
    );
    ```

2.  **Hapus Tabel Anak (Child Table) Jika Sudah Ada**:
    -   Jika tabel `siswa` sudah ada dan ingin dibuat ulang, hapus terlebih dahulu.
    ```sql
    DROP TABLE siswa;
    ```

3.  **Buat Tabel Anak (Child Table) dengan Foreign Key**:
    -   Buat tabel `siswa` yang memiliki kolom `kelas_id` yang akan menjadi *Foreign Key*.
    -   Deklarasikan `FOREIGN KEY(kelas_id) REFERENCES kelas(id)` untuk menghubungkan `kelas_id` di tabel `siswa` ke `id` di tabel `kelas`.
    ```sql
    CREATE TABLE siswa(
        id INT NOT NULL AUTO_INCREMENT,
        kelas_id INT NOT NULL,
        nama VARCHAR(50) NOT NULL,
        PRIMARY KEY(id),
        FOREIGN KEY(kelas_id) REFERENCES kelas(id)
    );
    ```

---

## Summary

Foreign Key adalah elemen krusial dalam *database* relasional yang berfungsi sebagai kolom referensi untuk membangun hubungan antar tabel dan menjaga integritas data. Dengan mendeklarasikan `FOREIGN KEY` yang merujuk ke `PRIMARY KEY` di tabel lain, kita dapat memastikan konsistensi data. Proses pembuatannya melibatkan definisi *Primary Key* di tabel utama dan kemudian mendeklarasikan *Foreign Key* di tabel anak yang menunjuk ke *Primary Key* tersebut.