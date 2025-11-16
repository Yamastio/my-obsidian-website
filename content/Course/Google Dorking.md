---
id: Google Dorking
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

- Apa itu Google Dorking?
- Apa tujuan utama dari Google Dorking?
- Bagaimana cara melakukan Google Dorking menggunakan operator pencarian?
- Apa saja contoh penggunaan Google Dorking dalam ethical hacking?
- Apa saja pertimbangan etika dan hukum saat menggunakan Google Dorking?

---

## Notes

### Apa Itu Google Dorking?
**Google Dorking** (juga dikenal sebagai Google Hacking) adalah teknik pengumpulan informasi (information gathering) yang memanfaatkan fitur pencarian lanjutan pada mesin pencari Google. Teknik ini memungkinkan pengguna untuk menemukan informasi tersembunyi atau sensitif yang tidak mudah ditemukan melalui pencarian biasa.

### Tujuan Google Dorking
1.  **Mengumpulkan Data Awal (Reconnaissance)**: Memahami teknologi, struktur, dan informasi target.
2.  **Menganalisis Potensi Kerentanan**: Melacak file sensitif, halaman login, atau *endpoint* yang bisa dieksploitasi.
3.  **Membantu Ethical Hacking**: Menemukan area yang dapat diperbaiki untuk mencegah akses tidak sah.

### Cara Melakukan Google Dorking
Google Dorking dilakukan dengan menggunakan **Google Search Operators** untuk mempersempit hasil pencarian.

#### Operator Dasar
-   **Mencari frasa spesifik**: Gunakan tanda kutip ganda (`"`) untuk mencari frasa persis, contoh: `"password file"`.
-   **Menggunakan `AND`/`OR`**: Menggabungkan atau memilih kondisi, contoh: `site:kominfo.go.id AND inurl:login`.
-   **Mengecualikan kata**: Gunakan tanda minus (`-`) untuk mengecualikan kata, contoh: `intitle:"admin panel" -site:example.com`.

#### Operator Lokasi
-   **`inurl:`**: Mencari kata dalam URL, contoh: `inurl:admin`.
-   **`intitle:`**: Mencari kata dalam judul halaman, contoh: `intitle:"index of /"`.
-   **`intext:`**: Mencari kata dalam teks halaman, contoh: `intext:"vulnerable"`.

#### Operator File
-   **`filetype:`**: Mencari jenis file tertentu, contoh: `filetype:pdf site:example.com`.

### Contoh Penggunaan Google Dorking dalam Ethical Hacking
-   **Mengidentifikasi Informasi Sensitif**: `filetype:txt intext:password`, `intitle:"index of /" intext:backup`.
-   **Mencari Panel Admin**: `inurl:admin`, `intitle:"admin panel" site:example.com`.
-   **Mencari Server Rentan**: `inurl:http:// site:example.com`, `inurl:wp-login.php`.

### Etika dan Batasan Hukum
-   **Etika**: Google Dorking harus digunakan untuk tujuan edukasi atau evaluasi keamanan dengan izin resmi dari pemilik sistem.
-   **Hukum**: Penggunaan tanpa izin untuk mengakses informasi sensitif dapat dianggap ilegal dan dapat mengakibatkan sanksi pidana.

---

## Summary

Google Dorking adalah teknik OSINT yang memanfaatkan operator pencarian lanjutan Google untuk menemukan informasi tersembunyi atau sensitif pada situs web. Ini adalah alat yang ampuh untuk reconnaissance dalam ethical hacking, membantu mengidentifikasi potensi kerentanan dan data sensitif. Namun, penggunaannya harus selalu mematuhi etika dan batasan hukum, serta dilakukan dengan izin yang jelas dari pemilik sistem untuk menghindari konsekuensi ilegal.