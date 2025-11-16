---
id: Memahami Sensitive Data Exposure & Security Misconfiguration
aliases: []
tags:
  - web_security
  - owasp
comments: true
date: 2024-12-05
draft: false
---

---

Related: [[index|Home]], [[web_security]], [[owasp]]

---

## Cue

- Apa itu Sensitive Data Exposure dan penyebab utamanya?
- Apa saja risiko dari Sensitive Data Exposure?
- Apa itu Security Misconfiguration dan contoh umumnya?
- Bagaimana Sensitive Data Exposure dan Security Misconfiguration saling terkait?
- Bagaimana contoh kasus Sensitive Data Exposure dan Security Misconfiguration pada DVWA dan situs lain?
- Apa saja langkah mitigasi untuk Sensitive Data Exposure dan Security Misconfiguration?

---

## Notes

### Sensitive Data Exposure

-   **Definisi**: Kondisi di mana data sensitif (misalnya, kata sandi, email, informasi pribadi) tidak terlindungi dengan baik dan dapat diakses oleh pihak yang tidak berwenang.
-   **Penyebab Utama**:
    -   Manajemen data yang buruk dalam aplikasi.
    -   Kurangnya enkripsi pada data sensitif.
    -   Penggunaan protokol yang tidak aman (misalnya, HTTP tanpa SSL/TLS).
    -   Penyimpanan *file* konfigurasi di lokasi yang mudah diakses.
-   **Risiko**:
    -   Kehilangan kredibilitas perusahaan.
    -   Kerugian finansial akibat pencurian data atau pelanggaran hukum.
    -   Serangan **MITM (Man-in-the-Middle)** yang memungkinkan penyadapan data selama transmisi.

### Security Misconfiguration

-   **Definisi**: Salah satu penyebab utama Sensitive Data Exposure, terjadi ketika sistem atau aplikasi tidak dikonfigurasi dengan benar sehingga menciptakan celah keamanan.
-   **Contoh Umum**:
    1.  **Fitur yang Tidak Diperlukan Terpasang**: Fitur, komponen, atau dokumentasi yang tidak digunakan dibiarkan aktif (misalnya, direktori `/backup`).
    2.  **Akun Default atau Kata Sandi Default Aktif**: Kredensial bawaan vendor tidak diubah (misalnya, `admin:admin`).
    3.  **Kebijakan Kata Sandi yang Lemah**: Tidak adanya persyaratan untuk kata sandi kuat (misalnya, panjang minimal, kombinasi karakter).
    4.  **Fitur Keamanan yang Tidak Dipelihara**: *File* sensitif atau direktori tidak dilindungi; pesan *error* terlalu detail.
    5.  **Penggunaan Versi Perangkat Lunak yang Usang**: Aplikasi atau *server* berjalan di versi lama dengan celah keamanan yang diketahui.
    6.  **CORS (Cross-Origin Resource Sharing) yang Salah Konfigurasi**: Memberikan izin akses terlalu luas ke sumber daya aplikasi dari domain luar.

### Contoh pada DVWA (Damn Vulnerable Web Application)

1.  **Akses Root Folder**:
    -   Semua pengguna dapat mengakses *folder root* web `/var/www/html`.
    -   *File* seperti `config.inc.php.bak` dapat diakses melalui URL `http://localhost:4280/config/config.inc.php.bak`.
    -   *File* ini menyimpan kredensial *database* (`$db_user = 'root'; $db_password = 'password';`).
2.  **File Setup yang Tidak Aman**:
    -   *File* `setup.php` memungkinkan siapa saja mereset *database* atau membuat/menghapus tabel hanya dengan klik tombol.
3.  **Pencarian Endpoint dengan Tools**:
    -   *Tools* seperti **Dirsearch** digunakan untuk menemukan direktori sensitif.
    -   Contoh Google Dork: `intitle:"index of" inurl:/backup/"wp-config"` untuk mencari *file* `wp-config` di direktori `/backup`.
4.  **Masalah pada Situs Contoh (testphp.vulnweb.com)**:
    -   Kebijakan *password* lemah: pengguna dapat mendaftar dengan *password* angka saja.
    -   Informasi sensitif (username dan *password*) ditampilkan setelah pendaftaran.
5.  **Penggunaan Teknologi Usang**:
    -   Dengan ekstensi *browser* seperti **Wappalyzer**, dapat ditemukan bahwa situs menggunakan PHP versi 5, yang usang dan memiliki banyak celah keamanan.

### Langkah Mitigasi

1.  **Lindungi Data Sensitif**:
    -   Gunakan enkripsi untuk data yang disimpan dan dalam transmisi.
    -   Terapkan protokol HTTPS menggunakan sertifikat SSL/TLS.
2.  **Konfigurasi Keamanan yang Baik**:
    -   Hapus fitur atau *file* yang tidak diperlukan.
    -   Nonaktifkan akun atau kata sandi *default* setelah instalasi.
    -   Terapkan kebijakan kata sandi yang kuat.
3.  **Update dan Patch**:
    -   Selalu perbarui aplikasi, *server*, dan perangkat lunak lainnya.
    -   Gunakan versi perangkat lunak yang didukung dengan *patch* keamanan terbaru.
4.  **Proteksi File dan Direktori**:
    -   Jangan simpan *file* konfigurasi di *root folder* yang dapat diakses publik.
    -   Lindungi direktori sensitif dengan autentikasi tambahan atau izin akses yang ketat.
5.  **Audit Keamanan**:
    -   Lakukan pemeriksaan rutin untuk mendeteksi *misconfiguration*.
    -   Gunakan *tools* seperti **Nmap** (port terbuka), **Dirbuster** (direktori tersembunyi), **Burp Suite** (pengujian aplikasi web).
6.  **Pengaturan CORS**:
    -   Batasi domain yang diizinkan untuk mengakses sumber daya aplikasi.

---

## Summary

Sensitive Data Exposure terjadi ketika data sensitif tidak terlindungi, seringkali disebabkan oleh Security Misconfiguration, di mana sistem atau aplikasi tidak dikonfigurasi dengan benar. Penyebab umum meliputi manajemen data yang buruk, kurangnya enkripsi, penggunaan protokol tidak aman, dan penyimpanan file konfigurasi yang rentan. Security Misconfiguration mencakup fitur tidak perlu yang aktif, kredensial default, kebijakan kata sandi lemah, fitur keamanan tidak terpelihara, perangkat lunak usang, dan CORS yang salah konfigurasi. Risiko yang timbul meliputi pencurian data, kerugian finansial, dan serangan MITM. Mitigasi melibatkan enkripsi data, konfigurasi keamanan yang ketat, pembaruan perangkat lunak, proteksi file, audit keamanan rutin, dan pengaturan CORS yang tepat.
