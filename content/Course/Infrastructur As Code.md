---
id: Infrastructure As Code
aliases: []
tags:
  - devops
comments: true
date: 2025-11-16
draft: false
---

---

Related: [[index|Home]], [[devops]]

---

## Cue

- Apa itu Infrastructure as Code (IaC) dan kategori utamanya?
- Apa itu Arsitektur Microservices dan apa keunggulannya?
- Mengapa Monitoring dan Logging penting dalam DevOps?
- Apa saja alat umum yang digunakan untuk IaC, Microservices (Container, Serverless), dan Monitoring/Logging?

---

## Notes

### Infrastructure as Code (IaC)
**Infrastructure as Code (IaC)** adalah praktik pengelolaan dan penyediaan infrastruktur komputasi (jaringan, server, database) menggunakan kode, bukan konfigurasi manual. Ini mengotomatisasi pembuatan dan konfigurasi lingkungan.

-   **Kategorisasi**:
    1.  **Infrastructure Automation**: Otomatisasi pembuatan infrastruktur. Contoh alat: **Terraform**, AWS CloudFormation.
    2.  **Configuration Management**: Otomatisasi konfigurasi sistem operasi dan server. Contoh alat: **Chef**, **Puppet**, **Ansible**, AWS OpsWorks.

### Arsitektur Microservices
**Arsitektur Microservices** adalah pendekatan desain aplikasi sebagai kumpulan layanan yang *loosely coupled*, di mana setiap layanan berfokus pada tujuan bisnis spesifik dan berkomunikasi melalui API.

-   **Keunggulan**: Memungkinkan tim bekerja secara independen, mempercepat pengembangan dan *deployment*.
-   **Topik Terkait**:
    1.  **Container**: Standarisasi pengemasan kode dan dependensi. Alat: **Kubernetes**, **OpenShift**, Amazon ECS, Amazon EKS.
    2.  **Serverless**: Pendekatan komputasi tanpa pengelolaan infrastruktur server. Alat: **Serverless Framework**, OpenFaaS, AWS Lambda.

### Monitoring dan Logging
**Monitoring dan Logging** adalah praktik penting dalam DevOps untuk menilai efektivitas perubahan aplikasi dan infrastruktur, serta meningkatkan kualitas pengalaman pengguna.

-   **Fungsi**: Memantau kinerja sistem, mengidentifikasi masalah, dan menghasilkan data yang cukup dari aplikasi dan layanan dalam bentuk *logs*, *metrics*, dan *traces*.
-   **Contoh Alat**: **Prometheus**, Elastic Stack, Dynatrace, AWS X-Ray, Amazon CloudWatch.

---

## Summary

Infrastructure as Code (IaC) mengotomatisasi pengelolaan infrastruktur melalui kode, terbagi menjadi otomatisasi infrastruktur dan manajemen konfigurasi. Arsitektur Microservices mendesain aplikasi sebagai layanan independen yang terhubung via API, seringkali memanfaatkan container dan serverless. Monitoring dan logging esensial untuk mengukur kinerja dan mengidentifikasi masalah. Ketiga praktik ini, didukung oleh berbagai alat, merupakan pilar penting dalam implementasi DevOps yang efektif.
