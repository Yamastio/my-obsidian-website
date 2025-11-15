---
id: DIG Comptia HOL
aliases: []
tags:
  - cybersecurity
  - networking
  - pentesting
comments: true
draft: false
date: 2025-11-15
---

Related: [[index|Home]], [[cybersecurity]], [[networking]], [[pentesting]]

## Inti Konsep

`dig` adalah alat untuk **bertanya langsung ke DNS**: “Domain ini disimpan di mana? IP-nya apa? Siapa yang jadi mail servernya?”

Ia dipakai oleh sysadmin, pentester, dan siapa saja yang ingin **memahami apa yang terjadi di balik sebuah nama domain**.

Mengapa dipakai?
Karena DNS sering jadi akar masalah jaringan. Jika DNS salah, seluruh komunikasi internet ikut bermasalah.

Cara kerja `dig` sederhana:
Kamu memberikan pertanyaan → DNS server menjawab → `dig` menampilkan jawabannya.

---

## Cara Pakai (Praktik Inti)

### Query dasar

```bash
dig facebook.com
dig +short facebook.com
dig +trace facebook.com
```

### Query ke DNS server tertentu

```bash
dig facebook.com @8.8.8.8
dig facebook.com @1.1.1.1
```

Ini berguna untuk membandingkan jawaban antar DNS.

### Bagian penting output

* Server yang digunakan
* Jawaban authoritative / non-authoritative
* Nama domain
* Alamat IP atau record lain

---

## Tipe Record Penting

Jenis informasi yang bisa kamu minta dari DNS:

| Query  | Fungsi                                     |
| ------ | ------------------------------------------ |
| `A`    | Mendapatkan IPv4                           |
| `AAAA` | Mendapatkan IPv6                           |
| `MX`   | Menemukan mail server                      |
| `TXT`  | Informasi tambahan (SPF, DKIM, verifikasi) |
| `NS`   | Mengetahui nameserver domain               |

Contoh:

```bash
dig facebook.com MX
dig facebook.com NS
```

---

## Reverse DNS

Menanyakan: “IP ini menunjuk ke domain apa?”

```bash
dig -x 8.8.8.8
dig -x 9.9.9.9
```

---

## Alternatif Web Tool

Jika ingin melihat record tanpa CLI:

* mxtoolbox.com (MX, AAAA, TXT, dll.)

---

## Kesimpulan Singkat

Jika internet seperti buku telepon raksasa, **DNS adalah orang yang memberi tahu kamu nomor telepon dari nama seseorang**. `dig` adalah cara langsung untuk berbicara dengan orang itu:
*“Hei, apa nomor telepon facebook.com?”*
*“Siapa mail servernya?”*
*“IP ini milik siapa?”*

Ketika kamu paham cara bertanya, kamu otomatis paham cara mendiagnosis masalah jaringan—dan juga cara menemukan informasi penting untuk pentesting.
