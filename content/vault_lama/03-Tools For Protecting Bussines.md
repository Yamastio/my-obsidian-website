---
id: 03-Tools For Protecting Bussines
aliases: []
tags:
  - cybersecurity
  - google_cybersecurity
  - forensics
  - network_security
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[google_cybersecurity]], [[forensics]], [[network_security]]

---

## Cue

- What are the essential cybersecurity tools for entry-level analysts in business protection?
- How do SIEM tools function, what are their benefits, and what are the hosting options?
- What are network protocol analyzers, and what is their primary use in cybersecurity?
- What are playbooks, specifically "chain of custody" and "protecting and preserving evidence" playbooks, and why are they crucial in forensic investigations?
- What are key considerations for a career in forensic investigation, and what additional resources are available?

---

## Notes

### Toolkit Analis Keamanan Pemula

- Setiap organisasi memiliki alat keamanan yang berbeda sesuai kebutuhannya.
- Penting untuk memahami alat standar industri dan menunjukkan kemampuan belajar alat serupa.

### Security Information and Event Management (SIEM) Tools

- **Fungsi**: Mengumpulkan dan menganalisis data log untuk memonitor aktivitas kritis organisasi.
- **Manfaat**:
  - Mengurangi waktu yang dibutuhkan untuk analisis log.
  - Menyediakan dasbor visual untuk menyusun data ke dalam kategori yang mudah diakses.
- **Hosting**:
  - **On-premise**: Memerlukan pengaturan dan perawatan manual, cocok untuk tim yang lebih berpengalaman.
  - **Cloud-hosted**: Mudah diatur dan dikelola, cocok untuk tim yang kurang berpengalaman.

### Network Protocol Analyzers (Packet Sniffers)

- **Fungsi**: Menangkap dan menganalisis lalu lintas data di jaringan.
- **Contoh alat**: `tcpdump` (alat baris perintah) dan `Wireshark` (alat GUI).
- Digunakan untuk memonitor data jaringan dan mengidentifikasi ancaman.

### Playbooks

- **Definisi**: Panduan manual yang mendokumentasikan tindakan operasional, seperti respons insiden.
- **Jenis Playbooks dalam Forensik**:
  - **Chain of Custody Playbook**:
    - Mencatat kepemilikan dan pengendalian bukti selama siklus hidup insiden.
    - Menyimpan catatan siapa yang mengakses bukti dan untuk tujuan apa.
  - **Protecting and Preserving Evidence Playbook**:
    - Memastikan bukti digital yang rapuh dan volatil dikelola dengan benar.
    - Mengikuti `order of volatility` untuk memprioritaskan data yang harus diselamatkan terlebih dahulu.
    - Menghindari pengelolaan yang salah agar bukti tetap valid dan dapat diterima.

### Tips untuk Karier di Investigasi Forensik

- Jika tertarik pada investigasi forensik, eksplorasi lebih lanjut tentang alat dan konsep forensik sangat dianjurkan.
- Dalam investigasi, menjaga keutuhan bukti digital adalah prioritas utama.

### Sumber Informasi Tambahan

- **Google Cybersecurity Action Team's Threat Horizon Report**: Memberikan wawasan strategis mengenai ancaman keamanan cloud.
- **CISA (Cybersecurity & Infrastructure Security Agency)**: Menyediakan daftar alat keamanan siber gratis yang dapat dijadikan referensi.

---

## Summary

This document outlines essential cybersecurity tools for entry-level analysts, including SIEM for log analysis, network protocol analyzers for traffic monitoring, and playbooks for structured operational responses. It particularly emphasizes the critical role of playbooks in forensic investigations, detailing "chain of custody" to track evidence and "protecting and preserving evidence" to maintain its integrity, especially by adhering to the order of volatility. The document also provides career advice for those interested in forensic investigation and lists valuable external resources, concluding that proficiency with these tools is fundamental for effectively identifying and mitigating business security risks.