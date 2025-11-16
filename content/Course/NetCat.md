---
id: NetCat
aliases: []
tags:
  - hacking_tools
  - networking
  - recon
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[hacking_tools]], [[networking]], [[recon]]

---

## Cue

- Apa itu Netcat dan apa saja fitur utamanya?
- Bagaimana cara menggunakan Netcat untuk membuat koneksi TCP/UDP?
- Bagaimana cara menggunakan Netcat untuk mendengarkan koneksi masuk?
- Bagaimana cara menggunakan Netcat untuk transfer file?

---

## Notes

### Apa itu Netcat?
Netcat adalah sebuah utilitas jaringan serbaguna yang sering dijuluki "pisau Swiss Army untuk jaringan". Alat ini sangat fleksibel dan dapat digunakan untuk berbagai tugas yang berkaitan dengan jaringan.

### Fitur Utama Netcat
-   **Koneksi TCP/UDP**: Mampu membuat koneksi keluar (client) atau mendengarkan koneksi masuk (server) menggunakan protokol TCP atau UDP.
-   **Transfer Data**: Mengirim atau menerima data melalui koneksi jaringan yang dibuat.
-   **Port Scanning**: Dapat digunakan untuk melakukan pemindaian port sederhana.
-   **Backdoor**: Sering digunakan untuk membuat *backdoor* atau *reverse shell* dalam skenario pengujian penetrasi.

### Contoh Penggunaan Netcat

-   **Membuat Koneksi ke Port Tertentu**:
    -   Untuk membuat koneksi ke port 22 (SSH) pada host target `192.168.1.1`:
        ```bash
        nc 192.168.1.1 22
        ```
-   **Mendengarkan Koneksi Masuk (Listener)**:
    -   Untuk mendengarkan koneksi masuk pada port 80 (HTTP) di mesin lokal:
        ```bash
        nc -l 80
        ```
-   **Mentransfer File**:
    -   **Di sisi pengirim**: Mengirimkan isi file `file.txt` ke host target pada port 1234.
        ```bash
        cat file.txt | nc 192.168.1.1 1234
        ```
    -   **Di sisi penerima**: Menerima file yang dikirim dan menyimpannya sebagai `received_file.txt`.
        ```bash
        nc -l 1234 > received_file.txt
        ```

---

## Summary

Netcat adalah utilitas jaringan serbaguna yang dikenal sebagai "pisau Swiss Army" karena kemampuannya yang luas. Alat ini dapat digunakan untuk membuat koneksi TCP/UDP, mendengarkan port, mentransfer data, dan bahkan melakukan port scanning. Fleksibilitasnya menjadikannya alat fundamental bagi administrator jaringan dan profesional keamanan siber untuk diagnostik, debugging, dan pengujian penetrasi.
