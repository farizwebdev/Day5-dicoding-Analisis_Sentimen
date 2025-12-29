# Analisis Sentimen Ulasan Aplikasi Al-Quran Indonesia

## Disusun Oleh:
### Nama: Fariz Husain Albar   
### Instansi: UIN Sunan Kalijaga Yogyakarta  

### Submission Kelas - Dicoding Academy

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![NLP](https://img.shields.io/badge/Domain-NLP-green)

## Deskripsi Proyek
Proyekk ini bertujuan untuk menganalisis sentimen pengguna terhadap aplikasi **"Al Quran Indonesia"** di Google Play Store. Sistem ini mengklasifikasikan ulasan pengguna menjadi dua kategori sentimen: **Positif** dan **Negatif**.

Proyek ini menerapkan pendekatan *End-to-End Machine Learning*, dimulai dari pengumpulan data mandiri (*scraping*), pemrosesan teks bahasa Indonesia, hingga komparasi empat algoritma klasifikasi untuk mencari performa terbaik.

## Struktur Repository
Berikut adalah deskripsi file dalam proyek ini:

| Nama File | Deskripsi |
| :--- | :--- |
| `Kode_Scraping_Fariz_Husain_Albar.ipynb` | **Tahap 1: Data Collection**. Notebook untuk mengambil ulasan *real-time* dari Google Play Store menggunakan library `google-play-scraper`. |
| `Proyek_Analisis_Sentimen_Fariz_Husain_Albar.ipynb` | **Tahap 2: Modeling**. Notebook utama yang berisi Preprocessing, Feature Extraction (TF-IDF), pelatihan model, dan evaluasi. |
| `requirements.txt` | Daftar pustaka (library) Python yang digunakan dalam proyek ini. |
| `ulasan_aplikasi_alquran_indonesia.csv` | (Output Scraping) Dataset mentah hasil scraping yang digunakan sebagai input model. |

## Metodologi & Alur Kerja

### 1. Data Collection (Scraping)
Mengambil data ulasan dari aplikasi dengan ID: `com.andi.alquran.id`.
* **Library:** `google-play-scraper`
* **Fitur yang diambil:** `content` (isi ulasan) dan `score` (rating bintang).

### 2. Text Preprocessing
Membersihkan data teks agar siap diolah oleh mesin:
* **Cleaning:** Menghapus angka, tanda baca, dan *emoji*.
* **Case Folding:** Mengubah teks menjadi huruf kecil (*lowercase*).
* **Tokenization:** Memecah kalimat menjadi kata-kata.
* **Stopword Removal:** Menghapus kata umum yang tidak bermakna (menggunakan NLTK).
* **Stemming:** Mengubah kata berimbuhan menjadi kata dasar bahasa Indonesia (menggunakan library **Sastrawi**).

### 3. Feature Extraction
Mengubah data teks menjadi representasi numerik menggunakan metode **TF-IDF** (*Term Frequency-Inverse Document Frequency*).

### 4. Modeling (Klasifikasi)
Membandingkan performa empat algoritma Machine Learning:
1.  **Naive Bayes** (MultinomialNB)
2.  **Random Forest Classifier**
3.  **Logistic Regression**
4.  **Decision Tree Classifier**

## Hasil Evaluasi
Evaluasi dilakukan menggunakan metrik **Akurasi** dan **Confusion Matrix**. Berikut adalah perbandingan performa model (Contoh hasil, sesuaikan dengan output notebook Anda):

| Algoritma | Akurasi | Keterangan |
| :--- | :--- | :--- |
| **Logistic Regression** | **0.938713%** | Performa Terbaik |
| Random Forest | 0.916023% | - |
| Naive Bayes | 0.883860% | - |
| Decision Tree | 0.889123% | - |

## Cara Menjalankan Project

1.  **Clone Repository** (atau download file zip).
2.  **Install Dependencies:**
    Disarankan menggunakan virtual environment.
    ```bash
    pip install -r requirements.txt
    ```
    *Catatan: Pastikan library `Sastrawi` dan `google-play-scraper` terinstall.*
3.  **Jalankan Notebook:**
    * Buka `Kode_Scraping...ipynb` jika ingin memperbarui data ulasan terbaru.
    * Buka `Proyek_Analisis_Sentimen...ipynb` untuk melihat proses analisis dan hasil akurasi.

## Pustaka Utama
* `pandas` & `numpy`: Manipulasi data.
* `scikit-learn`: Pembuatan model ML dan evaluasi.
* `nltk`: Preprocessing teks (stopwords).
* `Sastrawi`: Stemming bahasa Indonesia.
* `google-play-scraper`: Pengambilan data Play Store.
* `wordcloud`: Visualisasi kata yang sering muncul.

---
*Submission Tugas Akhir - Analisis Sentimen [Dicoding Academy]*
