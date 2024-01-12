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
  | Sumber                  | Kaggle |
  | Dataset Owner           | ANANTH R |
  | Lisensi                 | CC BY-NC-SA 4.0 DEED |
  | Kategori                | Weather and Climate |
  | Usability               | 10.00 |
  | Jenis dan Ukuran Berkas | csv 49.68 kB |

  Setelah melakukan observasi pada dataset yang diunduh melalui _link_ Kaggle yaitu `seattle-weather.csv`, didapatkan informasi sebagai berikut :

  - Terdapat 1461 baris (records atau jumlah pengamatan) yang berisi informasi mengenai data cuaca.
  - Terdapat 6 kolom yaitu date, precipitation, temp_max, temp_min, wind, weather yang merupakan variabel - variabel pada data
  - Dari kolom-kolom tersebut terdapat 4 kolom numerik dengan tipe data float64, yaitu precipitation, temp_max, temp_min, wind 
  - Terdapat 1 kolom dengan tipe object yaitu weather
  - Tidak terdapat missing value pada dataset.

  Untuk penjelasan mengenai variabel-variabel pada dataset dapat dilihat pada poin-poin berikut ini:

  - date : Tanggal pencatatan data
  - precipitation : proses jatuhnya segala materi yang dicurahkan dari atmosfer ke permukaan bumi dalam bentuk cair (hujan) maupun padat (salju).
  - temp_max : suhu maksimal
  - temp_min : suhu minimal
  - wind : kecepatan angin
  - weather : cuaca

  [boxplot](url_of_image)
- **Sebaran atau Distribusi Data pada Setiap Fitur**
  sebelum masuk ke tahap distribusi data, persiapan yang dilakukan yaitu perlu membuat dua variabel baru yaitu variabel temp_Average untuk menampung rata-rata suhu dan Temp_Next_Day untuk suhu setelah sehari. Berikut merupakan visualisasi data yang menunjukkan sebaran/distribusi data pada setiap fitur-fitur numerik `(temp_max, temp_min, temp_Average, temp_Next_Day)`
  
  
## Data Preparation
Penjelasan mengenai data preperation dan tahapan apa saja yang dilakukan dalam melakukan data preperation pada proyek yang dikerjakan beserta penjelasan & detail lengkapnya.

## Modeling
Pembahasan Model-model apa saja yang digunakan pada proyek yang dikerjakan beserta penjelasan lengkapnya serta kelebihan beserta kekurangannya. dan kesimpulan dari masing2 model serta model yang paling efektif digunakan

## Evaluation
Penjelasan mengenai evaluasi dari proyek yang dikerjakan menggunakan metrik evaluasi beserta penjelasan metrik tersebut dan kesimpulan dari hasil yang didapat dari apa yang telah dikerjakan disertai illustrasi evaluasinya.
