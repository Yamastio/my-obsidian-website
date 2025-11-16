---
id: Ping(ICMP)
aliases: []
tags:
  - tryhackme
  - networking
  - recon
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[tryhackme]], [[networking]], [[recon]]

---

## Cue

- Apa itu Ping dan protokol apa yang digunakannya?
- Bagaimana cara kerja Ping untuk menguji konektivitas?
- Bagaimana cara menggunakan Ping untuk menguji konektivitas jaringan?
- Informasi apa saja yang bisa didapatkan dari respons Ping?

---

## Notes

### Apa itu Ping (ICMP)?
**Ping** adalah alat diagnostik jaringan dasar yang digunakan untuk menguji konektivitas dan mengukur waktu respons (latensi) antara dua perangkat di jaringan. Ping menggunakan **ICMP (Internet Control Message Protocol)** untuk mengirim dan menerima paket.

### Cara Kerja Ping
1.  **Echo Request**: Perangkat pengirim mengirimkan paket ICMP "echo request" ke perangkat target.
2.  **Echo Reply**: Jika perangkat target dapat dijangkau, ia akan membalas dengan paket ICMP "echo reply".
3.  **Pengukuran Latensi**: Ping mengukur waktu yang dibutuhkan paket untuk pergi dan kembali (round-trip time), biasanya dalam milidetik (ms).

### Contoh Penggunaan Ping
- **Ping ke Alamat IP**:
  ```bash
  ping 8.8.8.8
  ```
- **Ping ke Nama Domain/URL**:
  ```bash
  ping www.google.com
  ```

### Informasi dari Respons Ping
- **`bytes`**: Ukuran paket yang dikirim.
- **`time`**: Waktu round-trip dalam milidetik (latensi).
- **`TTL` (Time to Live)**: Jumlah hop maksimum yang dapat dilalui paket sebelum dibuang. Ini menunjukkan seberapa jauh target berada dalam jaringan.

---

## Summary

Ping adalah alat jaringan fundamental yang menggunakan protokol ICMP untuk menguji konektivitas dan mengukur latensi antara perangkat. Dengan mengirimkan paket "echo request" dan menerima "echo reply", Ping memberikan informasi penting seperti waktu tempuh paket dan TTL, yang sangat berguna untuk mendiagnosis masalah jaringan dan memverifikasi ketersediaan host.