---
id: Delete di MySQL
aliases: []
tags:
  - mysql
  - databases
  - sql
comments: true
date: 2025-11-15
draft: false
---

---

Related: [[index|Home]], [[mysql]], [[databases]], [[sql]]

---

## Cue

- Penggunaan delete di sql
- Delete dengan kondisi
- Delete tanpa kondisi
- Perbedaan delete dan truncate
- Praktik aman saat menghapus data

---

## Notes

### Delete dengan Kondisi

- Menghapus baris yang memenuhi syarat tertentu.
- Penggunaan where sangat penting agar hanya baris yang dituju yang terhapus.
- Contoh: menghapus pelanggan dengan id tertentu.

### Delete tanpa Kondisi

- Menghapus seluruh baris dalam tabel.
- Memiliki efek yang sama seperti truncate namun berbeda secara teknis.
- Delete dapat memicu trigger dan mendukung transaksi.
- Truncate lebih cepat tetapi umumnya tidak dapat di rollback.

### Praktik Aman

- Selalu gunakan where saat menghapus baris spesifik.
- Hindari delete tanpa where jika tidak benar benar diperlukan.
- Gunakan transaksi untuk mengurangi risiko kehilangan data saat proses uji coba.

---

## Summary

Delete digunakan untuk menghapus baris dari tabel dan harus digunakan dengan hati hati. Perintah dengan where hanya menghapus baris tertentu, sedangkan tanpa where akan mengosongkan tabel. Penggunaan transaksi sangat dianjurkan untuk mencegah kehilangan data yang tidak diinginkan.
