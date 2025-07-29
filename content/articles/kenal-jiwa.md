---
title: "KENAL JIWA : Solusi Screening mental health Gen Z"
description: "Menyelesaikan Permasalahan Mental Health Gen Z"
published: 2025/06/18
tags: ['Capstone Project', 'Mental Health', 'Predictive Model', 'Classification']
author: 'Baskoro Aji'
slug: "kenal-jiwa"
---

# Problem
Gangguan kesehatan mental di kalangan remaja dan dewasa muda menjadi isu serius di seluruh dunia. WHO melaporkan bahwa sekitar 1 dari 7 remaja usia 10-19 tahun mengalami gangguan mental (World Health Organization, 2024). Depresi, kecemasan, dan gangguan perilaku menduduki peringkat utama penyebab permasalahan pada kelompok umur ini. Di sisi lain, bunuh diri merupakan penyebab kematian urutan ke-3 bagi usia 15-29 tahun secara global (World Health Organization, 2024). Ketimpangan ini diperparah oleh stigma sosial, kurangnya literasi kesehatan mental, dan keterbatasan akses layanan konvensional membuat banyak masalah kesehatan mental anak muda tidak terdeteksi dan ditangani secara menyeluruh, khususnya di negara berkembang. Kondisi mental yang buruk di usia muda dapat mengganggu prestasi pendidikan, produktivitas dan keterlibatan sosial kelompok remaja di masa depan (Patel et al., 2018). Lancet Commission dan WHO menekankan bahwa memajukan kesehatan mental adalah bagian penting dari tujuan Sustainable Development Goals (SDGs) 3.4 tentang promotif kesehatan mental (World Health Organization, 2016). Hal ini menunjukkan bahwa peningkatan kesehatan mental anak muda tidak hanya berdampak pada kesejahteraan individu, tetapi juga berkontribusi pada kemajuan pendidikan, kesetaraan gender, dan pertumbuhan ekonomi nasional.

Situasi ini tercermin pula di Indonesia. Survei Riset Kesehatan Dasar (Riskesdas) tahun 2018 menunjukkan bahwa 6,2% penduduk berusia 15-24 tahun mengalami depresi (Kementerian Kesehatan Republik Indonesia, 2023). Survey lain yang telah dilakukan oleh Indonesia-National Adolescent Mental Health Survey (I-NAMHS) pada tahun 2022 menunjukkan bahwa sekitar 1 dari 3 remaja (34,9 %) atau setara dengan 15,5 juta anak muda di Indonesia mengalami masalah kesehatan mental, namun hanya 2,6% di antaranya yang pernah mengakses layanan dukungan atau konseling untuk masalah emosi (Indonesia – National Adolescent Mental Health Survey, 2023). Temuan ini mengindikasikan adanya kesenjangan serius antara prevalensi gangguan dan intervensi yang tersedia, serta menguatkan kebutuhan akan solusi yang adaptif dan menjangkau kelompok usia ini secara tepat. Pemerintah berupaya dengan melakukan inisiasi seperti Swaperiksa PDSKJI dan fitur screening pada SATUSEHAT Mobile (Kemenkes) telah diluncurkan sebagai bentuk intervensi digital. Namun, kedua platform ini masih terbatas dalam hal user targeting dan belum sepenuhnya mengadopsi pendekatan berbasi pengalaman pengguna yang interaktif.

Oleh karena itu, Kenal Jiwa hadir sebagai solusi dalam bentuk website asesmen digital berbasis AI yang ditujukan bagi kalangan Gen Z dan dibawahnya. Alasan utama pemilihan target ini adalah karena kelompok usia ini sedang berada di fase rentan secara psikososial, menghadapi tekanan akademik, sosial, identitas diri, serta merupakan digital native yang lebih responsif terhadap pendekatan teknologi. Dalam konteks SDGs, solusi ini mendukung tujuan 3: Kehidupan Sehat dan Sejahtera, terutama pada indikator 3.4 terkait pengurangan mortalitas akibat gangguan mental dan peningkatan pencegahan bunuh diri

# Permasalahan Bisnis
1. Apakah model machine learning ini dapat bekerja dengan baik dalam pengujian ketika menentukan kondisi keadaan kesehatan mental seseorang?
2. Seberapa tinggi akurasi dari model machine learning (ex: Random Forest, Logistic Regression, XGBoost) dalam mengklasifikan depresi dan anxiety pada populasi Gen Z Indonesia?
3. Algoritma ML (bandingkan 2 algoritma seperti Random Forest, XGBoost, Logistic Regression, dll) mana yang menghasilkan performa terbaik dalam memprediksi status depresi dan kecemasan pada populasi Gen Z Indonesia?

# Sumber Data

**Sumber data**:  
- Depression Dataset: [Depression Dataset](https://www.kaggle.com/datasets/adilshamim8/student-depression-dataset)
- Anxiety Dataset: [Anxiety Dataset](https://www.kaggle.com/datasets/natezhang123/social-anxiety-dataset)

# Bentuk Aplikasi
![alt image](https://jie25.s-ul.eu/PO33inBq)
### Presentation Link
<a href="https://youtu.be/p8kE8Hb5dyA" target="_blank">
 <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/YouTube_full-color_icon_%282017%29.svg/2560px-YouTube_full-color_icon_%282017%29.svg.png" alt="Watch the video" width="30" height="24" />
</a>

### Demo Application Link
<a href="https://drive.google.com/file/d/1sOjm2-yxNYm4FT6Y6fdaQ2_LbHA8Ly6o/view?usp=sharing" target="_blank">
 <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/YouTube_full-color_icon_%282017%29.svg/2560px-YouTube_full-color_icon_%282017%29.svg.png" alt="Watch the video" width="30" height="24" />
</a>

**Streamlit [Link](https://kenal-jiwa-app.streamlit.app/)**

# PASAR TARGET
1. Usia 15–24 tahun, pelajar dan mahasiswa, terutama Gen Z yang aktif secara digital dan rentan terhadap tekanan emosional, sosial, dan akademik.
2. Mengapa target pasar Anda membutuhkan solusi ini? Karena rendahnya literasi kesehatan mental, stigma terhadap konsultasi psikologi, dan mahalnya layanan profesional membuat asesmen mandiri berbasis data menjadi solusi alternatif yang realistis dan inklusif.
    Data nasional (Riskesdas, I-NAMHS)
    Agenda SDGs 3.4
    Kebutuhan solusi teknologi berbasis data
    Aksesibilitas tinggi teknologi bagi Gen Z
    Stakeholder terkait: Kemenkes, lembaga pendidikan, organisasi kesehatan jiwa, dan startup teknologi kesehatan.

# Analisis lanjutan SWOT dari proyek
- Kekuatan: Antarmuka ringan, model fleksibel, tidak bergantung pada kuesioner psikologis formal.
- Kelemahan: Tingkat akurasi bergantung pada kualitas data survei, bukan diagnosis klinis.
- Peluang: Dapat dikembangkan untuk versi mobile dan API prediksi cepat.
- Ancaman: Kesalahpahaman pengguna terkait hasil, serta risiko interpretasi tanpa edukasi.

