---
id: 8-Memahami Kerentanan Otentikasi dan Manajemen Sesi
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

- Apa itu Otentikasi dan bagaimana kerentanannya terjadi (Broken Authentication)?
- Apa dampak dari kerentanan otentikasi?
- Bagaimana serangan Brute-Force bekerja dan proteksi yang cacat?
- Bagaimana kerentanan Otentikasi Multi-Faktor (MFA) dan Otentikasi Bypass melalui Akses Langsung?
- Bagaimana serangan terhadap Token Sesi bekerja?
- Bagaimana cara mencegah kerentanan otentikasi dan manajemen sesi?

---

## Notes

### Apa itu Otentikasi?
- Proses memverifikasi identitas pengguna atau klien.
- Tiga jenis faktor otentikasi:
    - Sesuatu yang Anda ketahui (kata sandi, pertanyaan keamanan).
    - Sesuatu yang Anda miliki (ponsel, token keamanan).
    - Sesuatu yang Anda lakukan atau Anda sendiri (biometrik, pola perilaku).
- Otentikasi berbeda dengan otorisasi (menentukan apa yang boleh dilakukan setelah masuk).

### Bagaimana Kerentanan Otentikasi Terjadi (Broken Authentication)?
- Mekanisme otentikasi yang lemah (tidak cukup melindungi dari brute-force).
- Cacat logika atau coding yang buruk (memungkinkan otentikasi dilewati).
- Disebut "broken authentication".

### Dampak Kerentanan Otentikasi
- Penyerang mendapatkan akses ke semua data dan fungsionalitas akun yang disusupi.
- Akses akun hak istimewa tinggi (administrator) bisa mengambil kendali penuh aplikasi.
- Akun hak istimewa rendah bisa akses data sensitif atau halaman tersembunyi.

### Serangan Brute-Force
- Penyerang menggunakan metode coba-coba untuk menebak kredensial valid, otomatis dengan wordlist.
- Menebak Nama Pengguna (Usernames): Mudah ditebak jika pola tertentu, atau menggunakan nama umum (admin).
    - Situs web bisa mengungkapkan nama pengguna melalui profil publik atau respons HTTP.
    - Enumerasi pengguna dengan melihat pesan kesalahan.
    - SecLists adalah wordlist yang baik.
- Menebak Kata Sandi (Passwords): Sulitnya tergantung kekuatan kata sandi.
    - Gunakan alat seperti ffuf dengan wordlist (rockyou.txt).
- Menyaring Hasil: Perhatikan perbedaan Kode Status HTTP, Pesan Kesalahan, atau Waktu Respons.

### Proteksi Brute-Force yang Cacat
- Mengunci akun atau memblokir IP bisa memiliki cacat logika.
- Penghitung percobaan gagal bisa diulang jika pemilik IP berhasil login.
- Penyerang bisa memasukkan kredensial akun sendiri secara berkala dalam wordlist.

### Menguji Kredensial Default
- Banyak platform memiliki kredensial default yang bisa dicari di database seperti CIRT.net.

### Kerentanan Otentikasi Multi-Faktor (MFA)
- MFA mengharuskan pengguna membuktikan identitas dengan beberapa faktor.
- Token Otentikasi Dua Faktor: Kode verifikasi SMS rentan disusupi atau SIM swapping.
- Melewati Otentikasi Dua Faktor: Penyerang bisa mencoba langsung mengakses halaman yang hanya bisa diakses setelah login.

### Otentikasi Bypass melalui Akses Langsung
- Aplikasi web mungkin mengirimkan konten halaman admin yang dilindungi dalam body respons, meskipun browser diarahkan ke halaman login.
- Penyerang bisa mengintersep respons dan mengubah kode status dari 302 Redirect menjadi 200 OK.
- Pencegahan: Script PHP perlu keluar setelah mengeluarkan redirect.

### Menyerang Token Sesi
- Token sesi penting untuk menjaga status pengguna.
- Serangan Brute-Force pada Token Sesi yang Dapat Diprediksi: Jika pola token dapat diprediksi.
- Token Sesi yang Lemah: Token hanya menggunakan pengkodean (Base64, Hex) mudah didekode.
    - Praktik terbaik: Token terenkripsi secara acak dengan secret-key kuat.
- Fiksasi Sesi (Session Fixation): Penyerang mendapatkan token sesi valid, menipu korban untuk menggunakan token ini saat login.
- Batas Waktu Sesi yang Tidak Tepat (Improper Session Timeout): Token sesi valid selamanya, memungkinkan penyerang menggunakan sesi yang dibajak tanpa batas waktu.

### Pencegahan (Mitigasi)
1. Jangan pernah mengirim data login melalui koneksi tidak terenkripsi (selalu gunakan HTTPS).
2. Terapkan pemeriksa kata sandi (password checker) yang kuat.
3. Implementasikan proteksi brute-force yang kuat (pembatasan tingkat permintaan, CAPTCHA).
4. Atur batas waktu untuk sesi dan kode OTP.
5. Wajibkan pengguna untuk menggunakan MFA berbasis fisik atau aplikasi.

## Summary

Kerentanan otentikasi dan manajemen sesi, sering disebut "Broken Authentication," adalah salah satu masalah keamanan paling kritis dalam aplikasi web. Memahami cara penyerang mengeksploitasi kelemahan dalam proses login, token sesi, dan mekanisme Multi-Factor Authentication (MFA) sangat penting. Dengan menerapkan praktik keamanan yang kuat, seperti penggunaan koneksi terenkripsi, kebijakan kata sandi yang kuat, perlindungan brute-force yang efektif, dan manajemen sesi yang tepat termasuk penetapan batas waktu sesi, pengembang dan administrator dapat secara signifikan mengurangi risiko bagi pengguna dan data sensitif.