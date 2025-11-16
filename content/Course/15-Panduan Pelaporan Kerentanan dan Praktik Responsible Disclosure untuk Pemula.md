---
id: 15-Panduan Pelaporan Kerentanan dan Praktik Responsible Disclosure untuk Pemula
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

- Apa itu Responsible Disclosure dan mengapa penting?
- Bagaimana cara melaporkan bug di dalam dan di luar platform Bug Bounty?
- Apa saja format pelaporan bug yang baik?
- Apa itu Proof of Concept (PoC) dan tipe-tipenya?

---

## Notes

### Apa Itu Responsible Disclosure?
- Praktik melaporkan kerentanan keamanan secara etis kepada pihak berwenang sebelum dipublikasikan.
- Tujuan: Memastikan kerentanan diperbaiki terlebih dahulu, mencegah eksploitasi jahat.
- Berbeda dengan Full Disclosure (publikasi langsung), Responsible Disclosure lebih aman dan bertanggung jawab.

### Bagaimana Cara Melaporkan Bug?

### 1. Melaporkan Bug di Dalam Platform Bug Bounty (BBP)
- Proses Pelaporan:
    - Klik "Submit Report" atau "Submission".
    - Ikuti petunjuk, masukkan Proof of Concept (PoC), lalu kirim laporan.
- Setelah Melaporkan:
    - Menunggu balasan dan memantau status laporan.
    - Status Penting:
        - TRIAGED: Bug valid, kemungkinan dapat bounty.
        - DUPLICATE: Bug sudah dilaporkan orang lain.
        - INFORMATIVE: Bug tidak memiliki dampak keamanan signifikan.
    - Disarankan follow-up jika belum ada balasan dalam seminggu.

### 2. Melaporkan Bug di Luar Platform Bug Bounty
- Proses Pelaporan:
    - Cek apakah target memiliki program bug bounty atau VDP.
    - Kumpulkan kontak (email keamanan).
    - Buat laporan dan PoC terpisah.
    - Kirim laporan melalui kontak yang ditemukan.
- Setelah Melaporkan:
    - Menunggu balasan.
    - Bisa jadi tidak ada balasan, tetapi bug diperbaiki secara diam-diam.

### Format Pelaporan Bug

### Di Platform Bug Bounty (Contoh HackerOne)
- Pilih Asset (target).
- Pilih Kategori bug berdasarkan CWE (Common Weakness Enumeration).
- Tentukan tingkat keparahan (Severity) atau pilih "Submit report without severity".
- Buat Proof of Concept sesuai template.
- Platform BBP lain memiliki format serupa.

### Di Luar Platform Bug Bounty
- Laporan lebih formal dan rapi, sering dalam bentuk PDF.
- Cantumkan: Title, Summary, CWE, CVSS, Security Impact, Affected Domain, POC, Remediation.

### Apa itu Proof of Concept (PoC)?
- Bukti bahwa berhasil mengeksploitasi bug/kerentanan dan menimbulkan dampak keamanan.
- Sangat penting agar bug dapat divalidasi dan pemilik aset bisa mereproduksi langkah-langkah eksploitasi.
- Tipe PoC:
    - Text-based: Langkah demi langkah dalam teks.
    - Text & Image-based: Lebih informatif dengan contoh gambar.
    - Video-based: Paling informatif, klien melihat langsung eksploitasi live (diunggah unlisted ke YouTube).

## Summary

Melaporkan kerentanan keamanan secara etis melalui Responsible Disclosure adalah fondasi penting dalam ethical hacking. Dengan mengikuti format pelaporan yang baik dan menyertakan Proof of Concept yang jelas dan mudah direproduksi, Anda membantu memastikan bahwa bug dapat diperbaiki dengan cepat, sehingga sistem menjadi lebih aman bagi semua orang. Ini adalah langkah yang bertanggung jawab untuk melindungi sistem dari eksploitasi oleh pihak yang tidak diinginkan.