---
id: 13-SSTI dan File Upload
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

- Apa itu SSTI dan bagaimana cara mengidentifikasi serta mengeksploitasinya?
- Bagaimana cara mencegah kerentanan SSTI?
- Apa itu kerentanan unggah berkas dan jenis serangannya?
- Bagaimana cara melewati pembatasan unggah berkas?
- Bagaimana cara mencegah kerentanan unggah berkas?

---

## Notes

### Mengenal Template Engine dan Server-Side Template Injection (SSTI)

### Apa itu Template Engine?
- Perangkat lunak untuk menggabungkan kerangka desain (template) dengan data dinamis.
- Contoh: Jinja (Python), Twig (PHP).

### Apa itu Server-Side Template Injection (SSTI)?
- Penyerang dapat mengendalikan bagian dari template itu sendiri, bukan hanya data.
- Terjadi jika input pengguna disisipkan langsung ke dalam string template sebelum diproses.

### Cara Mengidentifikasi SSTI
- Coba masukkan karakter khusus template engine (contoh: `{{<%.%'"}}%.`).
- Coba `{{7*7}}` atau `${7*7}` untuk melihat hasil `49` atau tetap string.

### Cara Mengeksploitasi SSTI (Contoh Jinja2 & Twig)
- Mendapatkan Informasi (Information Disclosure): Mengungkap detail konfigurasi.
- Membaca Berkas Lokal (Local File Inclusion - LFI): Membaca berkas di server (contoh: `passwd`).
- Mengeksekusi Kode dari Jarak Jauh (Remote Code Execution - RCE): Menjalankan perintah sistem di server.
    - Jinja2: Menggunakan library `os` Python.
    - Twig: Menggunakan fungsi PHP seperti `system`.
    - Alat otomatis: SSTImap.

### Pencegahan SSTI
- Pastikan input pengguna tidak pernah menjadi bagian dari kode template yang dieksekusi.
- Berikan input pengguna sebagai nilai data ke fungsi rendering template.
- Hardening template engine (hapus fungsi berbahaya) atau pisahkan lingkungan eksekusi.

### Mengenal Kerentanan Unggah Berkas (File Upload Vulnerabilities)

### Apa itu Kerentanan Unggah Berkas?
- Aplikasi web membiarkan pengguna mengunggah berkas tanpa validasi memadai.
- Penyerang bisa mengunggah berkas berbahaya.

### Jenis Serangan Umum: Unggah Berkas Arbitrer (Arbitrary File Upload)
- Penyerang dapat mengunggah berkas apa pun, termasuk Web Shell atau Reverse Shell.

### Web Shells dan Reverse Shells
- Web Shell: Skrip (contoh: PHP) diunggah ke server, memungkinkan penyerang menjalankan perintah sistem dari jarak jauh melalui browser.
- Reverse Shell: Server terinfeksi "menelepon balik" ke mesin penyerang, menghindari firewall. Alat: msfvenom.

### Langkah-langkah Eksploitasi
1. Identifikasi Bahasa Aplikasi Web (contoh: PHP, ASPX).
2. Uji Unggah: Coba unggah skrip "Hello World" sederhana.
3. Unggah Skrip Berbahaya: Unggah web shell atau reverse shell.

### Cara Melewati Pembatasan Unggah Berkas (Bypass Filter)

### Melewati Validasi Front-end (JavaScript)
- Matikan JavaScript, manipulasi kode di Developer Tools, atau kirim permintaan langsung.

### Melewati Validasi Ekstensi (Back-end)
- Blacklisting: Coba ekstensi lain yang diizinkan (contoh: `.phtml`, `.php5`).
- Whitelisting: Coba "Double Extensions" (contoh: `shell.jpg.php`) atau "Reverse Double Extension".

### Melewati Validasi Tipe Konten (MIME-Type)
- Manipulasi `Content-Type` header.
- Manipulasi "Magic Bytes" atau "File Signature" (tambahkan magic bytes gambar di awal skrip berbahaya).

### Pencegahan Kerentanan Unggah Berkas
- Validasi Ekstensi yang Ketat (Whitelisting).
- Validasi Konten yang Ketat (MIME-Type & Magic Bytes), pindai isi untuk kode berbahaya.
- Sembunyikan Direktori Unggahan.
- Batasi Ukuran Berkas.
- Perbarui Library.
- Gunakan Web Application Firewall (WAF).

## Summary

Memahami Server-Side Template Injection dan kerentanan unggah berkas sangat penting dalam dunia keamanan siber. Keduanya memungkinkan penyerang untuk mengeksekusi kode berbahaya di server, yang dapat menyebabkan kehilangan data, kerusakan sistem, atau bahkan kendali penuh atas server. Bagi pemula, penting untuk memahami bahwa kerentanan ini seringkali muncul karena validasi input yang tidak memadai atau konfigurasi yang tidak aman. Dengan memahami cara kerja kerentanan ini dan berbagai metode untuk melewatinya, kita dapat membangun aplikasi yang lebih aman dan melindungi sistem dari serangan.