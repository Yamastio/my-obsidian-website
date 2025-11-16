---
id: 3-Keamanan Aplikasi Web
aliases: []
tags:
  - cybersecurity
  - web_security
  - bughunting
  - jagoansiber
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[web_security]], [[bughunting]], [[jagoansiber]]

---

## Cue

- Bagaimana dasar-dasar komunikasi web (HTTP) bekerja?
- Apa perbedaan situs web dan aplikasi web, serta ancaman yang ada?
- Bagaimana arsitektur dan komponen aplikasi web?
- Bagaimana web proxy digunakan untuk keamanan?

---

## Notes

### 1. Dasar-Dasar Komunikasi Web (HTTP)

### Permintaan dan Respons HTTP
- Komunikasi utama di web: Permintaan HTTP (klien ke server) dan Respons HTTP (server ke klien).

### Header HTTP
- Setiap permintaan/respons memiliki Header HTTP berisi detail penting (jenis konten, opsi).
- Kategori: General, Entity, Request, Response, Security Headers.

### Metode HTTP (GET & POST)
- GET: Parameter dikirim melalui URL.
- POST: Parameter ditempatkan di body permintaan HTTP.
    - Keuntungan POST: Data tidak terekam di log browser, encoding lebih sedikit, lebih banyak data bisa dikirim.

### API (Application Programming Interface)
- Digunakan untuk berinteraksi dengan basis data, memungkinkan operasi CRUD (Create, Read, Update, Delete).

### 2. Memahami Aplikasi Web

### Situs Web vs. Aplikasi Web
- Situs web (Web 1.0) lebih statis.
- Aplikasi web modern (Web 2.0) menyajikan konten dinamis, fungsionalitas lebih luas.

### Distribusi Aplikasi Web
- Platform-independent: Dijalankan di browser tanpa instalasi lokal.
- Fungsionalitas berjalan di server jarak jauh.
- Open-source (WordPress) dan closed-source (Wix).

### Ancaman Aplikasi Web
- Sangat rentan terhadap serangan karena mudah diakses.
- Satu kerentanan bisa menyebabkan kerusakan besar, apalagi jika digabungkan.

### 3. Arsitektur dan Komponen Aplikasi Web

### Struktur Aplikasi Web
- Tidak ada dua aplikasi web yang persis sama, namun ada lapisan dan model infrastruktur umum:
    - One Server: Aplikasi dan basis data di satu server (paling berisiko).
    - Many Servers – One Database: Aplikasi di beberapa server, satu basis data terpisah (lebih aman, segmentasi).
    - Many Servers – Many Databases: Memisahkan data setiap aplikasi di basis data terpisah (redundansi, kurangi downtime).

### Komponen Utama Aplikasi Web
- Klien (Client): Berinteraksi dengan pengguna (HTML, CSS, JavaScript) - Front-End.
- Server: Menjalankan fungsionalitas inti aplikasi (Webserver, Logika Aplikasi Web, Database) - Back-End.
- Layanan (Services): Integrasi dengan pihak ketiga.
- Fungsi (Functions): Untuk model serverless.

### Kerentanan Front-End & Back-End
- Front-End: Sensitive Data Exposure, HTML Injection, XSS, CSRF.
- Back-End: Broken Authentication, File Upload, Command Injection, SQL Injection.

### Mengamankan Aplikasi
- Code Review dan Whitebox Pentesting (jika ada source code) untuk front-end.
- Blackbox Pentesting (jika source code tidak diakses) untuk back-end.

### 4. Menggunakan Web Proxy untuk Keamanan

### Apa itu Web Proxy?
- Alat khusus sebagai perantara (Man-in-the-Middle/MITM) antara browser/aplikasi seluler dan server.
- Menangkap dan melihat semua permintaan web.
- Fokus pada port web (HTTP/80, HTTPS/443).

### Manfaat Web Proxy
- Pemindaian kerentanan aplikasi web.
- Web fuzzing (cari direktori/file tersembunyi, bruteforce kredensial).
- Web crawling (membangun struktur situs).
- Analisis dan modifikasi permintaan/respons web.
- Pengujian konfigurasi web dan code review.

### Contoh Alat Web Proxy
- Burp Suite: Sangat populer untuk pengujian keamanan web.
- ZAP (OWASP Zed Attack Proxy): Alternatif open-source.

### Fitur Penting di Burp Suite
- Intercepting Requests/Responses: Menghentikan dan melihat permintaan/respons.
- Modify Responses: Mengedit header atau body respons.
- Automatic Requests Modification: Tambah/edit header HTTP otomatis (Match and Replace).
- Repeating Requests (Repeater): Mengirim ulang permintaan dengan modifikasi.
- Encoding/Decoding tools: Mengubah format data.
- Intruder / Fuzzer: Untuk fuzzing (kirim banyak payload) atau bruteforce.
- Scanner (Burp Scanner): Alat pemindai kerentanan web kuat.
- Extensions (BApp Store): Menambah fungsionalitas baru.

## Summary

Memahami keamanan aplikasi web adalah keterampilan penting dalam dunia digital saat ini. Materi ini memperkenalkan Anda pada cara kerja aplikasi web, mulai dari komunikasi dasar HTTP, perbedaan antara situs dan aplikasi web, hingga arsitektur di baliknya. Anda juga belajar tentang kerentanan umum pada front-end dan back-end serta bagaimana serangan dapat terjadi. Terakhir, Anda diperkenalkan pada Web Proxy seperti Burp Suite, alat yang sangat vital untuk menganalisis, memodifikasi, dan menguji aplikasi web dalam rangka Bug Hunting dan Ethical Hacking. Dengan memahami konsep-konsep ini dan alat-alat yang tersedia, Anda akan memiliki fondasi yang kuat untuk memulai perjalanan Anda dalam menjaga keamanan aplikasi web.