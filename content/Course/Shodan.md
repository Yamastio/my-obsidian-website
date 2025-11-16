---
id: Shodan
aliases: []
tags:
  - hacking_tools
  - osint
  - recon
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[osint]], [[recon]]

---

## Cue

- Apa itu Shodan dan apa bedanya dengan Google?
- Apa saja fungsi utama dari Shodan?
- Apa yang membuat Shodan unik dibandingkan mesin pencari lainnya?
- Apa saja contoh query pencarian yang bisa digunakan di Shodan?

---

## Notes

### Apa itu Shodan?
Shodan adalah sebuah mesin pencari yang secara khusus dirancang untuk mengindeks perangkat yang terhubung ke internet. Berbeda dengan Google yang mencari konten web, Shodan mencari perangkat seperti server, router, CCTV, printer, dan perangkat Internet of Things (IoT) dengan menganalisis *service banner* mereka.

### Fungsi Utama Shodan
- **Pemetaan Jaringan**: Mengidentifikasi perangkat yang dapat diakses publik di seluruh dunia.
- **Penilaian Risiko**: Membantu profesional keamanan menemukan perangkat dengan konfigurasi yang rentan, seperti kredensial default atau protokol yang tidak aman.
- **Pencarian Canggih**: Memungkinkan pencarian yang sangat spesifik menggunakan filter seperti lokasi geografis, nomor port, atau sistem operasi.

### Keunikan Shodan
- **Informasi Spesifik**: Memberikan detail teknis tentang perangkat, termasuk versi perangkat lunak, layanan yang berjalan, dan uptime.
- **Peringatan Ancaman (Alerts)**: Pengguna dapat mengatur notifikasi untuk memantau perubahan pada perangkat yang diawasi.
- **Tren Global**: Memungkinkan peneliti untuk menganalisis tren tentang perangkat dan teknologi yang paling sering terekspos di internet.

### Praktik Penggunaan Shodan
- **Akses**: Kunjungi situs [https://www.shodan.io](https://www.shodan.io) dan buat akun untuk fitur yang lebih lengkap.
- **Contoh Query**:
    - `http.title:"hacked by"`: Mencari situs yang telah diretas.
    - `country:ID port:22`: Menemukan perangkat dengan port SSH terbuka di Indonesia.
    - `os:Windows`: Menemukan perangkat yang menjalankan sistem operasi Windows.
    - `webcam`: Mencari perangkat kamera yang terekspos ke publik.

### Manfaat dan Etika
- **Manfaat**: Berguna untuk menilai keamanan jaringan, memantau perangkat IoT, dan melakukan riset keamanan siber.
- **Etika**: Shodan adalah alat yang sangat kuat dan harus digunakan secara legal dan bertanggung jawab. Mengakses atau mencoba mengeksploitasi perangkat tanpa izin adalah tindakan ilegal.

---

## Summary

Shodan adalah mesin pencari untuk perangkat yang terhubung ke internet, bukan untuk halaman web. Alat ini mengindeks server, router, CCTV, dan perangkat IoT dengan menganalisis *service banner* untuk mengumpulkan informasi seperti port terbuka, versi perangkat lunak, dan lokasi geografis. Profesional keamanan menggunakan Shodan untuk OSINT dan menemukan perangkat yang rentan, menjadikannya alat yang sangat kuat untuk pemetaan risiko keamanan, namun penggunaannya harus selalu etis dan legal.
