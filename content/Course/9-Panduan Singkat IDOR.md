---
id: 9-Panduan Singkat IDOR
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

- Apa itu Object References dan Insecure Direct Object References (IDOR)?
- Mengapa IDOR bisa terjadi?
- Bagaimana cara mengidentifikasi IDOR?
- Apa saja contoh kasus penggunaan IDOR?
- Bagaimana cara melewati referensi yang dienkode?
- Bagaimana cara mencegah IDOR?

---

## Notes

### Apa itu Object References?
- Cara aplikasi mengidentifikasi dan mengakses objek tertentu (milik pengguna/sistem).
- Contoh: ID pengguna (`uid=1`), nomor invoice, file di server (`filename=file_1.pdf`), nomor tiket.
- Sering muncul di parameter URL, body request, atau header HTTP.

### Apa itu Insecure Direct Object References (IDOR)?
- Kerentanan ketika aplikasi web secara langsung mengekspos referensi ke suatu objek.
- Pengguna dapat mengontrol referensi untuk mengakses objek serupa lainnya.
- Terjadi jika sistem kontrol akses lemah.
- Paling sering berkaitan dengan peningkatan hak akses horizontal (data pengguna lain), bisa juga vertikal (data administrator).

### Mengapa IDOR Bisa Terjadi?
- Penyebab utama: Sistem kontrol akses yang lemah.
- Sulit mengotomatiskan identifikasi kelemahan kontrol akses.

### Bagaimana Cara Mengidentifikasi IDOR?
- Mempelajari Parameter URL dan API: Periksa permintaan HTTP untuk parameter URL/API yang memiliki object reference (misalnya `?uid=1`).
    - Bisa juga di header HTTP (cookies) atau data body POST.
- Membandingkan Peran Pengguna: Daftar sebagai beberapa pengguna, bandingkan permintaan HTTP dan object reference.
    - Memahami bagaimana parameter URL dan unique identifier dihitung.
    - Contoh: Mengubah ID untuk melihat gaji pengguna lain.

### Contoh Kasus Penggunaan IDOR (Use Cases)

### Referensi Langsung ke Objek Database
- Contoh: `contoh.com/customer_account?customer_number=123`.
- Mengubah `customer_number` menjadi `124` untuk melihat catatan pelanggan lain (peningkatan hak akses horizontal).

### Referensi Langsung ke File Statis
- Sumber daya sensitif disimpan dalam file statis.
- Contoh: `contoh.com/transcripts/123.txt`.
- Mengubah `filename` menjadi `124.txt` untuk mengambil transkrip pengguna lain.

### Mengunduh File
- Dokumen diakses melalui URL dengan `uid`.
- Mengubah `uid` (misalnya dari `?uid=1` menjadi `?uid=2`) untuk melihat dokumen pengguna lain.
- Bisa diotomatisasi untuk mengunduh banyak file.

### API Broken Access Control
- Di halaman Edit Profil, data profil diperbarui melalui permintaan PUT ke endpoint API (misalnya `/profile/api.php/profile/1`).
- Mengubah ID pengguna di endpoint (misalnya menjadi `/profile/api.php/profile/2`) dan mengirim GET untuk melihat detail pengguna lain (Information Disclosure IDOR).

### Peningkatan Hak Akses (Privilege Escalation)
- Mendapatkan `uuid` pengguna lain, mengubah detail pengguna tersebut.
- Mencoba mengubah peran (`role`) pengguna lain menjadi peran hak akses lebih tinggi (misalnya `web_admin`).
- Menambahkan pengguna baru atau mengedit cookie sendiri untuk mendapatkan peran administrator.

### Melewati Referensi yang Dienkode (Bypassing Encoded References)
- Situs web menggunakan pengkodean (Hash, Base64, JWT) untuk menyembunyikan data.
- Bisa dilewati dengan: Mendekripsi Hash, Mendekode Base64/Hex, Mendekripsi Rahasia JWT.
- Membaca kode sumber untuk memahami pengkodean.

### Pencegahan IDOR
- Kontrol Akses Tingkat Objek (Object-Level Access Control):
    - Desain aplikasi web harus mendukung segmentasi peran (roles) dan izin (permissions) secara terpusat.
    - Server back-end harus mengizinkan/menolak permintaan berdasarkan hak istimewa pengguna.
- Referensi Objek yang Kuat (Strong Object Referencing):
    - Jangan gunakan object references dalam teks biasa atau pola sederhana (misalnya `uid=1`).
    - Gunakan referensi yang kuat dan unik, seperti salted hashes atau UUIDs (Universally Unique Identifiers).
    - UUID V4 menghasilkan ID teracak kuat (contoh: `89c9b29b-d19f-4515-b2dd-abb6e693eb20`).
    - UUID dipetakan ke objek yang direferensikan dalam database back-end.

## Summary

Insecure Direct Object References (IDOR) adalah kerentanan umum yang muncul akibat sistem kontrol akses yang lemah, memungkinkan penyerang untuk mengakses atau memanipulasi data yang seharusnya tidak mereka miliki. Dengan memahami bagaimana object references bekerja, cara mengidentifikasinya, serta berbagai contoh eksploitasinya, kita bisa lebih baik dalam mencari dan mencegah kerentanan ini. Pencegahan terbaik melibatkan penerapan kontrol akses yang ketat di setiap level dan penggunaan referensi objek yang unik dan sulit ditebak seperti UUIDs. Memahami IDOR adalah langkah krusial dalam perjalanan Anda menjadi seorang Ethical Hacker yang bertanggung jawab.