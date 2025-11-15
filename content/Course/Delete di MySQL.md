---
id: Delete di MySQL
aliases: []
tags:
  - mysql
  - databases
  - sql
comments: true
draft: false
date: 2025-11-15
---

Related: [[index|Home]], [[mysql]], [[databases]], [[sql]]

## DELETE di SQL

`DELETE` digunakan untuk menghapus baris dari sebuah tabel. Hati-hati karena operasi ini **tidak bisa dibatalkan** kecuali menggunakan transaksi (`BEGIN…ROLLBACK/COMMIT`).

---

### 1. DELETE dengan Kondisi

```sql
DELETE FROM customers
WHERE id = 3;
```

* Menghapus **hanya baris yang memenuhi kondisi** (`id = 3`).
* Selalu gunakan **WHERE** untuk membatasi baris yang dihapus.
* Contoh aman untuk menghapus satu pelanggan tertentu.

---

### 2. DELETE tanpa Kondisi

```sql
DELETE FROM customers;
```

* Menghapus **semua baris** dalam tabel `customers`.
* Sama efeknya dengan **truncate** tapi berbeda secara teknis:

  * `DELETE` dapat memicu trigger dan bisa digabung dengan transaksi.
  * `TRUNCATE` lebih cepat, tetapi tidak bisa di-rollback di sebagian besar RDBMS.

---

### Kesimpulan

* **Selalu pakai `WHERE`** saat ingin menghapus baris spesifik.
* Tanpa `WHERE`, seluruh tabel akan kosong, berisiko kehilangan data.
* Gunakan transaksi (`BEGIN; … COMMIT;`) jika ingin aman saat testing.

---