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

  [boxplot]()
  
- **Sebaran atau Distribusi Data pada Setiap Fitur**
  sebelum masuk ke tahap distribusi data, persiapan yang dilakukan yaitu perlu membuat dua variabel baru yaitu variabel temp_Average untuk menampung rata-rata suhu dan Temp_Next_Day untuk suhu setelah sehari. Berikut merupakan visualisasi data yang menunjukkan sebaran/distribusi data pada setiap fitur-fitur numerik `(temp_max, temp_min, temp_Average, temp_Next_Day)`
  
  
## Data Preparation
Berikut ini merupakan tahapan-tahapan dalam melakukan pra-pemrosesan data:

Melakukan pembagian dataset
Untuk mengetahui kinerja model ketika dihadapkan pada data yang belum pernah dilihat sebelumnya, maka perlu dilakukan pembagian dataset. Pada proyek ini dataset dibagi menjadi data latih dan data uji dengan rasio 80% untuk data latih dan 20% untuk data uji. Data latih merupakan data yang akan kita latih untuk membangun model machine learning, sedangkan data uji merupakan data yang belum pernah dilihat oleh model dan digunakan untuk melihat kinerja atau performa dari model yang dilatih. Pembagian dataset dilakukan dengan modul train_test_split dari scikit-learn. Setelah melakukan pembagian dataset, didapatkan jumlah sample pada data latih yaitu 1168 sampel dan jumlah sample pada data uji yaitu 292 sampel dari total jumlah sample pada dataset yaitu 1460 sampel.

Standardisasi data pada semua fitur numerik pada dataset
Standardisasi merupakan teknik transformasi yang paling umum digunakan dalam tahap data preparation. Standardisasi membantu untuk membuat semua fitur numerik berada dalam skala data yang sama dan membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma. Pada proyek ini, standardisasi data dilakukan dengan menerapkan teknik StandarScaler dari library Scikitlearn. StandardScaler melakukan proses standardisasi fitur dengan mengurangkan mean (nilai rata-rata) kemudian membaginya dengan standard deviasi untuk menggeser distribusi. StandardScaler menghasilkan distribusi dengan standard deviasi sama dengan 1 dan mean sama dengan 0. Sekitar 68% dari nilai akan berada di antara -1 dan 1.


## Modeling
Pada proyek ini, Proses modeling dalam proyek ini menggunakan 3 algoritma machine learning yaitu `K-Nearest Neighbor, Random Forest dan Boosting Algorithm` kemudian membandingkan performanya.

K-Nearest Neighbor
KNN bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k tetangga terdekat (dengan k adalah sebuah angka positif). Pada tahap ini pembuatan model dilakukan dengan menggunakan modul KNeighborsClassifier dari library Scikitlearn dengan nilai k = 10 dan metric Euclidean yang artinya, pada model ini akan membandingkan jarak satu sampel data ke 10 sampel data tetangganya yang terdekat, agar hasil persamaan regresi yang dihasilkannya nantinya akan lebih halus, tahapan itu akan dilakukan berulang-ulang hingga mendapatkan hasil persamaan regresi dengan nilai yang maksimal. Kemudian proses selanjutnya melakukan prediksi menggunakan data uji dan melakukan pengujian.

Kelebihan:
 - Algoritma KNN merupakan algoritma yang sederhana dan mudah untuk diimplementasikan.
 - Dapat di implementasikan pada beberapa kasus seperti klasifikasi, regresi dan pencarian.
Kekurangan:
 - Algoritma KNN menjadi lebih lambat secara signifikan seiring meningkatnya jumlah sampel dan/atau variabel independen.

