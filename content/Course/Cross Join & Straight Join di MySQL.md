---
id: Cross Join & Strainght Join
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

## Cross Join

### Konsep

Cross Join akan menggabungkan **setiap baris** dari tabel pertama dengan **setiap baris** dari tabel kedua (cartesian product).
Jika tabel A berisi 5 baris dan tabel B berisi 10 baris, hasilnya 5 × 10 = **50 baris**.

### Kapan digunakan

* Untuk membuat kombinasi semua kemungkinan antara dua tabel.
* Biasanya dihindari kecuali memang diperlukan, karena hasilnya bisa sangat besar.

### Contoh

```sql
SELECT * FROM products
CROSS JOIN customers
LIMIT 10;
```

Penjelasan:

* Menggabungkan semua baris dari `products` dengan semua baris dari `customers`.
* `LIMIT 10` digunakan agar output tidak terlalu besar.

---

## Straight Join

### Konsep

`STRAIGHT_JOIN` adalah jenis join yang memaksa MySQL menggunakan **urutan tabel** sebagaimana kamu menulisnya.
Normalnya MySQL optimizer bisa menukar urutan tabel untuk mencari eksekusi paling cepat, tapi `STRAIGHT_JOIN` mematikan optimasi itu.

Jadi:

```
A STRAIGHT_JOIN B
```

berarti MySQL harus membaca A dulu, lalu mencocokkan dengan B sesuai kondisi join.

### Kapan digunakan

* Saat query optimizer MySQL memilih urutan tabel yang buruk sehingga query menjadi lambat.
* Untuk tuning performa pada tabel besar.
* **Bukan** untuk penggunaan sehari-hari.

### Contoh

```sql
SELECT * FROM customers
STRAIGHT JOIN orders
WHERE orders.customer_id = 1
LIMIT 10;
```

Penjelasan:

* MySQL akan membaca tabel `customers` terlebih dahulu, kemudian mencocokkan dengan tabel `orders`.
* Kondisi join didefinisikan di bagian `WHERE`.
* Hasilnya adalah baris dari kedua tabel yang memenuhi `orders.customer_id = 1`.

---