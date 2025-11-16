---
id: Membuat Database
aliases: []
tags:
  - mysql
  - databases
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[mysql]], [[databases]]

---

## Cue

- Bagaimana cara mengakses MySQL dari command line?
- Bagaimana cara membuat database baru di MySQL?
- Bagaimana cara melihat daftar database yang ada?
- Bagaimana cara menghapus database di MySQL?
- Bagaimana cara memilih database untuk digunakan?

---

## Notes

### Mengakses dan Mengelola Database MySQL via Command Line

-   **Langkah Awal**:
    -   Pastikan layanan MySQL sedang berjalan (misalnya, melalui XAMPP Control Panel).
    -   Buka *shell* atau *command prompt*.

### Perintah Dasar MySQL

1.  **Login ke MySQL**:
    -   Gunakan perintah berikut untuk masuk ke *prompt* MySQL sebagai pengguna `root` (jika tidak ada kata sandi, hilangkan `-p`).
    ```bash
    mysql -u root -p
    ```

2.  **Membuat Database Baru**:
    -   Perintah untuk membuat *database* baru dengan nama `mysql_db`.
    ```sql
    CREATE DATABASE mysql_db;
    ```

3.  **Menampilkan Daftar Database**:
    -   Perintah untuk melihat semua *database* yang ada di *server* MySQL.
    ```sql
    SHOW DATABASES;
    ```

4.  **Menghapus Database**:
    -   Perintah untuk menghapus *database* dengan nama `mysql_db`. **Hati-hati**, operasi ini tidak dapat dibatalkan.
    ```sql
    DROP DATABASE mysql_db;
    ```

5.  **Memilih Database untuk Digunakan**:
    -   Perintah untuk memilih *database* `mysql_latihan` sebagai *database* aktif, sehingga perintah SQL selanjutnya akan berlaku pada *database* ini.
    ```sql
    USE mysql_latihan;
    ```

---

## Summary

Mengelola *database* MySQL dari *command line* melibatkan beberapa perintah dasar. Setelah *login* dengan `mysql -u root -p`, pengguna dapat membuat *database* baru menggunakan `CREATE DATABASE`, melihat daftar *database* dengan `SHOW DATABASES`, menghapus *database* dengan `DROP DATABASE`, dan memilih *database* aktif menggunakan `USE`. Perintah-perintah ini esensial untuk interaksi langsung dengan *server* MySQL.