Random Forest
Algoritma ini disusun dari banyak algoritma pohon (decision tree) yang pembagian data dan fiturnya dipilih secara acak. Pembuatan model dilakukan dengan menggunakan modul RandomForestClassifier dari library Scikitlearn. terdapat parameter yang harus digunakan agar hasil dari pembuatan model dapat maksimal. Parameter pertama ialah parameter n_estimator yang merupakan jumlah trees (pohon) di forest. Di proyek ini penulis melakukan set nilai n_estimator sebesar 50 trees. Selanjutnya ialah parameter max_depth yang merupakan kedalaman atau panjang pohon. Itu merupakan ukuran seberapa banyak pohon dapat membelah (splitting) untuk membagi setiap node ke dalam jumlah pengamatan yang di inginkan, di proyek ini penulis melakukan set nilai max_depth sebesar 16 split. Parameter random_state digunakan untuk mengontrol random number generator yang digunakan. Di proyek ini penulis melakukan set nilai pada parameter random_state sebesar 55. Lalu yang terakhir ialah parameter n_jobs yaitu jumlah job (pekerjaan) yang digunakan secara paralel. Itu merupakan komponen untuk mengontrol thread atau proses yang berjalan secara paralel. n_jobs = -1 artinya semua proses berjalan secara paralel. Kemudian proses selanjutnya melakukan prediksi menggunakan data uji dan melakukan pengujian.

Kelebihan :
 - Algoritma Random Forest merupakan algoritma dengan pembelajaran paling akurat yang tersedia. Untuk banyak kumpulan data, algoritma ini menghasilkan pengklasifikasi yang sangat akurat.
 - Berjalan secara efisien pada data besar.
 - Dapat menangani ribuan variabel input tanpa penghapusan variabel.
 - Memberikan perkiraan variabel apa yang penting dalam klasifikasi.
 - Memiliki metode yang efektif untuk memperkirakan data yang hilang dan menjaga akurasi ketika sebagian besar data hilang.
Kekurangan :
 - Algoritma Random Forest overfiting untuk beberapa kumpulan data dengan tugas klasifikasi/regresi yang bising/noise.
 - Untuk data yang menyertakan variabel kategorik dengan jumlah level yang berbeda, Random Forest menjadi bias dalam mendukung atribut dengan level yang lebih banyak. Oleh karena itu, skor kepentingan variabel dari Random Forest tidak dapat diandalkan untuk jenis data ini.

Boosting Algorithm
Algoritma ini bekerja dengan membangun model dari data latih. Kemudian ia membuat model kedua yang bertugas memperbaiki kesalahan dari model pertama. Model ditambahkan sampai data latih terprediksi dengan baik atau telah mencapai jumlah maksimum model untuk ditambahkan. Pada tahap ini pembuatan model dilakukan dengan menggunakan modul Boosting Alghoritm dari library Scikitlearn. Penulis meenggunakan metode adaptive boosting yaitu AdaBoost. Parameter yang penulis gunakan terdapat 2 parameter, yaitu parameter learning_rate yang merupakan bobot yang diterapkan pada setiap regressor di masing-masing proses iterasi boosting, dan parameter random_state yang digunakan untuk mengontrol random number generator yang digunakan. Kemudian proses selanjutnya melakukan prediksi menggunakan data uji dan melakukan pengujian.

Kelebihan :
 - Algoritma Boosting dapat mengurangi bias pada data.
 - Prosedur Boosting cukup sederhana.
 - Algoritma ini sangat powerful dalam meningkatkan akurasi prediksi.
 - Algoritma boosting sering mengungguli model yang lebih sederhana seperti logistic regression dan random forest.
Kekurangan :
 - AdaBoost sangat dipengaruhi oleh outlier.


Dapat disimpulkan model terbaik yang digunakan untuk dataset ini ialah model KNN di mana KNN memiliki nilai error terkecil dan nilai akurasi yang tinggi ketimbang kedua model lainnya(cek pada bagian Evaluasi)

## Evaluation

Pada proyek ini, metrik evaluasi yang digunakan untuk mengukur kinerja model yaitu menggunakan metrik akurasi dan MSE. Akurasi di sini merupakan tingkat keakuratan data prediksi yang didasarkan dari data latih pada model, tingkat akurasi tertinggi ialah pada model KNN sebesar 87.529353% dan ini menunjukkan bahwasannya KNN merupakan model terbaik dari kedua model lainnya dalam memprediksi cuaca di masa mendatang. MSE sendiri merupakan Mean Squared Error yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. 

Sebelum menggunakan metrik MSE, harus dilakukan scaling fitur numerik terlebih dahulu pada data uji untuk menghindari kebocoran data. Setelah melakukan evaluasi berdasarkan metrik MSE dan tingkat akurasi prediksi pada model, penulis mencoba memprediksi harga untuk 30 hari ke depan dengan model KNN dan hasilnya cukup memuaskan karena nilainya tidak jauh berbeda dengan data sebelumnya.




