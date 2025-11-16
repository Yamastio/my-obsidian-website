---
id: Method
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

- Apa itu method dalam konteks PHP OOP?
- Bagaimana cara mendefinisikan dan menggunakan method dalam sebuah class PHP?
- Bagaimana method mengakses properti di dalam class yang sama?
- Apa saja fungsi penting untuk memeriksa method di PHP?

---

## Notes

### Definisi Method
- **Method** adalah fungsi yang didefinisikan di dalam sebuah *class*.
- Method memungkinkan objek (*instance*) dari *class* tersebut untuk melakukan tindakan atau operasi.
- Method memiliki akses ke properti dan fitur lain yang dideklarasikan di dalam *class* yang sama.

### Contoh Dasar Penggunaan Method

```php
class Person {
    public $first_name; // Properti

    // Method
    public function sayHello() {
        return "Hello World!";
    }
}

// Membuat objek dari class
$customer = new Person;

// Menetapkan nilai properti
$customer->first_name = "Miku";

// Mengakses properti dan method
echo $customer->first_name; // Output: Miku
echo $customer->sayHello(); // Output: Hello World!
```

### Studi Kasus: Class dengan Beberapa Method dan Properti

```php
<?php

class Student {
    public $name;     // Properti
    public $country;  // Properti

    // Method untuk menampilkan pesan
    public function sayHello() {
        return "Hello, " . $this->name; // Mengakses properti menggunakan $this
    }
}

// Membuat dua objek dari class Student
$student1 = new Student;
$student2 = new Student;

// Menetapkan nilai properti
$student1->name = "Miku";
$student2->name = "Akane";

// Menampilkan properti dan method
echo $student1->name . "<br/>";
echo $student2->name . "<br/>";
echo $student1->sayHello() . "<br/>";
echo $student2->sayHello() . "<br/>";

// Fungsi PHP untuk memeriksa method
$class_method = get_class_methods("Student");
echo "Method milik Student: ";
echo "<pre>";
print_r($class_method); // Output: Array([0] => sayHello)
echo "</pre>";

if (method_exists("Student", "sayHello")) {
    echo "Method sayHello tersedia";
} else {
    echo "Method sayHello tidak tersedia";
}
```

### Catatan Penting
- Dalam PHP modern, selalu gunakan `public`, `protected`, atau `private` untuk mendeklarasikan method, bukan `function` tanpa visibilitas.
- Kata kunci `$this` digunakan di dalam method untuk merujuk pada objek saat ini, memungkinkan akses ke properti dan method lain dari objek tersebut.

---

## Summary

Method adalah fungsi yang didefinisikan di dalam sebuah class PHP, memungkinkan objek untuk melakukan tindakan dan berinteraksi dengan propertinya. Method diakses melalui operator `->` pada objek, dan dapat menggunakan `$this` untuk merujuk pada properti atau method internal class. Fungsi seperti `get_class_methods()` dan `method_exists()` berguna untuk memeriksa method yang tersedia dalam sebuah class.
