---
title: Hacking Methodologies and Framework
id: 251114-0708-x2
aliases: []
tags: ["learning", "ceh_v12", "cybersecurity"]
date: 2025-09-10
description: Ringkasan lengkap metodologi hacking CEH, Cyber Kill Chain, TTPs, IOC, MITRE ATT&CK, dan Diamond Model.
draft: false
comments: true
---

## Cue

- Apa itu CEH Methodology?
- Footprinting, Scanning, Enumeration
- Vulnerability Analysis dan System Hacking
- Cyber Kill Chain
- TTPs
- IOC dan macam-macamnya
- MITRE ATT&CK Framework
- Diamond Model

## CEH Methodology (CHM)

### 1. Footprinting

- Tahap persiapan: mengumpulkan informasi sebanyak mungkin
- Profiling organisasi: IP range, namespace, karyawan
- Social engineering dapat dilakukan berdasarkan informasi publik
- Whois query mengungkap informasi domain dan organisasi
- Lingkup: organisasi, karyawan, operasi, network, sistem

### 2. Scanning

- Mengidentifikasi host aktif, open ports, perangkat terhubung
- Merupakan perpanjangan dari active reconnaissance
- Scanning dan reconnaissance sering berjalan bersamaan

### 3. Enumeration

- Koneksi langsung ke target
- Mengambil data seperti: user list, routing table, security flaws, shared resources, banner

### 4. Vulnerability Analysis

- Mengidentifikasi dan mengklasifikasikan kelemahan keamanan
- Digunakan untuk mengetahui sejauh mana eksploitasi dapat dilakukan

### 5. System Hacking

#### a. Gaining Access

- Fase inti hacking
- Memanfaatkan password cracking, exploit, buffer overflow
- Setelah akses didapatkan, dilakukan privilege escalation dan mencoba mempertahankan akses

#### b. Escalating Privileges

- Meningkatkan hak akses dari low-privilege menjadi admin

#### c. Maintaining Access

- Menjaga akses jangka panjang
- Upload/hapus data, pivoting, mengamankan backdoor

#### d. Clearing Logs

- Menghapus jejak aktivitas untuk menghindari deteksi

## Cyber Kill Chain Methodology

![[ceh2.png]]

- Framework berbasis intelijen untuk mendeteksi dan mencegah aktivitas berbahaya
- Dikembangkan berdasarkan konsep _Military Kill Chain_

### 1. Reconnaissance

- Mengumpulkan informasi sebanyak mungkin
- Meliputi: OSINT, DNS, Whois, scanning, analisis aktivitas publik

### 2. Weaponization

- Menganalisis hasil reconnaissance untuk menentukan kelemahan
- Membuat/memilih payload: malware, exploit, phishing campaign

### 3. Delivery

- Mengirim payload ke target melalui email, USB, web kompromi, dll

### 4. Exploitation

- Payload dieksekusi
- Melibatkan auth attacks, arbitrary code execution, dan misconfiguration

### 5. Installation

- Menginstall malware/backdoor untuk mempertahankan akses

### 6. Command & Control

- Membuat channel komunikasi dua arah
- Menggunakan enkripsi untuk penyembunyian

### 7. Action on Objectives

- Penyerang mencapai tujuan: mencuri data, merusak sistem, meluncurkan serangan lanjutan

## Tactics, Techniques, and Procedures (TTPs)

- Tactic: Pedoman langkah serangan
- Technique: Metode teknis yang digunakan
- Procedure: Rangkaian langkah sistematis
- Membantu memprediksi, mendeteksi, dan memahami motif penyerang

## Adversary Behavior Identification

1. Internal Reconnaissance
2. Use of PowerShell
3. Unspecified Proxy Activities
4. Use of CLI
5. HTTP User Agent anomalies
6. Command & Control Server detection
7. DNS Tunneling
8. Web Shell detection
9. Data Staging

## Indicator of Compromise (IOC)

- What: Petunjuk adanya aktivitas berbahaya
- Dibagi menjadi 3:
  - Atomic Indicator (IP, email)
  - Computed Indicator (hash, regex)
  - Behavioral Indicator (logika gabungan, pola perilaku)

## Kategori IOC

### Email Indicators

- Subjek mencurigakan, attachment, link berbahaya

### Network Indicators

- URL, domain, IP, aktivitas C2

### Host-Based Indicators

- File abnormal, hash, registry keys, DLL, mutex

### Behavioral Indicators

- Perilaku abnormal seperti document menjalankan PowerShell

## Key Indicators of Compromise

1. Trafik keluar tidak biasa
2. Aktivitas abnormal pada privileged account
3. Anomali geolokasi
4. Login gagal
5. HTML response besar
6. Repeated requests
7. Lalu lintas port tidak wajar
8. Registry berubah
9. DNS request abnormal
10. Patch system aneh
11. Indikasi DDoS
12. Data berada di lokasi tidak semestinya
13. Web traffic superhuman

## MITRE ATT&CK Framework

- Pengetahuan global tentang taktik dan teknik serangan
- Enterprise memiliki 14 taktik: Recon hingga Impact
- Digunakan untuk: pemetaan musuh, deteksi, mitigasi

## Diamond Model of Intrusion Analysis

- Framework untuk mengidentifikasi rangkaian event dalam serangan
- Elemen inti:
  - Adversary
  - Victim
  - Capability
  - Infrastructure

### Additional Event Meta Features

- Timestamp, Phase, Result, Direction, Methodology, Resource

### Extended Diamond Model

- Menambahkan:
  1. Socio-political meta-feature
  2. Technology meta-feature
