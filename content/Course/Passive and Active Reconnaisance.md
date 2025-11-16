---
id: Passive and Active Reconnaissance
aliases: []
tags:
  - recon
  - pentesting
comments: true
date: 2025-09-21
draft: false
---

---

Related: [[index|Home]], [[recon]], [[pentesting]]

---

## Cue

- Apa itu reconnaissance dalam penetration testing dan cybersecurity?
- Apa perbedaan antara passive dan active reconnaissance?
- Metode apa saja yang digunakan dalam passive reconnaissance?
- Teknik apa saja yang digunakan dalam active reconnaissance?
- Tools apa saja yang umum dipakai untuk active reconnaissance?
- Apa hal penting yang harus diperhatikan sebelum melakukan reconnaissance?

---

## Notes

### Reconnaissance
**Reconnaissance** adalah fase awal dalam penetration testing dan cybersecurity, di mana informasi dikumpulkan tentang target. Tujuannya adalah untuk memahami struktur, titik lemah, dan arsitektur sistem target sebelum melakukan eksploitasi.

### Passive Reconnaissance
- **Definisi**: Mengumpulkan informasi tanpa interaksi langsung dengan target. Ini berarti tidak ada jejak yang ditinggalkan di sistem target.
- **Tujuan**: Memahami infrastruktur, mengidentifikasi potensi celah, dan menyusun strategi pengujian awal.
- **Metode**:
    1.  **OSINT (Open Source Intelligence)**: Menggunakan sumber publik seperti website resmi, media sosial, forum, dan berita.
    2.  **DNS Lookup**: Menggunakan WHOIS, Reverse DNS, atau Zone Transfer untuk mendapatkan informasi domain dan IP.
    3.  **Pencarian Cache**: Menganalisis cache mesin pencari untuk menemukan informasi lama atau tersembunyi.
    4.  **Analisis Metadata**: Mengekstrak metadata dari file publik (dokumen, gambar) untuk informasi sensitif.
- **Kelebihan**: Tidak terdeteksi oleh target, umumnya legal.
- **Keterbatasan**: Hanya mendapatkan data publik, tidak mendalam.

### Active Reconnaissance
- **Definisi**: Melibatkan interaksi langsung dengan target, yang berpotensi meninggalkan jejak.
- **Tujuan**: Mendapatkan pemahaman yang lebih rinci, menemukan titik masuk eksploitasi, dan fokus pada area risiko tinggi.
- **Teknik**:
    1.  **Scanning Jaringan**: Melakukan *port scanning*, *vulnerability scanning*, dan *service fingerprinting*.
    2.  **Social Engineering**: Menggunakan teknik manipulasi psikologis seperti *phishing* atau *pretexting*.
    3.  **Interaksi Langsung**: Telepon, eksplorasi situs web secara mendalam, atau formulir kontak.
- **Tools**: Nmap, Nessus, OpenVAS, Metasploit, Burp Suite, Wireshark.

### Hal Penting dalam Reconnaissance
- **Izin Tertulis**: Selalu dapatkan izin tertulis dari pemilik sistem sebelum melakukan *active reconnaissance*.
- **Etika dan Hukum**: Patuhi kode etik dan hukum yang berlaku.
- **Hindari Kerusakan**: Jangan melakukan tindakan yang dapat merusak sistem target.

---

## Summary

Reconnaissance adalah fase krusial dalam penetration testing untuk mengumpulkan informasi tentang target. Ini terbagi menjadi passive reconnaissance, yang mengandalkan sumber publik tanpa interaksi langsung, dan active reconnaissance, yang melibatkan interaksi langsung untuk detail lebih mendalam. Kombinasi keduanya memberikan pemahaman komprehensif, namun harus selalu dilakukan secara etis, legal, dan dengan izin yang jelas untuk menghindari konsekuensi hukum dan kerusakan sistem.