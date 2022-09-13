# Laporan Proyek Akhir - Lalu Habib Satya Wiguna

## Domain Proyek
Sektor perbankan merupakan sektor pasar di mana pelanggan tidak secara teratur berpindah dari satu bank ke bank lainnya. Di era globalisasi seperti sekarang ini, bank menjadi bagian dari sistem keuangan dan juga sistem pembayaran suatu negara. Menurut Fahrial dari Universitas Islam Riau di dalam jurnalnya yang berjudul [Peranan Bank Dalam Pembangunan Ekonomi Nasional](https://jurnal.ensiklopediaku.org/ojs-2.4.8-3/index.php/ensiklopedia/article/download/54/29), bank adalah badan usaha yang menghimpun dana dari masyarakat dalam bentuk simpanan dan menyalurkannya kepada masyarakat dalam bentuk kredit dan/atau bentuk-bentuk lainnya dalam rangka meningkatkan taraf hidup rakyat banyak. Dari hal tersebut dapat dikatakan bahwa peran bank dalam suatu negara sangatlah vital dan strategis dalam menopang pembangunan ekonomi nasional, sehingga apabila suatu bank mengalami kebangkrutan maka dapat menyebabkan ekonomi menjadi tidak stabil. Agar tidak mengalami kebangkrutan, tentunya sebuah bank memiliki sumber dana untuk menjalankan sistem operasionalnya. Salah satu sumber dana tersebut berasal dari masyarakat yang menjadi nasabah pada bank tersebut seperti simpanan giro, tabungan, dan deposito. Oleh karena itu, peran nasabah sangat penting demi menjaga stabilitas dana dari sebuah bank. Tentunya bank tidak ingin kehilangan nasabahnya karena merupakan salah satu pondasi yang membangun sistem keuangan pada bank tersebut. Penelitian yang dilakukan oleh perusahaan konsultan keuangan Bain & Company pada [Customer Loyalty in Banking Report](https://media.bain.com/Images/BAIN_REPORT_Loyalty_in_Retail_Banking_2013.pdf) menyebutkan bahwa bagi sebuah bank untuk mendapatkan nasabah baru tidaklah mudah, oleh karena itu lebih baik untuk menjaga nasabah yang sudah ada. Merupakan sebuah keuntungan bagi bank untuk mengetahui apa yang menyebabkan nasabah menutup rekening dan meninggalkan bank. Dengan menggunakan Machine Learning, data dari nasabah yang pergi ini dapat diorganisir dan diekstraksi untuk memfasilitasi prediksi masa depan demi mengembangkan loyalitas nasabah dan keputusan manajemen. Dengan hal tersebut tentunya akan meningkatkan keuntungan dan pemasukan bank sehingga akan mudah mempertahankan nasabahnya.

## Business Understanding
Untuk mendapatkan profit yang tinggi, bank tentunya akan mengutamakan kesejahteraan nasabahnya dengan cara mendapatkan feedback dari nasabah tersebut. Dari feedback tersebut, bank dapat mengembangkan pelayanannya sehingga setiap nasabah di bank akan merasa puas dan nyaman. Untuk mewujudkan hal tersebut tentunya perlu mengetahui faktor-faktor apa saja yang mungkin dapat mempengaruhi nasabah untuk menutup rekening dan meninggalkan bank. Faktor tersebut antara lain, region bank, gender, umur, lama menjadi nasabah, jumlah uang di rekening bank, produk yang dibeli menggunakan bank, kartu kredit, status aktif, dan gaji bulanan. Tidak semua nasabah memiliki masalah yang sama, sehingga bank memerlukan sistem untuk dapat memprediksi faktor apa yang mempengaruhi nasabah menutup rekening dan meninggalkan bank. Setelah mengetahui hal tersebut, maka bank dapat mengembangkan pelayanannya dan mempertahankan nasabah yang sudah ada.

### Problem Statements
Berdasarkan kondisi yang telah diuraikan sebelumnya, bank akan mengembangkan sebuah sistem untuk memprediksi nasabah yang mempunyai kemungkinan akan meninggalkan bank untuk menjawab permasalahan berikut:
- Dari serangkaian faktor yang ada, faktor apa yang paling berpengaruh terhadap nasabah yang meninggalkan bank?
- Apakah bank dapat mempertahankan nasabahnya hanya dengan melihat data nasabah yang menutup rekening sebelumnya?

### Goals
Untuk menjawab pertanyaan tersebut, dibuatlah predictive modelling dengan goals sebagai berikut:
- Mengetahui faktor yang paling berkorelasi dengan keluarnya nasabah dari bank.
- Membuat model machine learning yang dapat memprediksi nasabah yang memiliki kemungkinan untuk meninggalkan bank berdasarkan data nasabah sebelumnya yang telah keluar dari bank.

### Solution Statements
- Untuk mengetahui kemungkinan nasabah akan meninggalkan bank, perlu dilakukan analisis terhadap faktor yang paling berpengaruh yang dapat menyebabkan seorang nasabah menutup rekeningnya. Setelah mengetahui hal tersebut barulah akan dilakukan klasifikasi untuk mengetahui apakah seorang nasabah akan meninggalkan bank berdasarkan data-data nasabah saat ini. Oleh karena itu, metode yang akan digunakan pada proyek ini adalah klasifikasi dengan faktor-faktor yang diterangkan sebelumnya. Model yang akan digunakan pada proyek ini adalah K-Nearest Neighbor (KNN) yang merupakan supervised learning. Kemudian untuk mendapatkan hasil yang maksimal akan dilakukan hyperparameter tuning pada model KNN ini.
- Metrik yang akan digunakan untuk mengukur performa dari model KNN ini adalah Precision, Recall, F1-Score, Accuracy, dan Confussion Matrix. Secara garis besar, metrik yang disebutkan sebelumnya akan mengukur sejauh mana model yang dibangun dapat memprediksi dan mengklasifikasikan data dengan data yang sesungguhnya secara akurat.

## Data Understanding
Dataset yang akan mendukung penelitian pada proyek ini berisi data nasabah baik yang masih bertahan menjadi nasabah dan telah keluar dari bank atau menutup rekeningnya. Di dalam dataset ini terdapat 10.000 data dengan 14 kolom. Kolom-kolom tersebut akan dijadikan fitur seperti sisa saldo, negara asal, umur, lama menjadi nasabah, dan lain-lain yang dapat menjadi fitur pada penelitian ini. Dataset yang akan digunakan yaitu [Churn for Bank Customers](https://www.kaggle.com/datasets/mathchi/churn-for-bank-customers), diunduh dari situs [kaggle](https://www.kaggle.com/).
Variabel-variabel pada Churn for Bank Customers adalah sebagai berikut:
- RowNumber: nomor urut dari setiap kolom pada dataset.
- CustomerId: nomor ID dari nasabah.
- Surname: nama belakang atau nama keluarga dari nasabah.
- CreditScore: angka statistik yang mengevaluasi kelayakan kredit nasabah dan didasarkan pada riwayat kredit.
- Geography: negara asal dari nasabah.
- Gender: jenis kelamin dari nasabah.
- Age: usia dari nasabah.
- Tenure: mengacu pada jumlah tahun seorang nasabah telah menjadi nasabah bank.
- Balance: sisa uang di rekening bank nasabah.
- NumOfProducts: jumlah produk yang telah dibeli oleh nasabah melalui bank.
- HasCrCard: menunjukkan apakah nasabah memiliki kartu kredit atau tidak.
- IsActiveMember: menunjukkan apakah nasabah masih aktif atau tidak di bank.
- EstimatedSalary: gaji perorangan rata-rata.
- Exited: menunjukkan apakah nasabah meninggalkan bank atau tidak.

Yang akan menjadi target pada proyek ini adalah variabel Exited.

### Exploratory Data Analysis
Exploratory Data Analysis atau sering disingkat EDA merupakan proses investigasi awal pada data untuk menganalisis karakteristik, menemukan pola, anomali, dan memeriksa asumsi pada data. Di tahap ini akan dilakukan EDA dengan menggunakan metode bersifat univariate (melibatkan satu variate atau variabel) dan multivariate (melibatkan dua atau lebih variabel). Fitur pada dataset akan dibagi menjadi dua bagian, yaitu fitur numerik dan fitur kategorikal sebagai berikut:
- fitur numerik = 'CreditScore', 'Age', 'Tenure', 'Balance', 'NumOfProducts', 'EstimatedSalary'
- fitur kategorikal = 'Geography', 'Gender', 'HasCrCard', 'IsActiveMember', 'Exited'

Setelah dilakukan pembagian, akan dilakukan EDA dengan univariate analysis untuk fitur kategorikal dan fitur numerik sebagai berikut.

#### Univariate Analysis
Pada univariate analysis, hanya melibatkan satu variate atau satu fitur saja.

##### Fitur Kategorikal
![cat](https://user-images.githubusercontent.com/74854925/190021374-454e28de-e20a-4e51-bed1-1b5bb53b5f47.jpg)  
Berdasarkan visualisasi data kategorikal di atas didapatkan kesimpulan sebagai berikut:  
1. Hampir 50% nasabah berasal dari France, dan sisanya terbagi atas Spanyol dan Germany dengan komposisi yang hampir sama.
2. Nasabah dengan jenis kelamin laki-laki lebih banyak dibandingkan dengan perempuan.
3. Sebanyak +- 70% nasabah memiliki credit card.
4. Nasabah terbagi hampir sama untuk tingkat keaktifan, yaitu +-48% tidak aktif dan 52% nasabah aktif.
5. Sekitar 20% dari nasabah memilih untuk meninggalkan bank.

##### Fitur Numerik
![num](https://user-images.githubusercontent.com/74854925/190021428-a493cd51-8708-4646-9f01-c69917398937.jpg)  
Kemudian untuk visualisasi data numerik di atas didapatkan kesimpulan sebagai berikut:
1. Secara umum, nasabah memiliki CreditScore normal / umumnya di 500-800
2. Nasabah memiliki persebaran usia paling tinggi pada umur 30-40 tahun
3. Tenure secara umum tersebar secara merata kecuali di rentang 0-1 yang rendah dan 9-10 yang tinggi
4. Balance nasabah secara umum terbagi menjadi dua bagian utama, yaitu tinggi pada balance 0 dan normally distributed di 50.000 sd 200.000
5. Untuk NumOfProducts 50% 1 produk, 45% 2 produk, 3% 3 produk dan 2% 4 produk
6. EstimatedSalary memiliki distribusi data yang seragam.

#### Multivariate Analysis
Pada multivariate analysis menunjukkan hubungan antara dua atau lebih variabel pada data. Hubungan yang akan dilihat yaitu antara setiap variabel yang ada dengan variabel target yaitu 'Exited'.

##### Fitur Kategorikal
![1geo](https://user-images.githubusercontent.com/74854925/190021470-5621a6ca-bd80-47b1-9360-d141028ce7db.png)   
Note:  
0 = France  
1 = Germany  
2 = Spain  
Berdasarkan gambar di atas, dapat diambil kesimpulan sebagai berikut:  
1. Nasabah dari France lebih sedikit yang meninggalkan bank.
2. Spanyol memiliki lebih sedikit nasabah yang meninggalkan bank. 
3. Lebih banyak nasabah yang meninggalkan bank di region Germany dengan rasio lebih dari 30%.

![1gender](https://user-images.githubusercontent.com/74854925/190021497-39d6f01e-76be-445a-bdf3-368d33cd120d.png)    
Note:  
0 = Perempuan (female)  
1 = Laki-laki (male)
Berdasarkan gambar di atas, lebih banyak nasabah perempuan yang meninggalkan bank.

![1crcard](https://user-images.githubusercontent.com/74854925/190021551-dd4b71be-a951-4548-975a-4a55c10011b0.png)    
Note:  
0 = Tidak mempunyai credit card  
1 = Mempunyai credit card
Dari gambar diatas dapat dilihat bahwa nasabah yang memiliki credit card maupun tidak memiliki credit card persentasenya tidak terlalu signifikan yang berarti pengaruh kepemilikan credit card tidak berpengaruh besar pada nasabah untuk meninggalkan bank.

![1active](https://user-images.githubusercontent.com/74854925/190021575-8ef169f7-9822-4c18-a879-a49dc900523c.png)    
Note:  
0 = Tidak aktif  
1 = Aktif
Dari gambar di atas kita lihat bahwa lebih banyak nasabah tidak aktif yang meninggalkan bank daripada nasabah yang aktif dan perbandingannya signifikan yang berarti bahwa status keaktifan nasabah memiliki pengaruh terhadap nasabah untuk meninggalkan bank.

##### Fitur Numerik
![2crscore](https://user-images.githubusercontent.com/74854925/190021606-028a23f9-4065-43e1-b169-cff93357dd17.png)  
![2age](https://user-images.githubusercontent.com/74854925/190021614-4758f1f0-a6f9-42a3-8561-482ffe9c0498.png)  
![2tenure](https://user-images.githubusercontent.com/74854925/190021631-fd1724d1-2198-47b8-8db2-a49322188ebf.png)  
![2balance](https://user-images.githubusercontent.com/74854925/190021635-f817e067-b8fa-4ae2-a37d-08fb6597460a.png)  
![2num](https://user-images.githubusercontent.com/74854925/190021645-567d1e8a-4dbc-4ef2-952f-a5a6f46e210b.png)  
![2est](https://user-images.githubusercontent.com/74854925/190021661-4ca689b1-9754-4995-8135-2c46f12e824d.png)  
Berdasarkan visualisasi data di atas, dapat diambil kesimpulan sebagai berikut:
1. Distribusi nasabah yang meninggalkan bank berdasarkan credit score-nya tidak jauh berbeda (overlapping) satu sama lain, density nasabah yang pergi dan yang bertahan hampir sama sehingga dapat disimpulkan bahwa credit score tidak mempengaruhi nasabah untuk pergi meninggalkan bank.
2. Nasabah yang bertahan di bank lebih banyak pada kelompok usia 20-45 tahun, sedangkan yang meninggalkan bank lebih banyak pada kelompok usia 30-60 tahun yang artinya kebanyakan nasabah dengan usia relatif muda memilih untuk bertahan di bank dan kebanyakan nasabah dengan usia relatif tua meninggalkan bank.
3. Tidak ada insight khusus antara lama menjadi nasabah di bank dengan keluarnya customer bank, sisa tabungan di bank dengan keluarnya nasabah bank, dan produk yang dibeli melalui bank dengan keluarnya nasabah bank

##### Metrik Korelasi
![3cormat](https://user-images.githubusercontent.com/74854925/190021706-4906dfda-9701-4a92-9c43-ea126853bf58.png)
Note:  
- Jika korelasi (x,y) diantara -0.1 sd 0.1 maka disebut sebagai korelasi yang buruk (bad correlation)
- Jika korelasi (x,y) diantara 0.1 sd 0.5 maka disebut sebagai korelasi yang baik (good correlation)
- Jika korelasi (x,y) diantara -0.1 sd -0.5 disebut sebagai korelasi yang baik (good correlation)
- Jika korelasi (x,y) > 0.5 maka disebut sebagai korelasi yang sangat baik (very good correlation)
- Jika korelasi (x,y) < -0.5 maka disebut sebagai korelasi yang sangat baik (very good correlation)

Berdasarkan correlation matrix di atas didapatkan kesimpulan hubungan antara setiap variabel dengan fitur target kita yaitu Exited sebagai berikut:  
1. Bad correlation: CreditScore, Geography, Tenure, NumOfProducts, HasCrCard, EstimatedSalary   
2. Good correlation: Gender, Age, Balance, IsActiveMember

Kemudian untuk fitur yang memiliki korelasi yang buruk dapat di-drop.

## Data Preparation
Untuk mempermudah dalam memproses data ketika tahap pemodelan nanti, maka perlu dilakukan persiapan pada dataset. Berikut proses persiapan data yang dilakukan.

### Train-Test-Split
Dengan menggunakan fungsi train_test_split dari library Scikitlearn untuk melakukan pembagian data latih dan data uji dengan perbandingan sebanyak 80% dari total dataset sebagai data latih dan 20% sebagai data uji. Potongan kodenya sebagai berikut.  
![tts](https://user-images.githubusercontent.com/74854925/190021753-5be3f8be-5e46-4ed5-b338-71b1b4c36bc4.jpg)    
Berdasarkan potongan kode di atas, dapat dilihat bahwa kini dataset terbagi menjadi 2 bagian yakni 8.000 data menjadi data latih dan 2.000 data menjadi data uji dengan total 10.000 data pada dataset.

### Standarization
Standardisasi adalah teknik transformasi yang paling umum digunakan dalam tahap persiapan pemodelan. Standarisasi akan dilakukan dengan menggunakan teknik StandarScaler dari library Scikitlearn. StandardScaler melakukan proses standarisasi fitur dengan mengurangkan mean (nilai rata-rata) kemudian membaginya dengan standar deviasi untuk menggeser distribusi. StandardScaler menghasilkan distribusi dengan standar deviasi sama dengan 1 dan mean sama dengan 0. Sekitar 68% dari nilai akan berada di antara -1 dan 1. Untuk menghindari kebocoran informasi pada data uji, fitur standarisasi hanya diterapkan pada data latih. Kemudian, pada tahap evaluasi, akan dilakukan standarisasi pada data uji. Berikut potongan kode untuk standarisasi.  
![std](https://user-images.githubusercontent.com/74854925/190021800-f7afd033-8d7f-402c-a871-784febeea1a4.jpg)

## Modeling
K-Nearest Neighbor (KNN) adalah algoritma yang relatif sederhana dibandingkan dengan algoritma lain. Algoritma KNN menggunakan 'kesamaan fitur' untuk memprediksi nilai dari setiap data yang baru. Dengan kata lain, setiap data baru diberi nilai berdasarkan seberapa mirip titik tersebut dalam set pelatihan. KNN bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k tetangga terdekat (dengan k adalah sebuah angka positif). Itulah mengapa algoritma ini dinamakan k-nearest neighbor (sejumlah k tetangga terdekat). Pada proyek ini, algoritma KNN akan diakses melalui library Scikitlearn.
Penjelasan untuk setiap parameter yang ada pada model KNN sebagai berikut:  
- n_neighbors : merepresentasikan jumlah tetangga terdekat dari titik yang akan dihitung.  
- weights : fungsi pembobotan yang akan digunakan dalam menghitung jarak antara tetangga terdekat dengan titik yang dimasukkan.   
- algorithm : jenis algoritma yang akan digunakan untuk proses penghitungan tetangga terdekat.  
- leaf_size : ukuran atau size yang mengontrol titik dalam node tertentu.  
- p : power parameter untuk metrik yang menghitung jarak antara titik tertentu.  
- metric : metrik yang digunakan pada tree.  
- metric_params : keyword tambahan untuk metric function.  
- n_jobs : banyaknya penugasan parallel untuk menjalankan pencarian tetangga terdekat.  
Namun, pada proyek kali ini percobaan akan dilakukan dengan menggunakan parameter default terlebih dahulu untuk kemudian dilakukan hyperparameter tuning.

### Train Data
Training data dengan menggunakan parameter default dari model KNN yang dipanggil melalui library Scikitlearn dan meng-import KNeighborsClassifier model.  
![train](https://user-images.githubusercontent.com/74854925/190021841-8733c678-f235-4ed4-b0fd-c410de91887b.jpg)  
Selanjutnya, melihat akurasi dari model KNN dengan parameter default.  
![acc1](https://user-images.githubusercontent.com/74854925/190021878-353d951f-e4a7-4ec6-aaa3-4da7add7bfe2.jpg)   
Akurasi yang didapatkan dari model dengan parameter default adalah 45%, akurasi yang sangat rendah. Oleh karena itu perlu dilakukan hyperparameter tuning untuk menemukan parameter yang tepat dengan tujuan untuk mendapatkan model dengan akurasi yang lebih baik.

### Hyperparameter Tuning
Untuk melakukan hyperparameter tuning, terlebih dahulu harus mengetahui parameter apa saja yang akan dilakukan tuning di model KNN ini. Hyperparameter yang digunakan untuk dilakukan tuning adalah leaf_size, p, dan n_neighbors. Dalam melakukan hyperparameter tuning, akan digunakan GridSearchCV dari library Scikitlearn. Grid search sendiri berfungsi untuk menemukan parameter terbaik dalam model machine learning yang kita gunakan.  
![hptune](https://user-images.githubusercontent.com/74854925/190021916-63803405-a812-4536-8a81-cfd9e913bada.jpg)    
Setelah dilakukan hyperparameter tuning, didapatkan nilai terbaik untuk parameter yang akan kita gunakan yaitu leaf_size=1, p=1, dan n_neighbors=29. Selanjutnya, nilai parameter tersebut akan diaplikasian dan kemudian melihat akurasi yang didapatkan setelah melakukan hyperparameter tuning.  
![train2](https://user-images.githubusercontent.com/74854925/190022178-0d2d1be3-5d61-4c2d-a2d0-d696568ac73e.jpg)  
![acc2](https://user-images.githubusercontent.com/74854925/190022190-38bf77f3-50db-4fd3-86b5-2f9df26e6542.jpg)  
Ternyata setelah dilakukan hyperparameter tuning akurasi yang sebelumnya 45% sekarang menjadi 76%. Hal tersebut berarti hal baik karena kita telah menemukan parameter yang tepat untuk model yang kita gunakan.

## Evaluation
Pada tahap ini akan dilakukan evaluasi terhadap model yang telah dibuat. Jika prediksi mendekati nilai sebenarnya, performanya baik. Sedangkan jika tidak, performanya buruk. Oleh karena itu evaluasi perlu dilakukan untuk mengetahui performa dari model yang telah dibuat.

### Precision, Recall, F1-Score, and Accuracy
Selanjutnya mengukur performa dari model yang telah dibuat dengan melihat persentase dari precision, recall, f1-score, dan accuracy dengan menggunakan fungsi classification_report dari library Scikitlearn. Penjelasan mengenai precision, recall, f1-score, dan accuracy sebagai berikut:
- precision : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan hasil yang diprediksi positif.
- recall : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang benar positif.
- f1-score : f1-score merupakan perbandingan rata-rata precision dan recall yang dibobotkan.
accuracy : merupakan rasio prediksi Benar (positif dan negatif) dengan keseluruhan data.

![metric1](https://user-images.githubusercontent.com/74854925/190022264-642c4991-3e6e-4485-a086-2a9de74c8d2c.jpg)  
Dari output classification report di atas, dapat dilihat performa dari model yaitu 0.76 yang berarti dari 2000 data test yang ada, sekitar 76% data yang diklasifikasikan dengan benar sesuai dengan classnya.

### Confusion Matrix
Kemudian dilanjutkan dengan melihat performa berdasarkan confusion matrix. Pada dasarnya confusion matrix memberikan informasi perbandingan hasil klasifikasi yang dilakukan oleh sistem (model) dengan hasil klasifikasi sebenarnya.
Terdapat 4 istilah sebagai representasi hasil proses klasifikasi pada confusion matrix. Keempat istilah tersebut adalah True Positive (TP), True Negative (TN), False Positive (FP) dan False Negative (FN) dengan masing-masing penjelasannya sebagai berikut:
- True Positive (TP): Merupakan data positif yang diprediksi benar.
- True Negative (TN): Merupakan data negatif yang diprediksi benar.
- False Positive (FP): Merupakan data negatif namun diprediksi sebagai data positif.
- False Negative (FN): Merupakan data positif namun diprediksi sebagai data negatif.

Berikut confussion matrix dari model KNN hyper parameter tuning:  
![metric2](https://user-images.githubusercontent.com/74854925/190022292-2c4b1f10-9eaa-47f7-906d-c6016a03d7c6.jpg)  
Berdasarkan confusion matrix di atas dapat disimpulkan dari 2000 data yang digunakan sebagai data uji, sebanyak 76,25% atau 1525 diprediksi benar (True Negative dan True Positive) oleh model, serta 23.5% atau 475 data salah diprediksi oleh model (False Positive dan False Negative).

## Conclusion
Berdasarkan percobaan yang telah dilakukan untuk membangun sebuah model KNN dalam memprediksi nasabah yang memiliki kemungkinan untuk meninggalkan bank atau menutup rekeningnya, didapatkan kesimpulan sebagai berikut:  
1. Umur, sisa saldo, dan status keaktifan dari nasabah merupakan faktor yang paling berpengaruh terhadap kemungkinan seorang nasabah untuk menutup rekeningnya dari bank.  
2. Dengan menggunakan model machine learning, bank dapat melakukan prediksi terhadap nasabah yang ada saat ini untuk kemudian meningkatkan fitur serta pelayanannya di masa depan dengan memanfaatkan data nasabah sebelumnya.

## References
1. [Peranan Bank Dalam Pembangunan Ekonomi Nasional](https://jurnal.ensiklopediaku.org/ojs-2.4.8-3/index.php/ensiklopedia/article/download/54/29)
2. [Customer Loyalty in Banking Report](https://media.bain.com/Images/BAIN_REPORT_Loyalty_in_Retail_Banking_2013.pdf)
3. [KNeighborsClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
