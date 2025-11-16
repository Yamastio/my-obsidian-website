---
id: 02-Common Tools
aliases: []
tags:
  - cybersecurity
  - google_cybersecurity
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[google_cybersecurity]]

---

## Cue

- What are the primary cybersecurity tools utilized by entry-level analysts?
- How do system logs function as a foundational data source for cybersecurity analysis?
- What are SIEM tools, their core functionalities, and notable examples?
- What role do playbooks play in cybersecurity operations, particularly in incident response?
- How do network protocol analyzers assist in identifying potential network threats?

---

## Notes

### Log Sebagai Sumber Data

- Log adalah catatan aktivitas sistem, seperti login pengguna atau akses layanan web.
- Log sangat penting untuk mengidentifikasi potensi kerentanan atau pelanggaran keamanan.

### SIEM (Security Information and Event Management) Tools

- **Fungsi Utama**:
  - Mengumpulkan dan menganalisis data log dari berbagai sumber secara real-time.
  - Mengurangi volume data yang perlu dianalisis dengan menghasilkan peringatan untuk ancaman spesifik.
- **Contoh SIEM Tools**:
  - **Splunk**: Platform analisis data yang komprehensif untuk menyimpan, menganalisis, dan mencari data log.
  - **Google Chronicle**: Solusi SIEM berbasis cloud yang menawarkan penyimpanan dan analisis data keamanan yang cepat.
- **Kegunaan SIEM**:
  - Menganalisis pola dan peristiwa keamanan yang telah difilter.
  - Melakukan analisis insiden untuk memahami akar masalah.
  - Secara proaktif mencari ancaman (threat hunting) dalam lingkungan IT.

### Playbooks

- Playbooks adalah panduan manual yang mendokumentasikan langkah-langkah operasional.
- Sangat penting untuk respons insiden, mencakup tindakan sebelum, selama, dan setelah insiden.
- Digunakan untuk berbagai tugas seperti tinjauan keamanan, manajemen akses, dan memastikan kepatuhan.

### Network Protocol Analyzers (Packet Sniffers)

- Alat yang dirancang untuk menangkap dan menganalisis lalu lintas data yang mengalir dalam jaringan.
- **Contoh**:
  - **tcpdump**: Alat berbasis baris perintah yang efisien untuk menangkap data jaringan.
  - **Wireshark**: Alat GUI populer yang menyediakan analisis paket data secara mendalam.
- Membantu mengidentifikasi potensi ancaman dan anomali dalam komunikasi jaringan.

### Saran untuk Pemula

- Tidak diharapkan menjadi ahli dalam semua alat ini sejak awal.
- Program sertifikat ini akan memberikan latihan langsung yang ekstensif untuk membangun pemahaman dan keahlian.

---

## Summary

This document introduces entry-level cybersecurity analysts to essential tools for identifying, assessing, and mitigating security risks, all underpinned by system logs. It details SIEM tools like Splunk and Google Chronicle for real-time log analysis and threat detection, playbooks for structured incident response, and network protocol analyzers such as tcpdump and Wireshark for monitoring network traffic. The text emphasizes that while initial expertise isn't required, continuous practice with these tools is crucial for developing the skills necessary to effectively manage an organization's security posture.