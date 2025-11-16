---
id: XSS
aliases: []
tags:
  - web_security
  - owasp
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[web_security]], [[owasp]] 

---

## Cue

- Apa itu XSS (Cross-Site Scripting)?
- Bagaimana urutan serangan XSS terjadi?
- Apa saja jenis-jenis utama dari serangan XSS?
- Bagaimana cara mempraktikkan identifikasi kerentanan XSS menggunakan DVWA?

---

## Notes

### Apa itu XSS?
**XSS (Cross-Site Scripting)** adalah kerentanan keamanan web di mana penyerang menyisipkan skrip berbahaya (biasanya JavaScript) ke dalam halaman web yang dilihat oleh pengguna lain. Tujuannya adalah untuk mencuri data sensitif seperti *cookie* atau sesi *login*, yang dapat digunakan untuk mengambil alih akun korban.

### Urutan Serangan XSS
1.  **Penyisipan Skrip**: Penyerang menemukan *input* pada situs yang rentan dan menyisipkan skrip berbahaya.
2.  **Eksekusi oleh Korban**: Korban mengakses halaman yang telah disusupi, menyebabkan *browser* mereka menjalankan skrip berbahaya tersebut.
3.  **Pencurian Data**: Skrip tersebut kemudian mencuri data sensitif dari *browser* korban.
4.  **Penyalahgunaan**: Penyerang menggunakan data yang dicuri untuk tujuan jahat, seperti membajak sesi pengguna.

### Jenis-Jenis XSS
-   **Reflected XSS**: Skrip berbahaya disisipkan sebagai bagian dari URL atau permintaan HTTP. Skrip ini "dipantulkan" kembali oleh *server* ke *browser* korban dan dieksekusi. Serangan ini memerlukan korban untuk mengklik tautan yang telah dimanipulasi.
-   **Stored XSS**: Skrip berbahaya disimpan secara permanen di *server* target, misalnya dalam *database* melalui kolom komentar atau postingan forum. Setiap pengguna yang melihat halaman yang terinfeksi akan menjalankan skrip tersebut, membuatnya lebih berbahaya karena dampaknya yang luas.

### Demo XSS di DVWA
DVWA (Damn Vulnerable Web Application) adalah *platform* untuk melatih kemampuan keamanan siber.
-   **Instalasi**: DVWA dapat dengan mudah dijalankan menggunakan Docker.
-   **Tes Reflected XSS**: Masukkan `<script>alert(1)</script>` pada *form input* di halaman XSS (Reflected). Jika muncul *pop-up*, halaman tersebut rentan.
-   **Tes Stored XSS**: Masukkan skrip yang sama pada *form* di halaman XSS (Stored). Skrip akan tersimpan dan dieksekusi setiap kali halaman tersebut dimuat.

---

## Summary

Cross-Site Scripting (XSS) adalah serangan injeksi skrip di sisi klien yang bertujuan untuk mencuri data sensitif pengguna. Serangan ini terjadi dalam dua bentuk utama: Reflected XSS, di mana skrip dipantulkan melalui URL, dan Stored XSS, di mana skrip disimpan di *server* dan dieksekusi oleh setiap pengunjung halaman. Alat seperti DVWA sangat berguna untuk mempraktikkan cara menemukan dan memahami kerentanan XSS dalam lingkungan yang aman.
