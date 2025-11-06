# UTS Kecerdasan Buatan

Nama Anggota Kelompok: 
1. 312210401 - Abid Lu'ay Raihan Taufik
2. 312210382 - Rafi Maulana Firdaus
3. 312210445 - Hadi Permana
4. 312210397 - Muhamad Rizky Raka Pratama

# Klasifikasi Ujaran Kebencian (Hate Speech) Twitter

Proyek ini adalah implementasi model *machine learning* untuk mengklasifikasikan cuitan (tweets) berbahasa Indonesia sebagai ujaran kebencian (Hate Speech) atau bukan (Non-Hate Speech).

## CONTEXT
> **PENTING:** Proyek ini dibuat untuk memenuhi tugas Ujian Tengah Semester (UTS) mata kuliah **Kecerdasan Buatan** di **Universitas Pelita Bangsa**. Ini adalah proyek akademik dan bukan alat untuk penggunaan produksi.

## Deskripsi Proyek
Tujuan dari proyek ini adalah untuk membangun sebuah *pipeline* klasifikasi teks yang meliputi pembersihan data, *preprocessing* teks, representasi fitur, dan pembangunan model. Model dilatih untuk mengidentifikasi teks yang mengandung ujaran kebencian (label 1) dan teks netral (label 0).

## Dataset
Dataset yang digunakan dalam proyek ini terdiri dari tiga file:
1.  `data.csv`: Dataset utama yang berisi ribuan cuitan Twitter dengan label (kolom `HS`).
2.  `new_kamusalay.csv`: Kamus kata-kata "alay" (slang) untuk normalisasi teks.
3.  `abusive.csv`: Daftar kata-kata kasar (abusive) dalam bahasa Indonesia.

## Metodologi
Alur kerja pemrosesan dan pemodelan data adalah sebagai berikut:

1.  **Preprocessing Teks**
    * **Normalisasi Kata:** Mengubah kata-kata alay/slang menjadi kata baku menggunakan `new_kamusalay.csv`.
    * **Case Folding:** Mengubah semua teks menjadi huruf kecil.
    * **Pembersihan Teks:** Menghapus URL, *mention* (@username), *hashtag* (#), angka, dan tanda baca.
    * **Tokenisasi:** Memecah kalimat menjadi token (kata).
    * **Stopword Removal:** Menghapus kata-kata umum (seperti 'yang', 'di', 'dan')

2.  **Representasi Fitur**
    * Proyek ini menggunakan **TF-IDF (Term Frequency-Inverse Document Frequency)** untuk mengubah teks yang sudah bersih menjadi vektor numerik yang dapat dipahami oleh model.

3.  **Pembangunan Model**
    * Model yang digunakan adalah **Logistic Regression**[cite: 37], sebuah algoritma *machine learning* klasik yang efektif untuk klasifikasi teks biner.

---

## Hasil Evaluasi
Model dievaluasi menggunakan data uji (20% dari dataset) dan menghasilkan metrik berikut:

* **Accuracy:** `81.70%`
* **F1-Score (Makro Rata-rata):** `0.81`
* **F1-Score (Kelas HS):** `0.77`

