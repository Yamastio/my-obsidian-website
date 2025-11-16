---
id: Domain Names & Whois
aliases: []
tags:
  - networking
  - osint
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[networking]], [[osint]]

---

## Cue

- Apa itu nama domain dan mengapa itu penting?
- Apa fungsi dari perintah `whois`?
- Informasi apa saja yang bisa didapatkan dari `whois`?
- Bagaimana cara menggunakan perintah `whois`?
- Apa saja batasan atau kekurangan dari `whois`?

---

## Notes

### Apa Itu Domain Name?
- Domain adalah **nama alias** yang mudah diingat untuk sebuah alamat IP.
- Contohnya, `tryhackme.com` lebih mudah diingat daripada alamat IP-nya, `172.67.209.124`.
- Fungsinya adalah untuk membuat internet lebih mudah diakses oleh manusia.

### Registrasi Domain
- Domain tidak dibeli, melainkan "disewa" dari perusahaan **Domain Registrar** (seperti GoDaddy atau Namecheap) untuk periode tertentu, biasanya per tahun.

### Perintah `whois`
- `whois` adalah protokol dan alat command-line untuk **melihat informasi registrasi** sebuah domain.
- Informasi yang bisa didapat meliputi:
    - **Pemilik (Registrant)**: Individu atau organisasi yang mendaftarkan domain.
    - **Tanggal Penting**: Tanggal pendaftaran dan kedaluwarsa.
    - **Kontak**: Informasi kontak administratif dan teknis.
    - **Nameserver**: Server DNS yang digunakan oleh domain tersebut.

### Cara Menggunakan `whois`
- **Instalasi (Debian/Ubuntu)**:
  ```bash
  sudo apt update && sudo apt install whois
  ```
- **Sintaks Dasar**:
  ```bash
  whois <nama-domain>
  ```
- **Contoh**:
  ```bash
  whois bbc.co.uk
  ```

### Batasan `whois`
- **Privasi (GDPR)**: Banyak data pribadi pemilik domain di Eropa disensor untuk mematuhi peraturan privasi.
- **Layanan Privasi**: Registrar sering menawarkan layanan proteksi privasi yang menyembunyikan data asli pemilik.
- **Data Tidak Akurat**: Informasi yang ditampilkan bisa jadi sudah usang atau tidak diperbarui.

---

## Summary

Domain adalah nama alias yang ramah manusia untuk alamat IP teknis, yang disewa melalui registrar domain. Untuk menyelidiki siapa pemilik sebuah domain, digunakan protokol `whois`. Perintah `whois` dapat mengungkap detail registrasi seperti nama pemilik, tanggal kedaluwarsa, dan nameserver yang digunakan, menjadikannya alat penting untuk OSINT dan troubleshooting. Namun, efektivitasnya sering dibatasi oleh layanan proteksi privasi dan peraturan seperti GDPR.