---
id: Memahami Broken Authentication & Broken Access Control
aliases: []
tags:
  - web_security
  - owasp
  - authentication
  - authorization
comments: true
date: 2024-12-05
draft: false
---

---

Related: [[index|Home]], [[web_security]], [[owasp]], [[authentication]], [[authorization]]

---

## Cue

- Apa itu Broken Access Control?
- Apa saja penyebab umum dan risiko dari Broken Access Control?
- Apa saja tipe serangan Broken Access Control?
- Apa itu Broken Authentication?
- Apa saja penyebab umum dan risiko dari Broken Authentication?
- Apa saja tipe serangan Broken Authentication?
- Bagaimana langkah mitigasi untuk Broken Access Control dan Broken Authentication?
- Bagaimana demo serangan Broken Authentication dan Broken Access Control menggunakan Burp Suite?

---

## Notes

### Broken Access Control

-   **Definisi**: Situasi di mana sistem kontrol akses tidak dikelola dengan baik, memungkinkan penyerang mengakses data atau fitur yang seharusnya terbatas.
-   **Penyebab Umum**:
    -   Kurangnya validasi akses berdasarkan peran pengguna.
    -   Parameter input yang dapat dimodifikasi untuk mendapatkan akses.
    -   Hak akses *default* yang tidak diamankan.
    -   Kesalahan konfigurasi akses kontrol.
-   **Risiko**:
    -   Pencurian data sensitif.
    -   Penyalahgunaan fitur aplikasi oleh penyerang.
    -   Eskalasi hak akses yang tidak sah.

#### Ilustrasi Broken Access Control

-   Aplikasi web tidak memiliki mekanisme validasi yang kuat terhadap akses fitur.
-   Penyerang dapat memanfaatkan celah ini untuk mengakses data/fitur yang seharusnya dibatasi.
-   **Skema**: Pengguna tanpa hak akses memanipulasi URL atau parameter untuk mengakses fitur terlarang; sistem gagal memvalidasi dan memberikan akses.

#### Tipe Serangan Broken Access Control

1.  **Bypassing Access Control**: Penyerang mengakses fitur/data dengan memodifikasi parameter input atau *endpoint*. Contoh: Mengubah ID pengguna di URL.
2.  **Forceful Browsing**: Penyerang mencoba mengakses URL tersembunyi atau fitur yang seharusnya tidak terlihat. Contoh: Mengakses `/admin/dashboard` tanpa autentikasi.
3.  **Privilege Escalation**: Penyerang meningkatkan hak akses (misal: dari pengguna biasa menjadi administrator) melalui eksploitasi celah. Contoh: Manipulasi *header* API.
4.  **Default Account**: Penyerang menggunakan akun *default* dengan kredensial bawaan.

### Broken Authentication

-   **Definisi**: Kondisi di mana mekanisme autentikasi tidak diimplementasikan dengan benar, memungkinkan penyerang mengambil alih akun pengguna yang sah.
-   **Penyebab Umum**:
    -   Kebijakan kata sandi yang lemah.
    -   Penyimpanan kredensial yang tidak aman.
    -   Tidak adanya pembatasan pada upaya *login* yang gagal.
    -   Penanganan *token* sesi yang tidak aman.
-   **Risiko**:
    -   Pencurian akun pengguna.
    -   Penyalahgunaan data atau fitur aplikasi.
    -   Kehilangan kepercayaan dari pengguna.

#### Ilustrasi Broken Authentication

-   Penyerang memanfaatkan celah pada mekanisme *reset password*.
-   Penyerang mengirimkan tautan *phishing* atau memodifikasi *header* permintaan untuk mencuri *token reset* pengguna.
-   **Skema Serangan**: Korban membuka tautan *phishing*, penyerang memodifikasi *header host* untuk mendapatkan *token reset*, lalu menggunakan *token* tersebut untuk mengambil alih akun.

#### Tipe Serangan Broken Authentication

1.  **Password Cracking**: Penyerang menggunakan *brute force* untuk menebak *username* dan *password*.
2.  **Session Hijacking**: Penyerang mencuri *token* sesi pengguna untuk mengakses akun tanpa *login*.
3.  **Social Engineering**: Penyerang mengelabui korban untuk memberikan informasi sensitif (misal: *phishing*).
4.  **Insecure Communication**: Penyerang menyadap komunikasi pengguna melalui serangan *Man-in-the-Middle* (MITM) pada data tidak terenkripsi.
5.  **Default Credentials**: Penyerang memanfaatkan kredensial bawaan yang tidak diubah.

### Langkah Mitigasi

#### Untuk Broken Access Control

1.  **Validasi Akses Secara Ketat**: Pastikan setiap permintaan API atau fitur divalidasi berdasarkan peran pengguna.
2.  **Minimalkan Privilege**: Terapkan prinsip *least privilege* untuk setiap pengguna.
3.  **Audit dan Monitoring**: Lakukan audit rutin terhadap kontrol akses dan *log* aktivitas pengguna.
4.  **Hapus Akun Default**: Nonaktifkan atau hapus akun *default* setelah instalasi.

