---
id: OWASP TOP 10
aliases: []
tags:
  - owasp
  - web_security
  - cybersecurity
comments: true
date: 2025-09-21
draft: false
---

---

Related: [[index|Home]], [[owasp]], [[web_security]], [[cybersecurity]]

---

## Cue

- Apa itu OWASP dan fungsinya dalam keamanan web?
- Apa saja daftar OWASP Top 10 dan mitigasinya?
- Apa perbedaan dan update antara OWASP Top 10 tahun 2017 dan 2021?

---

## Notes

### OWASP (Open Web Application Security Project)
- Organisasi nirlaba global yang berfokus pada peningkatan keamanan perangkat lunak, khususnya aplikasi web.
- Didirikan oleh Mark Curphey.
- Menyediakan panduan, alat, dan praktik terbaik gratis untuk pengembang dan profesional keamanan.
- Alat populer termasuk OWASP ZAP, cheat sheets, dan dokumentasi.

### OWASP Top 10 (2017)
Daftar sepuluh risiko keamanan aplikasi web paling kritis, beserta definisi, contoh, dan mitigasinya:

| No | Kerentanan | Definisi & Contoh | Mitigasi |
|---|---|---|---|
| 1 | Injection (A01:2017) | Menyisipkan payload berbahaya ke input aplikasi (misal: SQL Injection). | Prepared statements, validasi & sanitasi input. |
| 2 | Broken Authentication (A02:2017) | Kelemahan autentikasi memungkinkan pengambilalihan akun (misal: kredensial default). | MFA, password hashing (bcrypt). |
| 3 | Sensitive Data Exposure (A03:2017) | Data sensitif bocor akibat kurangnya enkripsi (misal: HTTP bukan HTTPS). | Gunakan HTTPS, enkripsi data sensitif. |
| 4 | XXE (A04:2017) | Parser XML memproses entitas eksternal berbahaya (misal: membaca `/etc/passwd`). | Nonaktifkan entitas eksternal, gunakan parser XML aman. |
| 5 | Broken Access Control (A05:2017) | Kontrol akses tidak efektif (misal: pengguna biasa mengakses fungsi admin). | RBAC, validasi akses di server. |
| 6 | Security Misconfiguration (A06:2017) | Konfigurasi yang salah (misal: mode debug aktif, direktori publik). | Konfigurasi minimal, audit dengan OWASP ASVS. |
| 7 | XSS (A07:2017) | Menyisipkan kode berbahaya ke aplikasi (misal: JavaScript mencuri cookie). | Encoding input/output, Content Security Policy (CSP). |
| 8 | Insecure Deserialization (A08:2017) | Deserialisasi dari sumber tidak tepercaya (misal: eksekusi kode dari objek berbahaya). | Hindari deserialisasi tidak terpercaya, gunakan JSON. |
| 9 | Using Components w/ Known Vulnerabilities (A09:2017) | Komponen pihak ketiga yang rentan (misal: library usang). | Update dependensi rutin, gunakan tools seperti Dependabot atau Snyk. |
| 10 | Insufficient Logging & Monitoring (A10:2017) | Kurangnya logging dan monitoring (misal: gagal login tidak tercatat). | Logging komprehensif, gunakan SIEM. |

### Perbandingan OWASP 2017 vs 2021
- **Insecure Design** diperkenalkan sebagai kategori baru di OWASP Top 10 2021.
- **Broken Access Control** naik menjadi risiko nomor 1 di OWASP Top 10 2021, menunjukkan peningkatan keparahan dan frekuensi eksploitasi.

### Rekomendasi Belajar
- Praktik langsung dengan alat seperti **OWASP ZAP** dan **Burp Suite**.
- Simulasi di platform seperti **Hack The Box**, **TryHackMe**, dan **DVWA**.
- Ikuti pembaruan OWASP melalui situs resmi dan newsletter.

---

## Summary

OWASP adalah organisasi nirlaba yang menyediakan panduan penting untuk keamanan aplikasi web, terutama melalui daftar OWASP Top 10. Daftar ini mengidentifikasi sepuluh risiko keamanan paling kritis, seperti Injection, Broken Authentication, dan XSS, beserta mitigasinya. Pembaruan OWASP Top 10, seperti versi 2021, terus menekankan pentingnya desain yang aman dan kontrol akses yang kuat. Memahami dan mempraktikkan mitigasi ini sangat penting untuk melindungi aplikasi web dari serangan.