# Laporan-Proyek-Predictive-Analytics

# Laporan Proyek Machine Learning - Selly Rizkiyah

## Domain Proyek

### Latar Belakang
   Pendidikan merupakan salah satu faktor penting dalam pengembangan sumber daya manusia yang berkualitas. Namun, salah satu tantangan yang dihadapi dalam dunia pendidikan adalah bagaimana mengidentifikasi dan memahami faktor-faktor yang mempengaruhi pencapaian akademis siswa. Seiring berkembangnya teknologi dan ilmu data, penggunaan analisis prediktif untuk memprediksi prestasi akademis siswa menjadi semakin relevan dan penting.
   
   Dalam konteks ini, prediksi nilai akademis siswa dapat menjadi alat bantu yang sangat berguna bagi guru, orang tua, dan sekolah dalam membuat keputusan yang lebih efektif terkait intervensi pendidikan dan faktor terpenting dalam pendukung peningkatan nilai siswa. Dengan menganalisis berbagai faktor seperti waktu belajar mingguan, tingkat absensi, dukungan dari orang tua, serta keterlibatan siswa dalam kegiatan ekstrakurikuler, dapat diperoleh wawasan mendalam mengenai bagaimana setiap faktor tersebut berkontribusi terhadap prestasi akademik siswa.
   
   Proyek ini berfokus pada penerapan teknik analisis prediktif untuk memprediksi nilai siswa (GPA) berdasarkan berbagai faktor pendukung. Hasil dari analisis ini diharapkan dapat membantu dalam mengidentifikasi siswa yang mungkin membutuhkan bantuan tambahan serta memberikan rekomendasi intervensi yang lebih tepat sasaran untuk meningkatkan hasil belajar mereka.

## Business Understanding
### 1. Problem Statements (Pernyataan Masalah)
Dalam dunia pendidikan, banyak faktor yang berkontribusi terhadap pencapaian akademik siswa. Namun, tidak semua faktor ini terlihat jelas, dan sulit bagi pendidik untuk mengetahui dengan pasti faktor mana yang paling berpengaruh terhadap nilai siswa. Masalah ini muncul dalam pertanyaa, seperti:
- Apa saja faktor yang dapat mempengaruhi nilai akademis siswa?
- Apakah kegiatan siswa di luar sekolah, seperti ekstrakulikuler, olahraga, musik dan menjadi volunteer memiliki dampak positif terhadap prestasi akademis siswa?
- Apakah dukungan dari orang tua berpengaruh terhadap nilai akademis siswa?
- Bagaimana peran bimbingan belajar dalam mempengaruhi nilai akademis siswa?
- Bisakah kita membuat model prediksi yang akurat untuk memprediksi GPA siswa berdasarkan data pendukung yang ada?

#### 2. Goals (Tujuan)
Tujuan utama dari proyek analisis prediktif ini adalah untuk menjawab pertanyaan-pertanyaan di atas, beberapa tujuan spesifik yang ingin dicapai adalah sebagai berikut:
- Mengidentifikasi faktor-faktor yang dapat mempengaruhi nilai akademis siswa
- Menmeriksa faktor seperti kegiatan siswa di luar sekolah, seperti ekstrakulikuler, olahraga, musik dan menjadi volunteer memiliki dampak positif terhadap prestasi akademis siswa
- Mengetahui pengaruh dukungan dari orang tua terhadap nilai akademis siswa
- Melihat peran bimbingan belajar terhadap nilai akademis siswa
- Membuat model prediksi yang akurat untuk memprediksi GPA siswa berdasarkan data pendukung yang ada

#### 3. Solution Statement 
1. Memodelkan dengan K-Nearest Neighbors (KNN)

KNN akan digunakan sebagai model baseline untuk prediksi GPA siswa berdasarkan faktor-faktor seperti waktu belajar mingguan, ketidakhadiran, kegiatan ekstrakurikuler, olahraga, musik, dukungan orang tua, dan bimbingan belajar. KNN adalah algoritma yang intuitif dan mudah dipahami, namun memiliki beberapa kelemahan, seperti sensitivitas terhadap skala dan data berdimensi tinggi. Hyperparameter tuning akan dilakukan untuk menentukan jumlah tetangga terbaik (k) dan jarak metrik (misalnya, Euclidean). Metrik evaluasi yang akan digunakan adalah Mean Square Error (MSE).
   
2. Memodelkan dengan Random Forest 

