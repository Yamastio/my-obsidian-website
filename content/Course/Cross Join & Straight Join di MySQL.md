---
id: Cross Join & Strainght Join
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

- Cross Join: konsep, penggunaan, contoh
- Straight Join: konsep, penggunaan, contoh

---

## Notes

### Cross Join

**Konsep**

- Menggabungkan setiap baris tabel pertama dengan setiap baris tabel kedua (cartesian product)
- Jika tabel A = 5 baris dan tabel B = 10 baris → hasil = 50 baris

**Kapan digunakan**

- Untuk membuat semua kombinasi kemungkinan antar dua tabel
- Biasanya dihindari karena hasil bisa sangat besar

**Contoh**

```sql
SELECT * FROM products
CROSS JOIN customers
LIMIT 10;
```

- Menggabungkan semua baris dari products dan customers
- LIMIT digunakan agar output tidak terlalu besar

### Straight Join

**Konsep**

- STRAIGHT_JOIN memaksa MySQL mengikuti urutan tabel sesuai penulisan
- Menonaktifkan optimizer yang biasanya menukar urutan tabel untuk performa
- Contoh: A STRAIGHT_JOIN B → baca A dahulu, cocokkan dengan B

**Kapan digunakan**

- Saat optimizer memilih urutan tabel yang buruk sehingga query lambat
- Untuk tuning performa pada tabel besar
- Tidak digunakan untuk kebutuhan sehari-hari

**Contoh**

```sql
SELECT * FROM customers
STRAIGHT JOIN orders
WHERE orders.customer_id = 1
LIMIT 10;
```

- MySQL membaca customers terlebih dahulu
- Pencocokan dilakukan dengan orders
- Menghasilkan baris yang memenuhi kondisi customer_id = 1

---

## Summary

Cross Join menghasilkan cartesian product dari dua tabel dan digunakan saat perlu semua kombinasi data. Straight Join memaksa MySQL mengikuti urutan tabel untuk tuning performa ketika optimizer kurang optimal.
