---
id: Broken Authentication & Session Management
aliases: []
tags:
  - cybersecurity
  - web_security
comments: true
date: 2025-09-21
title: Broken Authentication & Session Management
---

---

Related: [[index|Home]], [[cybersecurity]], [[web_security]]

---

## Cue

- Apa itu masalah pada autentikasi dan sesi
- Bagaimana bypass 2FA terjadi
- Mengapa password reset bisa dieksploitasi
- Apa contoh authentication bypass via direct access
- Apa bahaya session token lemah
- Apa itu session fixation
- Mengapa session timeout penting

---

## Notes

- Sistem login dianalogikan sebagai pintu rumah; masalah muncul ketika akses diberikan sebelum semua verifikasi selesai.
- **Bypass 2FA**: beberapa aplikasi membuat “sesi setengah jadi” setelah password benar. Jika OTP tidak divalidasi dengan benar, penyerang bisa langsung akses `/dashboard`, memanipulasi cookie pre-OTP, atau brute-force OTP tanpa rate-limit. Inti: OTP ada tetapi tidak benar-benar diperiksa.
- **Password reset lemah**: token reset yang pendek, mudah ditebak, tidak kedaluwarsa, atau bisa dicoba berulang kali dapat dibrute-force. Solusi: token panjang, acak, dan single-use.
- **Authentication bypass via direct access**: kesalahan umum seperti redirect tanpa `exit()` membuat halaman sensitif tetap dirender meski tidak login. Penyerang bisa melihat konten melalui curl/Burp meski browser dialihkan ke login.
- **Session token lemah**: token yang punya pola, mudah ditebak, atau hanya hasil encoding dapat dipalsukan. Penyerang brute-force bagian token yang berubah. Solusi: token acak, panjang, dan rutin dirotasi.
- **Session fixation**: jika session ID tidak diganti setelah login, penyerang dapat memberi korban token yang disiapkan sebelumnya; setelah korban login, token sama sehingga penyerang ikut masuk.
- **Session timeout buruk**: sesi yang tidak kedaluwarsa membuat akses tetap terbuka jika token bocor. Timeout 15–30 menit plus rotasi token membantu membatasi risiko.
- Inti: kelemahan autentikasi muncul karena terlalu cepat mempercayai input, verifikasi tidak lengkap, percobaan tanpa batas, token dapat ditebak, dan sesi tidak ditutup dengan benar.

---

## Summary

Masalah autentikasi dan sesi muncul ketika aplikasi tidak memvalidasi setiap tahap, menggunakan token yang lemah, membiarkan brute-force, tidak mengganti session ID setelah login, atau tidak memiliki timeout. Sistem aman harus memverifikasi semua langkah, membatasi percobaan, menggunakan token acak, merotasi sesi, dan otomatis mengakhiri sesi setelah waktu tertentu.
