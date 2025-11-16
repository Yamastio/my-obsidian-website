---
id: Nmap
aliases: []
tags:
  - hacking_tools
  - recon
  - networking
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[recon]], [[networking]]

---

## Cue

- Apa itu Nmap dan apa saja fungsi utamanya?
- Bagaimana cara melakukan scan Nmap dasar untuk IP tertentu?
- Bagaimana cara memindai seluruh subnet dengan Nmap?
- Bagaimana cara menggunakan Nmap untuk fingerprinting sistem operasi?
- Bagaimana cara menggunakan Nmap untuk mendeteksi layanan yang terbuka dan versinya?

---

## Notes

### Deskripsi Nmap
Nmap (Network Mapper) adalah sebuah alat open-source yang sangat fleksibel dan kuat untuk eksplorasi jaringan dan audit keamanan. Fungsi utamanya meliputi:
- **Mendeteksi Host**: Menemukan perangkat yang aktif dan online di jaringan.
- **Identifikasi Layanan**: Menentukan jenis layanan yang berjalan pada port terbuka (misalnya, HTTP, FTP, SSH).
- **Fingerprinting Sistem Operasi**: Mencoba menebak sistem operasi yang digunakan oleh host target.
- **Analisis Topologi Jaringan**: Membantu memahami struktur dan hubungan antar perangkat di jaringan.

### Contoh Penggunaan Nmap
- **Scan Dasar untuk IP Tertentu**:
  ```bash
  nmap -v 192.168.1.1
  ```
  Opsi `-v` (verbose) akan menampilkan detail lebih lanjut tentang proses scan dan hasil yang ditemukan, seperti status host dan layanan yang terbuka.

- **Scan Seluruh Subnet**:
  ```bash
  nmap -v 192.168.1.0/24
  ```
  Perintah ini akan memindai semua perangkat dalam rentang IP yang ditentukan oleh subnet `/24`.

- **Fingerprinting Sistem Operasi**:
  ```bash
  nmap -O 192.168.1.1
  ```
  Opsi `-O` digunakan untuk mengaktifkan deteksi sistem operasi, yang mencoba menebak OS target berdasarkan respons paket.

- **Scan untuk Menemukan Layanan dan Versinya**:
  ```bash
  nmap -sV 192.168.1.1
  ```
  Opsi `-sV` digunakan untuk mendeteksi versi layanan yang berjalan pada port terbuka, memberikan informasi yang lebih spesifik tentang potensi kerentanan.

---

## Summary

Nmap (Network Mapper) adalah alat serbaguna untuk eksplorasi jaringan dan audit keamanan. Fungsinya mencakup deteksi host aktif, identifikasi layanan, fingerprinting sistem operasi, dan analisis topologi jaringan. Dengan berbagai opsi seperti `-v` untuk verbose, `-O` untuk deteksi OS, dan `-sV` untuk versi layanan, Nmap menjadi alat esensial bagi profesional keamanan untuk reconnaissance dan pengujian penetrasi.
