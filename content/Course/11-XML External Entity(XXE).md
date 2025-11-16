---
id: 11-XML External Entity(XXE)
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

- Apa itu XXE dan bagaimana kerentanannya terjadi?
- Tipe serangan XXE dan dampaknya?
- Bagaimana cara mencegah kerentanan XXE?

---

## Notes

### Pendahuluan XXE
- Materi ini fokus pada XML External Entity (XXE), risiko keamanan web teratas menurut OWASP.
- Tujuan: Memahami XXE, eksploitasi, dan pencegahannya.

### Apa itu XML dan XXE?
- XML (Extensible Markup Language):
    - Bahasa markup untuk menyimpan dan mentransfer data.
    - Dokumen XML terdiri dari elemen yang membentuk struktur pohon.
- XML Document Type Definition (DTD):
    - Memvalidasi struktur dokumen XML.
    - Bisa didefinisikan di dalam dokumen atau file eksternal.
- XML Entities:
    - "Variabel" dalam XML.
    - External XML Entities: Nilai diambil dari sumber eksternal (file sistem, URL).

### Bagaimana Kerentanan XXE Terjadi?
- XXE Injection terjadi ketika data XML dari pengguna tidak dibersihkan atau diproses dengan aman.
- Memungkinkan penyerang menggunakan fitur XML (External Entities) untuk tindakan berbahaya.

### Tipe Serangan XXE dan Dampaknya

### 1. Local File Disclosure (Membaca File Lokal)
- Penyerang mendefinisikan entitas eksternal yang merujuk ke file lokal di server.
- Ketika entitas direferensikan, isinya terlihat (contoh: `/etc/passwd`).

### 2. Membaca Kode Sumber Aplikasi (Source Code Disclosure)
- Digunakan untuk mendapatkan kode sumber aplikasi web.
- Berguna untuk menemukan kerentanan lain atau informasi rahasia.
- Solusi untuk karakter khusus: Menggunakan PHP `php://filter` wrapper untuk mengodekan isi file ke Base64.

### 3. Remote Code Execution (RCE) - Menjalankan Perintah Jarak Jauh
- Potensi untuk mengeksekusi perintah di server jarak jauh.
- Metode: Mencari kunci SSH, mencuri hash di Windows, `PHP://expect` (jika modul `expect` terinstal).
- Paling efisien: Mengunggah "webshell" ke server korban.

### 4. Denial of Service (DoS) - Serangan Penolakan Layanan
- Membuat server tidak responsif/mati dengan entitas yang memanggil diri sendiri berulang (entity self-reference loops).
- Menyebabkan memori server habis.
- Server modern (Apache) sudah memiliki perlindungan.

### 5. Ekstraksi Data Lanjutan dengan CDATA
- Untuk mengekstrak data non-XML (biner/karakter khusus), bungkus dengan tag CDATA.
- Parser XML memperlakukan konten sebagai data mentah.
- Untuk menggabungkan entitas internal/eksternal: Gunakan XML Parameter Entities (`%`) yang direferensikan dari sumber eksternal.

### 6. Out-of-band (OOB) Data Exfiltration - Ekstraksi Data "Blind"
- Digunakan saat serangan XXE "buta" (tidak ada output langsung).
- Aplikasi web mengirimkan permintaan ke server penyerang berisi konten file yang dibaca.
- Data file di-Base64-kan dan disertakan dalam URL permintaan HTTP.
- Dapat diotomatisasi dengan alat seperti XXEinjector.

### Pencegahan XXE
- Menghindari Komponen Lama: Perbarui pustaka XML dan komponen pemroses input XML (API SOAP) ke versi terbaru.
- Menggunakan Konfigurasi XML yang Aman:
    - Mematikan referensi Custom Document Type Definitions (DTDs).
    - Mematikan referensi External XML Entities.
    - Mematikan pemrosesan Parameter Entity.
    - Mematikan dukungan untuk XInclude.
    - Mencegah Entity Reference Loops.

## Summary

XXE adalah kerentanan serius yang dapat menyebabkan berbagai kerusakan, mulai dari pengungkapan file sensitif dan kode sumber hingga eksekusi kode jarak jauh dan serangan Denial of Service. Memahami cara kerja XML, DTD, dan entitas eksternal adalah kunci untuk mengidentifikasi dan mengeksploitasi kerentanan ini. Namun, yang terpenting adalah menerapkan praktik keamanan yang ketat, seperti selalu memperbarui pustaka dan mengkonfigurasi parser XML agar menonaktifkan fitur-fitur berbahaya yang memungkinkan referensi entitas eksternal. Bagi pengembang dan profesional keamanan, pencegahan XXE merupakan langkah krusial dalam membangun aplikasi web yang aman.