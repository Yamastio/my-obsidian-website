---
id: OSI Model
aliases: []
tags:
  - networking
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[networking]]

---

## Cue

- Apa itu Model OSI dan mengapa penting dalam jaringan komputer?
- Apa saja 7 lapisan dalam Model OSI?
- Apa fungsi utama dari setiap lapisan dalam Model OSI?

---

## Notes

### Apa itu Model OSI?
Model OSI (Open Systems Interconnection) adalah sebuah model standar yang menjelaskan bagaimana komputer berkomunikasi dalam jaringan. Model ini membagi proses komunikasi menjadi tujuh lapisan yang berbeda, di mana setiap lapisan memiliki tugas dan tanggung jawab spesifik.

### Kenapa Model OSI Penting?
Model OSI membantu kita memahami bagaimana data bergerak dari satu perangkat ke perangkat lain dalam jaringan. Ini memberikan kerangka kerja konseptual untuk memahami kompleksitas komunikasi jaringan, mulai dari aplikasi yang digunakan pengguna hingga transmisi data fisik.

### 7 Lapisan dalam Model OSI (Dari Atas ke Bawah)

#### Layer 7 - Application (Aplikasi)
- **Fungsi**: Lapisan ini berinteraksi langsung dengan aplikasi pengguna. Contoh: browser web, aplikasi email, WhatsApp.
- **Tugas**: Menyediakan antarmuka bagi pengguna untuk mengirim dan menerima data.

#### Layer 6 - Presentation (Presentasi)
- **Fungsi**: Mengubah data ke format yang bisa dipahami oleh sistem penerima.
- **Tugas**: Enkripsi/dekripsi, kompresi/dekompresi data, dan konversi format data.

#### Layer 5 - Session (Sesi)
- **Fungsi**: Membangun, mengelola, dan mengakhiri sesi komunikasi antara dua aplikasi.
- **Tugas**: Memastikan data dari satu sesi tidak tercampur dengan sesi lain.

#### Layer 4 - Transport (Transportasi)
- **Fungsi**: Mengatur pengiriman data secara end-to-end.
- **Tugas**: Membagi data menjadi segmen, mengelola kontrol aliran (flow control), dan kontrol kesalahan (error control). Protokol utama: TCP (andal, akurat) dan UDP (cepat, tidak andal).

#### Layer 3 - Network (Jaringan)
- **Fungsi**: Menentukan rute terbaik untuk pengiriman paket data antar jaringan.
- **Tugas**: Menggunakan alamat IP (logical address) untuk mengidentifikasi perangkat dan menentukan jalur pengiriman.

#### Layer 2 - Data Link (Tautan Data)
- **Fungsi**: Mengatur pengiriman data antar perangkat yang terhubung langsung dalam satu jaringan lokal.
- **Tugas**: Menggunakan alamat MAC (physical address) untuk identifikasi perangkat, serta mendeteksi dan mengoreksi kesalahan pada lapisan fisik.

#### Layer 1 - Physical (Fisik)
- **Fungsi**: Lapisan paling dasar yang bertanggung jawab untuk transmisi bit data mentah melalui media fisik.
- **Tugas**: Mengubah data menjadi sinyal listrik, optik, atau gelombang radio dan mengirimkannya melalui kabel, serat optik, atau nirkabel.

---

## Summary

Model OSI adalah kerangka kerja standar yang membagi proses komunikasi jaringan menjadi tujuh lapisan diskrit, masing-masing dengan fungsi spesifik. Dari lapisan fisik yang menangani transmisi bit hingga lapisan aplikasi yang berinteraksi dengan pengguna, model ini membantu memahami bagaimana data bergerak dan diproses dalam jaringan. Pemahaman Model OSI sangat penting untuk mendiagnosis masalah jaringan dan merancang sistem komunikasi yang efisien.