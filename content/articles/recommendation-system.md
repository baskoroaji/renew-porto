---
title: "Anime Recommendation System – Content-Based Filtering"
description: "anime recommendation system for new user"
tags: ['Recommendation System', 'Content-Based Filtering']
published: 2025/04/14
author: 'Baskoro Aji'
slug: "recommendation-system"
---


**Author: Mohamad Baskoro Aji**

**Github: [Github Link](https://github.com/baskoroaji/anime-recommendation)**

##  Overview

Anime kini telah menjadi bagian penting dari industri hiburan global, tidak hanya untuk anak-anak, tetapi juga remaja hingga dewasa. Dengan ribuan judul yang tersedia, banyak orang merasa kesulitan menentukan tontonan yang cocok. Untuk menjawab tantangan ini, proyek ini membangun **sistem rekomendasi anime berbasis metadata** dengan pendekatan **content-based filtering**, tanpa memerlukan riwayat pengguna.

---

##  Dataset

- **Sumber:** [Anime Database for Recommendation System](https://www.kaggle.com/datasets/vishalmane109/anime-recommendations-database)
- **Jumlah Data:** 17.002 judul anime
- **Fitur Penting:**
  - `Title`, `Synopsis`, `Genre`, `Type`, `Rating`, `Popularity`, `Studio`, `Producer`

---

##  Data Preparation

### 1. Cleaning
- Menghapus duplikasi (63 entri)
- Menangani missing values:
  - **Numerik:** Diisi dengan nilai rata-rata (e.g., rating, popularity)
  - **Teks/List:** Diisi dengan 'unknown' atau `['unknown']`

### 2. Seleksi Fitur
Hanya mempertahankan fitur-fitur yang relevan untuk sistem rekomendasi:
- `Title`, `Synopsis`, `Genre`, `Type`, `Rating`, `Popularity`, `Studio`, `Producer`

---

##  Feature Engineering

### Teknik yang Digunakan
- **TF-IDF Vectorization** pada:
  - Genre (setelah di-join)
  - Type
  - Synopsis (dengan stopwords removal dan limit fitur 5000)
- **Stacking Fitur:** Menggabungkan semua representasi vektor menggunakan `hstack`
- **Cosine Similarity:** Untuk menghitung kesamaan antar anime

---

##  Modeling: Content-Based Filtering

### Mekanisme Rekomendasi
Fungsi `recommend()` menerima:
- `anime_name`: Judul referensi
- `anime_df`: Dataset
- `similarity_matrix`: Hasil cosine similarity
- `top_n`: Jumlah rekomendasi

### Langkah Proses
1. Temukan indeks dari judul referensi
2. Ambil skor kesamaan dari similarity matrix
3. Urutkan skor tertinggi
4. Ambil top-N anime yang paling mirip

---

##  Contoh Rekomendasi: "One Piece"

**Genre:** Action, Adventure, Comedy, Super Power, Drama, Fantasy, Shounen  
**Tipe:** TV Series

| Rank | Judul Anime                           | Genre Dominan                                            | Tipe      |
|------|----------------------------------------|-----------------------------------------------------------|-----------|
| 1    | Fullmetal Alchemist                   | Action, Adventure, Comedy, Drama, Fantasy, Magic, Shounen| TV        |
| 2    | Soul Eater                            | Action, Fantasy, Comedy, Supernatural, Shounen           | TV        |
| 3    | Cowboy Bebop                          | Action, Adventure, Comedy, Drama, Sci-Fi, Space          | TV        |
| 4    | Nanatsu no Taizai                     | Action, Adventure, Magic, Fantasy, Shounen               | TV        |
| 5    | Shingeki no Kyojin Season 2           | Action, Military, Drama, Super Power, Fantasy, Shounen   | TV        |
| 6    | Boku dake ga Inai Machi               | Mystery, Psychological, Seinen, Supernatural             | TV        |
| 7    | Kill la Kill                          | Action, Comedy, Super Power, Ecchi, School               | TV        |
| 8    | Another                               | Unknown                                                   | TV        |
| 9    | Psycho-Pass                           | Unknown                                                   | TV        |
| 10   | Sen to Chihiro no Kamikakushi         | Adventure, Supernatural, Drama                            | Movie     |

---

##  Evaluasi

### Metrik yang Digunakan
- **Precision@10**: 0.7
- **Recall@10**: 1.0
- **F1 Score**: 0.82

### Penjelasan:
- **Precision** menunjukkan bahwa 7 dari 10 rekomendasi adalah relevan.
- **Recall** berarti seluruh anime relevan berhasil ditemukan (100% coverage).
- **F1 Score** menggabungkan keduanya dan menunjukkan performa sistem secara seimbang.

![Precision Visualization](https://jie25.s-ul.eu/bueYPjrl)

---

##  Kesimpulan

- Sistem rekomendasi berhasil memberikan **rekomendasi yang relevan** meski tanpa histori pengguna.
- Model menunjukkan performa **cukup baik** dengan F1 Score sebesar **0.82**.
- Cocok untuk membantu **pengguna baru mengeksplorasi anime** berdasarkan genre dan sinopsis.

---

## 🔗 Referensi

- [History About Anime](https://irij-jakarta.com/history-about-anime/)
- [Short History of Anime](https://japancitytour.com/short-history-anime/)
- [The influence of anime as Japanese popular culture among art and design students](https://www.researchgate.net/publication/372845388_The_influence_of_anime_as_Japanese_popular_culture_among_art_and_design_students)

