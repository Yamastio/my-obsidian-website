---
id: Instalasi MySQL
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

- Bagaimana cara menginstal MySQL menggunakan XAMPP?
- Bagaimana cara mengakses antarmuka command-line MySQL setelah instalasi?

---

## Notes

### Langkah-langkah Instalasi MySQL dengan XAMPP
XAMPP adalah paket perangkat lunak gratis dan open-source yang berisi Apache HTTP Server, MariaDB (pengganti MySQL), dan interpreter untuk skrip yang ditulis dalam bahasa PHP dan Perl. Ini adalah cara yang mudah untuk menginstal lingkungan server lokal, termasuk MySQL.

1.  **Unduh XAMPP**: Kunjungi situs web resmi Apache Friends dan unduh versi XAMPP yang sesuai dengan sistem operasi Anda.
2.  **Instalasi**: Jalankan installer XAMPP dan ikuti langkah-langkah instalasi standar (klik "Next" hingga selesai).
3.  **Jalankan Layanan**: Setelah instalasi, buka XAMPP Control Panel dan mulai layanan Apache dan MySQL. Pastikan statusnya "Running".

### Mengakses MySQL Command-Line
Setelah layanan MySQL berjalan, Anda dapat mengakses antarmuka command-line MySQL melalui shell XAMPP.

1.  **Buka XAMPP Shell**: Di XAMPP Control Panel, klik tombol "Shell" untuk membuka jendela command prompt atau terminal.
2.  **Login ke MySQL**: Ketik perintah berikut untuk login ke MySQL sebagai pengguna `root` (tanpa kata sandi default):
    ```bash
    mysql -uroot
    ```
    Anda sekarang berada di prompt MySQL dan dapat mulai menjalankan perintah SQL.

---

## Summary

MySQL dapat diinstal dengan mudah menggunakan XAMPP, sebuah paket server lokal yang mencakup MariaDB. Proses instalasi melibatkan pengunduhan dan menjalankan installer, diikuti dengan memulai layanan MySQL dari XAMPP Control Panel. Setelah itu, antarmuka command-line MySQL dapat diakses melalui XAMPP Shell dengan perintah `mysql -uroot`, memungkinkan pengguna untuk berinteraksi langsung dengan database.
