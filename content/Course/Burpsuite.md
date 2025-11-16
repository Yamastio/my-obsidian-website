---
id: Burpsuite
aliases: []
tags:
  - cybersecurity
  - web_security
comments: true
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[web_security]]

---

## Cue

- Apa itu Burp Suite
- Bagaimana cara kerja proxy intercepting
- Bagaimana alur Browser → Burp → Server
- Cara instalasi dan konfigurasi dasar
- Fungsi Proxy, Repeater, Intruder
- Kegunaan Target, Logger, Extension
- Kapan Burp dipakai dalam pentesting

---

## Notes

- Burp Suite adalah alat proxy intercepting yang memeriksa, menahan, dan memodifikasi percakapan antara browser dan server. Browser dipaksa melewati Burp sehingga setiap request dan response dapat dibaca atau diedit.
- Cara kerja intuitif: Browser mengirim request → Burp menangkap dan menampilkan → setelah diubah/ditinjau, Burp meneruskan ke server → server membalas → Burp mengembalikan ke browser. Ini membuat seluruh komunikasi web terlihat jelas.
- Instalasi dan konfigurasi inti: unduh Burp Community, atur browser (misalnya Firefox) memakai proxy 127.0.0.1:8080, aktifkan proxy listener di Burp pada port yang sama, dan pasang sertifikat CA Burp agar HTTPS berjalan tanpa error. Semua traffic browser akan mengalir melalui Burp.
- Fitur Proxy: tempat semua request lewat dan bisa diintersep atau dimodifikasi.
- Fitur Repeater: ruang eksperimen untuk mengambil satu request dan mengirim ulang berkali-kali sambil mengubah parameter; digunakan untuk eksploitasi manual seperti SQLi, auth bypass, dan parameter tampering.
- Fitur Intruder: mesin otomatis untuk brute-force, fuzzing, atau pengujian rate-limit dalam jumlah besar.
- Fitur Target: peta aplikasi yang menampilkan struktur endpoint dan request yang pernah dikirim.
- Fitur Logger: catatan lengkap seluruh traffic yang sudah lewat untuk analisis ulang.
- Extensions/BApp Store: menambah kemampuan seperti decoding, scanning, dan automasi lanjutan.
- Penggunaan dalam pentesting: mengubah request, menguji input user (SQLi, XSS, traversal), brute-force login atau OTP, menemukan endpoint tersembunyi, dan memeriksa mekanisme autentikasi serta sesi.

---

## Summary

Burp Suite adalah alat pengendali penuh komunikasi web dengan cara menangkap dan memodifikasi traffic antara browser dan server. Dengan proxy, repeater, intruder, dan fitur lain, Burp mempermudah analisis, eksploitasi, dan pengujian keamanan aplikasi web.
