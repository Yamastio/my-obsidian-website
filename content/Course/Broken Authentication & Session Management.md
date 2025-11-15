---
id: Broken Authentication & Session Management
aliases: []
tags:
  - cybersecurity
comments: true
date: 2025-09-21
title: Broken Authentication & Session Management
---
Related: [[index|Home]], [[cybersecurity]]

## Authentication & Session Security 

Bayangkan sistem login seperti **pintu masuk rumah**. Tujuanmu: memastikan hanya pemilik rumah yang bisa masuk, dan tamu tidak bisa diam-diam ikut masuk lewat celah pintu.

Masalahnya: banyak rumah digital dibangun dengan pintu yang “kelihatannya aman”, tapi sebenarnya longgar. Berikut penjelasannya secara sederhana.

---

## 1. Bypass 2FA

Banyak situs membuat tahap 2FA seperti ini:

1. Cek password → benar
2. Minta OTP → tapi sudah bikin “sesi setengah jadi”

Kesalahan fatal: **sesi setengah jadi ini kadang dianggap sesi penuh**.
Akibatnya, kamu bisa *langsung masuk ke dashboard* meski belum masukkan OTP.

Trik penyerang:

* Akses halaman sensitif langsung (`/dashboard`)
* Manipulasi cookie yang diberikan sebelum OTP
* Brute-force OTP karena tidak ada rate-limit

Inti masalah: **OTP ada, tapi tidak divalidasi dengan benar**.

---

## 2. Password Reset Lemah

Bayangkan reset password seperti mengirim “kunci cadangan”.
Jika kunci ini:

* terlalu pendek
* bisa ditebak
* tidak kedaluwarsa
* atau bisa dicoba berkali-kali

Maka rumahmu bisa dibuka orang lain hanya dengan menebak-nebak kombinasi.

Penyerang cukup brute-force token reset pendek sampai muncul respons berbeda.

Solusi sederhana: **buat kunci reset panjang, acak, dan hanya berlaku sekali**.

---

## 3. Authentication Bypass via Direct Access

Developer kadang membuat kode begini:

```plaintext
if (!login) redirect ke login.php
// tapi tetap lanjut render halaman sensitif
```

Browser memang pindah ke halaman login,
tapi penyerang bisa melihat *isi sebenarnya* dengan curl/Burp.

Kesalahan kecil (`header tanpa exit()`) → efek besar: bypass login.

---

## 4. Session Tokens Lemah

Token sesi adalah “kartu akses”.
Jika kartu itu:

* mudah ditebak
* punya pola
* hanya encoded, bukan acak

Maka penyerang bisa menghasilkan kartu palsu dan masuk sebagai korban.

Cara eksploitasi: brute-force sebagian token yang berubah.

Solusi: **token harus acak total, panjang, dan dirotasi secara berkala**.

---

## 5. Session Fixation

Jika aplikasi tidak mengganti session ID setelah login,
penyerang bisa menyiapkan token *sebelum* korban login.
Setelah korban masuk, tokennya tetap sama → penyerang ikut masuk.

Ini seperti memberi korban kunci palsu yang kamu gandakan duluan.

---

## 6. Session Timeout Buruk

Sesi yang tidak kedaluwarsa = pintu tidak pernah terkunci.
Jika token bocor, akun bisa dibuka kapan saja.

Timeout 15–30 menit + rotasi token = pintu otomatis terkunci ulang.

---

## Inti Semua Masalah

Kelemahan autentikasi biasanya terjadi karena aplikasi:

* mempercayai sesuatu terlalu cepat
* tidak mengecek sesuatu yang harusnya diperiksa
* membiarkan penyerang mencoba berkali-kali
* menggunakan token yang bisa ditebak
* lupa menutup pintu (timeout)

---

## Ringkasannya dalam satu kalimat

Sistem autentikasi yang aman adalah sistem yang **tidak memberi akses sampai semua langkah diverifikasi, token benar-benar acak, percobaan dibatasi, sesi diganti setelah login, dan pintu otomatis terkunci setelah beberapa waktu**.

