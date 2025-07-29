---
title: "Predicting Student Dropout – Jaya Jaya Learning"
description: "dropout factor student"
tags: ['Predictive Model', 'Data Science', 'BI', 'Metabase']
published: 2025/04/23
author: 'Baskoro Aji'
slug: "student-dropout"
---

**Github: [Github Link](https://github.com/baskoroaji/student_performance)**

##  Business Understanding

**Jaya Jaya Learning** adalah perusahaan Edutech yang menyediakan platform pembelajaran daring untuk mahasiswa program sarjana dari berbagai jurusan. Misi utama perusahaan adalah menurunkan angka **dropout** dan meningkatkan tingkat **kelulusan** melalui **intervensi tepat waktu** berbasis data.

###  Permasalahan Bisnis

1. **Tingginya Angka Dropout**  
   Institusi kesulitan mengidentifikasi faktor penyebab utama dropout mahasiswa.

2. **Kurangnya Pemantauan Real-Time**  
   Tidak tersedia sistem yang dapat mendeteksi risiko secara proaktif.

3. **Intervensi Terlambat**  
   Tim akademik hanya mengetahui masalah saat performa akademik sudah sangat rendah.

---

##  Dataset

- `students_performance.csv`  
  Jumlah data: 4.424 baris, 37 kolom  
  Berisi: informasi demografi, nilai akademik semester 1 & 2, serta status akhir (`Dropout`, `Enrolled`, `Graduate`)  
- 📥 [Link Dataset](https://github.com/dicodingacademy/dicoding_dataset/blob/main/students_performance/data.csv)

---


**Berikut adalah Link demo menggunakan streamlit:**

https://studentperformance-eqensdkgjrsgndmse4bwao.streamlit.app/

## Business Dashboard – Metabase
Dashboard berjudul "Student Risk Insights" telah dibangun dengan 7 kartu visualisasi utama:

1. Jumlah Mahasiswa berdasarkan status (Dropout, Graduate, Enrolled)

2. Rata-rata nilai saat masuk (Admission grade) berdasarkan status

3. Rata-rata nilai semester 1 & 2 berdasarkan status

4. Persentase beasiswa (Scholarship holder)

5. Distribusi jenis kelamin mahasiswa berdasarkan status

6. Status pernikahan mahasiswa berdasarkan status

7. Kelas (waktu pengambilan kuliah) dan dropout rate

## Screenshot Dashboard

![alt image](https://jie25.s-ul.eu/5xKsJJKk)
![alt image](https://jie25.s-ul.eu/qE4MXBxF)
![alt image](https://jie25.s-ul.eu/AMmqOOQb)

## Hasil & Kesimpulan
- Model dapat memprediksi risiko dropout mahasiswa dengan akurasi hingga 77%

- Dashboard Metabase membantu akademik mengenali mahasiswa berisiko tinggi lebih awal

- Faktor-faktor signifikan penyebab dropout:

- Nilai semester 1 & 2 rendah

- Usia mahasiswa > 25 tahun

- Mahasiswa kelas pagi/siang (memiliki dropout rate hingga 85%)

- Status pernikahan (single/married/divorced)

- Potensi mahasiswa bekerja sambil kuliah

### Rekomendasi Tindak Lanjut
1. Intervensi Mahasiswa dengan Nilai Rendah (< 10)
    Ajukan konseling via dosen pembimbing akademik

2. Konseling Berdasarkan Gender
    Tindak lanjuti lebih lanjut untuk mahasiswa perempuan (karena dropout sedikit lebih tinggi)

3. Kelas dengan Tingkat Dropout Tinggi
    Paketkan kelas dasar (SKS awal) untuk memudahkan transisi mahasiswa baru

4. Mahasiswa Senior (> semester 10)
    Pantau dan dorong penyelesaian skripsi/TA secepatnya melalui dosen pembimbing

5. Marital Status Support
    Konseling khusus bagi mahasiswa menikah/cerai agar tetap bisa menyelesaikan studi

6. Survey Mahasiswa yang Bekerja Sambil Kuliah
    Evaluasi jam kuliah fleksibel dan workload akademik untuk mahasiswa yang bekerja