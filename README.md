# HOTEL BOOKINGS DEMAND PREDICTION USING MACHINE LEARNING ALGORITHM

Disusun oleh :
- Muhammad Rasyaa Alif Fauzan
- Mohammad Kiflano Hazman
- Athaya Zahrani Irmansyah
--------------
Summary

Proyek ini bertujuan membantu pihak hotel dalam mengatasi masalah pembatalan pemesanan dengan membangun strategi berdasarkan analisis data dan machine learning.
--------------
Business Understanding

Dalam industri perhotelan, pembatalan pemesanan adalah masalah yang umum dan dapat berdampak signifikan pada pendapatan dan manajemen operasional. Setiap pembatalan tidak hanya mengurangi pendapatan yang diharapkan, tetapi juga dapat menyebabkan ketidakpastian dalam perencanaan kapasitas dan pengelolaan sumber daya. Oleh karena itu, pemahaman yang mendalam tentang faktor-faktor yang mempengaruhi pembatalan sangat penting bagi pihak hotel. Dengan menerapkan analisis data dan machine learning, hotel dapat mengidentifikasi pola dan tren dalam pembatalan pemesanan, memungkinkan mereka untuk merumuskan strategi proaktif. Dengan demikian, proyek ini bertujuan untuk memberikan solusi berbasis data yang dapat mengurangi tingkat pembatalan, meningkatkan pendapatan, dan memperbaiki pengalaman tamu secara keseluruhan.
-------------------------
Dataset

Dataset yang digunakan dalam proyek ini berasal dari dua hotel di Portugal, mencakup periode dari 1 Juli 2015 hingga 31 Agustus 2017. Dataset ini berisi berbagai informasi pemesanan hotel, termasuk tanggal kedatangan, lama menginap, jumlah tamu, agen pemesanan, jumlah hari antara pemesanan dan tanggal kedatangan, serta Average Daily Rate (ADR) dan data lainnya. Informasi ini akan menjadi dasar analisis untuk memahami pola pembatalan dan mengembangkan strategi mitigasi yang efektif.
-------------------------
Project Structure

