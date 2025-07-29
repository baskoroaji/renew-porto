---
title: "Predictive Analytics for Employee Attrition at Jaya Jaya Maju"
description: "Menyelesaikan Permasalahan Keluarnya Karyawan"
tags: ['Predictive Model', 'Data Science', 'Classfication', 'BI', 'Metabase']
published: 2025/04/21
author: 'Baskoro Aji'
slug: "hr-attrition-rate"
---

**Github: [Github Link](https://github.com/baskoroaji/Human-Resource)**

##  Business Background

**Jaya Jaya Maju** adalah perusahaan multinasional yang telah berdiri sejak tahun 2000 dengan lebih dari 1.000 karyawan di seluruh Indonesia. Meskipun perusahaan berkembang pesat, **tingkat attrition (pengunduran diri)** yang melebihi 10% per tahun menjadi masalah serius yang memengaruhi produktivitas dan efisiensi biaya.

---

##  Permasalahan Bisnis

1. **Tingginya Tingkat Attrition**  
   - Pengunduran diri memengaruhi stabilitas tim dan produktivitas.

2. **Kurangnya Pemahaman atas Faktor-Faktor Penyebab**  
   - Tidak ada analisis mendalam terhadap penyebab karyawan keluar.

3. **Tidak Tersedianya Sistem Monitoring**  
   - HR kesulitan mengantisipasi risiko sebelum karyawan resign.

4. **Pengambilan Keputusan Kurang Berbasis Data**  
   - Keputusan strategis dilakukan tanpa bantuan sistem prediksi.

---

###  Dataset
- [Dicoding Employee Dataset](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

### Dashboard Bisnis (Metabase)
Dashboard “HR Employee Attrition Insight” menyajikan visualisasi sebagai berikut:

1. Total & Persentase Attrition

2. Attrition berdasarkan Departemen & Job Role

3. Overtime Impact on Attrition

4. Attrition by Gender & Distance from Home

5. Monthly Rate vs Attrition

6. Rata-rata Masa Kerja & Perusahaan Sebelumnya


### Screenshot Dashboard
Berikut ini adalah contoh tampilan dari dashboard interaktif:
![alt image](https://jie25.s-ul.eu/K7bXm3K4)

![alt image](https://jie25.s-ul.eu/bInyVcze)

![alt image](https://jie25.s-ul.eu/DNKvuJjt)
### Evaluasi Model
1. **Logistic Regression**

---
      Precision: 86%

      Recall: 73%

      F1 Score: 76%

2. **Random Forest**

---
      Precision: 85%

      Recall: 86%

      F1 Score: 85%

Model Random Forest menunjukkan performa paling stabil dan akurat untuk prediksi attrition.

### Insight & Rekomendasi Strategis

Berdasarkan hasil modeling dan visualisasi, diperoleh insight penting berikut:

1. Departemen Berisiko Tinggi
   R&D dan Sales memiliki tingkat attrition tertinggi.
   Rekomendasi: Berikan bonus atau career path yang lebih jelas.

2. Gender (Laki-laki)
   Karyawan pria memiliki kecenderungan attrition lebih tinggi.
   Rekomendasi: Tinjau kebijakan dan hak kerja berbasis gender.

3. Overtime (Lembur)
   Karyawan dengan jam lembur tinggi lebih berisiko keluar.
   Rekomendasi: Batasi jam lembur, sediakan insentif dan konseling.

4. Jarak dari Rumah
   Karyawan yang tinggal jauh lebih berisiko resign.
   Rekomendasi: Berikan uang transportasi atau subsidi tempat tinggal.

5. Pengalaman Kerja Sebelumnya
   Karyawan dengan pengalaman di 1–2 perusahaan cenderung lebih cepat resign.
   Rekomendasi: Fokus rekrutmen pada kandidat dengan loyalitas kerja tinggi.

### Kesimpulan
Dengan menggabungkan kekuatan analisis data, machine learning, dan dashboard interaktif, proyek ini berhasil menyediakan sistem untuk:

- Memprediksi risiko attrition dengan akurasi tinggi

- Memberikan insight visual untuk HR dan manajemen

- Membantu pengambilan keputusan berbasis data

- Model dapat digunakan sebagai dasar dalam strategi retensi karyawan di perusahaan Jaya Jaya Maju ke depannya.

