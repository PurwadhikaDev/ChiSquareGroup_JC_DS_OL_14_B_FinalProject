# Final Project Bank Marketing Campaign Analysis

## Deskripsi Proyek

Proyek ini merupakan bagian dari *final project* untuk menyelesaikan program di Purwadhika Digital School. Tujuan utama dari proyek ini adalah untuk menerapkan pengetahuan yang telah dipelajari selama program, khususnya dalam analisis data dan machine learning, untuk memecahkan masalah nyata yang dihadapi oleh industri perbankan. 

Dalam proyek ini, kami menganalisis data kampanye pemasaran bank untuk memprediksi apakah klien akan berlangganan deposito berjangka. Kami menggunakan berbagai teknik pemodelan, termasuk Gradient Boosting dan AdaBoost, untuk menghasilkan prediksi yang akurat. Proyek ini juga mengajarkan kami pentingnya memahami karakteristik klien dan bagaimana model machine learning dapat digunakan untuk membantu pengambilan keputusan yang lebih efisien di dunia bisnis. 

Dengan proyek ini, kami tidak hanya bertujuan untuk lulus dari program Purwadhika Digital School, tetapi juga mengembangkan keterampilan praktis dalam menerapkan machine learning untuk pemecahan masalah di dunia nyata.


## Kontributor
- Marcia Devana (marciadevana20@gmail.com)
- Lintang Widyani (lintangwidyani96@gmail.com)
- Rifqi Muhammad Lionar (rifqimhd.lio@gmail.com)

## Data Understanding

