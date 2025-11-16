---
id: 1-Mengenal Bug Hunting dan Ethical Hacking
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

- Apa itu Hacking dan siapa itu Hacker?
- Perbedaan Bug Hunter dan Pentester?
- Framework Hacking apa yang digunakan?
- Langkah-langkah umum Bug Hunting dan Tools penting?

---

## Notes

### Pengenalan Ethical Hacking
- Ethical hacking adalah proses menjadi hacker yang terampil dan bertanggung jawab.

### Apa itu Hacking dan Siapa itu Hacker?
- Hacking: Proses atau teknik peretasan sistem komputer, jaringan, atau software.
    - Bisa legal (ethical hacking) atau ilegal (black hat hacking).
- Hacker: Orang yang melakukan hacking, ahli dalam sistem komputer, pemrograman, dan keamanan siber.
- Hacked: Kondisi sistem, akun, atau jaringan berhasil diretas/dieksploitasi.
    - Sistem bisa dikuasai, data dicuri, atau fungsi diubah tanpa izin.

### Jenis Hacker
- Bad Hacker (Black Hat):
    - Tujuan: Merusak sistem atau mencuri data.
    - Ilegal, motif: uang, politik, sabotase.
- Good Hacker (White Hat / Ethical Hacker):
    - Tujuan: Melindungi dan mengamankan sistem.
    - Legal, mengikuti etika dan hukum.
    - Motif: keamanan, edukasi, hadiah bug bounty.
    - Contoh: bug bounty hunter, penetration tester.

### Peran Ethical Hacker
- Melakukan pengujian keamanan pada sistem dan aplikasi.
- Mencari dan menutup celah keamanan sebelum dieksploitasi.
- Membantu organisasi meningkatkan keamanan siber.
- Menyusun laporan keamanan setelah pengujian.

### Manfaat Menjadi Ethical Hacker
- Profesi yang sangat dihargai dengan gaji tinggi.
- Permintaan kerja yang tinggi.
- Kesempatan ikut bug bounty dan mendapatkan hadiah.
- Bisa bekerja secara fleksibel (pegawai/freelancer).

### Bug Hunter vs. Pentester
- Bug Hunter:
    - Fokus mencari celah keamanan spesifik (bug bounty).
    - Bekerja independen/freelancer.
    - Tidak selalu eksploitasi penuh (hanya validasi bug).
    - Dibayar berdasarkan laporan bug.
- Penetration Tester (Pentester):
    - Pengujian keamanan menyeluruh pada sistem/jaringan.
    - Bekerja untuk perusahaan/konsultan.
    - Menganalisis, mengeksploitasi, laporan lengkap dengan rekomendasi.
    - Cakupan lebih luas.
- Red Teamer:
    - Pendekatan keamanan lebih agresif dari pentesting.
    - Mengeksploitasi sistem tanpa memberitahu tim keamanan (Blue Team).
    - Melibatkan social engineering, phishing, pengujian fisik.

### Framework Hacking
- Panduan sistematis untuk menemukan dan mengeksploitasi celah keamanan.
- Pilihan framework tergantung kebutuhan:
    - Cyber Kill Chain: Memahami tahapan serangan siber.
    - MITRE ATT&CK: Memahami teknik hacker.
    - OWASP Testing Guide / OWASP Top 10: Menemukan celah keamanan di aplikasi web.
    - PTES (Penetration Testing Execution Standard): Pentesting standar industri.
- Fokus kursus: Cyber Kill Chain, OWASP Top 10, RER (Reconnaissance, Exploit, Report).
- Manfaat: Profesional, hindari kesalahan kategori bug, analisis komprehensif.

### Langkah-langkah Umum Bug Hunting dan Tools Penting
- Proses bug hunting: Reconnaissance, Enumeration, Exploitation, Post-Exploitation, Reporting.

### Reconnaissance (Pengumpulan Informasi)
- Tahap awal, kumpulkan informasi sebanyak mungkin tentang target.
- Passive Reconnaissance: Tidak interaksi langsung (WHOIS lookup, Google Dorking). Deteksi rendah.
- Active Reconnaissance: Interaksi langsung (Nmap scanning). Deteksi tinggi.
- Hasil: Informasi domain & subdomain, IP & port terbuka, tech stack, user & credentials leak.

### Exploitation (Eksploitasi)
- Memanfaatkan celah keamanan yang ditemukan.
- Contoh: SQL Injection, Cross-Site Scripting (XSS), Command Injection, Remote Code Execution (RCE).

### Reporting (Pelaporan)
- Membuat laporan jelas dan terstruktur.
- Struktur: Ringkasan eksekutif, deskripsi celah, dampak keamanan, bukti eksploitasi, rekomendasi mitigasi.

### Tools Penting
- OWASP ZAP: Tools open-source untuk scanning keamanan aplikasi web.
- Burp Suite: Tools populer untuk pengujian keamanan aplikasi web (proxy, repeater, intruder, scanner).
- Nmap: Tools untuk scanning jaringan dan penemuan layanan.
- WHOIS: Mendapatkan informasi domain dan alamat IP.
- Penting: Latihan dengan lab (TryHackMe & HackTheBox), baca dokumentasi, jelajahi fitur.

## Summary

Menjadi seorang ethical hacker adalah pilihan karir yang menjanjikan dan sangat dibutuhkan di era digital saat ini. Anda akan belajar bagaimana sistem bekerja, menemukan kelemahan, dan melaporkannya untuk membuat dunia siber lebih aman. Dengan memahami perbedaan hacker baik dan jahat, mengikuti framework yang terstruktur seperti Cyber Kill Chain dan OWASP Top 10, serta menguasai tools penting seperti OWASP ZAP, Burp Suite, Nmap, dan WHOIS, Anda akan memiliki fondasi yang kuat untuk memulai perjalanan sebagai bug hunter atau pentester yang bertanggung jawab dan ahli. Latihan secara konsisten adalah kunci untuk menguasai keterampilan ini!