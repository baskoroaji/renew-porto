---
title: "Analisis Prediktif Energy Consumption"
description: "Laporan Proyek Machine Learning Analisis Prediktif Energy Consumption"
published: 2025/04/15
tags: ['Predictive Model', 'Regression', 'Data Science']
author: 'Baskoro Aji'
slug: "analisis-prediktif-energy-consumption"
---

**Github Link: [Link](https://github.com/baskoroaji/energy-consumption)**

## Domain Proyek

Penggunaan energi sangat krusial pada era sekarang, terutama untuk penggunaan rumah tangga. Banyaknya permintaan dari rumah tangga dipengaruhi oleh banyak faktor seperti lokasi, cuaca, karakteristik rumah, sosio-ekonomi, dan waktu. Dataset ini dibuat pada tahun 2022 ketika banyak orang masih bekerja dari rumah. Oleh karena itu, dibutuhkan analisis prediktif untuk mengukur seberapa besar penggunaan energi sehari-hari agar pemerintah atau perusahaan penyedia layanan listrik/energi dapat memprediksi pola penggunaan energi, meningkatkan efisiensi operasional, dan mengurangi dampak buruk terhadap lingkungan.

Referensi:
- [Energy Consumption Analysis and Characterization of the Residential Sector in the US towards Sustainable Development](https://www.mdpi.com/1996-1073/17/11/2789)
- [An analysis of monthly household energy consumption among single-family residences in Texas](https://www.sciencedirect.com/science/article/abs/pii/S0301421513012536)

## Business Understanding

### Problem Statements

- Bagaimana memprediksi penggunaan energi berdasarkan beberapa kondisi seperti temperatur, HVAC (Heating, Ventilation, and Air Conditioning), karakteristik bangunan, dan jumlah penghuni?
- Apa saja faktor terbesar dalam tingginya penggunaan energi?

### Goals

- Membangun model regresi machine learning berdasarkan faktor-faktor yang tersedia.
- Melakukan analisis dan identifikasi terhadap faktor yang paling berpengaruh dalam penggunaan energi.

### Solution Statements

- Menggunakan lima algoritma regresi:
  - SVR
  - Random Forest
  - Gradient Boosting
  - XGBoost
  - LightGBM

- Menggunakan Feature Importance untuk mengidentifikasi fitur yang paling berpengaruh.

## Data Understanding

Dataset: Energy Consumption (1000 data tahun 2022)

Link Dataset: [Energy Consumption Dataset](https://www.kaggle.com/datasets/mrsimple07/energy-consumption-prediction/code)

### Kondisi Data

- Tidak ada missing value
- Tidak ada duplikasi
- Terdapat outliers pada Energy Consumption

### Variabel dalam Dataset:

| Fitur                 | Tipe       | Deskripsi                                       |
|-----------------------|------------|-------------------------------------------------|
| TimeStamp             | datetime   | Waktu pengambilan data                          |
| Temperature           | numerik    | Temperatur                                      |
| Humidity              | numerik    | Kelembapan udara                                |
| SquareFootage         | numerik    | Ukuran bangunan                                 |
| Occupancy             | numerik    | Jumlah orang dalam bangunan                     |
| HVACUsage             | time       | Penggunaan HVAC                                 |
| LightningUsage        | kategorikal| Penggunaan lampu                                |
| RenewableEnergy       | numerik    | Penggunaan energi terbarukan                    |
| DayOfWeek             | kategorikal| Hari dalam seminggu                             |
| Holiday               | kategorikal| Apakah hari tersebut adalah hari libur          |
| EnergyConsumption     | numerik    | Total konsumsi energi                           |

## Exploratory Data Analysis

### Frekuensi pada Data Kategorikal

- Penggunaan lampu dan HVAC mode "on" lebih sedikit.
- Hari Jumat menunjukkan frekuensi permintaan energi yang tinggi.

### Korelasi Variabel Numerik

- Temperatur dan occupancy menjadi dua faktor utama penyebab naiknya konsumsi energi.

### Analisis Hari dalam Seminggu

- Konsumsi energi tertinggi terjadi pada hari Jumat.

## Data Preparation

1. Salin dataset menjadi `df_dummy` untuk menjaga keutuhan data asli.
2. Tangani outliers menggunakan metode IQR.
3. Drop fitur yang tidak berguna: timestamp, month, year.
4. OneHotEncoding pada fitur kategorikal.
5. Standardisasi fitur numerik kecuali target `EnergyConsumption`.
6. Splitting data:
   - X: semua fitur kecuali `EnergyConsumption`
   - Y: `EnergyConsumption`
   - Rasio train/test: 80/20, dengan random_state untuk replikasi

## Modeling

Menggunakan lima algoritma regresi untuk prediksi:

### SVR (Support Vector Regression)

- Parameter: default
- Kelebihan: menangkap hubungan non-linier, cocok untuk dataset kecil
- Kekurangan: tidak cocok untuk dataset besar, kurang interpretatif

### Random Forest

- Parameter: `random_state=42`
- Kelebihan: menangkap hubungan non-linier, robust terhadap noise
- Kekurangan: lambat pada dataset besar

### Gradient Boosting

- Parameter: default, `random_state=42`
- Kelebihan: akurat, cocok untuk model kompleks
- Kekurangan: sensitif terhadap noise

### XGBoost

- Parameter: default, `random_state=42`
- Kelebihan: efisien, mampu menangani missing value
- Kekurangan: tuning parameter kompleks, konsumsi resource tinggi

### LightGBM

- Parameter: default, `random_state=42`
- Kelebihan: sangat cepat dan cocok untuk data besar
- Kekurangan: overfitting dan sensitif terhadap distribusi fitur

## Evaluation

### Metrik Evaluasi

- MAE: Rata-rata kesalahan absolut
- RMSE: Akar dari rata-rata kuadrat kesalahan
- R2: Variansi yang dijelaskan oleh model

### Hasil Evaluasi

| Model              | MAE     | RMSE     | R2       |
|--------------------|---------|----------|----------|
| SVR                | 4.15    | 26.68    | 0.583    |
| Random Forest      | 4.05    | 27.27    | 0.574    |
| Gradient Boosting  | 4.22    | 28.25    | 0.559    |
| XGBoost            | 4.40    | 33.32    | 0.479    |
| LightGBM           | 4.28    | 30.71    | 0.520    |

**Relative MAE dan RMSE:**

| MAE     | RMSE    |
|---------|---------|
| 5.46%   | 39.17%  |

SVR memiliki performa terbaik dari sisi MAE, RMSE, dan R2 dibanding model lainnya, namun performanya masih dapat ditingkatkan dengan hyperparameter tuning.

![alt image](https://jie25.s-ul.eu/OPK27pOJ)

### Feature Importance

Berdasarkan hasil Random Forest, fitur dengan pengaruh terbesar:

- Temperature
- Renewable Energy
- Occupancy
- Humidity
- SquareFootage
- Hour

![alt image](https://camo.githubusercontent.com/ebea417317d9865a3adff5eb1e895f9c547aa69b0c166735f3ea07540a6244aa/68747470733a2f2f6a696532352e732d756c2e65752f64484c76514f5564)

## Dampak Terhadap Business Understanding

- Problem Statement 1 (Prediksi konsumsi energi) telah tercapai dengan model SVR sebagai model terbaik meskipun akurasi masih dapat ditingkatkan.
- Problem Statement 2 (Identifikasi faktor penyebab utama) telah dijawab melalui EDA dan feature importance yang menunjukkan pengaruh signifikan dari temperatur dan fitur lainnya terhadap konsumsi energi.

