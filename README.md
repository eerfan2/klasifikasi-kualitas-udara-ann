# Klasifikasi Kualitas Udara Menggunakan Artificial Neural Network (ANN)

## 📌 Deskripsi Proyek
Repositori ini berisi implementasi **klasifikasi kualitas udara** menggunakan metode **Artificial Neural Network (ANN)**.  
Model dibangun untuk mengklasifikasikan kategori kualitas udara berdasarkan **parameter indeks polutan**, seperti PM10, PM2.5, SO₂, CO, O₃, dan NO₂.

Dataset yang digunakan berasal dari **sumber data terbuka (open data)** dan diproses menggunakan Python di lingkungan **Google Colab**.

---

## 🎯 Tujuan
- Mengklasifikasikan kualitas udara ke dalam beberapa kategori (misalnya: *BAIK, SEDANG, TIDAK SEHAT*, dll)
- Menerapkan metode **Artificial Neural Network (ANN)** pada data indeks polutan
- Mengevaluasi performa model menggunakan metrik evaluasi klasifikasi

---

## 📂 Struktur Proyek
📁 klasifikasi-kualitas-udara-ann
│
├── klasifikasi_kualitas_udara_ann.ipynb # Notebook utama Google Colab
├── training_history.png # Grafik akurasi & loss training
├── confusion_matrix.png # Confusion matrix hasil evaluasi
├── hasil_evaluasi_model.csv # Ringkasan metrik evaluasi
├── model_ann_kualitas_udara.h5 # Model ANN terlatih
├── scaler.pkl # StandardScaler
├── label_encoder.pkl # LabelEncoder
└── README.md # Dokumentasi proyek

---

## 🧪 Dataset
Dataset berbentuk file **Excel (.xlsx)** yang berisi data indeks polutan dengan kolom utama:
- `pm_10`
- `pm_duakomalima`
- `so2`
- `co`
- `o3`
- `no2`
- `categori` (label kualitas udara)

Dataset diunggah langsung melalui Google Colab saat notebook dijalankan.

---

## ⚙️ Library yang Digunakan
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn`
- `tensorflow / keras`
- `openpyxl`, `xlrd`

---

## 🔄 Tahapan Metodologi
1. **Import & Install Library**
2. **Upload dan Load Dataset Excel**
3. **Eksplorasi Data**
4. **Data Preprocessing**
   - Seleksi fitur
   - Handling missing values
   - Penghapusan duplikasi
   - Penghapusan outlier (IQR)
5. **Encoding & Normalisasi**
   - Label Encoding
   - StandardScaler
6. **Split Data**
   - 80% Training
   - 20% Testing
7. **Pembangunan Model ANN**
8. **Training Model**
   - Early Stopping
   - Learning Rate Reduction
9. **Visualisasi Training**
10. **Evaluasi Model**
11. **Confusion Matrix**
12. **Penyimpanan Model**
13. **Testing Prediksi Data Baru**

---

## 🧠 Arsitektur Model ANN
- Input Layer: 6 neuron (sesuai jumlah fitur)
- Hidden Layer 1: 128 neuron (ReLU)
- Hidden Layer 2: 64 neuron (ReLU)
- Hidden Layer 3: 32 neuron (ReLU)
- Output Layer: Softmax (multi-class classification)
- Optimizer: Adam
- Loss Function: Categorical Crossentropy

---

## 📊 Evaluasi Model
Model dievaluasi menggunakan metrik:
- Accuracy
- Precision
- Recall
- F1-Score

Hasil evaluasi disimpan dalam file:

hasil_evaluasi_model.csv

Selain itu, ditampilkan juga:
- Grafik training (accuracy & loss)
- Confusion matrix
- Akurasi per kelas

---

## 🔍 Contoh Penggunaan (Prediksi)
Model dapat digunakan untuk memprediksi kualitas udara berdasarkan input manual:

python
predict_air_quality(
    pm10=54, 
    pm_duakomalima=73, 
    so2=56, 
    co=24, 
    o3=23, 
    no2=24
)

Output berupa:
Prediksi kategori kualitas udara
Confidence level (%)
Probabilitas setiap kelas

## 💾 Penyimpanan Model
Model dan preprocessing disimpan agar dapat digunakan kembali tanpa training ulang:
- model_ann_kualitas_udara.h5
- scaler.pkl
- label_encoder.pkl

## 🚀 Cara Menjalankan

- Buka file .ipynb di Google Colab
- Jalankan seluruh cell secara berurutan
- Upload dataset Excel saat diminta
- Model akan dilatih dan dievaluasi secara otomatis

✨ Author
Muhammad Irfan
Teknik Informatika
