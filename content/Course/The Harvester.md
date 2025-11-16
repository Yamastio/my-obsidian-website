---
id: The Harvester
aliases: []
tags:
  - hacking_tools
  - osint
  - recon
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[osint]], [[recon]]

---

## Cue

- Apa itu theHarvester?
- Informasi apa saja yang bisa dikumpulkan oleh theHarvester?
- Bagaimana sintaks dasar untuk menggunakan theHarvester?

---

## Notes

### Apa itu theHarvester?
`theHarvester` adalah sebuah alat *Open-Source Intelligence* (OSINT) yang digunakan untuk mengumpulkan informasi publik terkait sebuah domain. Alat ini sangat efektif untuk fase pengumpulan informasi (reconnaissance) dalam sebuah penetration testing.

Informasi yang dapat dikumpulkan meliputi:
- Alamat email
- Nama subdomain dan host
- Nama karyawan atau pengguna
- Port yang terbuka

### Penggunaan Dasar
`theHarvester` bekerja dengan cara menanyakan ke berbagai sumber data publik, seperti mesin pencari (Google, Bing, DuckDuckGo) dan layanan lainnya (misalnya, Shodan, ZoomEye).

- **Sintaks**: `theHarvester -d <domain> -b <sumber_data>`
- **Contoh 1**: Mengumpulkan informasi dari domain `example.com` menggunakan mesin pencari Bing.
  ```bash
  theHarvester -d example.com -b bing
  ```
- **Contoh 2**: Mencari di DuckDuckGo dengan batas 500 hasil untuk domain `kali.org`.
  ```bash
  theHarvester -d kali.org -l 500 -b duckduckgo
  ```

---

## Summary

theHarvester adalah sebuah alat OSINT yang kuat untuk mengumpulkan informasi publik tentang sebuah domain target, seperti alamat email, subdomain, dan host. Alat ini bekerja dengan memanfaatkan berbagai sumber data publik, termasuk mesin pencari populer. theHarvester merupakan salah satu alat utama yang digunakan pada fase reconnaissance dalam sebuah pengujian keamanan.
