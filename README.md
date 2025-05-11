### Analisis & Prediksi Capital Bike Sharing 2025

#### Gambaran Umum
Repositori ini berisi analisis dan pemodelan prediktif dari dataset Capital Bike Sharing untuk mengoptimalkan efisiensi operasional. Proyek ini berfokus pada prediksi jumlah penyewaan sepeda berdasarkan kondisi cuaca dan faktor waktu, dengan memanfaatkan teknik machine learning.

#### Struktur Proyek
- `capstone_3a.ipynb`: Notebook Jupyter yang berisi analisis lengkap, pra-pemrosesan data, pemodelan, dan visualisasi.
- `data_bike_sharing.csv`: Dataset yang digunakan untuk analisis, berisi data historis penyewaan sepeda.

#### Rumusan Masalah
Proyek ini menjawab pertanyaan utama berikut:
- Faktor cuaca (suhu, kelembapan, situasi cuaca) dan waktu (jam, musim, hari libur) mana yang secara signifikan memengaruhi penggunaan bike sharing?
- Bagaimana cara membangun model prediksi yang akurat untuk memperkirakan penggunaan bike sharing berdasarkan cuaca dan waktu?
- Bagaimana hasil prediksi dapat mengoptimalkan operasional bike sharing, seperti distribusi sepeda dan pengelolaan stasiun?

#### Tujuan
- Mengidentifikasi faktor cuaca dan waktu yang signifikan memengaruhi penggunaan bike sharing.
- Mengembangkan model prediktif berbasis data untuk memperkirakan penggunaan bike sharing.
- Memberikan strategi operasional bagi operator bike sharing untuk meningkatkan efisiensi dan kepuasan pengguna.

#### Audiens Sasaran
- **Operator Bike Sharing**: Untuk mengelola distribusi sepeda, menjadwalkan pemeliharaan, dan meningkatkan efisiensi operasional.
- **Pemerintah Kota/Perencana Transportasi**: Untuk mendukung kebijakan transportasi ramah lingkungan dan merencanakan infrastruktur seperti jalur sepeda.

#### Metodologi
- **Pemahaman Data**: Menganalisis dataset dengan 12.165 baris dan 11 kolom, termasuk `dteday`, `season`, `hr`, `holiday`, `temp`, `atemp`, `hum`, `casual`, `registered`, `cnt`, dan `weathersit`.
- **Pra-pemrosesan**: Menangani tipe data, menormalkan fitur, dan menyiapkan data untuk pemodelan.
- **Pemodelan**: Menggunakan CatBoost dengan parameter yang di-tuning (`learning_rate=0.0522`, `max_depth=10`, `n_estimators=200`, `random_strength=1.0`) dengan hasil RMSE 85.86, MAE 55.89, dan R² 0.7837.
- **Evaluasi**: Menilai performa model dengan metrik RMSE, MAE, dan R², serta memvisualisasikan nilai aktual versus prediksi.

#### Temuan Utama
- **Faktor yang Berpengaruh**: Suhu (`temp`, `atemp`) dan jam (`hr`) adalah prediktor utama, dengan puncak penggunaan pada pukul 8-9 pagi dan 5-6 sore, serta pada musim panas dan gugur. Hari libur memiliki dampak rendah, sementara cuaca buruk (kategori 3-4) mengurangi penggunaan.
- **Performa Model**: Model CatBoost yang di-tuning efektif memprediksi penggunaan dengan fitur utama `temp`, `hr`, `day`, dan `year`.
- **Wawasan Operasional**: Prediksi mendukung antisipasi permintaan, mengoptimalkan distribusi sepeda pada waktu puncak dan mengurangi inventori pada periode rendah.

#### Rekomendasi
- **Distribusi Sepeda**: Tingkatkan jumlah sepeda di stasiun pada pukul 8-9 pagi, 5-6 sore, dan musim panas/gugur; kurangi pada hari libur dan cuaca buruk.
- **Pemeliharaan**: Jadwalkan pemeliharaan stasiun pada jam dengan permintaan rendah (tengah malam) dan hari libur.
- **Infrastruktur**: Perluas jalur sepeda dan stasiun di area dengan permintaan tinggi berdasarkan pola harian/musiman; promosikan penggunaan ramah lingkungan pada cuaca cerah.
- **Peningkatan Model**: Tambahkan fitur seperti hari dalam seminggu atau acara, serta perbarui model secara berkala dengan data baru.

#### Persyaratan
- Python 3.x
- Library: `pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`, `xgboost`, `catboost`, `lightgbm`, `missingno`, `jcopml`, `category_encoders`, `imblearn`

#### Instalasi
1. Klon repositori: `git clone [https://github.com/Rick-zaa/Bike_Sharing_System3].git`
2. Jalankan notebook: `jupyter notebook capstone_3a.ipynb`
