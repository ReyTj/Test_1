# Laporan Proyek Data Science & Machine Learning - Nama
## Domain Proyek

Domain dari proyek _machine learning_ ini adalah tentang prediksi cuaca dengan judul "_Weather prediction based on average temperature_"

### Latar Belakang
  
Sejak revolusi industri, emisi yang dikeluarkan dari pabrik-pabrik besar mulai merusak lingkungan sekitar tetapi, dampak yang signifikan mulai tampak sejak awal tahun 2000an. Dampak yang signifikan ini disebut juga sebagai pemanasan global. Hal ini disebabkan oleh polusi CO2, penebangan pohon, gas rumah kaca, dan lainnya. Pemanasan global menyebabkan suhu di bumi semakin tidak terprediksi.

Dari masalah di atas, proyek ini akan membuat suatu model machine learning untuk memprediksi suhu setiap harinya di masa depan berdasarkan data yang didapat sejak awal tahun 2000-an. Model ini akan membantu pengguna agar semakin siap untuk menghadapi setiap harinya dengan memberikan perkiraan suhu setiap harinya agar pengguna dapat mempersiapkan pakaian yang tepat.  Model ini akan berjalan di aplikasi berbasis web

## Business Understanding

### Problem Statements
Berdasarkan pada latar belakang di atas, permasalahan yang dapat diselesaikan pada proyek ini adalah sebagai berikut:

 - Bagaimana cara mengolah data dari data suhu per hari agar dapat membuat model yang baik?
 - Bagaimana cara mengupdate model untuk agar dapat ditambahkan parameter untuk memprediksi suhu yang akan datang

### Goals
Tujuan dibuatnya proyek ini adalah sebagai berikut:

 - Melakukan pra-pemrosesan data suhu per hari agar dapat digunakan dalam membangun model.
 - Membangun model machine learning untuk memprediksi suhu di masa mendatang dengan tingkat akurasi > 80%.

### Solution statements
Solusi yang didapatkan setelah mengerjakan proyek DS/ML yang dikerjakan

- **Pra-pemrosesan Data**. Pada pra-pemrosesan data dapat dilakukan beberapa tahapan, antara lain:
  - Melakukan perhitungan rerata berdasarkan data temp_max dan temp_min.
  - Melakukan pembagian dataset.
  - Mengatasi data pencilan (outliers) dengan Metode IQR.
  - Standardisasi data fitur numerik pada dataset.

  
- **Pembangunan Model**. Pada pembangunan model terdapat beberapa algoritma yang digunakan, antara lain:
  - K-Nearest Neighbor
  - Random Forest
  - Boosting Algorithm

    
## Data Understanding
- **Informasi Dataset**
  <br> Berisi penjelasan singkat tentang dataset

  | Jenis                   | Keterangan                                                                              |
  | ----------------------- | --------------------------------------------------------------------------------------- |
  | Sumber                  | [Asal Dataset] |
  | Dataset Owner           | [Pengupload Dataset/Pemilik Dataset |
  | Lisensi                 | [Lisensi yang dimiliki dataset] |
  | Kategori                | [Kategori Dataset] |
  | Usability               | [Tingkat kualitas data] |
  | Jenis dan Ukuran Berkas | [Format data] |

  Setelah melakukan observasi pada dataset yang diunduh melalui _link_ Kaggle yaitu `coin_Bitcoin.csv`, didapatkan informasi sebagai berikut :
  
  Detail penjelasan dari isi dataset

- **Sebaran atau Distribusi Data pada Setiap Fitur**
  <br> Penjelasan dan ilustrasi mengenai persebaran data beserta analisis menggunakan Univariate & Multivariate Analysis, serta penjelasan dari ilustrasi persebaran data tersebut.
  
  
## Data Preparation
Penjelasan mengenai data preperation dan tahapan apa saja yang dilakukan dalam melakukan data preperation pada proyek yang dikerjakan beserta penjelasan & detail lengkapnya.

## Modeling
Pembahasan Model-model apa saja yang digunakan pada proyek yang dikerjakan beserta penjelasan lengkapnya serta kelebihan beserta kekurangannya. dan kesimpulan dari masing2 model serta model yang paling efektif digunakan

## Evaluation
Penjelasan mengenai evaluasi dari proyek yang dikerjakan menggunakan metrik evaluasi beserta penjelasan metrik tersebut dan kesimpulan dari hasil yang didapat dari apa yang telah dikerjakan disertai illustrasi evaluasinya.