Random Forest mampu menangani data yang kompleks, memiliki kemampuan untuk menangkap hubungan non-linear, dan menawarkan fitur penting seperti pemilihan fitur otomatis. Random Forest juga dapat digunakan untuk mengidentifikasi faktor mana yang paling berpengaruh terhadap GPA siswa, sehingga kita bisa mengetahui faktor-faktor yang benar-benar signifikan. Hyperparameter seperti jumlah pohon (n_estimators), kedalaman maksimum (max_depth), dan kontrol random generator (random_state) akan dioptimalkan menggunakan Grid Search atau Random Search. Metrik evaluasi yang akan digunakan adalah Mean Square Error (MSE).
   
## Data Understanding
Dataset berisi 2.392 baris dan 15 kolom, dataset terdiri dari Id siswa, demografi siswa (usia, gender, etnis, pendidikan terakhir oranb tua), jam belajar mingguan, jumlah absen dalam setahun, status memakai tutor, dukungan orang tua, kegiatan ekstrakurikuler, kegiatan musik, kegiatan olahraga, kegiatan relawan, nilai, dan kelas. Target dari prediksi ini yaitu gpa predictive, atau prediksi nilai yang akan diraih. Kondisi data sudah bersih dari outliers dan missing values.

Referensi: 
Rabie El Kharoua. "📚 Students Performance Dataset 📚". Tautan: https://www.kaggle.com/datasets/rabieelkharoua/students-performance-dataset. Diakses pada 12 Oktober 2024

### Variabel-variabel pada kolom-kolom student performance dataset adalah sebagai berikut:
- StudentID : id tiap siswa dengan rentang 1001 - 3392
- Age	: usia siswa dengan rentang 15 - 18 tahun
- Gender : jenis kelamin siswa (0: laki-laki, 1: perempuan)
- Ethnicity : etnis siswa (0: Kaukasia, 1: Afrika-Amerika,  2: Asia 3: Lainnya)
- ParentalEducation	: tingkat pendidikan terakhir orang tua (0: tidak ada, 1: SMA, 2: beberapa perguruan tinggi, 3: sarjana, 4: lebih tinggi)
- StudyTimeWeekly : waktu belajar mingguan dalam satuan jam dengan rentang dari 0 - 20 jam
- Absences : jumlah ketidakhadiran atau absen selama tahun ajaran dengan rentang dari 0 - 30.
- Tutoring : status bimbingan belajar (0: tidak dan 1: ya)
- ParentalSupport	: tingkat dukungan orang tua (0: tidak ada, 1: rendah, 2: sedang, 3: tinggi, 4: sangat tinggi)
- Extracurricular	: partisipasi dalam kegiatan ekstrakulikuler (0: tidak, 1: ya)
- Sports : partisipasi dalam kegiatan olahraga (0: tidak, 1: ya)
- Music : partisipasi dalam kegiatan musik (0: tidak, 1: ya)
- Volunteering : partisipasi dalam kegiatan sukarelawan (0: tidak, 1: ya)
- GPA	: nilai ipk dengan rentang 0.0 - 4.0
- GradeClass : klasifikasi nilai siswa dari GPA (0: 'A' (IPK >= 3,5), 1: 'B' (3.0 <= IPK < 3.5), 2: 'C' (2.5 <= IPK < 3.0), 3: 'D' (2.0 <= IPK < 2.5), 4: 'F' (IPK < 2.0))

Selain itu, untuk memahami persebaran data, dilakukan EDA dengan univariate analisys dan multivariate analisys. Univariate analisys dan multivariate analisys dilakukan secara bertahap dengan membagai data menjadi data kategorikal dan data numerikal. Dari dataset ini, data kategorikal diambil yaitu: 'Gender', 'Ethnicity', 'ParentalEducation', 'Tutoring', 'ParentalSupport', 'Extracurricular','Sports', 'Music', 'Volunteering', dan 'GradeClass'. Sementara data numerical yaitu: 'Age', 'StudyTimeWeekly', 'Absences', dan 'GPA'. 

Setelah itu, dilakukan tahap visualisasi dengan diagram batang, untuk mengetahui persebaran jumlah datanya, berikut ini contoh visualisasi dalam kolom 'Ethnicity':