1. Pemahaman Masalah Bisnis
2. Eksplorasi Data dan Data Cleaning
3. Feature Engineering
4. Analisis Data
5. Pemodelan Machine Learning 
6. Evaluasi dan Insight
-------------------------
Result
**TABEL KESIMPULAN ANALISIS**
|No.|Kolom|Insight|Rekomendasi|
|-|-|-|-|
|1.|Lead Time|Sebagian besar pembatalan hotel terjadi pada lead time pendek (kategori <=30), tetapi persentase pembatalan tertinggi ditemukan pada lead time panjang (>360), menunjukkan bahwa tamu yang memesan lebih awal cenderung membatalkan lebih sering|Menawarkan insentif untuk pemesanan dengan lead time lebih panjang (diskon atau fasilitas tambahan)|
||||Mengimplementasikan kebijakan pembatalan yang lebih fleksibel untuk menarik tamu melakukan pemesanan lebih awal|
|2.||Total pemesanan hotel meningkat dari Januari hingga Juni, dengan puncak di bulan Juli, kemudian menurun pada akhir tahun. Hal ini memungkinkan terjadi karena tanggal 4 Juli merupakan [hari libur umum di Portugal](https://en.wikipedia.org/wiki/Public_holidays_in_Portugal)|Mengembangkan kampanye pemasaran musiman untuk memaksimalkan pendapatan serta menarik tamu selama periode permintaan rendah|
||||Menawarkan kebijakan pembatalan yang fleksibel dan paket menarik untuk menarik tamu selama bulan Desember yang sepi, karena terdapat banyak [hari libur di bulan Desember](https://www.portugal-realty.com/en/blog/living-in-portugal/public-holidays-in-portugal.html).|
|3.||Jumlah pembatalan hotel bulan Agustus mencatat jumlah tertinggi (8.533) dan Desember terendah (2.362). Bulan April menunjukkan persentase pembatalan tertinggi (41,0%), menandakan waktu risiko tinggi untuk pembatalan|Melakukan analisis mendalam untuk memahami penyebab fluktuasi pembatalan|
||||Menawarkan kebijakan pembatalan yang lebih fleksibel atau insentif|
||||Menerapkan strategi pemasaran proaktif untuk menarik tamu lebih awal selama bulan-bulan dengan tingkat pembatalan tinggi|
|4.|Hotel|Presentase Pembatalan Tinggi pada City Hotel|Kebijakan pembatalan fleksibel, memberikan insentif reservasi, dan menganalisis penyebab pembatalan|
|5.||Presentase Pembatalan Rendah pada Resort Hotel|Melakukan kampanye pemasaran pada waktu liburan, meningkatkan komunikasi, dan memberikan program loyalitas kepada tamu setia|
|6.|Market Segment|Group Bookings, Travel Agent/Tour Operators, pemesanan untuk tipe kamar A, Setoran Non-Refundable, dan pesanan menggunakan Agent 1 sangat rentan terhadap pembatalan|Meningkatkan kebijakan pembatalan dan mempertimbangkan untuk memperkenalkan kebijakan pembatalan yang lebih ketat untuk mengurangi tingkat pembatalan|
|7.|Company|Perusahaan yang tidak dikenal yang memiliki tingkat pembatalan tertinggi hingga di atas rata-rata|Meningkatkan pengumpulan data perusahaan, menganalisis penyebab pembatalan, dan memperketat kebijakan pembatalan|
|8.|Country|Pemesan lokal dari Portugal menunjuklkan tingkat pembatalan tertinggi, bahkan hingga di atas rata-rata, dibandingkan dengan negara lainnya|Memberikan promosi khusus untuk wisatawan lokal|
|9.|ADR|Terdapat konsistensi tarif ADR yang sama di weekday dan weekend yaitu 95.00|Terus memantau data pemesanan dan menyesuaikan strategi harga berdasarkan tren dan permintaan. Ini termasuk mengevaluasi efektivitas promosi dan penetapan harga secara berkala.|

**Pemodelan**

1. Didalam pemodelan didapatkan model dengan score ROC-AUC dan score f1 tertinggi adalah model Random Forest Classifier, sedangkan untuk model dengan score f2 tertinggi adalah model XGB classifier.
2. Didalam pemodelan didapatkan model yang terbaik dalam memprediksi pembatalan hotel berdasarkan nilai F2 score adalah model XGBoost Classifier, dengan nilai F2 sebesar 0.8529, namun didalam model ini masih terdapat gejala overfitting.
3. Didalam pemodelan didapatkan model yang terbaik dalam meningkatkan nilai harapan pendapatan adalah Random Forest Classifier dengan threshold terbaik yaitu sebesar 0,24 namun didalam model ini masih terdapat gejala overfitting.

**Bisnis**

1. Variabel yang paling dapat membedakan apakah suatu pesanan akan dibatalkan antara lain adalah apakah depositnya 'Non Refund', banyaknya parkir mobil yang dibutuhkan, apakah kamar yang dipesan dan didapatkan sama, apakah pemesan berasal dari portugal dan apakah agen dari pemesan dari kelompok 'other'.
2. Niai pendapatan per booking yang didapatkan oleh hotel tanpa melakukan overbooking adalah sebesar 212.55 euro
3. Jika pihak hotel melakukan overbooking terhadap kamar yang yang sudah dipesan namun diprediksi akan dibatalkan, pihak hotel diprediksi dapat meningkatkan nilai harapan dari pendapatan sebesar 34.10 euro atau sebesar 16% menjadi 246.65 euro per bookingnya.
---------------

Conclusion

Menganalisis dan memprediksi pembatalan pesanan memungkinkan pihak hotel menyusun strategi efektif untuk mengurangi tingkat pembatalan dan meningkatkan pendapatan, salah satunya yang digunakan dalam proyek ini adalah overbooking.
--------------
Saran

**Pemodelan**

Dikarenakan pada model yang sudah ada masih terdapat gejala overfitting, model masih dapat ditingkatkan lagi dengan mengeneralkan model, megurangi fitur, dan tuning yang lebih baik.

**Bisnis**

Implementasi overbooking oleh pihak hotel bisa dilakukan dengan memperbolehkan satu kamar dipesan oleh dua pemesan, asalkan pemesan pertama diprediksi akan membatalkan reservasi. Dalam simulasi ini, probabilitas pemesanan kamar diambil dari data historis yang ada dan masih diasumsikan sama antara pemesan reguler dan pemesan overbooking. Kemudian, kerugian yang dihitung dalam simulasi ini juga masih bersifat asumsi. Dalam simulasi, pihak hotel harus membayar 30% dari harga kamar kepada pemesan yang datang dan mendapati kamarnya telah ditempati oleh orang lain. Agar simulasi ini lebih akurat, pihak hotel perlu melakukan perhitungan lebih detail dengan menganalisis data historis terkait kamar yang pernah di-overbook dan menghitung kerugian nyata yang timbul dari praktik overbooking.

Jika hotel belum pernah menerapkan sistem overbooking dan belum mengetahui dampak yang mungkin terjadi, pihak hotel bisa mempertimbangkan untuk menaikkan threshold pada model prediksi yang digunakan. Dengan menaikkan threshold, hanya pemesanan yang memiliki kemungkinan sangat tinggi untuk dibatalkan yang akan dipilih untuk overbooking. Hal ini akan meningkatkan akurasi dalam memprediksi pembatalan, sehingga lebih banyak pemesanan yang diprediksi akan dibatalkan benar-benar dibatalkan. Namun, kelemahannya adalah kemungkinan akan ada lebih banyak pemesanan yang diprediksi akan dibatalkan, tetapi sebenarnya tidak akan dibatalkan. Meskipun demikian, pendekatan ini bisa mengurangi risiko dari kesalahan prediksi pada awal penerapan sistem overbooking.
