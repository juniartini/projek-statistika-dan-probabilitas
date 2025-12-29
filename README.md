# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** `[NI KADEK JUNIARTINI]`
- **NIM:** `[2525091100]`
- **Program Studi:** `[SISTEM INFORMASI]`
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Proyek ini menggunakan dataset Startup SaaS yang berisi data kinerja
keuangan perusahaan rintisan berbasis layanan digital. Dataset ini
terdiri dari variabel numerik yang berkaitan dengan pendapatan dan biaya
operasional. Variabel yang dianalisis adalah
Pendapatan_Tahunan_Miliar_IDR sebagai total pendapatan tahunan
perusahaan dan Biaya_Akuisisi_Pelanggan_Juta_IDR sebagai biaya untuk
memperoleh pelanggan. Tujuan analisis adalah mengetahui distribusi
pendapatan startup, menguji kenormalan data pendapatan, serta
menganalisis hubungan antara biaya akuisisi pelanggan dan pendapatan
tahunan.
---

## 3. Struktur Proyek

-   data : berisi dataset mentah yang digunakan untuk analisis.

-   scripts : berisi semua skrip R yang digunakan dalam analisis dan
    diurutkan berdasarkan alur kerja.

-   results : berisi output dari analisis, seperti plot, gambar, atau
    tabel ringkasan.

-   README.md : berisi dokumentasi project.

---

## 4. Cara Menjalankan Analisis

1. Instalasi package: install.packages(c("tidyverse", "ggplot2", "readr"))
2. urutan menjalankan Script: 
- 01_data_preparation.R
- 02_analisis_deskriptif.R
- 03_uji_asumsi.R
- 04_analisis_korelasi.R
- 05_analisis_regresi.R

---

## 5. Hasil dan Interpretasi


### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
a) Mean (rata-rata) sebesar 31,88 miliar IDR
b) Median sebesar 30,50 miliar IDR
c) Modus sebesar 28 miliar IDR
Nilai mean yang sedikit lebih besar dari median menunjukkan bahwa terdapat beberapa perusahaan dengan pendapatan yang relatif tinggi sehingga menarik nilai rata-rata ke arah kanan. Median sebesar 30,50 miliar IDR menunjukkan bahwa sekitar 50% startup memiliki pendapatan tahunan di bawah nilai tersebut, sedangkan modus sebesar 28 miliar IDR menunjukkan nilai pendapatan yang paling sering muncul dalam dataset.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
a) Standar deviasi pendapatan sebesar ±12,40 miliar IDR
b) Range pendapatan berada pada kisaran 8 miliar IDR hingga 65 miliar IDR
c) Kuartil pertama (Q1) berada di sekitar 22 miliar IDR, sedangkan kuartil ketiga (Q3) berada di sekitar 41 miliar IDR
Nilai standar deviasi yang cukup besar menunjukkan bahwa pendapatan antar startup sangat bervariasi. Range yang lebar memperlihatkan adanya perbedaan skala bisnis yang signifikan, mulai dari startup dengan pendapatan relatif kecil hingga startup dengan pendapatan yang jauh lebih besar.
- **Visualisasi (Histogram/Boxplot):**
Histogram pendapatan menunjukkan distribusi data yang tidak sepenuhnya simetris dan cenderung menyebar ke kanan. Hal ini mengindikasikan adanya beberapa perusahaan dengan pendapatan tinggi. Sementara itu, boxplot memperlihatkan sebaran data yang cukup luas tanpa adanya outlier ekstrem.
Dari kedua visualisasi tersebut, dapat disimpulkan bahwa distribusi pendapatan startup cukup bervariasi dan tidak mengikuti pola distribusi normal secara sempurna.

### 5.2. Uji Normalitas
1. Q-Q plot: titik-titik tidak mengikuti garis diagonal secara sempurna
2. Statistik W: 0.94664
3. p-value = 1.497e-14 (≈ 0)
Uji normalitas dilakukan menggunakan uji Shapiro–Wilk dan Q-Q plot. Hasil uji Shapiro–Wilk menunjukkan nilai p-value < 0,05, sehingga hipotesis nol ditolak. Hal ini berarti data pendapatan tahunan tidak terdistribusi normal. Hasil Q-Q plot juga memperlihatkan bahwa titik-titik data tidak sepenuhnya mengikuti garis diagonal, terutama pada bagian ekor distribusi. Temuan ini memperkuat hasil uji statistik bahwa distribusi data pendapatan tidak normal.
### 5.3. Analisis Korelasi
Variabel:
- X: Pendapatan_Tahunan_Miliar_IDR
- Y: Nilai_Pelanggan_Juta_IDR
Hasil:
- Koefisien korelasi (r) = 0.997
- Arah hubungan: Positif
- Kekuatan: Kuat
- p-value =  2.2e-16 (≈ 0)(signifikan)
Nilai tersebut menunjukkan adanya korelasi positif yang sangat kuat dan signifikan. Scatter plot yang dihasilkan juga memperlihatkan pola hubungan linear yang jelas, di mana peningkatan biaya akuisisi pelanggan diikuti oleh peningkatan pendapatan tahunan perusahaan.


### 5.4. Analisis Regresi
Pendapatan_Tahunan=2,15+0,48×Biaya_Akuisisi_Pelanggan
Interpretasi dari model tersebut adalah bahwa ketika biaya akuisisi pelanggan bernilai nol, pendapatan tahunan diperkirakan sebesar 2,15 miliar IDR. Selain itu, setiap kenaikan 1 juta IDR biaya akuisisi pelanggan diperkirakan akan meningkatkan pendapatan tahunan sebesar 0,48 miliar IDR.
Nilai Adjusted R² sebesar 0,991 menunjukkan bahwa sekitar 99,1% variasi pendapatan tahunan dapat dijelaskan oleh biaya akuisisi pelanggan. Hal ini menunjukkan bahwa model regresi yang dibangun memiliki kemampuan penjelasan yang sangat baik.

---

## 6. Kesimpulan

Berdasarkan seluruh analisis yang telah dilakukan, dapat disimpulkan bahwa pendapatan tahunan startup dalam dataset ini memiliki variasi yang cukup tinggi dan tidak terdistribusi normal. Meskipun demikian, hubungan antara biaya akuisisi pelanggan dan pendapatan tahunan terbukti sangat kuat dan signifikan. Analisis korelasi dan regresi menunjukkan bahwa biaya akuisisi pelanggan berperan besar dalam meningkatkan pendapatan perusahaan. Dengan nilai koefisien determinasi yang sangat tinggi, model regresi linear sederhana yang dibangun mampu menjelaskan hampir seluruh variasi pendapatan tahunan, sehingga hasil analisis ini dapat memberikan gambaran yang jelas mengenai pentingnya strategi akuisisi pelanggan dalam pertumbuhan startup.
