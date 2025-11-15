---
id: Information Security Controls
aliases: []
tags:
  - ceh_v12
  - cybersecurity
comments: true
date: 2025-11-14
description: Ringkasan konsep dasar mengenai information security controls.
draft: false
title: Information Security Controls
---

Related: [[index|Home]], [[ceh_v12]], [[cybersecurity]]

- Information Security Controls (ISC) membantu mencegah kejadian yang tidak diinginkan
- Komponen terpenting dari organisasi adalah informasi

## Information Assurance (IA)

- Merujuk pada integritas, ketersediaan, kerahasiaan dan autentikasi informasi dan keamanan sistem selama digunakan, di proses dan didistribusikan
- Beberapa proses yang membantu mendapatkan jaminan informasi:
  1. Membangun kebijakan lokal, proses, dan panduan
  2. Mendesain jaringan dan strategi user authentication
  3. Mengidentifikasi kelemahan jaringan dan ancaman
  4. Mengidentifikasi masalah dan sumber daya yang dibutuhkan
  5. Membuat rencana untuk Mengidentifikasi sumber daya
  6. Menyetujui jaminan informasi yang sesuai kontrol
  7. Melakukan sertifikasi dan akreditasi
  8. Menyediakan latihan jaminan informasi(IA)

## Continual/Adaptive Security Strategy

- Organisasi seharusnya mengadposi strategi keamanan yang adaptif, dimana melibatkan 4 pendekatan keamanan
- 4 Aktivitas ini saling terkait:
  1. Protect: strategi pertahanan secara mendalam, melindungi endpoint, network, data
  2. Detect: Menilai kelemahan jaringan, monitoring dengan packet sniffing tools dan network monitoring
  3. Respond: Mengidentifikasi insiden, mencari dalang dari penyebanya, dan melakukan investigasi
  4. Predict: Mengidentifikasi kemungkinan serangan, target dan metode

## Defense in Depth

![[ceh3.png]]

- Defense in Depth adalah strategi dimana beberapa lapisan keamanan ditempatakn diseluruh sistem informasi
- Mencegah serangan secara langsung, karenan harus menjebol satu persatu lapisan

## Apa itu Risiko?

- Merujuk pada ekspektasi bahwa kejadian buruk akan menyebabkan kerusakan sistem
- Dikategorikan berdasarkan level terhadap dampak kerusakan ke sistem
- Matriks risiko dibuat untuk menilai kemungkinan dan konsekuensi dari dampak suatu kejadian
- Risiko adalah gabungan dari kemungkinan dan konsekuensi dari dampak
  | Risiko = Ancaman x Kelemahan x Dampak |

## Level Risiko

- Penilaian berdasarkan dampak yang terjadi di network
- Dibedakan berdasarkan frekuensi dan tingkat keparahan
- Formula perhitungan
  `Level Resiko = Konsekuensi x Kemungkinan`
- Dikategorikan menjadi 4 level: `extreme`, `high`, `medium`, `low`

| Risk Level      | Consequence                       | Action                                                                                                                                              |
| --------------- | --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Extreme or High | Serius atau bahaya segera terjadi | - Tindakan pengendalian diperlukan untuk mengurangi resiko<br>- Identifikasi dan paksakan kendali untuk mengurangi ke level rendah yang wajar       |
| Medium          | Bahaya Sedang                     | - Aksi segera tidak begitu diperlukan, tapi harus diimplementasikan secepatnya<br>- Implementasikan kendali secepat mungkin untuk mengurangi resiko |
| Low             | Bahaya yang dapat diabaikan       | Ambil langkah pencegahan untuk mengurangi dampak resiko                                                                                             |

## Matriks Risiko

- Memberikan skala pada resiko yang terjadi atau probabilitas kemungkinan, bersama dengan konsekuensi dan dampaknya
- Merupakan salah satu proses termudah dalam mengingkatkan visibilitas resiko
- Dibedakan menjadi beberapa level
- Banyak standar matriks resiko, sebuah organisasi harus membuatnya sendiri berdasarkan bisnis yang dibutuhkan

  ![[ceh4.png]]

## Manajemen Risiko

- Proses dari mengurangi dan mempertahankan resiko pada level yang dapat diterima
- Hal ini memiliki posisi yang penting dalam siklus hidup keamanan dan meningkatkan proses
- Tipe resiko berbeda disetiap organisasi, tetapi tindakan untuk mempersiapkan manajemen resiko adalah hal yang umum disetiap organisasi

### Tujuan Manajemen Risiko

- Mengidentifikasi potensi risiko
- Mengidentifikasi dampak dari risiko dan membuat rencana
- Memprioritaskan resiko berdasarkan dampak yang dihasilkan
- Memahami dan menganalisis resiko lalu melaporkan risiko kejadian
- Mengatur risiko dan mitigasi dampaknya
- Membuat kesadaran terhadap staff keamanan dan membangun strategi dan rencana risiko manajemen final

### 4 Fase Manajemen Risiko

#### 1. Risk Identification

- Langkah awal dalam rencana manajemen risiko
- Identifikasi sumber, penyebab, konsekuensi dari internal maupun eksternal risiko
- Berdasarkan kemampuan seseorang, dan berbeda antara organisasi yang satu dan yang lain

#### 2. Risk Assessment

- Menilai risiko organisasi dan mengestimasi kemungkinan dan dampak dari risiko tersebut
- Program yang dilakukan secara berulang, yang membantu menentukan kuantitatif dan kualitatif nilai risiko
- Dilakukan ketika mengidentifikasi bahaya tetapi belum bisa mengatur secepatnya, diikuti dengan pembaruan rutin informasinya

#### 3. Risk Treatment

- Proses seleksi dan implementasi pengendalian dari risiko yang teridentifikasi, untuk memodifikasinya
- Keputusan diambil dari hasil risk assessment
- Tujuan tahap ini adalah untuk mengidentifikasi perawatan untuk risiko yang ada
- Mengidentifikasi urutan berdasarkan tingkat prioritas yang akan ditangani, dipantau, dan direview
- Beberapa informasi diperlukan sebelum melakukan Risk Treatment:
  - Metode perawatan yang sesuai
  - Orang yang bertanggung jawab melakukan perawatan
  - Biaya yang terlibat
  - Manfaat dari treatment
  - Kemungkinan sukses
  - Cara untuk mengukur dan menilai perawatan

#### 4. Risk Tracking and Review

- Untuk memastikan efektifitas identifikasi dan penilaian dari risiko sebaik mungkin
- Memastikan bahwa penilaianya sesuai
- Mengevaluasi performa dari strategi risiko manajemen yang diterapkan
- Memastikan pengendalian sudah sesuai di organisasi, semua prosedur dipahami dan diikuti
