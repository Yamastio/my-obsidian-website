---
id: Instance
aliases: []
tags:
  - php
  - oop
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[php]], [[oop]]

---

## Cue

- Apa itu instance dalam Pemrograman Berorientasi Objek (OOP)?
- Bagaimana hubungan antara instance dan class?
- Bagaimana cara membuat dan menggunakan instance di PHP?
- Apa saja karakteristik utama dari sebuah instance?

---

## Notes

### Apa itu Instance?
- **Instance** adalah representasi konkret atau objek nyata dari sebuah *class*.
- Sebuah *class* hanyalah sebuah cetak biru atau template. Untuk menggunakan fungsionalitas dan data yang didefinisikan dalam *class*, kita perlu membuat objek dari *class* tersebut, yang disebut sebagai **instance**.

### Penjelasan dengan Analogi
Bayangkan sebuah *class* sebagai cetakan kue. Dari satu cetakan kue yang sama, Anda bisa membuat banyak kue. Setiap kue yang dihasilkan adalah **instance** dari cetakan kue tersebut. Setiap kue memiliki bentuk yang sama (sesuai *class*), tetapi bisa memiliki rasa atau hiasan yang berbeda (properti yang berbeda).

### Contoh Kode PHP

```PHP
<?php

// Deklarasi class
class Person {
    public $name;
    public $age;

    public function introduce() {
        return "Hi, my name is {$this->name}, and I am {$this->age} years old.";
    }
}

// Membuat instance (objek) dari class Person
$person1 = new Person(); // Instance pertama
$person1->name = "John";
$person1->age = 30;

$person2 = new Person(); // Instance kedua
$person2->name = "Doe";
$person2->age = 25;

// Mengakses method dari instance
echo $person1->introduce(); // Output: Hi, my name is John, and I am 30 years old.
echo $person2->introduce(); // Output: Hi, my name is Doe, and I am 25 years old.
```

### Poin Penting tentang Instance
1.  **Instance Unik**: Setiap instance memiliki set data (properti) dan keadaannya sendiri yang terpisah dari instance lain, meskipun berasal dari *class* yang sama.
2.  **Kata Kunci `new`**: Digunakan untuk membuat instance baru dari sebuah *class*. Contoh: `new Person()`.
3.  **Alokasi Memori**: Setiap instance dialokasikan di memori secara terpisah, memungkinkan mereka untuk menyimpan nilai properti yang berbeda.

---

## Summary

Instance adalah objek konkret yang dibuat dari sebuah class, yang berfungsi sebagai cetak biru. Setiap instance bersifat unik, memiliki set properti dan keadaannya sendiri, serta dapat menjalankan method yang didefinisikan dalam class-nya. Di PHP, instance dibuat menggunakan kata kunci `new`, memungkinkan penggunaan fungsionalitas class dalam program.