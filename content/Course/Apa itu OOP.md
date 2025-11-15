---
id: Apa itu OOP
aliases: []
tags:
  - php
  - oop
comments: true
description: Ringkasan konsep dasar mengenai LAN.
draft: false
title: Apa itu OOP
---

Related: [[index|Home]], [[php]], [[oop]]

## Apa itu OOP?

**Object Oriented Programming (OOP)** adalah paradigma pemrograman yang berfokus pada penggunaan objek, yaitu struktur data yang menggabungkan **data** (properties/attributes) dan **fungsi** (methods) ke dalam satu kesatuan.

## Ciri-ciri OOP

- Data dan fungsinya diikat menjadi satu entitas, disebut **objek**.
- Menyediakan konsep seperti **inheritance**, **encapsulation**, **polymorphism**, dan **abstraction**.
- Membuat kode lebih modular dan mudah untuk dikelola.

---

## Kapan Butuh OOP?

1. **Development aplikasi kompleks**
   - Misalnya: aplikasi enterprise, sistem berbasis web, aplikasi desktop yang besar.
2. **Aplikasi yang membutuhkan database**
   - Misalnya: e-commerce, manajemen data, atau aplikasi berbasis CRUD.
3. **Kolaborasi tim**
   - OOP membantu membagi tanggung jawab antar tim melalui modularisasi kode.
4. **Proyek skala besar dan jangka panjang**
   - Membutuhkan pemeliharaan dan pengembangan yang berkelanjutan.

> **Catatan:**

- OOP tidak cocok untuk proyek sederhana karena dapat menambah kompleksitas yang tidak perlu.

---

## Konsep Dasar dalam OOP

### Object

- **Definisi**: Entitas yang mewakili dunia nyata dalam kode, berisi **properties** dan **methods**.
- Contoh:
  - Objek **Siswa** memiliki property `nama` dan `kelas`, serta method `belajar()`.
  - Objek **Shopping Cart** memiliki property `items` dan method `add_to_cart()`.

---

### Properties

- Data atau atribut yang dimiliki oleh sebuah objek.
- Contoh:
  - **Meja** memiliki:
    - `tinggi = 1 meter`
    - `lebar = 2 meter`
  - **Siswa** memiliki:
    - `nama = "Ali"`
    - `kelas = "XII"`

### Methods

- Fungsi yang dapat dilakukan oleh sebuah objek, sering kali melibatkan properties objek tersebut.
- Contoh:
  - **Shopping Cart** memiliki method:
    - `add_to_cart(item)`
    - `calculate_total()`
  - **Siswa** memiliki method:
    - `belajar(materi)`
    - `ujian(nilai)`

---

## Manfaat OOP

1. **Kode terstruktur**
   - Membagi kode ke dalam objek-objek yang jelas, mempermudah pengelolaan dan pemahaman.

2. **Visualisasi kode yang rapi**
   - Logika aplikasi lebih mudah diorganisir dengan relasi antar objek.

3. **Simplicity**
   - Membuat kode lebih sederhana melalui abstraksi.

4. **Reusability (Kode Modular dan Reusable)**
   - Fungsi atau class yang telah dibuat dapat digunakan kembali di proyek lain.

5. **Easier Maintenance**
   - Memudahkan pemeliharaan karena fokus hanya pada objek tertentu ketika ada bug atau fitur baru.

---

## Fitur OOP dalam PHP

- **Sejak PHP 5.0**, PHP mendukung fitur OOP seperti:
  - **Class**: Template untuk membuat objek.
  - **Object**: Instansiasi dari sebuah class.
  - **Constructor**: Method khusus untuk inisialisasi properti objek.
  - **Encapsulation**: Pengaturan akses data (private, public, protected).
  - **Inheritance**: Pewarisan properti dan metode dari class induk.
  - **Polymorphism**: Kemampuan method untuk berperilaku berbeda berdasarkan context.
  - **Abstract Class & Interface**: Membuat kerangka dasar class.
