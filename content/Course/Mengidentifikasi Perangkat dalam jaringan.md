---
id: Mengidentifikasi Perangkat dalam jaringan
aliases: []
tags:
  - networking
  - cybersecurity
  - tryhackme
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[networking]], [[cybersecurity]], [[tryhackme]]

---

## Cue

- Bagaimana perangkat diidentifikasi dalam jaringan?
- Apa itu Alamat IP dan jenis-jenisnya?
- Apa perbedaan IPv4 dan IPv6?
- Apa itu Alamat MAC dan bagaimana strukturnya?
- Apa itu MAC spoofing dan bagaimana dampaknya?
- Bagaimana Alamat MAC digunakan dalam kontrol akses Wi-Fi publik?

---

## Notes

### Identifikasi Perangkat dalam Jaringan

-   Untuk menjaga komunikasi yang tertib dan terorganisir, perangkat dalam jaringan harus dapat **mengidentifikasi** dan **dikenali**.
-   Perangkat diidentifikasi melalui dua cara utama:
    1.  **Alamat IP** (Internet Protocol)
    2.  **Alamat MAC** (Media Access Control)

### Alamat IP (Internet Protocol)

-   Digunakan untuk mengidentifikasi perangkat di jaringan untuk jangka waktu tertentu.
-   Dibagi menjadi empat oktet, menunjukkan bagian dari alamat IP perangkat.
-   Dihitung menggunakan teknik **IP addressing & subnetting**.
-   **Dua Jenis Alamat IP**:
    -   **Alamat IP Publik**: Digunakan untuk mengidentifikasi perangkat di Internet.
    -   **Alamat IP Privat**: Digunakan untuk mengidentifikasi perangkat di jaringan lokal (misalnya di rumah atau kantor).
-   **Contoh**:
    | Nama Perangkat | Alamat IP Privat | Alamat IP Publik |
    | :------------- | :--------------- | :--------------- |
    | DESKTOP-KJE57FD | 192.168.1.77     | 86.157.52.21     |
    | CMNatic-PC     | 192.168.1.74     | 86.157.52.21     |
-   **IPv4 vs IPv6**:
    -   **IPv4**: Sistem lama, memungkinkan 4.29 miliar alamat.
    -   **IPv6**: Dibuat karena kebutuhan alamat yang lebih banyak, dengan kapasitas 340 triliun alamat.

### Alamat MAC (Media Access Control)

-   Setiap perangkat jaringan memiliki *interface* fisik jaringan (chip mikro) yang diberikan **alamat MAC** unik saat diproduksi.
-   Alamat MAC adalah **nomor heksadesimal 12 karakter**, dipisahkan oleh titik dua (misalnya, `a4:c3:f0:85:ac:2d`).
-   **Struktur**:
    -   Enam karakter pertama: menunjukkan perusahaan pembuat perangkat jaringan.
    -   Enam karakter terakhir: nomor unik untuk perangkat tersebut.
-   **MAC Spoofing**:
    -   Alamat MAC dapat dipalsukan (*spoofing*), yaitu ketika perangkat berpura-pura menggunakan alamat MAC perangkat lain.
    -   **Dampak**: Jika *firewall* mengizinkan komunikasi hanya dari alamat MAC administrator, peretas bisa menyamar dengan alamat MAC administrator untuk mendapatkan akses tidak sah.
-   **Kontrol Alamat MAC di Wi-Fi Publik**:
    -   Banyak tempat (kafe, hotel) menggunakan kontrol alamat MAC untuk membatasi akses Wi-Fi atau memberikan layanan berbeda.
    -   Peretas dapat mengubah alamat MAC untuk mendapatkan akses atau layanan yang lebih baik tanpa membayar.

### Praktik Langsung (Simulasi TryHackMe)

-   Dalam lab interaktif TryHackMe, *router* tidak mengizinkan paket dari Bob (ditandai biru) ke situs web TryHackMe karena belum membayar.
-   Paket Alice (hijau) berjalan lancar karena sudah membayar.
-   Mengubah alamat MAC Bob menjadi sama seperti milik Alice dapat memungkinkan Bob mengakses layanan.

---

## Summary

Perangkat dalam jaringan diidentifikasi melalui Alamat IP dan Alamat MAC. Alamat IP (publik dan privat) digunakan untuk komunikasi di jaringan lokal maupun internet, dengan IPv6 mengatasi keterbatasan alamat IPv4. Alamat MAC adalah identifikasi fisik unik yang diberikan saat produksi, namun dapat dipalsukan melalui MAC *spoofing* untuk tujuan jahat atau melewati kontrol akses Wi-Fi publik. Memahami kedua jenis identifikasi ini sangat fundamental untuk komunikasi jaringan yang aman dan efektif.