![image](https://github.com/user-attachments/assets/d973c9e3-2ed5-4e6f-8312-a4184a39732b)

Sementara itu, data numerikal divisualisasikan seluruhnya seperti ini:

![image](https://github.com/user-attachments/assets/a7165f77-3e16-4ad5-a2a3-2c4231d07c51)

Dalam memahami korelasi dan pengaruh tiap fitur, dilakukan visualisasi seperti di bawah ini pada data kategorikal yang sudah dibagi sebelumnya, misalnya ingin mengetahui perbandingan antara 'GPA' dan 'ParentalSupport':

![image](https://github.com/user-attachments/assets/47496f2d-0866-46db-b360-3e74dc08c4f1)

Bagaimana dengan data numerikal? Dapat digunakan scatter plot, untuk mengetahui pola yang dibentuk antara hubungan 'GPA' dan faktor yang bertipe numerik lainnya, seperti contohnya di bawah ini:

![image](https://github.com/user-attachments/assets/8f3f2f44-727c-4638-823d-7c02949a95d5)

Setelah melakukan tahap EDA, diketahui faktor-faktor apa yang berpengaruh terhadap 'GPA' dan tidak berpengaruh terhadap 'GPA". Faktor yang tidak berpengaruh terhadap 'GPA' akan dihapus, agar dataset lebih siap untuk masuk ke tahap data preparation.

## Data Preparation
### Teknik Data Preparation yang Digunakan
Pada proyek ini, beberapa teknik data preparation diterapkan untuk memastikan data siap digunakan dalam model prediktif. Berikut adalah langkah-langkah yang dilakukan:
#### 1. Principal Component Analysis (PCA)
PCA diterapkan pada kolom numerik `StudyTimeWeekly`, `Absences`, dan `GPA` untuk mereduksi dimensi data dan menangkap variabilitas utama dari ketiga fitur tersebut. Dengan mereduksi dimensi menggunakan PCA, didapat penyederhanaan dataset tanpa kehilangan informasi penting yang berkaitan dengan variabel target (`GPA`).

#### 2. Train-Test Split
Data dibagi menjadi subset training dan testing dengan menggunakan variabel target `GPA`. Proses ini dilakukan agar model dapat dilatih pada sebagian data (data training) dan diuji pada bagian lainnya (data testing) untuk mengevaluasi performa model. Proporsi pembagian data yang umum digunakan adalah 80:20, 80 untuk data train dan 20 untuk data test

#### 3. Standardisasi
Fitur-fitur kategorikal seperti `Tutoring`, `ParentalSupport`, `Extracurricular`, `Sports`, dan `Music` distandarisasi. Standardisasi ini dilakukan untuk memastikan bahwa fitur-fitur tersebut berada dalam skala yang sama, sehingga model tidak memberikan bobot berlebihan pada fitur tertentu hanya karena skala yang berbeda. Skala fitur diubah menjadi distribusi standar dengan rata-rata 0 dan deviasi standar 1.

Dengan menerapkan reduksi dimensi menggunakan PCA, membagi dataset secara seimbang dengan train-test split, dan melakukan standardisasi pada variabel-variabel kategorikal, data telah dipersiapkan untuk proses analisis prediktif yang optimal.

## Modeling
### Model Machine Learning yang Digunakan
Untuk memprediksi nilai siswa berdasarkan berbagai faktor pendukung, beberapa algoritma machine learning telah digunakan, yaitu K-Nearest Neighbors (KNN), Random Forest, dan Boosting
#### 1. K-Nearest Neighbors (KNN)
KNN bekerja dengan menghitung jarak antara data baru dengan data yang ada dalam training set dan mengklasifikasikannya berdasarkan mayoritas kelas tetangga terdekat. Dengan menggunakan `n_neighbors`(jumlah tetangga yang digunakan untuk membuat prediksi) sebesar 10 dan `metric`(etode pengukuran jarak) dengan Euclidean distance.

#### 2. Random Forest
Random Forest membangun beberapa decision trees selama pelatihan dan menggabungkan prediksi dari setiap tree untuk menghasilkan prediksi akhir. Algoritma ini bekerja dengan menggunakan teknik bagging (bootstrap aggregating) untuk mengurangi overfitting dan meningkatkan akurasi. Dengan menggunakan `n_estimators` (jumlah pohon dalam hutan) sebesar 50,`max_depth`(kedalaman maksimum dari setiap pohon untuk menghindari overfitting) sebesar 16, 'random_state' (mengontrol random number generator yang digunakan) sebesar 55 dan 'n_jobs' (jumlah job (pekerjaan) yang digunakan secara paralel) sebesar -1, yang artinya semua proses berjalan secara paralel.'

#### 3. Boosting (XGBoost/Gradient Boosting)
Boosting adalah teknik yang menggabungkan beberapa model lemah untuk membentuk model kuat secara iteratif. Setiap model berturut-turut memperbaiki kesalahan model sebelumnya. Algoritma ini fokus pada observasi yang sulit diklasifikasikan dalam iterasi sebelumnya. Dengan menggunakan  `learning_rate` (bobot yang diterapkan pada setiap regressor di masing-masing proses iterasi boosting) sebesar 0.05 dan random_state (mengontrol random number generator yang digunakan) sebesar 55.

#### Pemilihan Model Terbaik
   Setelah membandingkan kinerja dari KNN, Random Forest, dan Boosting, _Random Forest dipilih sebagai model terbaik karena memiliki error yang paling kecil dan hasil mse  (mean square error) yang paling kecil di antara algoritma lainnya. Ini menunjukkan bahwa Random Forest mampu menangani variasi dalam data dengan lebih baik, serta memberikan hasil prediksi yang lebih akurat dibandingkan KNN dan Boosting dalam konteks data ini. Random Forest juga memberikan keunggulan dalam hal interpretasi fitur melalui feature importance, yang dapat membantu memahami faktor-faktor yang mempengaruhi nilai siswa.

## Evaluation
### Hasil Proyek Berdasarkan Metrik MSE
Hasil dari evaluasi model menggunakan Mean Squared Error (MSE) untuk KNN, Random Forest (RF), dan Boosting menunjukkan bahwa model **Random Forest** memiliki performa terbaik dalam memprediksi nilai siswa (GPA):

#### 1. K-Nearest Neighbors (KNN)
   - MSE Train: 0.000165
   - MSE Test: 0.000202
Model KNN menghasilkan MSE yang relatif rendah, namun MSE pada data test sedikit lebih besar daripada pada data training. Hal ini menunjukkan bahwa model KNN kurang mampu menggeneralisasi data dengan baik, yang mungkin mengarah pada sedikit overfitting.

#### 2. Random Forest (RF)
   - MSE Train: 0.000007
   - MSE Test: 0.000046
Random Forest memiliki MSE terkecil baik pada data training maupun testing, dengan perbedaan yang kecil antara keduanya. Ini menunjukkan bahwa Random Forest mampu melakukan prediksi dengan sangat baik, mengurangi kesalahan prediksi secara signifikan, dan tidak overfitting, sehingga menghasilkan prediksi yang lebih akurat pada data baru.

#### 3. Boosting
   - MSE Train: 0.000105
   - MSE Test: 0.000104
Boosting juga memberikan hasil yang cukup baik, dengan nilai MSE yang hampir sama antara data training dan testing. MSE yang konsisten menunjukkan bahwa model ini mampu melakukan generalisasi dengan baik tanpa overfitting. Namun, performanya masih berada di bawah Random Forest.

Dari hasil perbandingan MSE pada data training dan testing, diperoleh bahwa Random Forest jelas merupakan model terbaik dengan MSE yang paling kecil pada kedua dataset, menunjukkan bahwa model ini mampu memprediksi nilai GPA dengan tingkat kesalahan paling rendah. Boosting menempati posisi kedua, dengan performa yang stabil, tetapi MSE-nya lebih tinggi dibandingkan Random Forest. Sementara, KNN memiliki MSE yang lebih besar dibandingkan kedua model lainnya, menunjukkan performa yang kurang optimal dalam memprediksi GPA.

Dengan mempertimbangkan bahwa Random Forest memiliki MSE yang paling kecil, baik pada data training maupun testing, model ini dipilih sebagai solusi terbaik untuk prediksi nilai siswa.

Kesimpulan:
Setelah melakukan prediksi, didapat jika faktor yang dapat mempengaruhi nilai akademis siswa ada 4, yaitu bimbingan belajar, dukungan dari orang tua, dan kegiatan di luar sekolah seperti esktrakulikuler, olahraga dan juga musik. Kegiatan siswa di luar sekolah, seperti ekstrakulikuler, olahraga, musik dan menjadi volunteer memiliki dampak positif terhadap prestasi akademis siswa, karena dibuktikan jika siswa yang mengikuti kegiatan di luar sekolah, memiliki GPA yang lebih tinggi. Dukungan dari orang tua berpengaruh terhadap nilai akademis siswa, hal ini berbanding lurus, semakin tinggi dukungan orang tua pada anaknya, maka akan semakin bagus juga nilai akademis siswa. Selain itu, peran bimbingan belajar dalam mempengaruhi nilai akademis siswa juga berperan baik. Walaupun masih sedikit siswa yang mengikuti bimbingan belajar, mengikuti bimbingan belajar tetap terbukti efektif untuk meningkatkan nilai siswa. Kita bisa membuat model prediksi beradasakan pendukung yang ada, seeprti pada lampiran:

y_tru: nilai GPA asli, dan Prediksi_RF: hasil prediksi

![image](https://github.com/user-attachments/assets/4bfc3785-3503-470f-ac0c-3219995e5f25)

**---Ini adalah bagian akhir laporan---**
