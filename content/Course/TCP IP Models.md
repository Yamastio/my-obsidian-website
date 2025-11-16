---
id: TCP IP Models
aliases: []
tags:
  - networking
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[networking]]

---

## Cue

- Apa saja lapisan-lapisan dalam model TCP/IP?
- Bagaimana perbandingan antara model TCP/IP dan model OSI?
- Apa itu proses Three-Way Handshake pada TCP?
- Apa yang dimaksud dengan enkapsulasi dan dekapsulasi?

---

## Notes

### Model TCP/IP
Model TCP/IP adalah fondasi dari jaringan internet modern, yang terdiri dari 4 lapisan utama:
1.  **Application**: Tempat aplikasi berinteraksi dengan jaringan (HTTP, FTP, DNS).
2.  **Transport**: Mengatur koneksi dan pengiriman data (TCP, UDP).
3.  **Internet**: Mengurus pengalamatan dan routing (IP, ICMP).
4.  **Network Interface**: Mengirimkan data melalui media fisik (Ethernet, Wi-Fi).

### Perbandingan Model TCP/IP dan OSI
| TCP/IP Model | OSI Model |
|---|---|
| **Application** | Application, Presentation, Session |
| **Transport** | Transport |
| **Internet** | Network |
| **Network Interface** | Data Link, Physical |

- **TCP/IP** lebih praktis dan merupakan model yang diimplementasikan di dunia nyata.
- **OSI** lebih teoritis dan sering digunakan sebagai kerangka acuan untuk pembelajaran konsep jaringan.

### Encapsulation & De-Encapsulation
- **Encapsulation**: Proses penambahan informasi header pada data saat bergerak turun melalui lapisan-lapisan model. Contoh: Data → Segment (TCP) → Packet (IP) → Frame (Ethernet).
- **De-Encapsulation**: Proses sebaliknya di sisi penerima, di mana setiap header dilepas lapis demi lapis untuk mendapatkan data asli.

### Three-Way Handshake (TCP)
Ini adalah proses yang digunakan oleh TCP untuk membangun koneksi yang andal sebelum data dikirim.
1.  **SYN**: Klien mengirim pesan "synchronize" untuk memulai koneksi.
2.  **SYN-ACK**: Server merespons dengan "synchronize-acknowledge" untuk menyetujui koneksi.
3.  **ACK**: Klien mengirim "acknowledge" sebagai konfirmasi, dan koneksi pun terbentuk.

Proses ini memastikan kedua pihak siap berkomunikasi dan menjamin pengiriman data yang andal.

---

## Summary

Model TCP/IP adalah arsitektur 4 lapis (Application, Transport, Internet, Network Interface) yang menjadi standar praktis untuk komunikasi di internet. Berbeda dengan model OSI yang lebih teoritis, TCP/IP digunakan secara luas. Proses kunci dalam model ini adalah enkapsulasi data untuk pengiriman dan Three-Way Handshake pada protokol TCP untuk memastikan koneksi yang andal sebelum transfer data dimulai.