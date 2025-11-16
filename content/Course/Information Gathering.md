---
id: Information Gathering
aliases: []
tags:
  - recon
  - pentesting
comments: true
date: 2025-09-21
draft: false
---

---

Related: [[index|Home]], [[recon]], [[pentesting]]

---

## Cue

- Apa itu Information Gathering dalam penetration testing?
- Apa perbedaan antara passive dan active information gathering?
- Teknik apa saja yang digunakan dalam masing-masing jenis information gathering?
- Tools apa saja yang umum digunakan untuk passive dan active information gathering?
- Mengapa tahap information gathering penting sebelum eksploitasi?

---

## Notes

### Apa itu Information Gathering?
**Information Gathering** adalah tahap awal dan krusial dalam *penetration testing*. Tujuannya adalah untuk mengumpulkan informasi sebanyak mungkin tentang target (organisasi, sistem, atau individu) guna memahami strukturnya, menemukan potensi celah keamanan, dan merencanakan strategi serangan yang efektif.

### Passive Information Gathering
- **Definisi**: Mengumpulkan informasi tanpa melakukan interaksi langsung dengan target. Ini berarti tidak ada jejak yang ditinggalkan di sistem target, sehingga sulit terdeteksi.
- **Teknik**:
    -   **Search Engine**: Menggunakan mesin pencari umum.
    -   **Google Dorking**: Menggunakan operator pencarian canggih untuk menemukan informasi spesifik.
    -   **DNS Lookup**: Mencari informasi DNS seperti record A, MX, NS.
    -   **Whois Lookup**: Mendapatkan informasi registrasi domain.
- **Tools**: Maltego, Google Dorking, Whois Lookup.
- **Kelebihan**: Aman, sulit terdeteksi, legal (jika menggunakan sumber publik).
- **Keterbatasan**: Hanya mendapatkan data publik, mungkin tidak mendalam.

### Active Information Gathering
- **Definisi**: Melibatkan interaksi langsung dengan target, yang berpotensi meninggalkan jejak dan lebih mudah terdeteksi.
- **Teknik**:
    -   **Port Scanning**: Memindai port terbuka pada target untuk mengidentifikasi layanan yang berjalan.
    -   **Vulnerability Scanning**: Memindai sistem untuk kerentanan yang diketahui.
    -   **Banner Grabbing**: Mengambil informasi versi layanan dari *banner* yang ditampilkan.
    -   **Social Engineering**: Menggunakan manipulasi psikologis untuk mendapatkan informasi.
- **Tools**: Nmap, Nikto, Shodan, Metasploit.
- **Kelebihan**: Mendapatkan informasi yang lebih rinci dan spesifik.
- **Keterbatasan**: Berisiko tinggi terdeteksi, memerlukan izin.

### Perbedaan Utama
| Kategori | Passive Information Gathering | Active Information Gathering |
|---|---|---|
| **Interaksi** | Tidak ada interaksi langsung dengan target. | Melibatkan interaksi langsung dengan target. |
| **Deteksi** | Sulit terdeteksi. | Lebih mudah terdeteksi. |
| **Contoh Teknik** | Google Dorking, DNS Lookup, Whois. | Port scanning, Banner grabbing, Vulnerability scanning. |
| **Risiko** | Rendah. | Tinggi (memerlukan izin). |

---

## Summary

Information Gathering adalah fase awal penting dalam penetration testing, yang terbagi menjadi passive dan active. Passive gathering mengumpulkan data dari sumber publik tanpa interaksi langsung, sehingga sulit terdeteksi. Active gathering melibatkan interaksi langsung dengan target untuk mendapatkan informasi lebih rinci, namun berisiko lebih tinggi terdeteksi. Penguasaan kedua metode ini, didukung oleh berbagai alat, memungkinkan pentester untuk memahami target secara mendalam dan merencanakan strategi eksploitasi yang efektif.