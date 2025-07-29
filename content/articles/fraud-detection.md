---
title: "Fraud Detection using machine learning"
description: "Menyelesaikan Permasalahan Perbankan di sektor Keamanan"
tags: ['Clustering', 'Classification', 'Banking Fraud']
published: 2025/03/17
author: 'Baskoro Aji'
slug: "fraud-detection"
---

**Github Link: [Github Link](https://github.com/baskoroaji/fraud-detection)**

# Background
Pada zaman sekarang, bank menjadi primadona dalam menyimpan uang orang orang sudah tidak lagi menyimpan uang di balik bantal ataupun di celengan
dari orang tua hingga anak muda di zaman sekarang kebanyakan sudah memiliki akses ke bank, akan tetapi muncul permasalahan baru. Orang orang
melakukan kejahatan seperti mencuri atau menipu tidak menggunakan cara konvensional, mungkin dulu orang mencuri mendobrak masuk ke rumah orang akan tetapi
sekarang orang mencuri/menipu bisa menggunakan akun atau simpanan bank orang lain. 
Dengan bantuan machine learning bank dapat melihat siapa saja yang melakukan transaksi mencurigakan

# Dataset
[Bank_transaction_dataset.csv](https://github.com/baskoroaji/fraud-detection/blob/main/bank_transactions_data_2.csv)

# Machine Learning
Dengan menggunakan algoritma clustering dan klasifikasi dapat disimpulkan

## Analisis Karakteristik Cluster dari Model KMeans dan DBscan
Berikut adalah analisis karakteristik untuk setiap cluster yang dihasilkan dari model KMeans.

![alt image](https://jie25.s-ul.eu/u8rQw5qc)
![alt image](https://jie25.s-ul.eu/nA3YthWd)
![alt image](https://jie25.s-ul.eu/aisRXbb1)
![alt image](https://jie25.s-ul.eu/WDTwLuyy)
1. Cluster -1:
    Rata-rata login attempt 3

    Rata-rata Durasi Transaksi: 128detik

    Analisis: Cluster ini mencakup outliers atau noise pada data dimana bisa jadi terindikasi fraud atau potential fraud dilihat dari pola login attempt dan durasi transaksi dimana lebih dari satu dan durasi transaksi yang lumayan lama tetapi tidak menutup kemungkinan bahwa terdapat transaksi yang legal dimana minimum login attempt 1 dan durasi transaksi amount yang sangat sedikit

2. Cluster 0:
    Rata-rata login attempt 1

    Rata-rata Durasi Transaksi: 119detik

    Analisis:Cluster ini mencakup customer dengan transaksi yang bukan fraud dimana login attempt hanya 1 dan proses transaksi yang sangat cepat yang dimana pada cluster ini customer melakukan transaksi secara legal parameter yang bisa dilihat lainnya adalah penggunaan kartu debit dan kredit yang lumayan besar, di dominasi oleh pelajar, dan transaction amount yang berada lebih kecil dari cluster -1

3. Cluster 1:
    Rata-rata login attempt 4

    Rata-rata Durasi Transaksi: 134detik

    Analisis:Cluster ini mencakup customer dengan transaksi yang fraud dimana login attempt rata 4 kali login attempt ini merupakan anomali dan proses transaksi yang sangat banyak menggunakan kartu debit daripada penggunaan kartu kredit dimana menjadi indikasi awal bahwa itu adalah fraud dan penggunaan mesin atm sebagai alat transaksi

Kesimpulan & Implikasi Bisnis
Berdasarkan analisis di atas, kita dapat menyimpulkan bahwa ada segmentasi pelanggan yang jelas:

1. Cluster -1 adalah customer yang memiliki kemungkinan melakukan fraud
2. Cluster 0 adalah customer yang melakukan transaksi secara legal
3. Cluster 1 adalah customer yang melakukan fraud

## Analisis model klasifikasi
### Confussion Matriks Sebelum Tuning
![alt image](https://jie25.s-ul.eu/ynna40yY)
![alt image](https://jie25.s-ul.eu/vr596ApJ)
### Confussion Matriks Setelah Tuning
![alt image](https://jie25.s-ul.eu/ss7FyPMa)
![alt image](https://jie25.s-ul.eu/W4NHRdH9)
Perbandingan Evaluasi Sebelum dan Setelah Tuning
1. Logistic Regression, sebelum dilakukan tuning logistic regression memiliki akurasi 97% dan f1 score 97% dan dari conffusion matrix terdapat kesalahan klasifikasi yang dimana adanya false positive dan false negative dan ketika di tuning akurasi dan f1 score naik ke 98% tetapi masih dengan masalah yang sama yaitu adanya kesalahan klasifikasi

2. Random Forest, sebelum dilakukan tuning random forest sudah memiliki hasil yang sangat bagus yaitu akurasi 99.6% dan f1-score 99.5% dan masih dengan masalah yang sama yaitu kesalahan klasifikasi, setelah di tuning akurasi dan f1 score naik ke 99.7% akan tetapi masih meninggalkan kesalahan klasifikasi pada conffusion matrix

Kelemahan model
- recall dan precision, recall dan precision mengalami kesalahan apalagi sebelum tuning, random forest dan logistic regression banyak mengalami kesalahan klasifikasi pada kelas 1/ cluster 1

- overfitting dan underfitting, tidak ada indikasi overfitting atau underfitting setelah tuning model

### Rekomendasi Tindak Lanjut
- Kelas yang tidak seimbang, untuk lebih meningkatkan performa disarankan menggunakan smote untuk menambahkan data latih
Eksplorasi Algoritma Lain, disarankan adanya ekplorasi algoritma lain seperti SVM
Eksplorasi Tuning Lain, disarankan untuk melakukan metode tuning lain seperti bayesian_optimization
kesimpulan

- kedua model memiliki performa yang bagus untuk dataset walaupun masih adanya kesalahan klasifikasi dan model ini memberikan nilai akurasi dan f-1 score di 98% dan 99.7% yang dimana hampir mendekati 1