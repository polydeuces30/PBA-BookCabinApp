# Sentiment Analysis Review BookCabin

## Pendahuluan
Proyek ini bertujuan untuk melakukan analisis sentimen terhadap ulasan pengguna aplikasi *BookCabin* yang diambil dari Google Play Store. Analisis sentimen akan membantu mengidentifikasi bagaimana perasaan dan opini pengguna terhadap aplikasi, yang dapat menjadi masukan berharga bagi pengembang untuk perbaikan dan pengembangan fitur.

## Dataset
Dataset yang digunakan dalam proyek ini adalah ulasan pengguna aplikasi BookCabin yang dikumpulkan dari Google Play Store. Pengambilan data dilakukan menggunakan library `google-play-scraper` di Python. Kami menargetkan untuk mengumpulkan hingga 20.000 ulasan untuk memastikan cakupan data yang memadai dan representatif.

## Tahapan Proyek
Proyek ini akan melalui beberapa tahapan kunci:

1.  **Scraping Data**: Mengambil data ulasan pengguna secara otomatis dari Google Play Store menggunakan library `google-play-scraper`. Data yang diambil meliputi teks ulasan, rating bintang, tanggal, dan informasi relevan lainnya.

2.  **Preprocessing Data**: Tahap ini bertujuan untuk membersihkan dan mempersiapkan teks ulasan agar siap untuk analisis. Langkah-langkah yang akan dilakukan meliputi:
    *   **Cleaning**: Menghapus karakter tidak relevan, tautan, angka, dan tanda baca yang tidak diperlukan.
    *   **Case Folding**: Mengubah semua teks menjadi huruf kecil untuk menyeragamkan data.
    *   **Stopword Removal**: Menghapus kata-kata umum yang tidak memberikan banyak makna dalam konteks sentimen (misalnya, "yang", "dan", "di"). Library `Sastrawi` akan digunakan untuk stopword removal bahasa Indonesia.
    *   **Stemming**: Mengubah kata menjadi bentuk dasarnya (kata akar) untuk mengurangi variasi kata dan meningkatkan konsistensi. Library `Sastrawi` juga akan digunakan untuk stemming bahasa Indonesia.

3.  **Labeling Sentiment**: Memberikan label sentimen (positif, negatif, netral) pada setiap ulasan berdasarkan rating bintang yang diberikan pengguna. Pembagian kategori sentimen dapat diatur sebagai berikut:
    *   **Rating 1-2 bintang**: Negatif
    *   **Rating 3 bintang**: Netral
    *   **Rating 4-5 bintang**: Positif

4.  **Visualisasi WordCloud**: Membuat visualisasi *WordCloud* dari kata-kata yang paling sering muncul dalam ulasan (terpisah untuk sentimen positif dan negatif) setelah preprocessing. Ini akan memberikan gambaran cepat tentang topik atau kata kunci utama yang terkait dengan sentimen pengguna.

5.  **Modeling menggunakan Naive Bayes**: Membangun model klasifikasi sentimen menggunakan algoritma Naive Bayes. Model ini akan dilatih menggunakan data ulasan yang telah dipreprocessing dan diberi label.

6.  **Evaluasi Model**: Mengevaluasi kinerja model Naive Bayes menggunakan metrik standar seperti akurasi, presisi, recall, dan F1-score. Tahap ini penting untuk memahami seberapa baik model dapat memprediksi sentimen ulasan baru.

## Tools dan Libraries
Proyek ini akan memanfaatkan berbagai alat dan library Python:

*   **Python**: Bahasa pemrograman utama yang digunakan.
*   **Google Colab**: Lingkungan pengembangan berbasis cloud untuk menjalankan notebook Jupyter.
*   **Scikit-learn**: Library Python untuk machine learning, digunakan untuk implementasi model Naive Bayes dan evaluasi model.
*   **Sastrawi**: Library Python untuk NLP bahasa Indonesia, digunakan untuk stopword removal dan stemming.
*   **WordCloud**: Library Python untuk menghasilkan visualisasi word cloud.
*   **Pandas**: Untuk manipulasi dan analisis data.
*   **Matplotlib/Seaborn**: Untuk visualisasi data dan hasil analisis.
*   **google-play-scraper**: Library Python untuk mengikis (scraping) ulasan dari Google Play Store.