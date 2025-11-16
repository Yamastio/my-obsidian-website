---
id: DIG
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

- Apa itu dig
- Fungsi utama dig
- Cara penggunaan di kali linux
- Contoh penggunaan dalam ethical hacking

---

## Notes

### Definisi

- Dig (Domain Information Groper) adalah tool untuk melakukan query dns.
- Lebih fleksibel dibanding nslookup.
- Dapat melakukan query tipe a, mx, ns, dan lainnya.

### Penggunaan di Kali Linux

- Sintaks dasar: `dig example.com`
- Menampilkan informasi dns terkait domain yang dituju.

### Contoh dalam Ethical Hacking

- Menentukan alamat ip dari domain target.
- Mengetahui nameserver yang digunakan domain.
- Query mx record untuk memeriksa konfigurasi email dan server mail.

---

## Summary

Dig adalah utilitas dns powerful yang digunakan untuk memperoleh informasi domain, ip, nameserver, dan konfigurasi email. Dalam konteks ethical hacking, dig membantu analisis target dan pemetaan infrastruktur jaringan.
