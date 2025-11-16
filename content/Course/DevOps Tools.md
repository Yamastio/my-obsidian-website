---
id: DevOps Tools
aliases: []
tags:
  - programming
  - devops
comments: true
date: 2025-11-15
draft: false
---

---

Related: [[index|Home]], [[programming]], [[devops]]

---

## Cue

- Kategori utama devops tools
- Contoh tools komunikasi, cloud, ide
- Tools untuk setiap tahap ci/cd
- Tools monitoring
- Hubungan devops tools dengan calms

---

## Notes

### Komunikasi dan Kolaborasi

- Mendukung koordinasi antara developer dan it operations.
- Tools umum: microsoft teams, slack, cisco webex teams.
- Tools aws: amazon chime.

### Cloud

- Mendukung environment on-demand tanpa server fisik.
- Meningkatkan fleksibilitas dan kolaborasi.
- Tools aws: aws cloud9, aws codecommit.

### IDE

- Membantu penulisan, debugging, dan kolaborasi kode.
- Tools umum: visual studio (live share), intellij idea (code with me).
- Tools aws: aws cloud9. ### CI/CD

#### Code (version control)

- Mengelola versi kode dan kolaborasi revisi.
- Tools umum: github, gitlab.
- Tools aws: aws codecommit.

#### Build

- Mengubah kode menjadi artifact siap deploy.
- Tools umum: jenkins, travis ci.
- Tools aws: aws codebuild.

#### Testing

- Pengujian otomatis sebelum aplikasi dideploy.
- Tools aws: aws codedeploy untuk load testing, third-party seperti gremlin, testable.

#### Release

- Penyimpanan dan distribusi container atau package.
- Tools umum: docker hub, jfrog artifactory.
- Tools aws: amazon ecr, aws codeartifact.

#### Deploy

- Pengiriman aplikasi ke production.
- Tools umum: heroku, netlify.
- Tools aws: aws codedeploy, aws elastic beanstalk.

### Monitoring

- Memastikan aplikasi berjalan sesuai ekspektasi setelah deployment.
- Tools umum: prometheus, elastic stack, dynatrace.
- Tools aws: aws x-ray, amazon cloudwatch.

### Kaitan dengan CALMS

- Tools mendukung culture, automation, lean, measurement, dan sharing.
- Meningkatkan efisiensi, konsistensi, dan prediktabilitas proses devops.

---

## Summary

Devops tools digunakan untuk mendukung komunikasi, kolaborasi, pengembangan, ci/cd, deployment, dan monitoring. Penggunaan tools yang tepat membantu mempercepat proses, meningkatkan kualitas rilis, dan selaras dengan prinsip calms dalam penerapan devops.
