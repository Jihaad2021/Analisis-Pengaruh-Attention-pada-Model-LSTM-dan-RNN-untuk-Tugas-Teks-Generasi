# 📝 Analisis Pengaruh Attention pada Model LSTM dan RNN untuk Teks Generasi  

## 📌 1. Gambaran Proyek  
Proyek ini bertujuan untuk mengevaluasi pengaruh penggunaan attention (tanpa attention, global, sparse, dan local attention) pada model LSTM dan RNN dalam tugas teks generasi. Attention mechanism sering digunakan untuk meningkatkan pemahaman model terhadap konteks input, tetapi seberapa besar pengaruhnya terhadap tugas generasi teks dalam bahasa Indonesia masih perlu dianalisis.  

## 🎯 2. Tujuan  
Penelitian ini bertujuan untuk:  
1. Membandingkan performa model LSTM dan RNN dalam tugas teks generasi dengan berbagai jenis attention (tanpa attention, global, sparse, dan local attention).  
2. Menganalisis bagaimana setiap jenis attention memengaruhi kualitas teks yang dihasilkan berdasarkan metrik **Rouge-1 Score** pada data pelatihan dan pengujian.  

## 📂 3. Dataset  
Dataset yang digunakan dalam penelitian ini adalah dataset **"Puisi Indonesia"** dari Kaggle, yang berisi **7.223 puisi** dalam bahasa Indonesia. Namun, hanya **3.000 data** yang digunakan dalam eksperimen ini untuk efisiensi pemrosesan.  

## 🏗️ 4. Arsitektur Model  
Penelitian ini menggunakan dua arsitektur utama:  
- **LSTM (Long Short-Term Memory)**  
- **RNN (Recurrent Neural Network)**  

Setiap model diuji dengan empat konfigurasi:  
1. **Tanpa Attention**  
2. **Global Attention**  
3. **Local Attention**  
4. **Sparse Attention**  

## 📊 5. Hasil  
Evaluasi dilakukan menggunakan metrik **Rouge-1 Score** pada data pelatihan dan pengujian. Berikut adalah hasil eksperimen:  

### 🔹 **LSTM**  
| Attention          | R-1 Train | R-1 Testing |
|-------------------|----------|------------|
| **Tanpa Attention** | 26.37%   | **8.49%**  |
| **Global Attention** | **31.37%**   | **19.07%**  |
| **Local Attention**  | 31.25%   | 8.13%  |
| **Sparse Attention** | 31.31%   | 13.43%  |

### 🔹 **RNN**  
| Attention          | R-1 Train | R-1 Testing |
|-------------------|----------|------------|
| **Tanpa Attention** | **28.48%**   | 8.28%  |
| **Global Attention** | **31.35%**   | **23.32%**  |
| **Local Attention**  | 30.92%   | 8.61%  |
| **Sparse Attention** | 30.93%   | 13.05%  |

## 📌 6. Kesimpulan  

### 🔹 **Perbandingan Arsitektur Model**  
- Model **LSTM dan RNN tanpa attention** memiliki performa lebih rendah dibandingkan model dengan attention, terutama pada data pengujian.  
- Model **dengan Global Attention** menunjukkan peningkatan yang signifikan dalam **Rouge-1 Score**, khususnya pada data pengujian, dibandingkan dengan model tanpa attention. Hal ini terjadi karena Global Attention memungkinkan model untuk mempertimbangkan seluruh konteks input saat menghasilkan teks, yang sangat penting dalam tugas teks generasi.  
- Model dengan **Local Attention** dan **Sparse Attention** tidak memberikan peningkatan signifikan pada data pengujian, yang menunjukkan bahwa perhatian terbatas pada bagian tertentu dari input mungkin kurang efektif dibandingkan Global Attention.  

### 🔹 **Pengaruh Penggunaan Attention**  
- **Global Attention memberikan hasil terbaik**, terutama pada **RNN**, dengan peningkatan Rouge-1 Score dari **8.28% (tanpa attention) menjadi 23.32% (dengan Global Attention)**.  
- Pada **LSTM**, Global Attention juga memberikan peningkatan, tetapi tidak sebaik pada RNN.  
- **Sparse dan Local Attention tidak memberikan peningkatan yang signifikan**, yang mungkin disebabkan oleh ketidakmampuan model untuk menangkap dependensi panjang dalam teks puisi.  

## 🔗 7. Kode Implementasi  
- **LSTM tanpa dan dengan attention:** [Kaggle Notebook](https://www.kaggle.com/code/jihaadariefpangestu/text-generation-puisi-bahasa)  

---  
