---
id: 2-Dasar-Dasar Jaringan dan Protokol untuk Pemula
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

- Apa itu jaringan dan jenis-jenisnya?
- Bagaimana model OSI dan TCP/IP bekerja?
- Apa itu alamat IP dan bagaimana cara kerjanya?
- Apa perbedaan TCP dan UDP?
- Bagaimana DNS dan HTTP bekerja?

---

## Notes

### Pendahuluan Jaringan dan Protokol
- Memahami jaringan adalah langkah awal krusial dalam dunia siber.

### Apa Itu Jaringan?
- Kumpulan perangkat yang saling terhubung untuk berkomunikasi dan berbagi sumber daya.
- Perangkat disebut node (komputer, smartphone, printer, server).
- Penting karena memungkinkan banyak hal esensial, terutama Internet.

### Jenis-Jenis Jaringan
- Local Area Network (LAN): Menghubungkan perangkat dalam jarak dekat (rumah, sekolah, kantor kecil).
- Wide Area Network (WAN): Mencakup area geografis luas, menghubungkan beberapa LAN.
    - Internet adalah contoh terbesar WAN.

### Bagaimana LAN dan WAN Bekerja Bersama?
- LAN terhubung ke WAN untuk akses jaringan lebih luas.
- ISP (Penyedia Layanan Internet) menyediakan akses Internet.
- Modem: Jembatan yang mengubah sinyal digital dari router untuk transmisi.

### Model Open Systems Interconnection (OSI)
- Kerangka kerja konseptual 7 lapisan untuk menstandarkan fungsi sistem telekomunikasi/komputasi.
- Membantu vendor/pengembang membuat perangkat/perangkat lunak jaringan yang inter-operable.
- Lapisan 1: Physical Layer (Fisik) - Peralatan fisik (kabel, switch), data jadi bit stream.
- Lapisan 2: Data Link Layer (Tautan Data) - Transfer data antar dua perangkat di jaringan sama, memecah paket jadi frame, flow/error control intra-jaringan.
- Lapisan 3: Network Layer (Jaringan) - Transfer data antar dua jaringan berbeda, memecah segmen jadi paket, routing (contoh: IP).
- Lapisan 4: Transport Layer (Transportasi) - Komunikasi end-to-end, memecah data jadi segmen, flow/error control.
- Lapisan 5: Session Layer (Sesi) - Membuka/menutup komunikasi, memastikan sesi tetap terbuka.
- Lapisan 6: Presentation Layer (Presentasi) - Menyiapkan data untuk lapisan aplikasi (terjemahan, enkripsi, kompresi).
- Lapisan 7: Application Layer (Aplikasi) - Berinteraksi langsung dengan data dari pengguna (browser, email), protokol dan manipulasi data.

### Model TCP/IP
- Model lain dengan 4 lapisan:
- Link Layer: Aspek fisik hardware dan media jaringan (mirip Lapisan Fisik & Data Link OSI).
- Internet Layer: Pengalamatan logis perangkat, perutean paket (mirip Lapisan Jaringan OSI). Protokol: IP, ICMP.
- Transport Layer: Layanan komunikasi end-to-end (mirip Lapisan Transportasi OSI). Protokol: TCP (andal), UDP (cepat, tanpa koneksi).
- Application Layer: Protokol layanan komunikasi data spesifik ke aplikasi (mirip Lapisan Sesi, Presentasi, Aplikasi OSI). Contoh: HTTP, FTP, SMTP.

### Alamat IP (IP Addresses)
- Setiap host diidentifikasi oleh MAC address (dalam satu jaringan).
- Untuk komunikasi antar-jaringan (Internet), digunakan alamat IP (IPv4 dan/atau IPv6).
- IPv4: 32-bit biner jadi angka desimal (contoh: 192.168.10.39).
- CIDR (Classless Inter-Domain Routing): Metode representasi untuk pembagian ruang alamat IP ke subnet (contoh: 192.168.10.39/24).

### Protokol Penting: TCP vs. UDP
- TCP (Transmission Control Protocol):
    - Protokol berorientasi koneksi (Three-Way-Handshake).
    - Andal tapi lebih lambat.
    - Contoh: HTTP, HTTPS, SSH, FTP, SMTP, DNS (port 53).
- UDP (User Datagram Protocol):
    - Protokol tanpa koneksi.
    - Lebih cepat tapi kurang andal.
    - Contoh: Streaming video, DNS (port 53), TFTP, NTP, SNMP, DHCP.

### Domain Name System (DNS)
- "Buku telepon Internet": Menemukan alamat IP untuk nama domain.
- Proses Resolusi DNS: Browser -> Cache lokal -> Server DNS rekursif -> Server root -> Server TLD -> Server otoritatif -> Alamat IP kembali ke komputer.

### HyperText Transfer Protocol (HTTP)
- Protokol tingkat aplikasi untuk mengakses sumber daya World Wide Web.
- Klien meminta sumber daya dari server, server merespons.
- Port default: 80.
- Sumber daya diakses melalui URL.

### cURL
- Alat baris perintah dan pustaka yang mendukung HTTP dan protokol lain.
- Berguna untuk mengirim berbagai jenis permintaan web dari baris perintah.

## Summary

Materi ini memberikan fondasi yang kuat dalam memahami bagaimana jaringan bekerja, mulai dari konsep dasar seperti LAN dan WAN hingga model arsitektur seperti OSI dan TCP/IP. Pemahaman tentang alamat IP, perbedaan antara TCP dan UDP, serta cara kerja DNS dan HTTP sangatlah krusial. Pengetahuan ini bukan hanya dasar untuk berinteraksi dengan Internet sehari-hari, tetapi juga merupakan pilar utama bagi siapa pun yang ingin memulai perjalanan di dunia keamanan siber dan menjadi seorang Ethical Hacker. Dengan memahami cara jaringan beroperasi, Anda akan lebih siap untuk mengidentifikasi dan menganalisis potensi kerentanan di masa depan.