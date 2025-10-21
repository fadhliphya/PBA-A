# 🧠 Sentiment Analysis — Google Reviews (Emirates Airlines App)

**👤 Name:** Maureen Ghassani Fadhliphya  
**📚 NRP:** 5026221193  
**📱 App Target:** `com.emirates.ek.android` (Google Play Store)  
**📆 Week Covered:** 2 & 3  
**🎯 Focus:** Text Scraping, Preprocessing, EDA, Regex Cleaning, and Feature Extraction (BoW)

---

## 📘 Overview
Proyek ini merupakan bagian dari eksplorasi analisis sentimen menggunakan data ulasan pengguna aplikasi **Emirates Airlines** yang diambil dari **Google Play Store**.

Setiap minggu berfokus pada tahapan berbeda dalam pipeline NLP agar lebih mudah dipahami secara bertahap:

- **Week 2:** Data Scraping dan Text Preprocessing  
- **Week 3:** Exploratory Data Analysis (EDA), Regex Cleaning, dan Feature Extraction menggunakan *Bag of Words (BoW)*  

Tujuan utama proyek ini adalah membangun pemahaman dasar analisis sentimen berbasis teks secara end-to-end — mulai dari pengambilan data mentah hingga pembentukan fitur teks.

---

## 🗓️ Week 2 – Data Scraping & Preprocessing

### 🔹 1. Scraping Data
- Data diambil dari **Google Play Store** menggunakan link:  
  [https://play.google.com/store/apps/details?id=com.emirates.ek.android&hl=en](https://play.google.com/store/apps/details?id=com.emirates.ek.android&hl=en)
- Proses scraping dilakukan untuk mengumpulkan **ulasan pengguna (Google Reviews)** aplikasi **Emirates Airlines**.  
- Data disimpan dalam format **CSV** (`emirates_reviews.csv`) berisi kolom:
  - `user`, `rating`, `date`, `review_text`

---

### 🔹 2. Text Cleaning
Tahap pembersihan data dilakukan untuk menghapus elemen yang tidak relevan pada teks ulasan:
- Menghapus karakter khusus, angka, tanda baca, dan emoji.
- Mengubah seluruh teks menjadi huruf kecil.
- Menghapus duplikasi dan baris kosong.

---

### 🔹 3. Tokenization
- Proses tokenisasi dilakukan untuk memecah kalimat menjadi token (kata-kata individual).  
- Tokenisasi membantu identifikasi pola kata umum dan persiapan ke tahap analisis lanjutan.

---

### 🔹 4. Stopword Removal
- Stopwords (kata umum seperti *yang, dan, di, ke, dengan*) dihapus menggunakan daftar stopword Bahasa Inggris & Indonesia.
- Tujuannya untuk mempertahankan kata-kata bermakna dalam konteks sentimen.

---

### 🔹 5. Stemming
- Menggunakan library **Sastrawi** untuk mengembalikan kata ke bentuk dasarnya (contoh: *“membeli” → “beli”*).
- Hasil stemming disimpan dalam file `emirates_reviews_stemmed.csv`.

---

### 💡 Kesimpulan Week 2
- Dataset berhasil dibersihkan dan diproses menjadi bentuk teks siap analisis.  
- Hasil preprocessing menunjukkan banyak ulasan positif dengan kata kunci umum seperti “easy”, “good”, dan “great”.  
- Data siap untuk tahap eksplorasi dan representasi fitur pada Week 3.

---

## 🗓️ Week 3 – Exploratory Data Analysis, Regex Cleaning, and Feature Extraction

### 🔹 1. Exploratory Data Analysis (EDA)
📓 Notebook: `01_WEEK_3_EDA.ipynb`  

**Tujuan:**  
Melakukan eksplorasi awal terhadap dataset yang telah melalui tahap preprocessing untuk memahami distribusi dan karakteristik teks.

**Langkah yang dilakukan:**
- Analisis jumlah kata per review.  
- Visualisasi distribusi panjang teks.  
- Mengidentifikasi kata yang paling sering muncul.  

**Hasil utama:**
- Mayoritas review **pendek**, dengan rata-rata kurang dari **20 kata**.  
- Kata-kata yang paling sering muncul setelah penghapusan stopwords adalah:  
  **easy**, **good**, **use**, **great**, **excellent**, **best**, **service**, **friendly**, **nice**, dan **love**.  
- Kata **“easy”** muncul paling sering (> 4000 kali), menunjukkan bahwa pengguna menilai aplikasi **mudah digunakan**.  

**Kesimpulan EDA:**  
Teks ulasan didominasi oleh kata-kata positif, mengindikasikan pengalaman pengguna yang baik terhadap aplikasi Emirates Airlines.

---

### 🔹 2. Bag of Words (BoW)
📓 Notebook: `BoW_WEEK_3.ipynb`  

**Tujuan:**  
Mengonversi teks ke bentuk numerik dengan menghitung frekuensi kemunculan setiap kata.

**Langkah yang dilakukan:**
- Menerapkan metode **Bag of Words** menggunakan `CountVectorizer`.  
- Menampilkan kata dengan frekuensi tertinggi.  
- Menghasilkan representasi numerik yang siap digunakan untuk modeling.  

**Top Frequent Words (Sample Output):**
| Word | Frequency |
|------|------------|
| easy | 4023 |
| good | 3071 |
| use | 2726 |
| great | 1781 |
| excellent | 1686 |

**Kesimpulan BoW:**  
BoW berhasil mengekstraksi kata dominan dari teks.  
Pola kata positif mendominasi dataset, menandakan citra baik terhadap aplikasi Emirates Airlines.

---

### 🔹 3. Regular Expression (Regex)
📓 Notebook: `REGEX_WEEK_3.ipynb`  

**Tujuan:**  
Melakukan pembersihan lanjutan pada teks menggunakan **Regular Expression (Regex)** untuk memastikan data bersih dari karakter tidak relevan.

**Langkah yang dilakukan:**
- Menghapus angka, simbol, emoji, dan karakter non-ASCII.  
- Menormalkan spasi ganda menjadi satu spasi.  
- Menyimpan teks bersih dalam format CSV akhir sebelum tahap modeling.  

**Kesimpulan Regex:**  
Regex berhasil meningkatkan kualitas teks dengan menghilangkan noise, sehingga dataset menjadi lebih bersih dan konsisten.

---

### 💡 Kesimpulan Week 3
- Hasil EDA dan BoW menunjukkan bahwa **sebagian besar ulasan bersentimen positif**.  
- Regex cleaning membantu menyiapkan data untuk tahap **sentiment classification** berikutnya.  
- Dataset kini siap digunakan untuk modeling berbasis **TF-IDF** atau **FinBERT** pada minggu selanjutnya.

---

---

## 📁 Repository Structure
```bash
├── WEEK 2/
│   ├── 01_Scrapping_Apps_Review_Emirates.ipynb
│   ├── 02_Stemmer.ipynb
│   ├── 03_Tokenization.ipynb
│   └── DATA/
│       ├── emirates_reviews.csv
│       ├── emirates_reviews_stopwords.csv
│       ├── emirates_reviews_stemmed.csv
│       └── emirates_reviews_tokenized.csv
│
├── WEEK 3/
│   ├── 01_WEEK_3_EDA.ipynb
│   ├── BoW_WEEK_3.ipynb
│   ├── REGEX_WEEK_3.ipynb
│   └── outputs/
│       ├── eda_top_words.png
│       └── review_length_distribution.png
│
└── README.md
