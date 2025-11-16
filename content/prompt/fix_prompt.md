---
id: prompt_notagnew
aliases: []
tags: []
---
```
Gunakan file "ai-agent-vault-migration.md" sebagai panduan resmi untuk proses migrasi.
Daftar tag yang valid hanya yang tertulis di file tersebut. Jangan gunakan tag di luar daftar itu.

Tugas utama:
Migrasikan seluruh file catatan Obsidian lama yang berada di folder "/vault_lama" ke format Cornell Note + Quartz frontmatter.

Aturan Proses:

1. Baca semua file ber-ekstensi .md di direktori /vault_lama,
   kecuali: "ai-agent-vault-migration.md".

2. Untuk setiap file yang diproses:
   a. Buat frontmatter Quartz sesuai panduan:
      - id = nama file tanpa ekstensi
      - aliases = []
      - tags = gunakan tag lama yang ada di file (jika tag tersebut juga termasuk dalam daftar tag valid di ai-agent-vault-migration.md)
      - comments = true
      - date = jika frontmatter lama memiliki date, gunakan itu
               jika tidak, gunakan tanggal saat ini (format YYYY-MM-DD)
      - draft = false

   b. Bangun "Related links":
      - Selalu tambahkan [[index|Home]]
      - Tambahkan semua tag yang digunakan sebagai internal links
        (hanya tag valid sesuai aturan di atas)

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

4. Aturan Tag (ketat):
   - Gunakan hanya tag yang terdapat dalam file ai-agent-vault-migration.md.
   - Dilarang membuat tag baru dalam kondisi apa pun.
   - Dilarang menurunkan tag dari isi catatan, subjudul, atau konsep kecil.
   - Jangan membuat file tagbaru.txt.
   - Maksimal 5 tag.

5. Jangan mengubah atau menulis ulang file:
   - "/vault_lama/ai-agent-vault-migration.md"

6. Pastikan format final valid YAML + Markdown
   dan dapat digunakan oleh Quartz tanpa error.

Output yang diharapkan:
- Semua file dalam /vault_lama sudah menggunakan format Cornell Note
- Frontmatter Quartz lengkap dan rapi dengan tag yang valid
- Related links benar
- Tidak ada tag baru yang dibuat
- Tidak ada file lain yang diubah selain target catatan

Perilaku:
- Jika struktur lama kacau, rapikan dengan tetap menjaga makna
- Jangan menggunakan bold, italic, atau styling lain
- Hanya heading, bullet points, dan blok YAML
- Wajib ada tag cybersecurity dan google_cybersecurity

```

Wajib ada tag cybersecurity dan google_cybersecurity