Dataset yang digunakan berasal dari [Bank Marketing Campaign Dataset](https://www.kaggle.com/datasets/volodymyrgavrysh/bank-marketing-campaigns-dataset).  Dataset ini berisi informasi tentang kampanye pemasaran yang dilakukan oleh bank, termasuk detail klien, kontak, dan hasil kampanye. Berikut adalah beberapa catatan terkait dataset ini:

- Dataset ini tidak seimbang (imbalanced); mayoritas klien tidak berlangganan deposito berjangka.
- Sebagian besar fitur bersifat kategorikal (Nominal, Ordinal, Binary), beberapa memiliki cardinalitas tinggi (misalnya, pekerjaan, pendidikan).
- Setiap baris mewakili interaksi kampanye pemasaran dengan klien bank, menawarkan deposito berjangka.
- Kampanye dilakukan melalui panggilan telepon langsung.
- Target variabel **y** menunjukkan apakah klien berlangganan deposito berjangka (‘yes’ atau ‘no’).

### Data Overview:
- **Number of Instances**: 41,188
- **Number of Attributes**: 20 input features + 1 target (binary classification).
- **Source of Data**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- **Relevant Publication**: 
  - S. Moro, P. Cortez, and P. Rita. *A Data-Driven Approach to Predict the Success of Bank Telemarketing.* Decision Support Systems, Elsevier, 62:22–31, June 2014.

### Attribute Information:
| Attribute       | Data Type | Description                                                                                                |
|-----------------|-----------|------------------------------------------------------------------------------------------------------------|
| age             | Integer   | Age of the client                                                                                           |
| job             | Text      | Type of job (e.g., ‘admin.’, ‘blue-collar’, ‘technician’)                                                    |
| marital         | Text      | Marital status (e.g., ‘married’, ‘single’, ‘divorced’)                                                      |
| education       | Text      | Client’s education level (e.g., ‘university.degree’, ‘high.school’)                                         |
| default         | Text      | Has credit in default? (‘yes’, ‘no’, ‘unknown’)                                                             |
| housing         | Text      | Does the client have a housing loan? (‘yes’, ‘no’, ‘unknown’)                                                |
| loan            | Text      | Does the client have a personal loan? (‘yes’, ‘no’, ‘unknown’)                                               |
| contact         | Text      | Contact communication type (‘cellular’, ‘telephone’)                                                        |
| month           | Text      | Last contact month of the year (e.g., ‘may’, ‘jun’, ‘jul’)                                                   |
| day_of_week     | Text      | Last contact day of the week (e.g., ‘mon’, ‘tue’, ‘wed’)                                                     |
| duration        | Integer   | Last contact duration in seconds                                                                            |
| campaign        | Integer   | Number of contacts performed during this campaign                                                           |
| pdays           | Integer   | Days since the client was last contacted (999 means client was not contacted)                                |
| previous        | Integer   | Number of contacts performed before this campaign                                                           |
| poutcome        | Text      | Outcome of the previous marketing campaign (‘success’, ‘failure’, ‘nonexistent’)                            |
| emp.var.rate    | Float     | Employment variation rate — quarterly indicator                                                             |
| cons.price.idx  | Float     | Consumer price index — monthly indicator                                                                    |
| cons.conf.idx   | Float     | Consumer confidence index — monthly indicator                                                               |
| euribor3m       | Float     | Euribor 3-month interest rate                                                                                |
| nr.employed     | Float     | Number of employees — quarterly indicator                                                                   |
| y               | Text      | Has the client subscribed to a term deposit? (‘yes’, ‘no’)                                                  |


### File yang digunakan:
- **bank-additional-full.csv**: Dataset utama yang digunakan untuk analisis dan pemodelan.
- **finpro-chisquare-tableau.csv**: Dataset tambahan yang digunakan untuk visualisasi lebih lanjut.
- **FINPROCHISQUARE.twbx**: File Tableau yang digunakan untuk membuat visualisasi interaktif.

## Model yang Digunakan

Dalam proyek ini, kami mengeksplorasi beberapa model machine learning untuk memprediksi apakah klien akan berlangganan deposito berjangka. Model-model yang digunakan meliputi:

- **Logistic Regression**: Model dasar yang digunakan untuk klasifikasi biner.
- **Decision Tree**: Model pohon keputusan yang memisahkan data berdasarkan fitur untuk membuat prediksi.
- **K-Neighbors Classifier**: Algoritma berbasis tetangga terdekat yang memprediksi kelas berdasarkan data tetangga yang paling dekat.
- **Random Forest**: Ensambel dari pohon keputusan yang digunakan untuk meningkatkan akurasi prediksi.
- **AdaBoost**: Model ensambel yang meningkatkan performa klasifikasi dengan menggabungkan beberapa model sederhana.
- **XGBoost**: Algoritma boosting yang lebih cepat dan efisien untuk prediksi yang akurat.
- **Gradient Boosting (GBM)**: Awalnya digunakan untuk prediksi dengan hasil yang cukup baik.
- **LightGBM**: Variasi lain dari boosting yang lebih efisien dalam menangani dataset besar.

### Model Terbaik

Setelah evaluasi, model **AdaBoost** dipilih sebagai model terbaik karena memberikan performa yang lebih baik dalam beberapa metrik, terutama recall yang lebih tinggi, yang penting dalam konteks kampanye pemasaran.

## Struktur File
- `bank-additional-full.csv`: Dataset utama yang digunakan untuk analisis.
- `finpro-chisquare-tableau.csv`: Dataset tambahan untuk visualisasi.
- `best_adaboost_model.pkl`: Model AdaBoost terbaik yang disimpan dalam format pickle.
- `FINPROCHISQUARE.twbx`: File Tableau yang digunakan untuk visualisasi data.

## Cara Menjalankan
1. Clone repositori ini:
   ```bash
   git clone https://github.com/PurwadhikaDev/ChiSquareGroup_JC_DS_OL_14_B_FinalProject.git
2. Jalankan Jupyter Notebook (`.ipynb`) untuk melakukan analisis dan pemodelan.
3. Buka file Tableau (`.twbx`) untuk melihat visualisasi interaktif.

## Hasil Akhir

Model terbaik yang diperoleh adalah **AdaBoost** dengan metrik evaluasi sebagai berikut:

| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.92      | 0.97   | 0.94     | 6796    |
| 1     | 0.57      | 0.33   | 0.42     | 851     |

- **Akurasi Keseluruhan**: 0.90
- **Macro Average**:
  - Precision: 0.75
  - Recall: 0.65
  - F1-Score: 0.68
- **Weighted Average**:
  - Precision: 0.88
  - Recall: 0.90
  - F1-Score: 0.89

### Hyperparameter Terbaik:
- `learning_rate`: 1
- `n_estimators`: 200


## Visualisasi
Kami menggunakan Tableau untuk membuat visualisasi interaktif dari data pemasaran bank. Beberapa insight utama yang bisa ditemukan:

- Distribusi klien berdasarkan atribut seperti pekerjaan, usia, dan pendidikan.
- Rasio keberhasilan kampanye terhadap jumlah kontak yang dilakukan.

## Kesimpulan

Model *AdaBoost + SMOTE* memberikan hasil yang lebih seimbang untuk mendeteksi nasabah yang tertarik, meskipun precision-nya lebih rendah dibandingkan dengan *Gradient Boosting*. Dalam kampanye pemasaran, recall lebih penting untuk memastikan kita tidak melewatkan banyak nasabah potensial. Oleh karena itu, *AdaBoost + SMOTE* adalah pilihan yang lebih baik, terutama jika tujuan utamanya adalah mendeteksi lebih banyak nasabah potensial meskipun ada peningkatan biaya untuk nasabah yang salah diprediksi.

### Kinerja Model:
- **Kelas 0 (Nasabah Tidak Tertarik)**:
  - Precision: 0.92
  - Recall: 0.97
  - F1-Score: 0.94
- **Kelas 1 (Nasabah Tertarik)**:
  - Precision: 0.57
  - Recall: 0.33
  - F1-Score: 0.42
- **Akurasi Keseluruhan**: 0.90

### Implikasi Bisnis:
- Model mampu menghemat biaya pemasaran dengan menyaring 97% nasabah yang tidak tertarik, mengurangi pengeluaran yang tidak perlu.
- Namun, model hanya mendeteksi 33% nasabah yang tertarik, sehingga ada risiko kehilangan peluang bisnis dari 67% nasabah potensial yang tidak terdeteksi.

### Perbandingan Biaya:
- **Tanpa Model**: Menghubungi 200 nasabah (100 tertarik, 100 tidak tertarik) menghabiskan 2.000 €.
- **Dengan Model**: Model menghubungi 36 nasabah (33 tertarik, 3 tidak tertarik), dengan total biaya 360 €, dan penghematan 970 € untuk nasabah yang tidak tertarik.

### Kesimpulan Akhir:
- *Keuntungan*: Penghematan biaya pemasaran yang signifikan.
- *Kelemahan*: Masih kehilangan banyak nasabah potensial (67%), yang bisa menyebabkan hilangnya peluang bisnis.

Secara keseluruhan, model ini efektif untuk mengurangi biaya pemasaran, tetapi peningkatan recall pada kelas nasabah tertarik diperlukan agar lebih banyak nasabah potensial dapat dihubungi.

## Rekomendasi

Berikut beberapa rekomendasi yang dapat diberikan kepada tim marketing untuk meningkatkan keberhasilan kampanye bank:

1. **Fokus pada Nasabah Tanpa Personal Loan**  
   Targetkan nasabah yang tidak memiliki personal loan karena mereka lebih cenderung melakukan deposit. Penawaran produk tabungan atau program loyalitas dengan suku bunga menarik bisa menjadi daya tarik.

2. **Fokus pada Nasabah dengan Housing Loan**  
   Nasabah dengan housing loan memiliki kecenderungan lebih tinggi untuk melakukan deposit. Penawaran bundling produk investasi atau tabungan dapat menarik segmen ini.

3. **Perhatikan Segmen Usia dan Pendidikan**  
   Fokus pada nasabah berpendidikan tinggi dan kelompok usia lansia (lebih dari 65 tahun) yang cenderung lebih sadar akan pentingnya perencanaan keuangan. Kampanye bisa difokuskan pada edukasi finansial dan perencanaan pensiun.

4. **Kampanye Berdasarkan Status Pernikahan**  
   Nasabah yang sudah menikah lebih cenderung melakukan deposit. Kampanye bisa difokuskan pada produk yang mendukung gaya hidup keluarga seperti tabungan pendidikan anak atau perencanaan masa depan.

5. **Segmentasi Berdasarkan Pekerjaan**  
   Targetkan profesi seperti admin, technician, dan blue-collar yang memiliki kecenderungan lebih besar untuk melakukan deposit. Penawaran produk pensiun atau tabungan jangka pendek dapat menarik segmen ini.

### Rekomendasi Terhadap Model Machine Learning:

1. Mencoba algoritma lain dan melakukan hyperparameter tuning kembali.
2. Mengisi data 'unknown' dengan informasi yang lebih detail untuk meningkatkan akurasi.
3. Menambah data nasabah yang tertarik membuka deposito berjangka.
4. Mengintegrasikan data ekonomi yang relevan untuk analisis lebih lanjut.

Dengan segmentasi yang lebih tepat dan kampanye yang disesuaikan, tim marketing dapat lebih efektif dalam menarik nasabah yang potensial dan meningkatkan konversi ke produk deposito.

