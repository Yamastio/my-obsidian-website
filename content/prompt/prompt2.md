---
id: prompt2
aliases: []
tags: []
---

Agent harus membaca pedoman yang ada di file bernama “ai-agent-vault-migration.md” di direktori /vault_lama sebagai referensi resmi.

Tugas agent adalah memigrasikan seluruh file markdown di folder /vault_lama (kecuali ai-agent-vault-migration.md) ke format Cornell Notes lengkap dengan frontmatter Quartz.

Langkah-langkah yang harus diikuti agent:

1. Agent menelusuri seluruh file ber-ekstensi .md pada direktori /vault_lama, lalu memilih semua file kecuali ai-agent-vault-migration.md.

2. Untuk setiap file yang diproses, agent membangun frontmatter Quartz dengan ketentuan berikut:

   * id diambil dari nama file tanpa ekstensi
   * title sama dengan id
   * aliases diatur menjadi array kosong
   * tags diambil dari tag lama jika ada dan relevan. Bila tag baru diperlukan, agent menciptakannya kecuali jika tag tersebut masuk daftar blacklist. Semua tag baru harus dicatat ke dalam file bernama tagbaru.txt di direktori yang sama.
   * comments diset ke true
   * draft diset ke false
   * date diambil dari metadata lama jika tersedia, jika tidak maka menggunakan tanggal hari ini dalam format YYYY-MM-DD

3. Setelah frontmatter, agent membuat bagian Related links yang selalu berisi [[index|Home]] serta seluruh tag yang digunakan sebagai internal links.

4. Isi file harus ditata ulang dengan format Cornell Notes yang terdiri dari tiga heading level 2: Cue, Notes, dan Summary.

   * Bagian Cue berisi daftar istilah atau pertanyaan penting
   * Bagian Notes disusun menggunakan heading level 3 untuk subtopik dan bullet points untuk isinya
   * Bagian Summary terdiri dari tiga hingga lima kalimat yang merangkum keseluruhan materi

5. Format teks tidak boleh menggunakan bold, italic, atau bentuk dekoratif apa pun selain heading dan bullet points.

6. Setelah selesai memformat, agent menulis ulang file asli menggunakan path di direktori /vault_lama melalui MCP filesystem.

7. File ai-agent-vault-migration.md tidak boleh diubah.

8. Setelah semua selesai, file tagbaru.txt harus berisi daftar tag baru yang tidak termasuk blacklist.

Instruksi ini adalah pedoman umum. Agent akan menggunakan kemampuan reasoning internal untuk memutuskan kapan harus memanggil MCP filesystem.readFile, writeFile, atau listDirectory sesuai kebutuhan, tetapi tidak memanggil fungsi secara otomatis dari prompt ini.

