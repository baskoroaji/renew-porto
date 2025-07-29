---
title: "Sentiment Analysis Identitas Kependudukan Digital"
description: "Analisis Sentimen aplikasi IKD"
tags: ['Sentiment Analysis', 'NLP', 'LLM', 'Data Scraping']
published: 2025/03/24
author: 'Baskoro Aji'
slug: "sentiment-analysis"
---

## Background
IKD atau Identitas Kependudukan Digital merupakan aplikasi yang dirilis oleh Ditjen Dukcapil Kemendagri.
Aplikasi ini sudah mencapai 10 juta download dan sudah mencapai 65,6 ribu ulasan di playstore. Akan tetapi
rating di playstore mereka sangat rendah yaitu di 3 bintang dari 5 bintang, dengan menggunakan analisis sentiment
kita dapat mengetahui bagaimana distribusi polaritas(negatif, netral, positif) sebuah review pada aplikasi ini, selain itu dengan bantuan
machine learning dapat memprediksi apakah sentimen yang dikeluarkan merupakan positif,netral atau negatif.

## Hasil Polaritas Sentimen
![alt image](https://jie25.s-ul.eu/WRQQq8GH)
bisa dilihat bahwa kebanyakan review dari user playstore memberikan review negatif ini membuktikan bahwa aplikasi
masih kurang bagus atau masih memiliki banyak bug yang membuat user kesulitan dengan menggunakan aplikasi ini.

## Model
1. Menggunakan Logistic Regression dan TF-IDF
    dengan rasio train test 70/30 dapat menghasilkan
    ```
    acc sebelum tuning
    train: 93%
    test: 91%

    acc setelah tuning
    test accuracy: 92%
    ```

2. Menggunakan Random Forest dan Word2Vec
    dengan rasio train test 70/30 dapat menghasilkan
    ```
    akurasi
    train: 99%
    test: 82%
    ```
3. LSTM deep learning dengan rasio train test 80/20

    mendapatkan akurasi sebesar: 93%
    ![alt image](https://jie25.s-ul.eu/AtTJZLDQ)