---
id: Find Sub Domain
aliases: []
tags:
  - hacking_tools
  - recon
  - osint
  - pentesting
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[recon]], [[osint]], [[pentesting]]

---

## Cue

- Apa itu proses penemuan subdomain (subdomain enumeration)?
- Mengapa menemukan subdomain penting dalam sebuah penilaian keamanan?
- Apa saja teknik dan alat yang bisa digunakan untuk menemukan subdomain?
- Bagaimana cara menggunakan Google Dorking untuk tujuan ini?
- Apa saja alat command-line populer untuk mencari subdomain?

---

## Notes

### Apa itu Penemuan Subdomain?
- Proses ini adalah kegiatan mencari subdomain yang terkait dengan sebuah domain utama (contoh: `blog.example.com` adalah subdomain dari `example.com`).
- Tujuannya adalah untuk memperluas area target (attack surface) dalam sebuah pengujian keamanan, karena subdomain seringkali memiliki tingkat keamanan yang lebih rendah.

### Manfaat Mencari Subdomain
- **Menemukan Titik Lemah**: Subdomain seringkali tidak diamankan seketat domain utama.
- **Mendapat Informasi Tambahan**: Dapat mengungkap server, aplikasi, atau API tersembunyi.
- **Identifikasi Infrastruktur**: Memberikan petunjuk tentang teknologi, alamat IP, dan penyedia hosting yang digunakan.

### Tools dan Teknik
#### c99 Subdomain Finder
- Alat berbasis web yang secara otomatis menemukan subdomain beserta informasi tambahan seperti alamat IP dan penggunaan firewall.
- Cukup masukkan domain utama untuk memulai pencarian.

#### Google Dorking
- Teknik pencarian canggih menggunakan Google untuk menemukan subdomain yang terindeks.
- **Perintah Umum**:
    - `site:*.example.com` untuk mencari semua subdomain.
    - `site:*.example.com inurl:login` untuk menemukan halaman login di semua subdomain.

#### Alat Command-Line
- **Sublist3r**: Alat Python yang menggunakan berbagai mesin pencari dan teknik brute force.
  ```bash
  sublist3r -d example.com
  ```
- **Amass**: Alat open-source yang komprehensif untuk penemuan aset digital.
  ```bash
  amass enum -d example.com
  ```
- **crt.sh**: Layanan web yang mencari subdomain dengan menganalisis catatan transparansi sertifikat SSL/TLS.

### Pentingnya Etika dan Legalitas
- Pastikan selalu memiliki izin sebelum melakukan pemindaian subdomain terhadap sebuah sistem.
- Gunakan informasi yang ditemukan hanya untuk tujuan yang etis dan tidak melanggar hukum.

---

## Summary

Penemuan subdomain adalah bagian krusial dari fase reconnaissance dalam penetration testing untuk memperluas permukaan serangan. Proses ini bertujuan menemukan aset-aset tersembunyi yang mungkin memiliki kerentanan keamanan. Berbagai metode dapat digunakan, mulai dari alat online sederhana seperti c99 Subdomain Finder, teknik Google Dorking, hingga alat command-line canggih seperti Sublist3r dan Amass. Penting untuk selalu melakukan aktivitas ini secara etis dan dengan izin yang sah.