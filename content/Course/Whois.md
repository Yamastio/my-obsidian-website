---
id: Whois
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

- Apa itu protokol WHOIS?
- Bagaimana cara menggunakan WHOIS di Kali Linux?
- Apa saja contoh penggunaan WHOIS dalam ethical hacking?

---

## Notes

### Apa itu WHOIS?
WHOIS adalah sebuah protokol kueri yang digunakan untuk mendapatkan informasi publik mengenai registrasi sebuah domain internet. Informasi ini bisa mencakup nama pemilik, organisasi, alamat email, lokasi geografis, dan tanggal penting seperti pendaftaran dan kedaluwarsa domain.

### Penggunaan di Kali Linux
- Perintah WHOIS sudah terintegrasi di sebagian besar sistem operasi berbasis Linux, termasuk Kali Linux.
- Penggunaannya sangat sederhana, cukup jalankan perintah berikut di terminal:
  ```bash
  whois example.com
  ```

### Contoh dalam Ethical Hacking
WHOIS adalah alat fundamental dalam fase pengumpulan informasi (reconnaissance).
- **Footprinting**: Memberikan data awal untuk memetakan target.
- **Social Engineering**: Informasi kontak pemilik domain dapat dimanfaatkan sebagai bahan untuk serangan rekayasa sosial.
- **Identifikasi Target**: Membantu memahami siapa di balik sebuah domain, yang bisa mengarah pada penemuan aset-aset terkait lainnya.

---

## Summary

WHOIS adalah protokol untuk meminta informasi registrasi publik sebuah domain, seperti detail pemilik dan tanggal pendaftaran. Di Kali Linux, perintah `whois` dapat dijalankan langsung dari terminal untuk mengumpulkan data intelijen. Alat ini sangat penting dalam fase awal ethical hacking untuk kegiatan reconnaissance, footprinting, dan sebagai dasar untuk serangan social engineering.
