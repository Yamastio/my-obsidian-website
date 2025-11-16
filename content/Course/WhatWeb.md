---
id: WhatWeb
aliases: []
tags:
  - hacking_tools
  - recon
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[recon]]

---

## Cue

- Apa itu WhatWeb?
- Bagaimana cara menggunakan WhatWeb?
- Informasi apa yang bisa didapatkan dari WhatWeb?

---

## Notes

### Apa itu WhatWeb?
`whatweb` adalah sebuah alat pemindai yang digunakan untuk mengidentifikasi berbagai teknologi yang digunakan oleh sebuah website. Alat ini sangat berguna dalam fase pengumpulan informasi (reconnaissance) untuk memahami "jeroan" dari target.

### Penggunaan Dasar
- Perintah dasarnya sangat sederhana dan dijalankan langsung dari terminal.
- Cukup ketik `whatweb` diikuti dengan nama domain target.
  ```bash
  whatweb example.com
  ```
- **Contoh Hasil**: `whatweb` dapat mengungkap informasi seperti:
    - Content Management System (CMS) yang digunakan (misal: WordPress, Joomla).
    - Web server (misal: Apache, Nginx).
    - Framework JavaScript (misal: jQuery, React).
    - Alamat IP dan negara hosting.

---

## Summary

WhatWeb adalah alat reconnaissance yang esensial untuk mengidentifikasi teknologi di balik sebuah website. Dengan perintah sederhana, `whatweb` dapat mengungkap informasi seperti CMS, web server, dan framework yang digunakan oleh target. Informasi ini sangat berharga bagi seorang pentester untuk memetakan permukaan serangan dan mencari kerentanan yang spesifik terhadap teknologi tersebut.
