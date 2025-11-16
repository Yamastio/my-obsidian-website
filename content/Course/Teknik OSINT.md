---
id: Teknik OSINT
aliases: []
tags:
  - osint
  - recon
comments: true
date: 2025-09-21
draft: false
---

---

Related: [[index|Home]], [[osint]], [[recon]]

---

## Cue

- Apa itu Open Source Intelligence (OSINT) dan tujuannya?
- Teknik OSINT apa saja yang umum digunakan dalam pengintaian pasif?
- Alat apa saja yang digunakan untuk tiap teknik OSINT?
- Apa manfaat dan risiko penggunaan OSINT dalam penetration testing?
- Bagaimana OSINT membantu merencanakan strategi pengujian keamanan?

---

## Notes

### Definisi OSINT
OSINT adalah proses pengumpulan dan analisis informasi dari sumber-sumber yang tersedia untuk publik (open source) guna memahami target tanpa melakukan interaksi langsung. Ini adalah fase pengintaian pasif yang krusial.

### Teknik OSINT Umum
1.  **Search Engine Dorking**: Menggunakan query pencarian khusus di Google/Bing untuk menemukan file, halaman login, atau informasi sensitif lainnya.
2.  **Social Media Scraping**: Mengumpulkan informasi tentang karyawan, struktur organisasi, dan teknologi yang digunakan dari platform seperti LinkedIn.
3.  **DNS & WHOIS Enumeration**: Mengidentifikasi detail registrasi domain, alamat IP, dan server yang digunakan.
4.  **Email Harvesting**: Mengumpulkan alamat email yang terekspos di situs web, forum, atau sumber publik lainnya.
5.  **Metadata Extraction**: Mengekstrak informasi tersembunyi (seperti versi software, lokasi, nama pengguna) dari metadata file dokumen atau gambar.
6.  **Analisis Repositori Kode**: Mencari kode sumber, dokumentasi, atau kunci API yang bocor di GitHub, GitLab, atau Bitbucket.
7.  **Pencarian Database Bocor**: Memeriksa apakah kredensial atau data target ada dalam kebocoran data yang telah terjadi sebelumnya.

### Alat Pendukung OSINT
- **Google Dorks, Maltego, SpiderFoot**: Untuk pemetaan dan analisis hubungan.
- **WHOIS, DNSDumpster**: Untuk informasi domain dan DNS.
- **theHarvester, Hunter.io**: Untuk pengumpulan email.
- **ExifTool, FOCA**: Untuk ekstraksi metadata.
- **Shodan, Censys**: Mesin pencari untuk perangkat yang terhubung ke internet.

### Manfaat dan Risiko
- **Manfaat**: Pengumpulan informasi secara legal dan etis (jika dari data publik), merancang strategi serangan yang lebih efektif, dan dilakukan tanpa terdeteksi.
- **Risiko**: Dapat disalahgunakan jika jatuh ke tangan yang salah; data publik yang berlebihan dapat meningkatkan eksposur risiko bagi organisasi.

---

## Summary

OSINT adalah metode pengumpulan intelijen dari sumber publik untuk memahami target tanpa interaksi langsung, menjadikannya komponen kunci dalam fase reconnaissance. Tekniknya bervariasi mulai dari Google Dorking, analisis media sosial, hingga ekstraksi metadata, yang didukung oleh berbagai alat seperti Maltego, theHarvester, dan Shodan. Meskipun legal dan efektif untuk merancang strategi pengujian keamanan, OSINT harus digunakan secara etis untuk menghindari penyalahgunaan informasi.