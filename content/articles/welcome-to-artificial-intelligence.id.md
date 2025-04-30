---
title: "Welcome to Artificial Intelligence"
date: 2025-04-30T10:31:44+07:00
draft: false
---

# Pengantar Kecerdasan Buatan

| Kecerdasan Alamiah | Kecerdasan Buatan |
| ----------------------------------------------- | --------------------------------------------------------- |
| tugas tersebut dilakukan oleh manusia dengan menggunakan Kecerdasan | jika kita menambahkan kecerdasan alami manusia ini ke dalam sebuah mesin |

Kecerdasan Buatan adalah
> Ilmu Pengetahuan dan Rekayasa untuk membuat Mesin Cerdas
> ~ John McCarthy

# Peta Jalan Menuju Kecerdasan Buatan
![Peta Jalan Menuju AI](https://i.imgur.com/cqIX8Ea.png)
## 1. Bahasa Pemrograman
- Python
- R
- Lisp
- Prolog
- Java

## 2. Pengetahuan Matematika
- Aljabar Linier
- Probabilitas dan Distribusi
- Statistika
- Kalkulus Vektor
- Dekomposisi Matriks

## 3. Algoritma Pembelajaran Mesin
> Algoritma adalah metode langkah demi langkah untuk memecahkan masalah

| Klasifikasi | Algoritma | |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Pembelajaran Terbimbing | Pohon Keputusan<br>Klasifikasi Naif Bayes<br>Regresi Kuadrat Terkecil Biasa<br>Regresi Logistik<br>Mesin Vektor Pendukung<br>Metode Ensemble | |
| Pembelajaran Tanpa Pengawasan | Algoritma Pengelompokan<br>Analisis Komponen Utama<br>Dekomposisi Nilai Singular<br>Algoritma Dijkstra | |

## 4. Alat Pembelajaran Mesin
- TensorFlow Google
- Obor
- Microsoft Cognitive Toolkit
- IBM Watson
- Amazon Web Services
- Accord.NET Framework
- Caffe
- Eclipse Deeplearning4j
- Apache Mahout
- Theano
- H20
- PredictionlO
- ai-one
- Protégé
- DiffBlue
- Nervana Neon
- OpenNN
- Veles
- Scikit-learn
## 5. Studi Kasus AI
- Prediksi Harga Properti
- Sistem Pengenalan Gambar
- Prediksi Cuaca
- Mobil Self-Driving
- Komposisi Musik Otomatis
- Diagnosis Penyakit Medis
- Mengidentifikasi Berita Palsu
- Rekomendasi Buku

# Pembelajaran Mesin

| Algoritma Pembelajaran Mandiri | Pembelajaran Mesin |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Algoritma Pembelajaran Mandiri adalah algoritma yang akan belajar sendiri dan mengambil keputusan/prediksi sendiri | Pembelajaran mesin adalah bagian dari Kecerdasan Buatan. Yang bekerja berdasarkan algoritma pembelajaran mandiri menggunakan pengalaman masa lalu atau kumpulan data tanpa diprogram secara eksplisit. |

> Pembelajaran mesin adalah ilmu untuk membuat komputer bertindak tanpa diprogram secara eksplisit
> ~ Stanford

> Algoritma pembelajaran mesin dapat mengetahui cara melakukan tugas-tugas penting dengan melakukan generalisasi dari contoh-contoh.
> ~ Universitas Washington

> Pembelajaran mesin didasarkan pada algoritma yang dapat belajar dari data tanpa bergantung pada pemrograman berbasis aturan.
> ~ McKinsey & Co.

| Pembelajaran Terbimbing | Pembelajaran Tanpa Pengawasan | Pembelajaran Penguatan |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| Ini menyimpulkan fungsi dari data berlabel dan menggunakan fungsi ini pada contoh baru/data yang belum pernah dilihat/data uji. | Ini adalah pelatihan algoritma kecerdasan buatan menggunakan informasi yang tidak diklasifikasikan atau diberi label dan memungkinkan algoritma untuk bertindak atas informasi tersebut tanpa panduan | Ini memungkinkan agen untuk belajar dalam lingkungan interaktif dengan coba-coba menggunakan umpan balik dari tindakan dan pengalamannya sendiri |

## Pembelajaran Terbimbing
![Pembelajaran Terbimbing](https://i.imgur.com/ZyX38Ty.png)
### Keluaran Pembelajaran Terbimbing

| | Klasifikasi | Regresi<br> |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definisi | Algoritma klasifikasi digunakan ketika keluaran yang diinginkan adalah label<br>Diskrit. Disebut sebagai Klasifikasi Biner (Hanya dua<br>kemungkinan hasil) | Algoritma regresi digunakan ketika keluaran yang diinginkan adalah nilai Riil atau Kontinu (Kuantitas) |
| Contoh | 1. saat memfilter email "spam" atau "bukan spam"<br>2. saat melihat data transaksi, "penipuan", atau "resmi" | 1. Memprediksi harga rumah berdasarkan area<br>2. Memprediksi jumlah salinan album musik yang akan terjual bulan depan |
| Model | - Regresi Logistik<br>- Pohon Keputusan<br>- Pohon yang Didorong Gradien<br>- Perseptron Multilapis<br>- Satu-vs-yang-lain<br>- Naive Bayes<br>- Aproksimasi Kernel<br>- K-Nearest Neighbors<br>- Support Vector Machine<br>- Random Forest | - Regresi Kuadrat Terkecil Biasa (OLSR)<br>- Regresi Linier<br>- Regresi Bertahap<br>- Spline Regresi Adaptif Multivariat (MARS)<br>- Pemulusan Plot Sebar yang Diperkirakan Secara Lokal (LOESS)<br>- Hutan Acak |

## Pembelajaran Tanpa Pengawasan
![Pembelajaran Tanpa Pengawasan](https://i.imgur.com/84QJK4O.png)
### Hasil Pembelajaran Tanpa Pengawasan

| | Pengelompokan | Pengurangan Dimensionalitas |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Contoh | - Sistem Rekomendasi<br>- Pemasaran Bertarget<br>- Segmentasi Pelanggan<br>- Merekomendasikan produk kepada pelanggan berdasarkan pembelian sebelumnya | - Visualisasi Data Besar<br>- Kompresi yang Bermakna<br>- Penemuan Struktur<br>- Penggalian Fitur |

### Daftar Algoritma Tanpa Pengawasan
- K-Means, K-Medoids Fuzzy C-Means
- Hirarkis
- Campuran Gaussian
- Jaringan Syaraf Tiruan
- Model Markov Tersembunyi

## Pembelajaran Penguatan
![Pembelajaran Penguatan](https://i.imgur.com/jeqhXPj.png)
### Jenis Tugas

| | Tugas Episodik<br> | Tugas Berkelanjutan |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definisi | Memiliki titik awal dan titik akhir (keadaan terminal). Ini menciptakan episode - daftar Keadaan, Tindakan, Penghargaan, dan Keadaan Baru. | Tugas ini akan berlanjut selamanya (Tidak ada keadaan terminal). Agen harus mempelajari cara memilih tindakan terbaik dan secara bersamaan berinteraksi dengan lingkungan. |
| Contoh | Super Mario<br>Begin: Episode dimulai saat peluncuran<br>Ending: saat Anda terbunuh atau<br>mencapai akhir level | Perdagangan saham otomatis |

### Jenis Pembelajaran

| Pendekatan Monte Carlo<br> | Pembelajaran Perbedaan Temporal<br> |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Mengumpulkan hadiah di akhir episode dan kemudian menghitung hadiah masa depan maksimum yang diharapkan<br> | Ini akan memperbarui estimasi nilainya untuk status non-terminal yang terjadi pada pengalaman tersebut.<br> |
| Kami memulai permainan baru dengan pengetahuan tambahan. Agen membuat keputusan yang lebih baik dengan setiap iterasi | Ini juga disebut TD(O) atau one step TD |

### Daftar Algoritma Pembelajaran Penguatan
- Monte Carlo
- Q-Learning
- Q-Learning dengan Fungsi Keunggulan Ternormalisasi NAF
- State-Action-Reward-State-Action (SARSA)
- Deep Q Network (DQN)
- Deep Deterministic Policy Gradient (DDPG)

---
Sumber:
https://www.udemy.com/share/101wLU3@RWdeqwDpmDHxFXMMhd30r8qN0hZUM7eIZoKyzh0flCJI9HDqI7JBptf0PY8U2J8t8A==/