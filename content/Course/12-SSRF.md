---
id: 12-SSRF
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

- Apa itu SSRF dan bagaimana kerentanannya terjadi?
- Bagaimana cara mendeteksi SSRF?
- Apa saja yang bisa dilakukan dengan SSRF?
- Bagaimana cara mencegah SSRF?

---

## Notes

### Pengantar Server-Side Request Forgery (SSRF)
- SSRF adalah kerentanan penting dalam Ethical Hacking, masuk dalam OWASP Top 10.

### Apa itu SSRF?
- Kerentanan terjadi ketika penyerang bisa memaksa server web untuk membuat permintaan ke URL atau alamat lain yang ditentukan penyerang.
- Berbahaya tergantung konfigurasi aplikasi web.

### Bagaimana Cara Mengetahui Jika Ada SSRF?
- Petunjuk: Parameter dalam permintaan yang berisi URL (contoh: `dateserver`).
- Memastikan SSRF:
    - Mengarahkan aplikasi web untuk membuat permintaan ke sistem penyerang (gunakan `netcat`). Jika menerima koneksi, SSRF terkonfirmasi.
    - Mengarahkan aplikasi web untuk membuat permintaan ke dirinya sendiri (`http://127.0.0.1/index.php`). Jika respons menampilkan kode HTML aplikasi, SSRF tidak "blind".

### Apa Itu Blind SSRF?
- Tidak bisa langsung melihat respons dari permintaan yang dibuat server.
- Eksploitasi lebih terbatas.
- Masih bisa:
    - Melakukan pemindaian port terbatas (jika ada perbedaan respons).
    - Mengidentifikasi file yang ada (pesan kesalahan berbeda).

### Apa Saja yang Bisa Dilakukan dengan SSRF? (Kasus Penggunaan)
- Pemindaian Port Internal (Enumerating System): Mencari port terbuka di server target.
- Mengakses Endpoint Terlarang: Mengakses halaman admin atau bagian terlarang lain dengan "menyamar" sebagai server.
- Membaca File Lokal (Local File Inclusion/LFI): Membaca file sensitif (contoh: `/etc/passwd`) menggunakan skema `file://`.
- Pindah ke Sistem Lain (Lateral Movement) dengan Gopher: Membuat permintaan POST atau berinteraksi dengan layanan internal (MySQL, Redis) menggunakan protokol Gopher.
- Serangan di Infrastruktur Cloud Publik: Mengakses Cloud Metadata Endpoints (contoh AWS: `http://169.254.169.254/latest/meta-data/`) untuk mencuri kredensial.
- Chaining dengan XXE: Menggabungkan SSRF dengan kerentanan XXE untuk menyuntikkan payload SSRF.

### Bagaimana Cara Mencegah SSRF?
- Whitelisting: Hanya izinkan permintaan ke URL atau alamat yang sudah disetujui dan aman.
- Pembatasan Skema URL dan Protokol: Batasi skema URL (http://, https://, file://, gopher://) yang diizinkan.
- Sanitasi Input: Selalu bersihkan dan validasi semua input pengguna.
- Aturan Firewall yang Ketat: Konfigurasi firewall untuk mencegah permintaan keluar ke sistem internal.
- Segmentasi Jaringan: Pisahkan jaringan untuk membatasi akses aplikasi web ke sistem internal sensitif.

## Summary

SSRF adalah kerentanan serius yang memungkinkan penyerang memaksa server Anda untuk melakukan permintaan atas nama mereka, berpotensi mengakses sumber daya internal, file sensitif, atau bahkan mengambil alih kontrol di lingkungan cloud. Konsekuensinya bisa sangat merusak. Oleh karena itu, penting untuk selalu memvalidasi dan membatasi input pengguna, serta menerapkan kontrol jaringan yang ketat seperti whitelisting dan firewall, untuk melindungi aplikasi web Anda dari serangan SSRF. Memahami cara kerja dan pencegahannya adalah kunci untuk membangun aplikasi yang lebih aman.