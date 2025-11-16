---
id: Keyword This
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

- Apa fungsi dari kata kunci `$this` dalam PHP OOP?
- Mengapa terjadi error saat mengakses properti tanpa `$this` di dalam method?
- Bagaimana cara mengakses properti dan memanggil method dengan benar menggunakan `$this`?

---

## Notes

### Apa itu Kata Kunci `$this`?
Dalam PHP Object-Oriented Programming (OOP), kata kunci `$this` adalah sebuah variabel khusus yang merujuk pada *instance* (objek) saat ini dari sebuah *class*. Ini digunakan untuk mengakses properti dan method yang dimiliki oleh objek tersebut dari dalam *method* *class* itu sendiri.

### Contoh Kesalahan pada Akses Properti
Ketika properti diakses di dalam method tanpa menggunakan `$this`, PHP akan menganggapnya sebagai variabel lokal, yang akan menyebabkan error `Undefined variable`.

```php
class Person {
    var $first_name;
    var $last_name;

    function fullName() {
        // Kesalahan: $first_name dan $last_name dianggap variabel lokal
        return $first_name . ' ' . $last_name;
    }
}

$p = new Person;
$p->first_name = "Akane";
$p->last_name = "Miku";

echo $p->fullName(); // Akan menghasilkan Notice: Undefined variable
```

### Solusi: Gunakan `$this`
Untuk mengakses properti atau method dari objek saat ini di dalam *class*, Anda harus selalu menggunakan `$this->nama_properti` atau `$this->nama_method()`.

```php
class Person {
    var $first_name;
    var $last_name;

    function fullName() {
        // Solusi: Menggunakan $this untuk mengakses properti objek
        return $this->first_name . ' ' . $this->last_name;
    }
}

$p = new Person;
$p->first_name = "Akane";
$p->last_name = "Miku";

echo $p->fullName(); // Output: Akane Miku
```

### Implementasi yang Benar
Berikut adalah contoh implementasi yang benar dalam sebuah *class* `Student`:

```php
<?php

class Student {
    public $firstName;
    public $lastName;

    public function sayHello() {
        return "Hello, " . $this->firstName . "!";
    }

    public function fullName() {
        return $this->firstName . ' ' . $this->lastName;
    }
}

$student1 = new Student;
$student1->firstName = "Nakano";
$student1->lastName = "Miku";

echo $student1->sayHello() . "<br/>"; // Output: Hello, Nakano!
echo $student1->fullName() . "<br/>"; // Output: Nakano Miku
```

### Catatan Penting
- Properti diakses dengan `$this->property` di dalam method.
- Method dipanggil dengan `$object->methodName()`.
- Properti dimodifikasi dengan `$object->property = value;`.

---

## Summary

Kata kunci `$this` dalam PHP OOP adalah referensi penting ke objek saat ini, yang memungkinkan akses ke properti dan method dari dalam class. Kegagalan menggunakan `$this` saat mengakses properti di dalam method akan menyebabkan error karena properti tersebut akan dianggap sebagai variabel lokal. Penggunaan `$this->property` dan `$this->method()` adalah cara yang benar untuk berinteraksi dengan anggota objek, memastikan fungsionalitas OOP yang tepat.
