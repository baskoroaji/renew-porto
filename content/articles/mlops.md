---
title: "Machine Learning System"
description: "Pembuatan machine learning dari awal hingga deployment"
tags: ['MLOperation', 'Docker', 'MLFlow', 'Dagshub']
published: 2025/06/5
author: 'Baskoro Aji'
slug: "mlops"
---


# Background
Pembuatan machine learning sangatlah menarik, dari bagaimana para machine learning developer membuat sebuah model hingga mendeploynya
maka dari itu pada proyek ini akan mencakup tentang machine learning dari awal pembuatan hingga deployement ke Docker

## Otomisasi Preprocessing Dataset
Sebelum dataset di training di machine learning, dataset perlu melewati tahap preprocessing dimana tahap ini dataset melalui serangkaian
proses seperti encoding, penanganan missing value, normalisasi, standarisasi, penanganan outliers.
Pembuatan preprocessing dataset ini melalui sebuah otomisasi dengan menggunakan github CI/CD dimana jika ada perubahan terhadap dataset akan langsung dibentuk sebuah preprocessing pipeline
yang dimana berfungsi untuk ke tahap selanjutnya yaitu melakukan modelling

berikut dokumentasi CI/CD pipeline untuk preprocessing dataset:

![alt image](https://jie25.s-ul.eu/jshPgRtW)

## Modelling
dengan menggunakan MLflow model jadi lebih mudah dibuat dan dimonitor dengan menggunakan MLflow yang dihubungkan ke Dagshub
kita dapat melihat hasil training dan testing dari model machine learning dengan menggunakan algoritma random forest regressor.

dokumentasi DagsHub:

![alt image](https://jie25.s-ul.eu/h78S8oX7)
**Dagshub Link : [Link](https://dagshub.com/baskoroaji/MSML_aji/experiments)**

## Deployment
dengan menggunakan otomisasi deployment, kita dapat dengan mudah melakukan deployment model machine learning
dengan menggunakan github action atau CI/CD.

dokumentasi deployement docker menggunakan CI/CD:

![alt image](https://jie25.s-ul.eu/5OmyBxYm)

## Monitoring
Setelah kita mendeploy aplikasi ke Docker ada baiknya dilakukan monitoring aplikasi
karena tanpa monitoring bisa saja ada hal hal yang membuat model tidak bekerja bisa karena model drift atau bahkan services yang down
dengan menggunakan grafana dan prometheus kita dapat membuat monitoring yang juga dapat memberikan peringatan ke email jika terjadi sesuatu

**Grafana**
![alt image](https://jie25.s-ul.eu/V2jduZOt)

**Prometheus**
![alt image](https://jie25.s-ul.eu/SINjXN5d)

**Grafana Alerting**
![alt image](https://jie25.s-ul.eu/kLDNUyWY)
