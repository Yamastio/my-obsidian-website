---
id: 5-Mengenal Reconnaisance
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

- Apa itu Reconnaissance dan tujuan utamanya?
- Apa perbedaan Reconnaissance berbasis target dan berbasis teknik?
- Apa perbedaan Reconnaissance aktif dan pasif, serta contoh tekniknya?
- Apa itu subdomain dan virtual host, serta bagaimana cara menemukannya?
- Apa itu Fingerprinting dan alat penting lainnya dalam Reconnaissance?

---

## Notes

### Pendahuluan Reconnaissance
- Reconnaissance (pengintaian) atau Information Gathering adalah langkah pertama dan paling penting dalam ethical hacking.
- Proses pengumpulan informasi sistematis tentang target sebelum analisis/pencarian celah.

### 1. Tujuan Utama Reconnaissance
- Mengidentifikasi Aset: Mencari aset digital target (situs web, subdomain, aplikasi).
- Menemukan Informasi Tersembunyi: Menggali informasi tidak terlihat (halaman login tersembunyi, file konfigurasi lama).
- Menganalisis Permukaan Serangan (Attack Surface): Memahami ukuran, kerumitan, dan "pintu" yang bisa diakses penyerang.
- Mengumpulkan Intelijen: Data dan wawasan relevan untuk merencanakan "serangan" etis.

### 2. Dua Konsep Dasar Reconnaissance: Target-based dan Technique-based
- Target-based: Fokus mengumpulkan informasi tentang satu target, mencari banyak kelemahan (cocok untuk advanced).
- Technique-based: Fokus menguasai satu kelemahan, mencari di banyak target (cocok untuk pemula dan advanced).

### 3. Jenis-jenis Reconnaissance: Aktif vs. Pasif

### a. Reconnaissance Aktif
- Definisi: Melibatkan interaksi langsung dengan sistem target. Risiko terdeteksi lebih tinggi.
- Teknik & Contoh:
    - Port Scanning (Nmap): Mencari port terbuka.
    - Vulnerability Scanning (Nessus): Mencari kerentanan diketahui.
    - Network Mapping (Traceroute): Membuat peta jaringan.
    - Banner Grabbing (Netcat, curl): Mengambil informasi software/versi.
    - OS Fingerprinting (Nmap): Mengidentifikasi OS.
    - Service Enumeration (Nmap): Menentukan versi layanan.
    - Web Spidering (Burp Suite Spider, OWASP ZAP Spider): Merayapi situs web.

### b. Reconnaissance Pasif
- Definisi: Mengumpulkan informasi tanpa interaksi langsung. Lebih "senyap", risiko deteksi rendah.
- Teknik & Contoh:
    - Search Engine Queries (Google Dorking): Mencari informasi tersembunyi/sensitif.
        - Operator: `site:`, `inurl:`, `filetype:`, `intitle:`, `intext:`, `inbody:`, dll.
    - WHOIS Lookups: Mencari detail registrasi domain.
    - DNS Analysis (dig, nslookup, host, dnsenum): Menganalisis catatan DNS, subdomain.
    - Web Archive Analysis (Wayback Machine): Memeriksa arsip historis situs web.
    - Social Media Analysis: Mengumpulkan informasi dari platform media sosial.
    - Code Repositories (GitHub): Menganalisis repositori kode publik.

### 4. Mengenal Subdomain dan Virtual Host

### Subdomain
- Ekstensi dari nama domain utama (contoh: `dev.example.com`).
- Sering menyimpan informasi berharga (lingkungan pengembangan, portal login tersembunyi).
- Pencarian Subdomain (Subdomain Enumeration):
    - Aktif: Interaksi langsung dengan DNS server (brute-force dengan `dnsenum`, `ffuf`, `gobuster`), DNS Zone Transfer.
    - Pasif: Mengandalkan sumber eksternal (Certificate Transparency logs, mesin pencari).

### Virtual Host (VHost)
- Konfigurasi di server web yang memungkinkan banyak situs/aplikasi di satu server fisik.
- Subdomain punya catatan DNS sendiri, virtual host konfigurasi internal server.
- Tools: `gobuster`, `Feroxbuster`, `ffuf`.

### 5. Fingerprinting dan Tool Penting Lainnya

### Fingerprinting
- Proses mengidentifikasi detail teknis teknologi yang digunakan situs/aplikasi (server web, OS, komponen software).
- Tools: Wappalyzer, BuiltWith, WhatWeb, Nmap, Netcraft, wafw00f, Nikto.

### Hal Lain yang Perlu Dicek
- `robots.txt`, `.well-known`, Web Crawling.

## Summary

Reconnaissance dan Information Gathering adalah langkah awal yang sangat krusial dan tak tergantikan dalam setiap penilaian keamanan siber, termasuk dalam praktik ethical hacking. Dengan mengumpulkan informasi sebanyak-banyaknya tentang target, baik secara aktif maupun pasif, seorang ethical hacker dapat membangun pemahaman yang komprehensif mengenai attack surface target, potensi kerentanan, serta aset-aset penting yang perlu dilindungi. Menguasai berbagai teknik Reconnaissance, mulai dari WHOIS lookup hingga Google Dorking, serta memahami perbedaan antara pendekatan aktif dan pasif, akan menjadi modal dasar yang kuat bagi pemula untuk melangkah lebih jauh dalam dunia keamanan siber dan melakukan pengujian penetrasi secara lebih efektif dan bertanggung jawab.