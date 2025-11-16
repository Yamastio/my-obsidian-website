---
id: Mendefinisikan Class di PHP
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

- Apa saja tips untuk penamaan dan struktur file class di PHP?
- Bagaimana contoh dasar definisi class di PHP?
- Bagaimana cara memeriksa keberadaan class di PHP?
- Apa fungsi `get_declared_classes()` dan `class_exists()`?

---

## Notes

### Tips Membuat Class di PHP

1.  **Penamaan Class**:
    -   Selalu diawali dengan huruf kapital (menggunakan *CamelCase*). Contoh: `Person`, `ProductPhoto`, `Student`.
    -   Gunakan nama dalam bentuk tunggal (singular). Contoh yang benar: `Product` (bukan `Products`).
    -   Hindari menggunakan angka atau simbol pada awal nama *class*.
2.  **Struktur File**:
    -   Setiap *class* didefinisikan dalam *file* terpisah untuk mempermudah pengelolaan kode.
    -   Contoh: `Person.php` untuk *class* `Person`, `ProductPhoto.php` untuk *class* `ProductPhoto`.
3.  **Penamaan File**:
    -   Nama *file* harus sama dengan nama *class*. Contoh: *File* `Student.php` berisi *class* `Student`.

### Contoh Definisi Class di PHP

```PHP
<?php

// File: Person.php
class Person {
    public $name;
    public $age;

    public function introduce() {
        return "Hi, my name is {$this->name}, and I am {$this->age} years old.";
    }
}

// File: ProductPhoto.php
class ProductPhoto {
    public $resolution;

    public function displayResolution() {
        return "Resolution: {$this->resolution}";
    }
}
```

### Memeriksa Keberadaan Class

PHP menyediakan fungsi bawaan untuk mengecek *class* yang telah dideklarasikan atau keberadaan *class* tertentu.

#### Kode Contoh

```PHP
<?php

// Deklarasi class
class Student {}

// Mendapatkan semua class yang telah dideklarasikan
$classes = get_declared_classes();
echo "Classes: " . implode(', ', $classes) . "<br />";

// Memeriksa keberadaan class tertentu
$classNames = ["Products", "Student", "student"];
foreach ($classNames as $className) {
    if (class_exists($className)) {
        echo "{$className} class ada. <br />";
    } else {
        echo "{$className} class tidak ada. <br />";
    }
}
```

#### Penjelasan Fungsi

1.  **`get_declared_classes()`**:
    -   Mengembalikan *array* semua *class* yang telah dideklarasikan dalam *script*.
    -   Berguna untuk melihat daftar *class* aktif.
2.  **`class_exists($className)`**:
    -   Mengecek apakah *class* tertentu sudah dideklarasikan.
    -   *Case-sensitive*: `Student` berbeda dengan `student`.

#### Contoh Output

Jika *class* `Student` dideklarasikan, hasilnya akan seperti ini:

```
Classes: Student, ...
Products class tidak ada.
Student class ada.
student class tidak ada.
```

---

## Summary

Mendefinisikan *class* di PHP mengikuti konvensi penamaan *CamelCase* dan singular, dengan setiap *class* idealnya berada dalam *file* terpisah yang namanya sesuai dengan *class*. *Class* berfungsi sebagai *blueprint* untuk objek, dengan properti dan *method*. PHP menyediakan fungsi `get_declared_classes()` untuk melihat semua *class* yang aktif dan `class_exists()` untuk memverifikasi keberadaan *class* tertentu, yang bersifat *case-sensitive*.
