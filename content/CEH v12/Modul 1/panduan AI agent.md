---
id: panduan AI agent
aliases: []
tags: []
---

Berikut template standar yang bisa kamu gunakan untuk membuat atau merapikan file menjadi format **Cornell Note + Quartz frontmatter** seperti contoh Censys di atas. Kamu bisa menggunakannya dengan AI Agent untuk otomatis menyesuaikan konten.

---

```yaml
---
id: [JudulFile]
aliases: []
tags:
  - [tag1]
  - [tag2]
comments: true
date: [YYYY-MM-DD]
draft: false
---

---

Related: [[index|Home]], [[tag1]], [[tag2]]

---

## Cue

- [Pertanyaan utama atau istilah kunci 1]
- [Pertanyaan utama atau istilah kunci 2]
- [Pertanyaan utama atau istilah kunci 3]
- dst.

---

## Notes

### [Subjudul 1]

- [Catatan utama 1]
- [Catatan utama 2]
- dst.

### [Subjudul 2]

- [Catatan utama 1]
- [Catatan utama 2]
- dst.

### [Subjudul 3]

- [Catatan utama 1]
- [Catatan utama 2]
- dst.

---

## Summary

[Ringkasan singkat, padat, menyampaikan inti dari seluruh catatan. Biasanya 3–5 kalimat.]
```

---

### Panduan Praktis Penggunaan AI Agent

1. **Input**: Salin seluruh konten catatan mentah ke AI Agent.
2. **Prompt**:

```
Ubah catatan ini menjadi Cornell Notes dengan format Quartz seperti template berikut:
- Isi Cue dengan pertanyaan atau istilah kunci
- Notes berisi penjelasan tiap subjudul dengan poin-poin
- Summary merangkum keseluruhan
- Lengkapi frontmatter (id, tags, date, comments, draft)
- Related link sesuai tags
```

3. **Output**: AI Agent menghasilkan file siap pakai sesuai template, bisa langsung dimasukkan ke Obsidian Vault.
4. **Tips**:
   - Gunakan frontmatter `id` sesuai nama file atau istilah utama.
   - Tags ambil dari topik utama catatan.
   - Cue harus ringkas dan mencakup semua poin penting.
   - Notes pisahkan tiap subjudul dengan poin-poin singkat, jelas, dan terstruktur.
   - Summary harus menjawab semua Cue dan Notes dalam 1–2 paragraf.
