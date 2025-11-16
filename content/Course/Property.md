---
id: Property
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

- Apa itu property dalam konteks PHP OOP?
- Bagaimana cara mendefinisikan dan mengakses property dalam sebuah class PHP?
- Bagaimana cara menginisialisasi property dengan nilai default?
- Apa saja tips penting saat bekerja dengan property di PHP?

---

## Notes

### Definisi Property
- **Property** (juga dikenal sebagai atribut, variabel kelas, atau variabel instance) adalah variabel yang didefinisikan di dalam sebuah *class* PHP.
- Fungsinya adalah untuk menyimpan nilai atau data yang terkait dengan objek (*instance*) dari *class* tersebut.

### Poin Penting tentang Property
1.  **Deklarasi**: Property dideklarasikan di dalam *class*. Pada PHP modern, disarankan menggunakan kata kunci visibilitas (`public`, `private`, `protected`) daripada `var`.
2.  **Akses**: Property diakses menggunakan operator `->` pada objek (*instance*) dari *class*.
3.  **Nilai Default**: Property dapat didefinisikan tanpa nilai awal atau langsung diberi nilai default.

### Contoh Kode: Definisi dan Akses Property

```PHP
<?php

class Person {
    public $first_name;         // Property tanpa nilai awal
    public $last_name;
    public $student = false;    // Property dengan nilai default
    public $country = "None";   // Property dengan nilai default
}

// Membuat objek (instance)
$customer = new Person();

// Memberi nilai pada property
$customer->first_name = "Hakim";

// Mengakses property
echo $customer->first_name . "<br>"; // Output: Hakim
echo $customer->country . "<br>";   // Output: None

// Mengubah nilai property
$customer->country = "Indonesia";
echo $customer->country . "<br>";   // Output: Indonesia
```

### Tips Penting
1.  **Gunakan Visibilitas Modern**: Selalu gunakan `public`, `private`, atau `protected` untuk mendeklarasikan property, bukan `var`.
    ```PHP
    class Student {
        public $name;         // Dapat diakses dari mana saja
        private $id;          // Hanya dapat diakses dari dalam class
        protected $country;   // Dapat diakses dari dalam class dan class turunannya
    }
    ```
2.  **Gunakan Constructor**: Untuk inisialisasi nilai property yang lebih terorganisir saat objek dibuat.
    ```PHP
    class Student {
        public $name;
        public $country;

        public function __construct($name, $country = "None") {
            $this->name = $name;
            $this->country = $country;
        }
    }

    $student1 = new Student("Miku", "Japan");
    echo $student1->name;    // Output: Miku
    echo $student1->country; // Output: Japan
    ```
3.  **Periksa Property**: Gunakan fungsi bawaan seperti `get_class_vars()` untuk mendapatkan semua property kelas, atau `property_exists()` untuk memeriksa keberadaan property tertentu.

---

## Summary

Property adalah variabel yang didefinisikan dalam sebuah class PHP untuk menyimpan data objek. Property dapat dideklarasikan dengan atau tanpa nilai default, dan diakses menggunakan operator `->`. Dalam pengembangan PHP modern, disarankan menggunakan kata kunci visibilitas (`public`, `private`, `protected`) dan memanfaatkan constructor untuk inisialisasi yang terstruktur, serta fungsi bawaan untuk memeriksa keberadaan property.