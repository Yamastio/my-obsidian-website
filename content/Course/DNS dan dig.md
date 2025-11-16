---
id: DNS dan dig
aliases:
  - dig
  - DNS
tags:
  - networking
  - recon
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[networking]], [[recon]]

---

## Cue

- Apa itu DNS (Domain Name System) dan mengapa itu penting?
- Bagaimana alur kerja proses DNS lookup dari awal hingga akhir?
- Apa fungsi dari perintah `dig`?
- Apa saja jenis-jenis server DNS dan peran masing-masing?
- Kapan sebaiknya kita menggunakan perintah `dig`?

---

## Notes

### Apa Itu DNS?
- DNS (Domain Name System) adalah sistem yang berfungsi sebagai "buku telepon internet".
- Tugasnya adalah menerjemahkan nama domain yang mudah diingat (misal: `google.com`) menjadi alamat IP numerik (misal: `172.217.16.206`) yang dipahami oleh komputer.

### Proses DNS Lookup
Proses ini berjalan secara hierarkis untuk menemukan alamat IP:
1.  **Cache Lokal & Hosts File**: Komputer pertama-tama memeriksa cache DNS lokal dan file `hosts` untuk melihat apakah alamat IP sudah disimpan.
2.  **Recursive DNS Server**: Jika tidak ditemukan, permintaan diteruskan ke server DNS rekursif (biasanya dari ISP atau layanan seperti Google `8.8.8.8`).
3.  **Root DNS Server**: Server rekursif bertanya ke server root, yang akan mengarahkannya ke server TLD yang sesuai.
4.  **TLD DNS Server**: Server Top-Level Domain (misal: untuk `.com` atau `.org`) kemudian mengarahkan ke server DNS otoritatif.
5.  **Authoritative DNS Server**: Server ini adalah sumber kebenaran yang menyimpan catatan DNS asli untuk domain tersebut dan memberikan alamat IP yang benar.

### Perintah `dig` (Domain Information Groper)
- `dig` adalah alat command-line untuk melakukan kueri DNS secara manual. Sangat berguna untuk troubleshooting dan analisis.
- **Sintaks Dasar**: `dig <domain> @<dns-server>`
- **Contoh**: `dig google.com @8.8.8.8`
- **Output Penting**: Bagian `ANSWER SECTION` menunjukkan alamat IP (A record) dan TTL (Time To Live).

### Jenis-Jenis DNS Server
| Tipe | Peran | Contoh |
|---|---|---|
| **Recursive** | Mencari jawaban untuk pengguna | `8.8.8.8` (Google DNS) |
| **Root** | Mengarahkan ke server TLD | 13 server inti di seluruh dunia |
| **TLD** | Mengarahkan ke server Otoritatif | Server khusus untuk `.com`, `.id`, dll. |
| **Authoritative** | Menyimpan data DNS asli sebuah domain | Server DNS milik pemilik website |

### Kapan Menggunakan `dig`?
- **Troubleshooting**: Memastikan server DNS merespons dengan benar.
- **Verifikasi Perubahan**: Mengecek apakah perubahan DNS (misal: IP baru) sudah terpropagasi.
- **Inspeksi Record**: Memeriksa berbagai jenis record seperti `MX` (email), `CNAME` (alias), atau `TXT`.
- **Melacak Alur**: Menggunakan `dig +trace` untuk melihat seluruh alur proses lookup.

---

## Summary

DNS (Domain Name System) adalah sistem fundamental di internet yang menerjemahkan nama domain menjadi alamat IP melalui proses lookup hierarkis yang melibatkan server Recursive, Root, TLD, dan Authoritative. Untuk menganalisis dan melakukan troubleshooting proses ini, digunakan perintah `dig`. Alat ini memungkinkan pengguna untuk mengirim kueri DNS secara manual, memeriksa berbagai jenis record, dan melacak seluruh alur permintaan untuk memastikan konfigurasi DNS berjalan dengan benar.