---
id: Steganography
aliases: []
tags:
  - cybersecurity
  - cryptography
  - forensics
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[cybersecurity]], [[cryptography]], [[forensics]]

---

## Cue

- Apa itu steganografi?
- Mengapa steganografi digunakan?
- Apa saja alat yang umum digunakan untuk steganografi?
- Bagaimana cara menggunakan `steghide` untuk menyisipkan dan mengekstrak pesan?

---

## Notes

### Apa itu Steganografi?
**Steganografi** adalah seni dan ilmu menyembunyikan pesan, *file*, atau informasi rahasia di dalam *file* lain yang terlihat normal (disebut *carrier file*). Berbeda dengan kriptografi yang mengenkripsi pesan menjadi tidak terbaca, steganografi menyembunyikan keberadaan pesan itu sendiri. *Carrier file* bisa berupa gambar, audio, atau video.

### Alat untuk Steganografi
Ada berbagai alat yang dapat digunakan untuk melakukan steganografi, baik melalui *command-line* maupun antarmuka grafis.
-   **Steghide**: Alat *command-line* populer di Linux untuk menyembunyikan data di dalam *file* JPEG, BMP, WAV, dan AU.
-   **Stegosuite**: Alternatif dengan antarmuka grafis (GUI) yang lebih mudah digunakan oleh pemula.

### Cara Menggunakan Steghide
`steghide` memungkinkan Anda menyisipkan (*embed*) dan mengekstrak (*extract*) *file* rahasia.

1.  **Menyisipkan Pesan**:
    -   Buat *file* pesan rahasia (misal: `pesan.txt`).
    -   Gunakan perintah `embed` untuk menyisipkannya ke dalam gambar.
        ```bash
        # steghide embed -cf <file_gambar> -ef <file_rahasia>
        steghide embed -cf gambar.jpg -ef pesan.txt
        ```
    -   Anda akan diminta memasukkan kata sandi untuk melindungi data.

2.  **Mengekstrak Pesan**:
    -   Gunakan perintah `extract` pada *file* gambar yang berisi pesan.
        ```bash
        # steghide extract -sf <file_gambar_tersembunyi>
        steghide extract -sf gambar.jpg
        ```
    -   Masukkan kata sandi yang benar, dan *file* rahasia akan diekstrak.

---

## Summary

Steganografi adalah teknik menyembunyikan pesan rahasia di dalam *file* media biasa seperti gambar atau audio, sehingga keberadaan pesan itu sendiri tidak terdeteksi. Tujuannya adalah untuk berkomunikasi secara rahasia tanpa menarik kecurigaan. Alat populer untuk ini adalah `steghide` (*command-line*) dan `Stegosuite` (GUI), yang memungkinkan pengguna untuk menyisipkan dan mengekstrak data tersembunyi dengan proteksi kata sandi.