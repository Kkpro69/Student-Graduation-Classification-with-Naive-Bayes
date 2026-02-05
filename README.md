🎓 Student Graduation Classification with Naive Bayes

Proyek ini bertujuan untuk melakukan klasifikasi kelulusan mahasiswa menggunakan data dummy guna menguji performa model Naive Bayes pada dataset berukuran kecil. Studi ini berfokus pada analisis data (tanpa implementasi ke end user).

📌 Deskripsi Singkat

Pada kasus ini digunakan model Naive Bayes untuk mengklasifikasikan status kelulusan mahasiswa berdasarkan beberapa variabel akademik. Dataset bersifat dummy dan digunakan untuk melihat apakah model mampu bekerja dengan baik meskipun jumlah data relatif sedikit.

Hasil pengujian menunjukkan performa model yang sangat baik dengan akurasi sebesar 0.98 (98%).

🔄 Pipeline Implementasi

Tahapan pemodelan dilakukan menggunakan pipeline dengan urutan sebagai berikut:

1. First Cleaning
(Tidak dilakukan imputasi maupun encoding)
2. Data Splitting
Pembagian data menjadi training set dan testing set
3. Exploratory Data Analysis (EDA)
Dilakukan hanya pada data training
4. Preprocessing
Scaling data
5. Modeling
Naive Bayes + baseline evaluation
6. Cross-Validation
K-Fold Cross Validation
7. Final Evaluation

📊 Dataset

Dataset terdiri dari 300 data dengan struktur sebagai berikut:
| Column             | Non-Null Count | Dtype   |
|--------------------|----------------|---------|
| ipk                | 300            | float64 |
| sks_lulus          | 300            | int64   |
| kehadiran_persen   | 300            | float64 |
| mk_mengulang       | 300            | int64   |
| status_kelulusan   | 300            | int64   |


⚖️ Data Imbalance

Dataset memiliki kondisi imbalance, di mana jumlah mahasiswa lulus lebih banyak dibandingkan tidak lulus.

<img width="590" height="485" alt="Data Imbalance" src="https://github.com/user-attachments/assets/83fb6bdb-e385-44d8-aceb-eedf95e1ff59" />


📈 Analisis IPK terhadap Kelulusan

Berdasarkan visualisasi di bawah, terlihat bahwa mahasiswa dengan IPK rata-rata 3.00 – 3.50 memiliki angka kelulusan yang tinggi. Semakin tinggi IPK, jumlah mahasiswa yang lulus semakin sedikit karena distribusi data.

Dapat disimpulkan bahwa mahasiswa dengan IPK ≥ 3.00 memiliki peluang kelulusan yang tinggi.

<img width="636" height="427" alt="IPK vs Kelulusan" src="https://github.com/user-attachments/assets/76699e9a-05e3-4161-a8fb-a763c1753da0" />


🔥 Korelasi Antar Variabel

Berdasarkan heatmap korelasi berikut:

IPK memiliki hubungan kuat dengan jumlah SKS lulus

Semakin banyak SKS yang lulus, IPK cenderung meningkat

SKS lulus juga memiliki korelasi tinggi dengan status kelulusan (0.80)

Hal ini menunjukkan bahwa semakin banyak SKS yang diselesaikan, semakin besar kemungkinan mahasiswa untuk lulus.

<img width="716" height="577" alt="Heatmap Korelasi" src="https://github.com/user-attachments/assets/0fb85435-f6d2-48cf-a535-aa779a44e37a" />


🧠 Hasil Modeling

Setelah dilakukan pemodelan, diperoleh hasil sebagai berikut:
Test Accuracy:0.9833333333333333
Classification Report:
              | Class / Metric | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| 0              | 1.00      | 0.95   | 0.97     | 20      |
| 1              | 0.98      | 1.00   | 0.99     | 40      |
| **Accuracy**   | —         | —      | **0.98** | 60      |
| **Macro Avg**  | 0.99      | 0.97   | 0.98     | 60      |
| **Weighted Avg** | 0.98    | 0.98   | 0.98     | 60      |



📉 Evaluasi Model

Evaluasi akhir menggunakan confusion matrix menunjukkan bahwa model memiliki performa yang sangat baik. Terdapat 1 kasus false negative, yaitu mahasiswa yang diprediksi tidak lulus namun sebenarnya lulus.

Secara keseluruhan, model cukup andal dalam menangani studi kasus klasifikasi kelulusan mahasiswa.

<img width="585" height="484" alt="Confusion Matrix" src="https://github.com/user-attachments/assets/d03b096e-1e8f-40aa-988f-bd13c0eeb570" />
