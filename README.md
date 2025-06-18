- Nama: MUHAMMAD TEGAR ABHIRAM
- Email: tagar.abhiram77@student.ub.ac.id
- Id Dicoding: garrr007

# Proyek: Menyelesaikan Permasalahan Human Resources

## Business Understanding 
Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Ia memiliki lebih dari 1000 karyawan yang tersebar di seluruh penjuru negeri. 

Walaupun telah menjadi menjadi perusahaan yang cukup besar, Jaya Jaya Maju masih cukup kesulitan dalam mengelola karyawan. Hal ini berimbas tingginya attrition rate (rasio jumlah karyawan yang keluar dengan total karyawan keseluruhan) hingga lebih dari 10%.

Untuk mencegah hal ini semakin parah, manajer departemen HR ingin meminta bantuan untuk mengidentifikasi berbagai faktor yang mempengaruhi tingginya attrition rate tersebut. Selain itu, dibuat juga business dashboard untuk membantunya memonitori berbagai faktor tersebut. 

## Permasalahan Bisnis 
Meskipun Jaya Jaya Maju telah berkembang menjadi perusahaan multinasional dengan lebih dari 1000 karyawan,  tingkat attrition rate  menjadi tantangan serius bagi keberlanjutan dan stabilitas perusahaan. 

Kondisi ini menunjukkan bahwa ada masalah mendasar dalam **manajemen sumber daya manusia**, yang jika dibiarkan, dapat berdampak pada:

- **Produktivitas tim yang terganggu** karena seringnya terjadi pergantian karyawan.
- **Peningkatan biaya rekrutmen dan pelatihan** akibat tingginya kebutuhan penggantian tenaga kerja.
- **Menurunnya moral karyawan** yang tersisa, karena merasa lingkungan kerja tidak stabil.
- **Risiko kehilangan talenta terbaik**, terutama jika mereka tidak puas dengan kondisi kerja yang ada.

---

Dalam upaya memahami penyebab utama dari tingginya tingkat attrition ini, diperlukan analisis data karyawan secara menyeluruh untuk mengidentifikasi pola-pola atau faktor-faktor signifikan yang berkontribusi terhadap keputusan karyawan untuk keluar, seperti:

- Tingkat kepuasan kerja
- Tingkat Work Life Balance
- Gaji dan tunjangan
- Hubungan dengan atasan
- Dan lainnya
---

Selain itu, business dashboard interaktif juga dibutuhkan sebagai alat bantu untuk:

- Memberikan **visualisasi faktor-faktor kunci** yang berkorelasi dengan attrition.
- Memungkinkan **pemantauan real-time** terhadap kondisi sumber daya manusia.
- Mendukung **pengambilan keputusan berbasis data** oleh manajer HR.

---

Tujuan akhir dari inisiatif ini adalah untuk merancang strategi HR yang lebih efektif dalam:

- Menurunkan tingkat attrition
- Meningkatkan retensi karyawan
- Menjaga keberlangsungan dan kualitas operasional perusahaan

## Cakupan Proyek

Proyek ini bertujuan untuk membantu departemen Human Resource (HR) Jaya Jaya Maju dalam mengidentifikasi dan memahami faktor-faktor yang mempengaruhi tingginya tingkat attrition karyawan. Adapun cakupan dari proyek ini meliputi:

### 1. Pengumpulan dan Persiapan Data
- Mengumpulkan data karyawan dari berbagai sumber internal perusahaan.
- Melakukan pembersihan dan praproses data untuk memastikan kualitas data yang digunakan dalam analisis.

### 2. Eksplorasi dan Analisis Data (EDA)
- Melakukan analisis deskriptif untuk memahami karakteristik data karyawan.
- Mengidentifikasi korelasi antara variabel-variabel seperti masa kerja, gaji, kepuasan kerja, dan jam lembur dengan attrition.
- Menggali pola-pola potensial penyebab karyawan keluar.

### 3. Pembuatan Model Prediksi Attrition 
- Membangun model machine learning untuk memprediksi kemungkinan seorang karyawan akan keluar dari perusahaan.
- Mengevaluasi performa model menggunakan metrik seperti precision, recall, F1-score, dan akurasi.

### 4. Pengembangan Dashboard Interaktif
- Mendesain dan membangun business dashboard yang menampilkan:
  - Statistik attrition secara umum dan berdasarkan kategori tertentu.
  - Visualisasi hubungan antara faktor-faktor seperti kepuasan kerja, masa kerja, dan beban kerja terhadap attrition.
  - Fitur filter interaktif untuk eksplorasi data oleh manajer HR.

