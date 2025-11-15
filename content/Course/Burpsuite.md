---
id: Burpsuite
aliases: []
tags:
  - cybersecurity
  - web_security
comments: true
draft: false
---

Related: [[index|Home]], [[cybersecurity]], [[web_security]]

## Burp Suite 

Bayangkan kamu ingin melihat, mengubah, dan mempelajari semua percakapan antara **browser** dan **server web**. Biasanya percakapan itu berjalan cepat dan tersembunyi. Burp Suite adalah **alat yang duduk di tengah**—seperti operator telepon—yang bisa membaca, menahan, bahkan memodifikasi pesan yang dikirimkan.

Itulah inti Burp Suite: **proxy intercepting**. Kamu memaksakan browser untuk berbicara lewat Burp dulu, baru ke server. Maka setiap request dan response lewat tanganmu.

---

## Cara Kerja Burp (Gambaran Intuitif)

1. Browser → (Proxy: Burp) → Server
2. Burp menangkap pesan → kamu bisa membaca atau mengedit
3. Burp meneruskan ke server → server membalas → Burp memberi ke browser

Dengan cara ini, kamu bisa melihat seluruh “isi perut” aplikasi web.

---

## Instalasi & Konfigurasi (Inti)

* Unduh Burp → instal Community Edition.
* Atur Firefox agar memakai proxy `127.0.0.1:8080`.
* Burp juga harus membuka port yang sama sebagai listener.
* Instal sertifikat CA Burp agar HTTPS tidak error.

Setelah itu, semua traffic browser mengalir melalui Burp.

---

## Fitur-Fitur Burp (Penjelasan Sederhana)

### 1. Proxy

- “Terminal penyadap.”
- Tempat semua permintaan lewat dan bisa kamu ubah sebelum dikirim.

### 2. Repeater

- Laboratorium eksperimen.
- Ambil satu request lalu kirim ulang berkali-kali sambil mengubah parameternya.
- Dipakai untuk eksploitasi manual (SQLi, auth bypass, parameter tampering).

### 3. Intruder

- “Mesin otomatis penyerang.”
- Melakukan brute force, fuzzing, testing rate-limit — semua secara massal.

### 4. Target

- Peta aplikasi.
- Kamu dapat melihat halaman apa saja yang ada dan request apa yang pernah dikirim.

### 5. Logger

- Catatan lengkap setiap traffic — berguna untuk analisis ulang.

### 6. Extensions (BApp Store)

- Tambahan fitur untuk decode, scan, automasi, dan analisis lanjutan.

---

## Kapan Burp Dipakai dalam Pentesting?

* Mengubah request sebelum terkirim
* Mengetes input user (SQLi, XSS, path traversal)
* Brute force login, API key, OTP
* Menemukan endpoint tersembunyi
* Menguji mekanisme autentikasi dan session

Burp membuat **trafik web yang tadinya tidak terlihat menjadi sangat transparan**.

---

## Inti Pemahaman

Burp Suite itu bukan sekadar alat; ia adalah **gerbang kontrol penuh** atas komunikasi web aplikasi.
Dengan mengarahkan traffic browser ke Burp, kamu dapat:

* melihat semuanya,
* mengubah semuanya,
* menguji semuanya,

sebelum aplikasi tahu apa yang sedang terjadi.