#### Untuk Broken Authentication

1.  **Perkuat Kebijakan Kata Sandi**: Gunakan panjang minimal 12 karakter dengan kombinasi huruf, angka, dan simbol.
2.  **Amankan Token Sesi**: Gunakan *cookie* dengan atribut `Secure` dan `HttpOnly`.
3.  **Batasi Upaya Login Gagal**: Terapkan mekanisme pembatasan seperti CAPTCHA atau pemblokiran sementara.
4.  **Gunakan Protokol HTTPS**: Pastikan semua komunikasi menggunakan protokol SSL/TLS.
5.  **Otentikasi Multi-Faktor (MFA)**: Implementasikan MFA untuk meningkatkan keamanan autentikasi.

### Demo Serangan (Menggunakan DVWA dan OWASP Juice Shop dengan Burp Suite)

-   **Konfigurasi Burp Suite**:
    -   Unduh dan instal Burp Suite Community Edition.
    -   Konfigurasikan dengan *browser* (misal: menggunakan ekstensi FoxyProxy).
    -   Unduh dan *import* sertifikat `cacert.der` dari `http://burpsuite` ke *browser*.
-   **Broken Access Control (DVWA)**:
    1.  Akses DVWA, buka dua *tab* (satu *private*, satu biasa).
    2.  *Login* sebagai *admin* di satu *tab*, dan sebagai pengguna biasa (misal: Smithy) di *tab* lain.
    3.  Perhatikan menu yang hanya tersedia untuk *admin*.
    4.  Meskipun menu "Authorization Bypass" tidak terlihat oleh Smithy, jika Smithy mengetahui alamatnya (`http://127.0.0.1:4280/vulnerabilities/authbypass/`), ia tetap bisa mengaksesnya.
    5.  Bahkan, Smithy bisa mengubah data, menunjukkan *bug* pada autentikasi.
-   **Broken Access Control (OWASP Juice Shop)**:
    1.  Pergi ke `https://demo.owasp-juice.shop/#/`.
    2.  *Login* dengan akun baru (misal: `sured@gmail.com`, *password* `test123`).
    3.  Tambahkan barang ke keranjang (*basket*).
    4.  Lihat *request* di Burp Suite, cari ID keranjang.
    5.  Nyalakan *intercept*, klik keranjang, kirim *request* ke *repeater*.
    6.  Ubah ID keranjang (misal ke 5), periksa *response* untuk melihat apakah data keranjang pengguna lain bisa diakses.
-   **Melakukan Bypass Login (SQL Injection)**:
    1.  *Logout*, coba *login* dengan *username* `'or 1=1 --` dan *password* apa saja.
    2.  Ini akan berhasil *login* sebagai *admin/root* karena kerentanan SQL Injection.
-   **Default Credential (DVWA)**:
    1.  *Login* ke DVWA sebagai *root* dengan *username* dan *password default*.
-   **Password Policy Tidak Diatur dengan Baik (Juice Shop)**:
    -   Validasi *password* hanya di sisi *frontend*, tidak ada validasi kuat di *backend*.
-   **Bruteforce (DVWA)**:
    1.  Pergi ke menu *bruteforce* di DVWA.
    2.  Coba *username* `admin` dan *password* `admin`.
    3.  DVWA memungkinkan percobaan *login* berkali-kali tanpa pemblokiran.
    4.  Gunakan Burp Suite Intruder:
        -   Cari *request login* di *HTTP history*, kirim ke *Intruder*.
        -   Tandai *password* sebagai *payload position*.
        -   Pilih *Attack type*: *Sniper*.
        -   Tambahkan *wordlist* sederhana (misal: `admin`, `password`, `root`, `admin123`, `smithy`).
        -   Mulai serangan.
        -   Cek *status code* (semua 200) dan *length* *response*. Cari *length* yang paling berbeda.
        -   Lihat *response* yang berbeda di *render tab* untuk menemukan *password* yang benar (misal: `smithy`).

---

## Summary

Broken Authentication dan Broken Access Control adalah dua kerentanan keamanan web kritis yang sering dieksploitasi. Broken Access Control terjadi ketika pengguna dapat mengakses sumber daya yang tidak sah karena validasi akses yang lemah, sementara Broken Authentication memungkinkan penyerang mengambil alih akun akibat implementasi autentikasi yang cacat. Keduanya dapat menyebabkan pencurian data, penyalahgunaan fitur, dan eskalasi hak akses. Mitigasi melibatkan validasi akses ketat, prinsip *least privilege*, kebijakan kata sandi kuat, penggunaan HTTPS, dan MFA. Demonstrasi serangan menggunakan alat seperti Burp Suite menunjukkan bagaimana kerentanan ini dapat dieksploitasi melalui manipulasi URL, *SQL injection*, atau *brute force*.