### 5. Penyusunan Rekomendasi Strategis
- Memberikan insight berbasis data untuk membantu manajer HR dalam mengambil keputusan.
- Menyusun rekomendasi strategis untuk menurunkan tingkat attrition dan meningkatkan retensi karyawan.

## Pengumpulan dan Persiapan Data
### Setup Environment
```
docker pull metabase/metabase:v0.46.4
```
Perintah Docker yang digunakan untuk mengunduh image Metabase versi 0.46.4 dari Docker Hub ke komputer lokal
```
docker run -p 3000:3000 --name metabase metabase/metabase
```
Perintah itu akan menjalankan Metabase di localhost:3000
### Informasi Dataset

Sumber: [Dicoding](https://raw.githubusercontent.com/dicodingacademy/dicoding_dataset/main/employee/employee_data.csv), 

Dataset yang digunakan memuat dimensi sebesar **1470 baris** dan **36 kolom**. Untuk kolom yang terdapat pada dataset dijabarkan sebagai berikut:

| Nama Fitur               | Deskripsi                                                                 |
|--------------------------|---------------------------------------------------------------------------|
| EmployeeId               | ID unik karyawan                                                         |
| Age                      | Usia karyawan (tahun)                                                    |
| Attrition               | Status karyawan keluar (1) atau tetap (0)   |
| BusinessTravel           | Frekuensi perjalanan bisnis                                              |
| DailyRate                | Gaji harian                                                              |
| Department               | Departemen tempat karyawan bekerja                                       |
| DistanceFromHome         | Jarak dari rumah ke tempat kerja (mil)                                   |
| Education                | Tingkat pendidikan (1: SD, 2: SMP, ..., 5: S3)                            |
| EducationField           | Bidang pendidikan                                                        |
| EmployeeCount            | Jumlah karyawan |
| EnvironmentSatisfaction  | Tingkat kepuasan terhadap lingkungan kerja (1 – 4)                        |
| Gender                   | Jenis kelamin (Male/Female)                                              |
| HourlyRate               | Gaji per jam                                                             |
| JobInvolvement           | Tingkat keterlibatan dalam pekerjaan (1 – 4)                              |
| JobLevel                 | Level pekerjaan (1 – 5)                                                  |
| JobRole                  | Jabatan karyawan                                                         |
| JobSatisfaction          | Tingkat kepuasan terhadap pekerjaan (1 – 4)                               |
| MaritalStatus            | Status pernikahan (Single/Married/Divorced)                             |
| MonthlyIncome            | Gaji bulanan                                                             |
| MonthlyRate              | Gaji bulanan dalam bentuk rate (bisa berbeda dengan MonthlyIncome)      |
| NumCompaniesWorked       | Jumlah perusahaan sebelumnya yang pernah bekerja                         |
| Over18                   | Apakah berusia di atas 18 tahun (Y/N)                                    |
| OverTime                 | Apakah sering bekerja lembur (Yes/No)                                    |
| PercentSalaryHike        | Persentase kenaikan gaji terakhir                                        |
| PerformanceRating        | Penilaian kinerja (1 – 4)                                                 |
| RelationshipSatisfaction | Tingkat kepuasan terhadap hubungan di tempat kerja (1 – 4)                |
| StandardHours            | Jam kerja standar                            |
| StockOptionLevel         | Level opsi saham yang diberikan (0 – 3)                                  |
| TotalWorkingYears        | Total tahun pengalaman kerja                                             |
| TrainingTimesLastYear    | Jumlah pelatihan yang diikuti dalam 1 tahun terakhir                     |
| WorkLifeBalance          | Keseimbangan kerja dan kehidupan pribadi (1 – 4)                          |
| YearsAtCompany           | Lama bekerja di perusahaan saat ini (tahun)                              |
| YearsInCurrentRole       | Lama menjabat posisi saat ini (tahun)                                    |
| YearsSinceLastPromotion  | Tahun sejak terakhir promosi                                             |
| YearsWithCurrManager     | Lama bekerja dengan manajer saat ini (tahun) 

### Data Preparation
#### Checking Missing Values
Skrip Python cek nilai null
```
employee_df.isna().sum()
```

| Fitur                     | Jumlah Missing Values |
|--------------------------|------------------------|
| index                    | 0                      |
| EmployeeId               | 0                      |
| Age                      | 0                      |
| Attrition                | 412                    |
| BusinessTravel           | 0                      |
| DailyRate                | 0                      |
| Department               | 0                      |
| DistanceFromHome         | 0                      |
| Education                | 0                      |
| EducationField           | 0                      |
| EmployeeCount            | 0                      |
| EnvironmentSatisfaction  | 0                      |
| Gender                   | 0                      |
| HourlyRate               | 0                      |
| JobInvolvement           | 0                      |
| JobLevel                 | 0                      |
| JobRole                  | 0                      |
| JobSatisfaction          | 0                      |
| MaritalStatus            | 0                      |
| MonthlyIncome            | 0                      |
| MonthlyRate              | 0                      |
| NumCompaniesWorked       | 0                      |
| Over18                   | 0                      |
| OverTime                 | 0                      |
| PercentSalaryHike        | 0                      |
| PerformanceRating        | 0                      |
| RelationshipSatisfaction | 0                      |
| StandardHours            | 0                      |
| StockOptionLevel         | 0                      |
| TotalWorkingYears        | 0                      |
| TrainingTimesLastYear    | 0                      |
| WorkLifeBalance          | 0                      |
| YearsAtCompany           | 0                      |
| YearsInCurrentRole       | 0                      |
| YearsSinceLastPromotion  | 0                      |
| YearsWithCurrManager     | 0                      |

Terdapat 412 baris data pada kolom Attrion yang bernilai Null
```
employee_df['Attrition'] = employee_df['Attrition'].fillna(0.0)
```
Mengisi (fill) nilai kosong (NaN) di kolom 'Attrition' dengan angka 0.0.
Jadi, kalau ada data yang hilang di kolom Attrition, sekarang akan diganti jadi 0.0 supaya tidak ada missing value.

#### Mengecek jumlah nilai unik per kolom 
```
unique_counts = employee_df.nunique()
print("Jumlah nilai unik per kolom:")
```

Jumlah Nilai Unik per Kolom

| Fitur                     | Jumlah Nilai Unik |
|--------------------------|--------------------|
| index                    | 1470               |
| EmployeeId               | 1470               |
| Age                      | 43                 |
| Attrition                | 2                  |
| BusinessTravel           | 3                  |
| DailyRate                | 886                |
| Department               | 3                  |
| DistanceFromHome         | 29                 |
| Education                | 5                  |
| EducationField           | 6                  |
| EmployeeCount            | 1                  |
| EnvironmentSatisfaction  | 4                  |
| Gender                   | 2                  |
| HourlyRate               | 71                 |
| JobInvolvement           | 4                  |
| JobLevel                 | 5                  |
| JobRole                  | 9                  |
| JobSatisfaction          | 4                  |
| MaritalStatus            | 3                  |
| MonthlyIncome            | 1349               |
| MonthlyRate              | 1427               |
| NumCompaniesWorked       | 10                 |
| Over18                   | 1                  |
| OverTime                 | 2                  |
| PercentSalaryHike        | 15                 |
| PerformanceRating        | 2                  |
| RelationshipSatisfaction | 4                  |
| StandardHours            | 1                  |
| StockOptionLevel         | 4                  |
| TotalWorkingYears        | 40                 |
| TrainingTimesLastYear    | 7                  |
| WorkLifeBalance          | 4                  |
| YearsAtCompany           | 37                 |
| YearsInCurrentRole       | 19                 |
| YearsSinceLastPromotion  | 16                 |
| YearsWithCurrManager     | 18                 |

Memilih kolom yang hanya memiliki satu nilai unik
```
columns_to_drop = unique_counts[unique_counts == 1].index.tolist()
```
Kolom yang akan dihapus karena hanya memiliki satu nilai unik:
['EmployeeCount', 'Over18', 'StandardHours']

Menghapus kolom tersebut
```
employee_df_cleaned = employee_df.drop(columns=columns_to_drop)
```

#### Memiliih kolom kolom yang berhubungan langsung dengan karakteristik karyawan dan faktor-faktor yang mungkin memengaruhi attrition 
'Attrition', 'Age', 'Gender', 'MaritalStatus',
    'JobRole', 'JobLevel', 'Department',
    'PerformanceRating', 'JobInvolvement', 'JobSatisfaction',
    'EnvironmentSatisfaction', 'RelationshipSatisfaction', 'WorkLifeBalance',
    'TotalWorkingYears', 'YearsAtCompany', 'YearsInCurrentRole',
    'YearsSinceLastPromotion', 'YearsWithCurrManager', 'NumCompaniesWorked',
    'TrainingTimesLastYear', 'MonthlyIncome', 'PercentSalaryHike',
    'StockOptionLevel', 'BusinessTravel', 'DistanceFromHome',
    'OverTime', 'Education', 'EducationField'
    
#### Menambahkan fitur turunan ke dalam dataset main_df
```
main_df['YearsSinceChange'] = main_df['YearsAtCompany'] - main_df['YearsInCurrentRole']
main_df['IsRecentlyPromoted'] = (main_df['YearsSinceLastPromotion'] < 2).astype(int)
main_df['IsNewEmployee'] = (main_df['YearsAtCompany'] < 2).astype(int)
main_df['IsManagerConsistent'] = (main_df['YearsWithCurrManager'] >= main_df['YearsAtCompany']).astype(int)
main_df['IncomePerYear'] = main_df['MonthlyIncome'] * 12 / main_df['TotalWorkingYears'].replace(0, 1)
main_df['JobSatisfactionLevel'] = main_df[['JobSatisfaction', 'JobInvolvement', 'EnvironmentSatisfaction']].mean(axis=1)
main_df['IsOverTime'] = (main_df['OverTime'] == 'Yes').astype(int)
```
YearsSinceChange: Lama waktu sejak karyawan terakhir berganti peran.  
IsRecentlyPromoted: Apakah karyawan baru saja dipromosikan (kurang dari 2 tahun).  
IsNewEmployee: Menandai karyawan yang baru bekerja (< 2 tahun).  
IsManagerConsistent: Apakah manajer mereka tidak berubah sejak bergabung.  
IncomePerYear: Rata-rata pendapatan per tahun bekerja.  
JobSatisfactionLevel: Rata-rata kepuasan kerja gabungan dari beberapa aspek.  
IsOverTime: Menandai apakah karyawan bekerja lembur.

## Exploratory Data Analysis (EDA)
### Data Numerik
![Image](https://github.com/user-attachments/assets/378e4557-9806-4559-99ca-457f673d7aa4)

Berikut adalah ringkasan interpretasi dari grafik distribusi fitur numerik pada dataset karyawan:
- **Age**: Mayoritas karyawan berada pada rentang usia 25–45 tahun, menunjukkan dominasi usia produktif di perusahaan.
- **Attrition**: Sebagian besar karyawan tidak keluar dari perusahaan, menandakan tingkat retensi karyawan yang cukup tinggi.
- **DailyRate**: Nilai gaji harian tersebar secara acak, tidak menunjukkan distribusi atau pola khusus.
- **DistanceFromHome**: Sebagian besar karyawan tinggal cukup dekat dengan lokasi kantor.
- **Education**: Tingkat pendidikan didominasi oleh jenjang menengah (misalnya D3/S1).
- **EmployeeCount**: Nilainya konstan (satu nilai saja), sehingga tidak memberikan informasi berarti.
- **EnvironmentSatisfaction**: Mayoritas karyawan merasa puas dengan lingkungan kerja.
- **HourlyRate**: Gaji per jam tersebar acak tanpa pola distribusi yang jelas.
- **JobInvolvement**: Keterlibatan dalam pekerjaan berada pada tingkat sedang hingga tinggi.
- **JobLevel**: Mayoritas karyawan berada di level pekerjaan yang lebih rendah (entry-level).
- **JobSatisfaction**: Tingkat kepuasan kerja cukup bervariasi antar karyawan.
- **MonthlyIncome**: Sebagian besar karyawan memiliki pendapatan bulanan di bawah 10.000 (mata uang tidak disebutkan).
- **MonthlyRate**: Distribusi gaji bulanan tidak merata, tampak acak.
- **NumCompaniesWorked**: Banyak karyawan yang hanya pernah bekerja di sedikit perusahaan sebelumnya.
- **PercentSalaryHike**: Kenaikan gaji mayoritas berada pada kisaran 11–15%.
- **PerformanceRating**: Hampir semua karyawan memiliki rating performa sedang, menunjukkan distribusi yang tidak bervariasi.
- **RelationshipSatisfaction**: Kepuasan terhadap hubungan kerja tergolong tinggi pada sebagian besar karyawan.
- **StandardHours**: Nilainya sama untuk semua karyawan, sehingga tidak relevan untuk dianalisis lebih lanjut.
- **StockOptionLevel**: Sebagian besar karyawan tidak mendapatkan opsi saham.
- **TotalWorkingYears**: Mayoritas karyawan memiliki pengalaman kerja kurang dari 15 tahun.
- **TrainingTimesLastYear**: Pelatihan yang diikuti dalam setahun terakhir tidak merata.
- **WorkLifeBalance**: Sebagian besar karyawan merasa memiliki keseimbangan hidup dan kerja yang baik.
- **YearsAtCompany**: Banyak karyawan baru dengan lama bekerja 0–5 tahun.
- **YearsInCurrentRole**: Mayoritas karyawan belum terlalu lama di peran saat ini.
- **YearsWithCurrManager**: Hubungan dengan manajer saat ini masih tergolong baru.
- **YearsSinceLastPromotion**: Banyak karyawan yang belum dipromosikan dalam waktu yang cukup.

### Data Kategorikal
![Image](https://github.com/user-attachments/assets/4b87a441-982a-4be1-b98b-12580b68b69e)

Berikut adalah ringkasan interpretasi dari grafik distribusi fitur kategorikal pada dataset karyawan:
- **BusinessTravel** – Mayoritas karyawan hanya sesekali melakukan perjalanan bisnis.
- **Department** – Karyawan paling banyak bekerja di Research & Development, disusul Sales.
- **EducationField** – Latar belakang pendidikan paling umum adalah Life Sciences dan Medical.
- **Gender** – Komposisi karyawan lebih banyak laki-laki dibanding perempuan.
- **JobRole** – Pekerjaan terbanyak adalah Sales Executive dan Research Scientist.
- **MaritalStatus** – Sebagian besar karyawan sudah menikah, disusul yang masih lajang.
- **Over18** – Semua karyawan berusia di atas 18 tahun, fitur ini tidak variatif.
- **OverTime** – Lebih banyak karyawan yang tidak bekerja lembur dibanding yang lembur.

## Heatmap Korelasi Fitur Numerik Terpilih terhadap Attrition
![Image](https://github.com/user-attachments/assets/3b19baac-6e43-4875-ae03-84d2291a5e3e)

**Fitur** | **Korelasi** | **Interpretasi**
--- | --- | ---
Age | -0.14 | Karyawan lebih tua cenderung lebih stabil dan jarang keluar.
MonthlyIncome | -0.13 | Gaji tinggi berkorelasi dengan tingkat keluar yang lebih rendah.
TotalWorkingYears | -0.14 | Karyawan dengan pengalaman panjang cenderung lebih loyal.
YearsAtCompany | -0.13 | Lama bekerja di perusahaan mengurangi kecenderungan keluar.
YearsInCurrentRole | -0.13 | Lama di peran saat ini → loyalitas atau stabilitas posisi.
YearsWithCurrManager | -0.13 | Hubungan jangka panjang dengan atasan berkaitan dengan retensi.

## Pembuatan Model Prediksi Attrition
### Preprocessing
#### Encoding Target
```
main_df['Attrition'] = main_df['Attrition'].map({'Yes': 1, 'No': 0})
```
'Yes' → 1 (menandakan karyawan resign)
'No' → 0 (menandakan karyawan tetap)
Ini dilakukan agar kolom target bisa diproses oleh model machine learning yang membutuhkan input numerik.

#### Encoding Fitur Kategorikal
```
categorical_cols = main_df.select_dtypes(include=['object']).columns.tolist()
categorical_cols = [col for col in categorical_cols if col != 'Attrition']
```

Menyiapkan daftar kolom kategorikal untuk proses encoding selanjutnya
```
le = LabelEncoder()
for col in categorical_cols:
    main_df[col] = le.fit_transform(main_df[col])
```
Menggunakan LabelEncoder untuk mengubah nilai kategori (teks) di setiap kolom kategorikal menjadi angka.
Setiap nilai unik di kolom akan diberi label numerik (misalnya: Male → 1, Female → 0).
Dilakukan agar fitur kategorikal bisa diproses oleh model machine learning.

#### Split fitur dan target
```
X = main_df.drop(['Attrition', 'AttritionNum', 'EmployeeId'], axis=1)
y = main_df["Attrition"]
```
Memisahkan fitur (X) dan target (y) sebelum pelatihan model

#### Data Splitting
```
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)
```
Membagi data menjadi training set dan testing set dengan proporsi:
80% untuk training, 20% untuk testing 

#### Feature Scaling
```
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```
Standarisasi fitur (skala data) agar setiap fitur memiliki mean = 0 dan standar deviasi = 1:

### Modeling 
#### SMOTE (Synthetic Minority Over-sampling Technique)
```
smote = SMOTE(random_state=42)
X_train_res, y_train_res = smote.fit_resample(X_train_scaled, y_train)
```
SMOTE adalah teknik oversampling yang digunakan untuk menangani masalah ketidakseimbangan kelas (class imbalance) pada data klasifikasi. Dalam konteks ini, kemungkinan besar target y_train (seperti Attrition) memiliki jumlah kelas yang tidak seimbang — misalnya, lebih banyak karyawan yang tidak keluar (No) dibandingkan yang keluar (Yes).

Tujuan dari SMOTE
- Meningkatkan jumlah data pada kelas minoritas (misalnya Attrition = Yes) dengan mensintesis data baru, bukan sekadar menduplikasinya.
- Membantu model agar tidak bias terhadap kelas mayoritas dan bisa belajar lebih baik mengenali pola dari kedua kelas.

#### Model Training 
Setelah data diseimbangkan menggunakan teknik **SMOTE**, proses berikutnya adalah melatih beberapa model klasifikasi untuk memprediksi kemungkinan karyawan melakukan *attrition* (keluar dari perusahaan). Lima algoritma klasifikasi digunakan dalam proyek ini, yaitu:

- Logistic Regression  
- K-Nearest Neighbors (KNN)  
- Support Vector Machine (SVM)  
- Random Forest  
- Gradient Boosting  

Pemilihan kelima model ini didasarkan pada kombinasi antara **kemampuan generalisasi**, **kemudahan interpretasi**, serta **kemampuan menangani data yang tidak seimbang**.

---

##### logistic Regression

Model statistik yang memprediksi probabilitas dari kelas target. Logistic Regression sangat cocok digunakan sebagai baseline karena:

- Sederhana dan mudah diinterpretasikan  
- Menghasilkan output probabilitas, berguna untuk menganalisis risiko  
- Cocok untuk data linier dan efisien dalam pelatihan  

---

##### Nearest Neighbors (KNN)

Model berbasis instance yang menentukan kelas berdasarkan mayoritas dari k tetangga terdekat. Karakteristik:

- Tidak ada proses training yang kompleks (*lazy learning*)  
- Hasil sangat bergantung pada pemilihan nilai K dan preprocessing (terutama skala data)  
- Cocok untuk dataset kecil dan pola yang tidak linier  

---

##### Support Vector Machine (SVM)

Model yang berusaha menemukan hyperplane terbaik untuk memisahkan dua kelas dengan margin maksimal. Keunggulan:

- Baik untuk data berdimensi tinggi  
- Mampu menangani data linier dan non-linier dengan kernel  
- Relatif tahan terhadap overfitting  

---

##### Random Forest

Random Forest adalah model berbasis ensemble learning yang terdiri dari banyak *decision tree* yang dilatih secara acak. Keunggulan:

- Mengurangi overfitting dibandingkan decision tree tunggal  
- Baik dalam menangani data dengan banyak fitur dan interaksi antar fitur  
- Memberikan fitur penting (*feature importance*) sebagai hasil interpretasi model  

---

##### Gradient Boosting

Gradient Boosting adalah model ensemble yang membangun pohon keputusan secara bertahap, dengan memperbaiki kesalahan dari model sebelumnya. Karakteristik:

- Performa tinggi, terutama untuk data kompleks  
- Cocok untuk prediksi yang sensitif terhadap kesalahan kecil  
- Cenderung lebih lambat dibanding Random Forest karena pembelajaran dilakukan secara sekuensial, bukan paralel  

---

##### Tujuan Pelatihan Multi-Model

Pelatihan kelima model ini dilakukan untuk membandingkan performa dari berbagai algoritma, terutama pada:

- Akurasi keseluruhan prediksi  
- Recall dan precision pada kelas *Attrition* (positif)  
- Kemampuan model dalam menangani data tidak seimbang  
- Interpretabilitas model untuk keperluan bisnis 


### Evaluasi Model
Model Terbaik Berdasarkan Accuracy
| Model                   | Accuracy | Precision | Recall   | F1-Score |
|-------------------------|----------|-----------|----------|----------|
| Random Forest           | 0.891156 | 0.666667  | 0.222222 | 0.333333 |
| Gradient Boosting       | 0.891156 | 0.642857  | 0.250000 | 0.360000 |
| Support Vector Machine  | 0.850340 | 0.394737  | 0.416667 | 0.405405 |
| Logistic Regression     | 0.799320 | 0.361446  | 0.833333 | 0.504202 |
| K-Nearest Neighbors     | 0.700680 | 0.240000  | 0.666667 | 0.352941 |


 Model terbaik adalah model random forest dengan accuracy sebesar 0.89
 
### Contoh 20 Data Prediksi
Berikut adalah 20 contoh perbandingan nilai asli dan hasil prediksi model yang digunakan:

| Index | Actual | Pred_LR | Pred_DT | Pred_RF | Pred_GB | Pred_SVM |
|-------|--------|---------|---------|---------|---------|----------|
| 0     | 0      | 1       | 0       | 0       | 0       | 0        |
| 1     | 1      | 1       | 0       | 0       | 0       | 0        |
| 2     | 0      | 0       | 0       | 0       | 0       | 0        |
| 3     | 0      | 0       | 0       | 0       | 0       | 0        |
| 4     | 0      | 0       | 0       | 0       | 0       | 0        |
| 5     | 0      | 0       | 0       | 0       | 0       | 0        |
| 6     | 0      | 0       | 0       | 0       | 0       | 0        |
| 7     | 0      | 1       | 0       | 0       | 0       | 0        |
| 8     | 0      | 0       | 0       | 0       | 0       | 0        |
| 9     | 0      | 1       | 1       | 0       | 0       | 0        |
| 10    | 0      | 0       | 0       | 0       | 0       | 0        |
| 11    | 1      | 1       | 0       | 0       | 1       | 1        |
| 12    | 0      | 0       | 0       | 0       | 0       | 0        |
| 13    | 0      | 0       | 0       | 0       | 0       | 0        |
| 14    | 0      | 0       | 1       | 1       | 0       | 0        |
| 15    | 0      | 0       | 0       | 0       | 0       | 0        |
| 16    | 1      | 1       | 1       | 0       | 0       | 1        |
| 17    | 0      | 0       | 0       | 0       | 0       | 0        |
| 18    | 0      | 0       | 0       | 0       | 0       | 0        |
| 19    | 0      | 0       | 0       | 0       | 0       | 0        |

Berdasarkan tabel di atas, kita dapat melihat bahwa model SVM (SVM) memiliki prediksi yang paling mendekati nilai aktual (y_true) di antara model-model yang dibandingkan.

## Business Dashboard
![Image](https://github.com/user-attachments/assets/ccc0365b-6a50-4b10-b6e8-9cdf1b0afb88)
![Image](https://github.com/user-attachments/assets/20884b0d-c87b-43d9-8843-ddcdfe11eab5)

Dashboard ini dirancang untuk memberikan gambaran komprehensif terkait faktor-faktor yang mempengaruhi tingginya tingkat keluar (attrition) karyawan di perusahaan Jaya Jaya Maju. 

Ringkasan umum mengenai kondisi attrition di perusahaan:

- Total Karyawan dan Tingkat Attrition
  - Total karyawan: 1.470  
  - Jumlah keluar: 179  
  - Attrition Rate: 22,12% – termasuk kategori tinggi.

- Attrition Berdasarkan Job Role  
  - `Sales Representative`: tingkat tertinggi (30,12%)  
  - Diikuti oleh `Laboratory Technician` dan `Research Scientist`.

- Attrition Berdasarkan Usia  
  - Usia di bawah 25 tahun: hampir 30% keluar.  
  - Usia 35–54 tahun cenderung lebih stabil.

- Attrition Berdasarkan Departemen  
  - Departemen `Sales`: attrition tertinggi (14,8%)  
  - Disusul oleh `R&D` dan `Human Resources`.

- Attrition Berdasarkan Status Pernikahan & Gender  
  - Karyawan single memiliki kemungkinan keluar lebih tinggi daripada yang menikah atau bercerai.
  - 
- Job Satisfaction (Kepuasan Kerja)  
  - Semakin rendah kepuasan, semakin tinggi attrition rate.

- Pendapatan* 
  - Rata-rata gaji karyawan yang keluar: $4.9k 
  - Rata-rata gaji karyawan yang bertahan: $6.7k

- Lama Bekerja (Tenure)  
  - Karyawan dengan masa kerja < 1 tahun memiliki attrition tertinggi (40%).  
  - Ini menandakan pentingnya proses onboarding yang efektif.

- Riwayat Kerja Sebelumnya (NumCompaniesWorked)  
  - Mereka yang pernah bekerja di >5 perusahaan memiliki kemungkinan keluar lebih tinggi.  
  - Tertinggi pada angka 5 perusahaan sebelumnya: 20,63%

- **Work-Life Balance (WLB)  
  - WLB level 1 (buruk): 22,5% attrition  
  - WLB level 4 (sangat baik): hanya 14,38%  
  - Semakin baik WLB, semakin rendah kemungkinan keluar.
  - 

Dari dashboard ini, terdapat beberapa insight kunci:

1. Usia muda dan posisi tertentu (seperti Sales Representative) memiliki tingkat attrition yang tinggi.
2. Kepuasan kerja dan keseimbangan kerja-hidup sangat berpengaruh terhadap keputusan karyawan.
3. Gaji rendah merupakan salah satu indikator yang berkorelasi kuat dengan keputusan untuk keluar.
4. Karyawan dengan masa kerja singkat dan riwayat pekerjaan yang berpindah-pindah cenderung lebih tidak stabil.

## Rekomendasi Action Items untuk Menurunkan Attrition dan Mencapai Target Perusahaan

### 1.  Fokus pada Karyawan Muda (Usia <25 dan 25–34 Tahun)
**Masalah:** Tingkat attrition tertinggi berada pada kelompok usia muda (29,9% dan 15,34%).

**Action:**
- Perkuat program onboarding dan mentoring untuk karyawan baru.
- Buat jalur karier yang jelas dan komunikasikan peluang pengembangan.
- Tawarkan pelatihan keterampilan dan sertifikasi yang relevan.

---

###  2. Perhatikan Role dengan Tingkat Attrition Tinggi (Sales Rep & Lab Technician)
**Masalah:** Sales Representative memiliki tingkat attrition 30,12% dan Laboratory Technician 18,92%.

**Action:**
- Evaluasi kembali beban kerja dan kompensasi di posisi tersebut.
- Buat program penghargaan berbasis performa dan engagement bulanan.
- Lakukan sesi feedback rutin untuk mengetahui pain point karyawan di role tersebut.

---

### 3. Tingkatkan Kompensasi dan Kenaikan Gaji
**Masalah:** Rata-rata salary karyawan yang keluar hanya $4.9k, lebih rendah dari yang tetap ($6.7k).

**Action:**
- Evaluasi struktur gaji, terutama untuk karyawan level awal.
- Jadwalkan review tahunan yang adil dan transparan untuk kenaikan gaji.
- Tawarkan benefit non-finansial seperti asuransi kesehatan, cuti tambahan, atau hybrid work.

---

### 4. Tingkatkan Work-Life Balance
**Masalah:** Level WorkLifeBalance terendah (Level 1) memiliki attrition rate 22,5%.

**Action:**
- Lakukan survei internal untuk mengetahui faktor stres dan kelelahan kerja.
- Terapkan kebijakan work-from-home atau jam kerja fleksibel di departemen tertentu.
- Bangun budaya kerja yang mendukung keseimbangan hidup dengan pelatihan manajerial.

---

### 5. Perkuat Engagement di Tahun-Tahun Awal Kerja
**Masalah:** Karyawan <1 tahun dan 1–3 tahun memiliki attrition rate tinggi (40% dan 31%).

**Action:**
- Desain program retensi khusus untuk 3 tahun pertama (career roadmap, bonus milestone).
- Lakukan exit interview untuk karyawan awal yang keluar dan petakan pola penyebabnya.
- Berikan benefit loyalitas untuk karyawan yang bertahan 1-3 tahun.

---

### Fokus pada Karyawan yang Sering Pindah Perusahaan 
**Masalah:** Karyawan dengan 5–7 perusahaan sebelumnya menunjukkan attrition tinggi.

**Action:**
- Lakukan screening lebih mendalam terhadap kandidat dengan riwayat kerja pendek.
- Pertimbangkan probation atau contract-to-permanent model pada rekrutmen.

---

