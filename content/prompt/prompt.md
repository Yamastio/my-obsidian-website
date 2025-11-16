---
id: prompt
aliases: []
tags: []
---

Gunakan file **"/vault_lama/ai-agent-vault-migration.md"** sebagai panduan resmi proses migrasi.
Agent menggunakan dua MCP tools: **filesystem** dan **obsidian** (jika diperlukan untuk metadata).

Tugas utama:
Migrasikan semua file catatan Obsidian lama di folder **"/vault_lama"** ke format **Cornell Notes + Quartz frontmatter**.

---

## **Aturan Proses Utama**

### **1. Pemrosesan File**

Baca seluruh file `.md` di direktori `/vault_lama`,
kecuali:

* `ai-agent-vault-migration.md`

Gunakan MCP filesystem:

* `filesystem.readFile`
* `filesystem.writeFile`
* `filesystem.listDirectory`

### **2. Untuk setiap file .md yang diproses:**

### **(a) Buat frontmatter Quartz**

Gunakan format YAML berikut:

```
---
title: [judul_asli_file]
id: [nama file tanpa ekstensi]
aliases: []
tags: [daftar_tag]
date: YYYY-MM-DD
draft: false
comments: true
---
```

Ketentuan:

* **id = nama file tanpa ekstensi**
* **title = nama file tanpa ekstensi**
* **tags:**

  * gunakan tag lama jika relevan
  * jika butuh tag baru:

    * hanya buat jika tidak ada tag dari taksonomi resmi yang cocok
    * jangan gunakan tag blacklist
    * semua tag baru harus dicatat ke `/vault_lama/tagbaru.txt`
* **date:**

  * ambil dari metadata lama jika ada
  * jika tidak ada, gunakan tanggal hari ini (YYYY-MM-DD)

### **Blacklist Tag (dilarang dibuat):**

```
learning
hacking_fundamentals
hacking_intermediate
networking_fundamentals
devops_fundamentals
hacking_advance
fundamentals
vulnerability_exploitation
vulnerability_management
```

### **(b) Bangun Related links**

Format setelah frontmatter:

```
Related: [[index|Home]], [[tag1]], [[tag2]], ...
```

Gunakan semua tag sebagai wikilinks.

### **(c) Struktur Cornell Notes**

Gunakan **H2 saja** untuk tiga bagian utama:

```
## Cue
- daftar pertanyaan atau istilah kunci

## Notes
### subtopik
- bullet points ringkas

### subtopik lain
- bullet points

## Summary
Ringkasan 3–5 kalimat.
```

Ketentuan:

* Notes boleh dibagi menjadi beberapa heading 3 (`###`)
* Tidak boleh ada bold, italic, underline, atau format dekoratif
* Reformat isi jika struktur lama kacau, tetapi jangan ubah makna

### **(d) Menyimpan File**

Tulis ulang file menggunakan:

```
filesystem.writeFile
path: "/vault_lama/[nama_file].md"
```

---

## **3. Penanganan Tag Baru**

Untuk setiap tag baru:

* Pastikan tidak termasuk blacklist
* Tambahkan ke file `/vault_lama/tagbaru.txt` dengan format:

```
tag_baru
```

Satu tag per baris.

---

## **4. Menjaga File Tertentu**

Jangan mengubah file:

* `/vault_lama/ai-agent-vault-migration.md`

---

## **5. Validasi Sebelum Menyimpan**

Pastikan:

* YAML frontmatter valid
* Struktur Cornell lengkap (Cue, Notes, Summary)
* Related links ada
* Tidak ada formatting terlarang
* Informasi asli tetap utuh namun lebih ringkas
