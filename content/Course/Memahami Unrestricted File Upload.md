---
id: Memahami Unrestricted File Upload
aliases: []
tags:
  - web_security
  - owasp
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[web_security]], [[owasp]] 

---

## Cue

- Apa itu kerentanan Unrestricted File Upload?
- Apa saja potensi bahaya dari kerentanan ini?
- Bagaimana cara menemukan bug ini selama pengujian penetrasi?
- Apa saja metode pencegahan yang efektif untuk Unrestricted File Upload?
- Bagaimana kerentanan ini dapat didemonstrasikan menggunakan DVWA?

---

## Notes

### Apa itu Unrestricted File Upload?
**Unrestricted File Upload** adalah kelemahan keamanan pada aplikasi web yang terjadi ketika aplikasi tidak menerapkan validasi atau pembatasan yang memadai pada file yang diunggah oleh pengguna. Ini memungkinkan penyerang untuk mengunggah file berbahaya ke server.

### Potensi Bahaya
1.  **Eksekusi Kode Berbahaya**: Penyerang dapat mengunggah skrip (misalnya `.php`, `.jsp`) yang kemudian dieksekusi di server, memberikan kontrol penuh.
2.  **Pencurian Data**: File yang diunggah dapat digunakan untuk mencuri atau membocorkan data sensitif dari server.
3.  **Pengambilalihan Sistem**: Dalam skenario terburuk, penyerang bisa mendapatkan akses penuh ke server.
4.  **Serangan Lainnya**: Termasuk *defacing* situs web, penanaman *backdoor*, atau penyebaran *malware*.

### Bagaimana Cara Menemukan Bug Ini?
Langkah-langkah pengujian penetrasi meliputi:
1.  **Identifikasi Fitur Unggahan**: Temukan semua *endpoint* yang memungkinkan pengguna mengunggah file.
2.  **Uji Format File**: Coba unggah file dengan ekstensi yang tidak diizinkan (misalnya `.php`, `.exe`) atau ekstensi ganda (`test.php.jpg`).
3.  **Uji Ukuran File**: Periksa batasan ukuran file.
4.  **Periksa Rename File**: Amati apakah server mengubah nama file yang diunggah.
5.  **Uji Mekanisme Ekstrak**: Jika aplikasi menerima file ZIP, coba unggah ZIP berisi file berbahaya.
6.  **Evaluasi Mekanisme Blokir**: Periksa apakah ada pemindaian file berbahaya atau validasi tipe MIME.

### Cara Kerja Bug
1.  Pengguna (penyerang) mengunggah file berbahaya ke server.
2.  Aplikasi web tidak memvalidasi ekstensi, tipe MIME, atau isi file.
3.  File berbahaya disimpan di server dan dapat diakses melalui URL publik.
4.  Jika file tersebut adalah skrip yang dapat dieksekusi, penyerang dapat memanggilnya melalui *browser* untuk menjalankan kode di server.

### Pencegahan
1.  **Validasi MIME Type**: Hanya izinkan tipe MIME yang spesifik dan aman (whitelist).
2.  **Validasi Ekstensi File**: Gunakan *whitelist* ekstensi yang diperbolehkan (misalnya `.jpg`, `.png`, `.pdf`).
3.  **Validasi Isi File (Content Validation)**: Analisis *header* dan isi file untuk memastikan kecocokan dengan format yang diharapkan.
4.  **Rename File**: Selalu ubah nama file yang diunggah secara otomatis menjadi nama yang unik dan tidak dapat ditebak.
5.  **Penyimpanan Aman**: Simpan file yang diunggah di luar direktori *web root* agar tidak dapat diakses langsung melalui URL.
6.  **Batasi Akses File**: Terapkan izin file yang ketat pada direktori unggahan.
7.  **Gunakan Library Keamanan**: Manfaatkan *library* atau *framework* yang sudah teruji keamanannya untuk menangani unggahan file.

### Studi Kasus: Serangan pada Lab DVWA
- **Skenario**: Menggunakan DVWA (Damn Vulnerable Web Application) untuk mendemonstrasikan kerentanan ini.
- **Langkah**: Unggah file PHP berisi perintah sistem (misalnya `<?php echo system("id"); ?>`) ke fitur unggahan file DVWA. Jika berhasil diunggah dan dapat diakses melalui URL, perintah tersebut akan dieksekusi di server.

---

## Summary

Unrestricted File Upload adalah kerentanan kritis yang memungkinkan penyerang mengunggah dan mengeksekusi file berbahaya di server, berpotensi menyebabkan eksekusi kode jarak jauh atau pengambilalihan sistem. Pencegahannya melibatkan validasi ketat terhadap tipe, ekstensi, dan isi file, serta praktik penyimpanan yang aman di luar *web root*. Pengujian kerentanan ini sangat penting dalam pentesting, dan dapat didemonstrasikan di lingkungan lab seperti DVWA.
