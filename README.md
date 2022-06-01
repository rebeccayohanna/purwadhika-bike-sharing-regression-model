# purwadhika-bike-sharing-regression-model
Capstone Project Module 3 Purwadhika : Bike Sharing Regression

Nama : Yohanna Inawati Santoso

Dataset : Bike Sharing 

Dataset Source : https://drive.google.com/drive/folders/1Qk9VJXpVlYnZofzRmH5z15Kpi-5M8KOv

# Contents
 - Business Problem Understanding
 - Data Understanding
 - Data Preprocessing (Data Cleaning, Feature Selection, Feature Engineering)
 - Modeling (Algorithm, Evaluation Metrics)
 - Conclusion
 - Recommendation / Improvement

# Business Problem & Data Understanding
Bike sharing merupakan sistem persewaan sepeda dimana sepeda dapat disewa baik oleh penyewa yang telah menjadi member maupun yang belum menjadi member. Pada beberapa sistem Bike sharing, penyewa dapat menyewa sebuah sepeda dari satu lokasi station, dan mengembalikannya pada station lain yang lokasinya berbeda namun masih dalam satu sistem.

Data yang digunakan dalam project ini adalah data kondisi cuaca, musim, tanggal dan jam, serta total penyewa. Dari data tersebut, dapat dipelajari dan dianalisis keterkaitan antar fitur, sehingga dapat diperoleh metode untuk memprediksi perkiraan sepeda yang diperlukan pada waktu dengan kondisi tertentu.

# Data Preprocessing
 - Penambahan fitur month, year, dayname yang diambil dari dteday
 - Penghapusan outlier
 - Pengapusan fitur dteday, casual, registered, atemp
 - Pengubahan tipe data untuk weathersit, season, holiday menjadi category

# Modeling
Membandingkan Linear Regression, KNN Regressor, Decision Tree Regressor, Random Forest Regressor, XGBoost Regressor.

Hasilnya adalah XGBoost merupakan model terbaik, kemudian dilakukan hyperparameter tuning.

Hasil before dan after Hyperparameter Tuning :

RMSE, MAE & MAPE sebelum tuning: 40.25, 25.66, 0.41 

RMSE, MAE & MAPE setelah tuning: 39.12, 24.97, 0.43

# Conclusion
Berdasarkan pemodelan yang telah dilakukan, fitur 'Hour' merupakan fitur yang paling berpengaruh terhadap 'Count'.

Untuk matriks evaluasi yang digunakan adalah RMSE, MAE, dan MAPE. Nilai RMSE yang dihasilkan setelah hyperparameter tuning adalah 39,12. Sehingga dapat disimpulkan bahwa jika model akan digunakan untuk memperkirakan penyewa sepeda pada rentang nilai sesuai model yang dilatih (maksimal Count 645), maka perkiraan penyewa dapat meleset kurang lebih 39 orang dari total aktualnya. Namun dapat terjadi kesalahan lebih jauh juga karena masih terdapat bias yang terlihat dari visualisasi data prediksi dan aktual. Bias dapat terjadi karena masih kurangnya fitur pada dataset untuk merepresentasikan keadaan dimana orang akan memutuskan untuk menyewa sepeda, seperti lokasi station, adanya event tertentu, dan lain - lain.

# Recommendation
Rekomendasi yang dapat dilakukan untuk pengembangan model yang lebih baik, seperti :

Penambahan fitur yang lebih korelatif dengan target ('Count') seperti adanya event tertentu dan jarak lokasi station dengan lokasi perkantoran, sekolah, atau tempat wisata.

Penambahan data. Jika terdapat data lebih banyak dan lebih dari dua tahun, dapat dianalisis lebih baik lagi keterkaitan tahun dengan Count. Dapat juga digunakan model yang lebih kompleks untuk proses pemodelannya untuk dibandingan dan dicari model dengan error paling sedikit.

Model yang telah dibangun juga dapat dimanfaatkan untuk pengembangan lainnya. Misalnya pembuatan model untuk memprediksi harga rental atau pembuatan model untuk memprediksi jumlah sepeda yang keluar atau masuk di station tertentu. Jika ada, dapat dianalisis lokasi station strategis, dan dapat menjadi sebuah pertimbangan untuk membuka station baru di tempat yang serupa.

# Save Model Menggunakan PICKLE
