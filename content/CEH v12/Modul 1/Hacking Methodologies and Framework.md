---
id: Hacking Methodologies and Framework
aliases: []
tags:
  - ceh_v12
  - cybersecurity
comments: true
date: 2025-09-10
description: Ringkasan lengkap metodologi hacking CEH, Cyber Kill Chain, TTPs, IOC, MITRE ATT&CK, dan Diamond Model.
draft: false
title: Hacking Methodologies and Framework
---

---

Related: [[index|Home]], [[ceh_v12]], [[cybersecurity]]

---

## Cue

- Apa itu CEH Methodology?
- Apa saja tahapan dalam Cyber Kill Chain?
- Apa itu TTPs, IOC, dan MITRE ATT&CK Framework?
- Apa itu Diamond Model of Intrusion Analysis?

---

## Notes

### CEH Methodology (CHM)

1.  **Footprinting**: Mengumpulkan informasi awal tentang target.
2.  **Scanning**: Mengidentifikasi host aktif dan port terbuka.
3.  **Enumeration**: Mengambil data detail seperti user list dan routing table.
4.  **Vulnerability Analysis**: Mengidentifikasi kelemahan keamanan.
5.  **System Hacking**:
    - **Gaining Access**: Mengeksploitasi kelemahan untuk masuk ke sistem.
    - **Escalating Privileges**: Meningkatkan hak akses.
    - **Maintaining Access**: Menjaga akses jangka panjang dengan backdoor.
    - **Clearing Logs**: Menghapus jejak aktivitas.

### Cyber Kill Chain Methodology

Framework untuk mendeteksi dan mencegah serangan siber, terdiri dari 7 tahapan:
1.  **Reconnaissance**: Mengumpulkan informasi target.
2.  **Weaponization**: Membuat payload (malware/exploit).
3.  **Delivery**: Mengirim payload ke target.
4.  **Exploitation**: Mengeksekusi payload untuk memanfaatkan kelemahan.
5.  **Installation**: Menginstall malware atau backdoor.
6.  **Command & Control (C2)**: Membuat channel komunikasi dengan target.
7.  **Action on Objectives**: Mencapai tujuan akhir (mencuri data, merusak sistem).

### Tactics, Techniques, and Procedures (TTPs)

- **Tactic**: Pedoman langkah serangan.
- **Technique**: Metode teknis yang digunakan.
- **Procedure**: Rangkaian langkah sistematis.
- TTPs membantu dalam memprediksi, mendeteksi, dan memahami motif penyerang.

### Indicator of Compromise (IOC)

- Petunjuk adanya aktivitas berbahaya pada sistem atau jaringan.
- **Kategori IOC**:
    - **Email Indicators**: Subjek atau attachment mencurigakan.
    - **Network Indicators**: URL, domain, atau IP berbahaya.
    - **Host-Based Indicators**: File abnormal, hash, atau registry key.
    - **Behavioral Indicators**: Perilaku aneh seperti dokumen yang menjalankan PowerShell.

### MITRE ATT&CK Framework

- Basis pengetahuan global tentang taktik dan teknik serangan yang digunakan oleh penyerang.
- Terdiri dari 14 taktik untuk enterprise, mulai dari Reconnaissance hingga Impact.
- Digunakan untuk pemetaan musuh, deteksi, dan mitigasi serangan.

### Diamond Model of Intrusion Analysis

- Framework untuk menganalisis rangkaian peristiwa dalam sebuah serangan siber.
- **Elemen Inti**:
    - **Adversary**: Penyerang.
    - **Victim**: Korban.
    - **Capability**: Kemampuan atau alat yang digunakan.
    - **Infrastructure**: Infrastruktur yang digunakan untuk serangan.
- Model ini dapat diperluas dengan meta-features seperti waktu, fase, dan hasil serangan.

---

## Summary

Metodologi hacking adalah serangkaian langkah terstruktur yang digunakan penyerang untuk menargetkan sistem. **CEH Methodology** mencakup tahapan dari Footprinting hingga Clearing Logs. **Cyber Kill Chain** menyediakan framework 7 langkah dari Reconnaissance hingga Action on Objectives. Konsep penting lainnya termasuk **TTPs** (Tactics, Techniques, Procedures) untuk memahami perilaku penyerang, **IOC** (Indicator of Compromise) sebagai bukti adanya intrusi, serta **MITRE ATT&CK** dan **Diamond Model** yang berfungsi sebagai kerangka kerja untuk analisis dan pertahanan terhadap serangan siber.