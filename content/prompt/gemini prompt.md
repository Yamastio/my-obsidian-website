---
id: gemini prompt
aliases: []
tags: []
---
```
Gunakan file "ai-agent-vault-migration.md" sebagai panduan resmi untuk proses migrasi.

Tugas utama:
Migrasikan seluruh file catatan Obsidian lama yang berada di folder "/vault_lama" ke format Cornell Note + Quartz frontmatter.

Aturan Proses:

1. Baca semua file ber-ekstensi .md di direktori /vault_lama,
   kecuali: "ai-agent-vault-migration.md".

2. Untuk setiap file yang diproses:
   a. Buat frontmatter Quartz sesuai panduan:
      - id = nama file tanpa ekstensi
      - aliases = []
      - tags = gunakan tag lama jika relevan
      - comments = true
      - date = jika frontmatter lama memiliki date, gunakan itu
               jika tidak, gunakan tanggal saat ini (format YYYY-MM-DD)
      - draft = false

   b. Bangun "Related links":
      - Selalu tambahkan [[index|Home]]
      - Tambahkan semua tag yang digunakan sebagai internal links

   c. Buat struktur Cornell Notes:
      ## Cue
      - Buat daftar pertanyaan, istilah kunci, atau topik pokok

      ## Notes
      - Pecah materi menjadi subjudul (Heading 3)
      - Setiap subjudul berisi bullet point yang merangkum isi asli file
      - Tidak menghilangkan informasi penting, namun ringkas dan terstruktur

      ## Summary
      - Ringkasan padat 3–5 kalimat
      - Harus mencakup seluruh ide utama dari file tersebut

   d. Hanya gunakan heading berlevel 2 untuk:
      - Cue
      - Notes
      - Summary

3. Simpan hasil revisi dengan menimpa file lama
   memakai filesystem MCP:
   - method: writeFile
   - path: "/vault_lama/[nama_file].md"

4. Tag baru:
   - Jika suatu catatan tidak cocok dengan tag mana pun, gunakan tag `misc`.
   - Dilarang membuat tag baru kecuali konsep tersebut adalah kategori top-level yang penting.
   - Dilarang membuat tag berdasarkan subjudul atau istilah teknis kecil.

5. Jangan mengubah atau menulis ulang file:
   - "/vault_lama/ai-agent-vault-migration.md"

6. Pastikan format final valid YAML + Markdown
   dan dapat digunakan oleh Quartz tanpa error.

Output yang diharapkan:
- Semua file dalam /vault_lama sudah menggunakan format Cornell Note
- Frontmatter Quartz lengkap dan rapi
- Related links benar
- tagbaru.txt dibuat jika diperlukan
- Tidak ada file lain yang diubah selain target catatan

Perilaku:
- Jika struktur lama kacau, rapikan dengan tetap menjaga makna
- Jangan menggunakan bold, italic, atau styling lain
- Hanya heading, bullet points, dan blok YAML
- Jangan buat tag baru yang di blacklist di file "ai-agent-vault-migration.md"
- Wajib tambahkan tag google_cybersecurity dan cybersecurity
```
