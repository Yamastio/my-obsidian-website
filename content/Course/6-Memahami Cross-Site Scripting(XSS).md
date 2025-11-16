---
id: 6-Memahami Cross-Site Scripting(XSS)
aliases: []
tags:
  - cybersecurity
  - web_security
  - bughunting
  - jagoansiber
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[web_security]], [[bughunting]], [[jagoansiber]]

---

## Cue

- Apa itu Cross-site Scripting (XSS) dan apa yang bisa dilakukan penyerang dengannya?
- Bagaimana sejarah dan contoh nyata serangan XSS?
- Apa saja tiga jenis utama XSS (Stored, Reflected, DOM-based) dan cara kerjanya?
- Bagaimana melakukan Reconnaissance untuk XSS dan cara menguji potensinya?
- Bagaimana cara mencegah XSS?

---

## Notes

### Pendahuluan Cross-site Scripting (XSS)
- XSS adalah celah keamanan fundamental di mana kode jahat (biasanya JavaScript) disuntikkan ke situs web sah.
- Terjadi ketika aplikasi web tidak "membersihkan" (sanitize) input pengguna dengan benar.
- Hanya dieksekusi di sisi browser pengguna (client-side), tidak merusak server back-end.

### Apa yang Bisa Dilakukan Penyerang dengan XSS?
- Menyamar atau bertindak sebagai pengguna korban.
- Melakukan tindakan apa pun yang bisa dilakukan pengguna korban.
- Membaca data apa pun yang bisa diakses pengguna korban.
- Mencuri kredensial login pengguna (cookie sesi).
- Mengubah tampilan situs web secara virtual (virtual defacement).
- Menyuntikkan fungsi trojan.
- Serangan lain seperti Bitcoin mining atau menampilkan iklan.

### Sejarah dan Contoh Nyata XSS
- Dimulai akhir 1999.
- Samy Worm (2005): Worm berbasis browser memanfaatkan Stored XSS di MySpace, menyebar ke lebih dari satu juta pengguna.
- TweetDeck (2014): Kerentanan XSS menyebabkan tweet me-retweet diri sendiri, memaksa Twitter menutup TweetDeck sementara.

### Tiga Jenis Utama XSS

### 1. Stored (Persistent) XSS
- Jenis XSS paling kritis.
- Input berbahaya dari pengguna disimpan di database back-end.
- Kode jahat diambil dari database dan dieksekusi di browser pengguna lain.
- Bersifat persisten, memengaruhi siapa pun yang mengunjungi halaman.
- Contoh Vektor Serangan: Form input tidak disanitasi (chat, komentar), API, CMS.
- Skenario: Penyerang memasukkan `<script>document.cookie = document.domain;</script>` ke komentar.
- Dampak: Session hijacking, keylogging, manipulasi tampilan halaman.

### 2. Reflected (Non-Persistent) XSS
- Aplikasi menerima data dari permintaan HTTP dan langsung memasukkan ke respons, tanpa menyimpan.
- Tidak persisten. Penyerang harus memancing korban mengklik tautan berbahaya.
- Contoh Vektor Serangan: Parameter URL tidak difilter, form input langsung ke respons, header HTTP.
- Skenario: Penyerang membuat tautan `https://example.com/search.php?q=<script>alert(1)</script>`.
- Dampak: Mirip Stored XSS, penyerang bisa melakukan tindakan, melihat info, mengubah data.

### 3. DOM-based XSS
- Jenis XSS Non-Persistent lainnya, sepenuhnya di sisi browser (client-side).
- JavaScript di halaman memproses input pengguna tidak tepercaya dan memperbarui DOM tidak aman.
- Cara Kerja: Pengguna mengunjungi halaman rentan, penyerang membuat URL jahat, JavaScript membaca input berbahaya dari URL, disuntikkan ke DOM, script dieksekusi.
- Contoh Vektor Serangan: JavaScript memproses input tanpa validasi (document.URL, innerHTML, eval()), event handlers tidak divalidasi.
- Skenario: Penyerang membuat URL `https://example.com/page?name=<script>alert('XSS')</script>`.
- Dampak: Script berbahaya dieksekusi di browser korban.

### Reconnaissance (Pengintaian) untuk XSS
- Mengidentifikasi di mana input pengguna diterima dan bagaimana website memprosesnya.
- Titik Input yang Perlu Diperiksa: Form, kolom pencarian, komentar, parameter URL, Cookies, localStorage, sessionStorage.
- Alat Bantu Penting: Burp Suite, Browser Dev Tools, Google Dorking.
- Cara Menguji Potensi XSS (Test Reflection):
    - Cek apakah input terpantul kembali dan karakter khusus di-encode.
    - Kirim string uji sederhana (contoh: `<script>alert(1)</script>`).
    - Jika popup `alert(1)` muncul, XSS berhasil.

### Mengenai Payload XSS
- `alert(1)` adalah payload dasar.
- Payload lain: `<plaintext>`, `<script>print()</script>`.

### Melewati Filter dan WAF (Web Application Firewall)
- Penyerang bisa melewati filter/WAF menggunakan teknik encoding, event handlers, dan obfuscation.

### Cara Mencegah XSS
- Pertahanan berlapis (defense-in-depth):
    - Memfilter input saat diterima.
    - Meng-encode data saat dikeluarkan (output).
    - Menggunakan header respons yang tepat (Content-Type, X-Content-Type-Options).
    - Mengimplementasikan Content Security Policy (CSP).

## Summary

Memahami Cross-site Scripting (XSS) adalah pengetahuan dasar yang sangat penting bagi setiap pemula dalam ethical hacking. XSS memungkinkan penyerang menyuntikkan kode berbahaya ke browser korban, membuka pintu bagi berbagai serangan mulai dari pencurian kredensial hingga manipulasi tampilan halaman web. Dengan mengetahui tiga jenis XSS (Stored, Reflected, DOM-based), cara mereka bekerja, dan teknik pengintaian (Reconnaissance) untuk mengidentifikasi titik-titik rentan, Anda akan memiliki fondasi yang kuat untuk tidak hanya menemukan, tetapi juga memahami bagaimana melindungi aplikasi web dari serangan XSS dengan menerapkan praktik keamanan yang tepat seperti sanitasi dan encoding input.