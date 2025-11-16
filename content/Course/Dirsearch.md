---
id: Dirsearch
aliases: []
tags:
  - hacking_tools
  - pentesting
  - web_security
  - python
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[pentesting]], [[web_security]], [[python]]

---

## Cue

- Apa itu Dirsearch dan apa fungsinya?
- Apa saja fitur-fitur utama yang dimiliki Dirsearch?
- Bagaimana cara menginstal Dirsearch?
- Apa saja contoh perintah umum untuk menggunakan Dirsearch?
- Apa praktik terbaik (best practices) saat menggunakan Dirsearch?

---

## Notes

### Apa itu Dirsearch?
- **Dirsearch** adalah alat pentest berbasis **Python** yang digunakan untuk melakukan **brute force** pada direktori atau file tersembunyi di sebuah aplikasi web.
- Tujuannya adalah untuk mengidentifikasi sumber daya yang tidak terdokumentasi yang dapat menjadi celah keamanan.

### Fitur Utama
- **Pencarian Tersembunyi**: Mendeteksi file atau folder yang tidak terlihat secara publik.
- **Filter Ekstensi**: Membatasi pencarian pada jenis file tertentu (misal: `.php`, `.zip`, `.sql`).
- **Dukungan Protokol**: Kompatibel dengan **HTTP**, **HTTPS**, dan dapat digunakan melalui proxy.
- **Custom Headers**: Mendukung pengaturan header kustom dan autentikasi dasar.
- **Parallel Scanning**: Menggunakan **multithreading** untuk mempercepat proses pemindaian.

### Cara Instalasi
1.  **Clone Repository**:
    ```bash
    git clone https://github.com/maurosoria/dirsearch.git
    cd dirsearch
    ```
2.  **Install Dependensi**:
    ```bash
    pip install -r requirements.txt
    ```
3.  **Verifikasi Instalasi**:
    ```bash
    python3 dirsearch.py --help
    ```

### Contoh Penggunaan
- **Scan Dasar**: Mencari ekstensi file tertentu pada sebuah URL.
  ```bash
  python3 dirsearch.py -u http://testphp.vulnweb.com/ -e php,sql,rar,zip
  ```
- **Menggunakan Wordlist Khusus**: Menentukan wordlist sendiri untuk pencarian.
  ```bash
  python3 dirsearch.py -u http://example.com -w /path/to/wordlist.txt
  ```
- **Menggunakan Proxy**: Mengarahkan traffic melalui proxy seperti Burp Suite.
  ```bash
  python3 dirsearch.py -u http://example.com --proxy 127.0.0.1:8080
  ```
- **Mengatur Thread**: Menyesuaikan jumlah thread untuk performa.
  ```bash
  python3 dirsearch.py -u http://example.com -t 10
  ```

### Best Practices
- **Gunakan Wordlist Relevan**: Pilih wordlist yang sesuai dengan teknologi target (misalnya, WordPress, PHP).
- **Gunakan dengan Izin**: Jangan menggunakan alat ini pada sistem tanpa izin eksplisit.
- **Simpan Hasil**: Simpan output ke file untuk analisis lebih lanjut.
  ```bash
  python3 dirsearch.py -u http://example.com -o result.txt
  ```

---

## Summary

Dirsearch adalah alat brute force direktori dan file berbasis Python yang esensial untuk pengujian keamanan web. Alat ini membantu menemukan sumber daya tersembunyi dengan fitur seperti multithreading, filter ekstensi, dan dukungan proxy. Penggunaannya yang efektif memerlukan pemilihan wordlist yang tepat dan harus selalu dilakukan dengan izin dari pemilik sistem.