---
id: Fase Penetration Testing
aliases: []
tags:
  - pentesting
  - cybersecurity
comments: true
date: 2025-09-21
draft: false
---

---

Related: [[index|Home]], [[pentesting]], [[cybersecurity]]

---

## Cue

- Apa itu penetration testing dan apa tujuannya?
- Apa saja lima fase utama dalam sebuah penetration testing?
- Apa tujuan, teknik, dan alat yang digunakan pada setiap fasenya?
- Bagaimana hasil dari penetration testing dapat digunakan untuk memperkuat keamanan sistem?

---

## Notes

Penetration testing (uji penetrasi) adalah sebuah proses simulasi serangan siber yang dilakukan secara etis dan dengan izin untuk mengidentifikasi serta memperbaiki kerentanan pada sistem sebelum dieksploitasi oleh penyerang.

### 1. Reconnaissance (Pengumpulan Informasi)
- **Tujuan**: Mengumpulkan informasi sebanyak mungkin tentang target.
- **Metode**:
    - *Passive*: Observasi tanpa interaksi langsung (misal: analisis media sosial, Whois).
    - *Active*: Interaksi langsung dengan sistem target (misal: ping, port scanning).
- **Tools**: Whois, Shodan, Google Hacking.

### 2. Scanning (Pemindaian)
- **Tujuan**: Mengidentifikasi layanan yang berjalan, port yang terbuka, dan potensi kerentanan.
- **Jenis**:
    - *Port Scanning*: Mendeteksi port dan layanan yang aktif.
    - *Vulnerability Scanning*: Mencari kerentanan yang sudah diketahui.
- **Tools**: Nmap, Nessus, OpenVAS.

### 3. Gaining Access (Mendapatkan Akses)
- **Tujuan**: Mengeksploitasi kerentanan yang ditemukan untuk masuk ke dalam sistem.
- **Teknik**: SQL Injection, Cross-Site Scripting (XSS), Buffer Overflow.
- **Tools**: Metasploit Framework.

### 4. Maintaining Access (Menjaga Akses)
- **Tujuan**: Mempertahankan akses yang sudah didapat untuk tujuan jangka panjang.
- **Teknik**: Menginstal *backdoors*, *rootkits*, atau mekanisme persistensi lainnya.

### 5. Covering Tracks (Menyembunyikan Jejak)
- **Tujuan**: Menghapus atau menyamarkan jejak aktivitas serangan agar tidak terdeteksi.
- **Teknik**: Menghapus log, mengubah *timestamp* file, atau menyembunyikan file berbahaya.

---

## Summary

Penetration testing adalah proses etis yang terdiri dari lima fase kunci: Reconnaissance, Scanning, Gaining Access, Maintaining Access, dan Covering Tracks. Setiap fase memiliki tujuan, teknik, dan alat spesifik, mulai dari pengumpulan informasi hingga penghapusan jejak. Proses ini secara sistematis mengidentifikasi dan mengeksploitasi kerentanan, di mana hasilnya memberikan wawasan berharga bagi tim keamanan untuk memperkuat pertahanan sistem dan mengurangi risiko serangan siber.