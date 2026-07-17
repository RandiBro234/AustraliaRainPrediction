# 🌧️ Rain Tomorrow Prediction using Machine Learning

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk membangun model Machine Learning yang dapat memprediksi apakah akan terjadi hujan pada hari berikutnya (**RainTomorrow**) berdasarkan kondisi cuaca saat ini.

Dataset yang digunakan adalah **Rain in Australia** yang berisi data historis cuaca dari berbagai lokasi di Australia.

---

## 🎯 Tujuan

- Melakukan preprocessing pada dataset cuaca.
- Melakukan feature engineering untuk meningkatkan kualitas fitur.
- Membandingkan beberapa algoritma klasifikasi.
- Memilih model terbaik berdasarkan metrik evaluasi.
- Mengoptimalkan model menggunakan Hyperparameter Tuning dan Threshold Optimization.

---

## 📂 Struktur Project

```
RainTomorrowPrediction/
│
├── RainTomorrowPrediction.ipynb
├── weatherAUS.csv
├── final_catboost_model.pkl
├── final_threshold.pkl
├── requirements.txt
└── README.md
```

---

## 🚀 Cara Menjalankan

### 1. Clone Repository

```bash
git clone <repository_url>
```

---

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 3. Jalankan Notebook

```bash
jupyter notebook
```

Kemudian buka

```
RainTomorrowPrediction.ipynb
```

dan jalankan seluruh cell secara berurutan.

---

## ⚙️ Preprocessing

Tahapan preprocessing yang dilakukan:

- Menghapus data dengan target (`RainTomorrow`) yang kosong.
- Missing value imputation.
- Feature engineering.
- Train-Test Split.
- Column Transformer (untuk model baseline).
- Class Weight (khusus CatBoost).

---

## 🧠 Feature Engineering

Fitur baru yang dibuat:

- TempRange
- PressureDiff
- HumidityDiff
- AvgTemp
- AvgPressure
- AvgHumidity
- WindSpeedDiff

---

## 🤖 Model yang Dibandingkan

- Logistic Regression
- Random Forest
- XGBoost
- XGBoost + SMOTE
- CatBoost
- CatBoost + Hyperparameter Tuning
- CatBoost + Threshold Optimization

---

## 🏆 Model Terbaik

Model terbaik yang diperoleh adalah:

**CatBoost + Hyperparameter Tuning + Threshold Optimization**

Threshold terbaik:

```
0.59
```

Hasil evaluasi:

| Metric | Score |
|---------|------:|
| Accuracy | 85.84% |
| Precision | 67.42% |
| Recall | 71.26% |
| F1 Score | 69.29% |
| ROC AUC | 90.65% |

---

## 📊 Insight

Beberapa insight yang diperoleh dari proyek ini:

- Dataset memiliki distribusi kelas yang tidak seimbang sehingga diperlukan penanganan imbalance menggunakan **class weights** pada CatBoost.
- Feature engineering membantu menambahkan informasi penting seperti perubahan suhu, tekanan udara, dan kelembapan yang berpotensi meningkatkan performa model.
- CatBoost memberikan performa terbaik dibandingkan Logistic Regression, Random Forest, dan XGBoost karena mampu menangani fitur kategorikal secara langsung tanpa memerlukan One-Hot Encoding.
- Hyperparameter tuning meningkatkan kemampuan model dalam membedakan kelas (ROC AUC), sedangkan threshold optimization meningkatkan keseimbangan antara precision dan recall sehingga menghasilkan F1 Score terbaik.

---

## 📚 Library

Seluruh dependency dapat diinstall melalui

```
requirements.txt
```