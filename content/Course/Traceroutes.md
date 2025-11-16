---
id: Traceroutes
aliases: []
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

- Apa fungsi dari perintah `traceroute`?
- Bagaimana cara kerja `traceroute` menggunakan TTL?
- Apa perbedaan mendasar antara `ping` dan `traceroute`?
- Apa saja batasan dari `traceroute`?

---

## Notes

### Apa Itu `traceroute`?
`traceroute` (atau `tracert` di Windows) adalah sebuah alat diagnostik jaringan untuk melacak rute (path) yang dilewati paket data dari satu komputer ke tujuan lain di internet. Alat ini menampilkan setiap "lompatan" (hop) atau router perantara yang dilalui paket.

### Cara Kerja `traceroute`
- `traceroute` bekerja dengan mengirimkan serangkaian paket ke tujuan dengan nilai **Time-To-Live (TTL)** yang terus meningkat.
- TTL adalah sebuah nilai yang berkurang satu setiap kali paket melewati sebuah router.
- `traceroute` mengirim paket pertama dengan TTL=1. Router pertama akan mengurangi TTL menjadi 0, membuang paket, dan mengirimkan pesan balasan "Time Exceeded" ke pengirim. Dari balasan ini, `traceroute` mengetahui alamat router pertama.
- Proses ini diulangi dengan TTL=2, TTL=3, dan seterusnya, hingga paket mencapai tujuan akhir.

### Perbedaan `ping` dan `traceroute`
| Fitur | `ping` | `traceroute` |
|---|---|---|
| **Tujuan** | Mengecek apakah tujuan dapat dijangkau (konektivitas). | Melacak seluruh rute yang dilewati paket. |
| **Informasi** | Memberikan waktu bolak-balik (latency) ke tujuan akhir. | Memberikan latency untuk setiap hop di sepanjang rute. |
| **Kasus** | Cepat untuk tes koneksi dasar. | Berguna untuk mengidentifikasi di mana letak kelambatan atau kegagalan jaringan. |

### Contoh Penggunaan dan Tips
- **Penggunaan Dasar**:
  ```bash
  traceroute google.com
  ```
- **Menggunakan Protokol ICMP (di Linux)**:
  ```bash
  traceroute -I google.com
  ```
- **Batasan `traceroute`**:
    - **Firewall**: Banyak router atau firewall dikonfigurasi untuk tidak mengirim balasan ICMP/UDP, sehingga hop tersebut akan ditampilkan sebagai `* * *`.
    - **Rute Asimetris**: Rute yang ditempuh paket ke tujuan bisa berbeda dengan rute baliknya.
    - **Rute Dinamis**: Rute dapat berubah-ubah tergantung pada kondisi jaringan saat itu.

---

## Summary

`traceroute` adalah alat fundamental untuk diagnostik jaringan yang memetakan jalur paket data dari sumber ke tujuan. Dengan memanfaatkan mekanisme TTL (Time-To-Live), ia dapat mengidentifikasi setiap router perantara (hop) yang dilalui. Berbeda dengan `ping` yang hanya menguji konektivitas akhir, `traceroute` memberikan detail setiap langkah, sehingga sangat berguna untuk menemukan titik lambat atau kegagalan dalam sebuah koneksi jaringan.