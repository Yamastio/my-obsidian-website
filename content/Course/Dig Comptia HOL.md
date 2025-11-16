---
id: DIG Comptia HOL
aliases: []
tags:
  - cybersecurity
  - networking
  - pentesting
comments: true
date: 2025-11-15
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[networking]], [[pentesting]]

---

## Cue

- Apa itu dig dan fungsinya
- Cara kerja dig
- Query dasar dan query ke dns server tertentu
- Bagian penting output dig
- Tipe record dns yang sering digunakan
- Reverse dns
- Alternatif web tool

---

## Notes

### Inti Konsep

- Dig adalah alat untuk bertanya langsung ke dns mengenai ip, mail server, dan authoritative server suatu domain.
- Dig digunakan oleh sysadmin, pentester, dan profesional lain untuk memahami infrastruktur domain.
- Cara kerja: pertanyaan dikirim ke dns server → jawaban diterima → dig menampilkan hasil.
- DNS sering menjadi akar masalah jaringan, sehingga analisis dns penting.

### Cara Pakai

#### Query Dasar

```bash
dig facebook.com
dig +short facebook.com
dig +trace facebook.com
```

#### Query ke DNS Server Tertentu

```bash
dig facebook.com @8.8.8.8
dig facebook.com @1.1.1.1
```

#### Bagian Penting Output

- Server yang digunakan
- Jawaban authoritative / non-authoritative
- Nama domain
- Alamat ip atau record lain

### Tipe Record Penting

| Query | Fungsi                                     |
| ----- | ------------------------------------------ |
| A     | Mendapatkan IPv4                           |
| AAAA  | Mendapatkan IPv6                           |
| MX    | Menemukan mail server                      |
| TXT   | Informasi tambahan (SPF, DKIM, verifikasi) |
| NS    | Mengetahui nameserver domain               |

Contoh:

```bash
dig facebook.com MX
dig facebook.com NS
```

### Reverse DNS

- Menanyakan domain dari sebuah IP.

```bash
dig -x 8.8.8.8
dig -x 9.9.9.9
```

### Alternatif Web Tool

- mxtoolbox.com untuk melihat MX, AAAA, TXT, dan record lain tanpa CLI.

---

## Summary

Dig adalah alat langsung untuk bertanya ke dns tentang ip, mail server, dan nameserver suatu domain. Dengan memahami query dan outputnya, pengguna dapat mendiagnosis masalah jaringan dan memperoleh informasi penting untuk pentesting.
