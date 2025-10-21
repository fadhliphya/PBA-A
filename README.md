# 🧠 Sentiment Analysis — Google Reviews (Emirates Airlines App)

**👤 Maureen Ghassani Fadhliphya | 5026221193
**📱 App Target:** `com.emirates.ek.android` (Google Play Store)  
**🎯 Focus:** Text Preprocessing, EDA, Regex Cleaning, and Feature Extraction (BoW)

---

## 📘 Overview
Proyek ini merupakan bagian dari eksplorasi analisis sentimen menggunakan data ulasan pengguna aplikasi **Emirates Airlines** yang diambil dari **Google Play Store**.

Tahapan proyek dilakukan per minggu untuk menjaga alur dan fokus pembelajaran:

- **Week 2:** Data Scraping dan Preprocessing (tokenization, stopwords removal, stemming)  
- **Week 3:** Exploratory Data Analysis (EDA), pembersihan lanjutan menggunakan Regex, dan representasi teks dengan *Bag of Words (BoW)*  

Tujuan utama proyek ini adalah memahami pola teks dalam ulasan pengguna dan menyiapkan dataset yang bersih untuk tahap analisis sentimen berikutnya.

---
## 🗓️ Week 2 Summary – Data Scraping & Preprocessing

### 🔹 1. Scraping Data
- Data diambil dari **Google Play Store** menggunakan link: https://play.google.com/store/apps/details?id=com.emirates.ek.android&hl=en
- Proses scraping dilakukan untuk mengumpulkan **ulasan pengguna (Google Reviews)** aplikasi **Emirates Airlines**.  
- Data disimpan dalam format **CSV** (`emirates_reviews.csv`) berisi beberapa kolom seperti:
- `user`, `rating`, `date`, `review_text`

### 🔹 2. Text Cleaning
Tahap pembersihan data dilakukan untuk menghapus elemen yang tidak relevan pada teks ulasan:
- Menghapus karakter khusus, angka, tanda baca, dan emoji.
- Mengubah seluruh teks menjadi huruf kecil.
- Menghapus duplikasi dan baris kosong.

### 🔹 3. Tokenization
- Proses tokenisasi dilakukan untuk memecah kalimat menjadi token (kata-kata individual).  
- Tokenisasi membantu identifikasi pola kata umum dan persiapan ke tahap analisis lanjutan.

### 🔹 4. Stopword Removal
- Stopwords (kata umum seperti *yang, dan, di, ke, dengan*) dihapus menggunakan daftar stopword Bahasa Inggris & Indonesia.
- Tujuannya untuk mempertahankan kata-kata bermakna dalam konteks sentimen.

### 🔹 5. Stemming
- Menggunakan library **Sastrawi** untuk mengembalikan kata ke bentuk dasarnya (contoh: *“membeli” → “beli”*).
- Hasil stemming disimpan dalam file `emirates_reviews_stemmed.csv`.

### 💡 Kesimpulan Week 2
- Dataset berhasil dibersihkan dan diproses menjadi bentuk teks siap analisis.  
- Hasil preprocessing menunjukkan banyak ulasan positif dengan kata kunci umum seperti “easy”, “good”, dan “great”.  
- Data siap untuk tahap eksplorasi dan representasi fitur pada Week 3.

---

## 📊 Week 3 Summary – Exploratory Data Analysis & Feature Extraction

### 🔍 Key Insights
- Sebagian besar review **pendek**, rata-rata berisi kurang dari **20 kata**.  
- Setelah penghapusan stopwords, kata-kata yang paling sering muncul adalah:  
**easy**, **good**, **use**, **great**, **excellent**, **best**, **service**, **friendly**, **nice**, dan **love**.  
- Kata **“easy”** menjadi kata paling dominan (lebih dari 4000 kemunculan), menandakan mayoritas pengguna menilai aplikasi **mudah digunakan**.  
- Distribusi kata menunjukkan kecenderungan **positif**, di mana banyak ulasan menggambarkan pengalaman baik dan kemudahan akses.  

### 💡 Conclusion
- Ulasan pengguna umumnya **positif dan singkat**, cocok untuk analisis berbasis model sederhana seperti **BoW** atau **TF-IDF + klasik classifier** (Logistic Regression / SVM).  
- Pembersihan tambahan dengan **Regex** berhasil menghilangkan noise seperti angka, emoji, dan simbol.  
- Dataset sudah siap untuk masuk ke tahap **Sentiment Modeling** pada minggu berikutnya.  

---

## 📁 Repository Structure
├── WEEK 2/
│ ├── 01_Scrapping_Apps_Review_Emirates.ipynb
│ ├── 02_Stemmer.ipynb
│ ├── 03_Tokenization.ipynb
│ └── DATA/
│ ├── emirates_reviews.csv
│ ├── emirates_reviews_stopwords.csv
│ ├── emirates_reviews_stemmed.csv
│ └── emirates_reviews_tokenized.csv
│
├── WEEK 3/
│ ├── 01_WEEK_3_EDA.ipynb
│ ├── BoW_WEEK_3.ipynb
│ ├── REGEX_WEEK_3.ipynb
│ └── outputs/
│ ├── eda_top_words.png
│ └── review_length_distribution.png
│
└── README.md
---

