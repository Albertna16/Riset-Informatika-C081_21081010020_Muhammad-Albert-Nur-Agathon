# Deteksi Penyakit Daun Tomat Dengan Menggunakan Arsitektur Alexnet

Metodologi yang digunakan dalam Penelitian Kecil berjudul *"Deteksi Penyakit Daun Tomat Dengan Menggunakan Arsitektur Alexnet"* adalah sebagai berikut:

## 1. Datasets
Penelitian ini menggunakan dataset gambar daun tomat dari *AI Challenger Crop Disease Dataset 2018*, yang mencakup 8 jenis penyakit daun tomat dan daun yang sehat. Dataset terdiri dari total 13.038 gambar yang kemudian diperbesar menjadi 18.363 gambar menggunakan teknik augmentasi gambar seperti translasi, rotasi, pemotongan, flipping, dan transformasi perspektif.

## 2. Proses Data
Teknik augmentasi gambar digunakan untuk menyeimbangkan jumlah gambar antara kategori yang berbeda. Gambar diproses dalam resolusi 256x256 piksel, kemudian di-crop secara acak menjadi 224x224 piksel untuk model pelatihan.

## 3. Ekstraksi Fitur Fusi
Fitur gambar diekstraksi menggunakan metode *Histogram of Oriented Gradients (HOG)* dan *Local Binary Pattern (LBP)*. HOG digunakan untuk menangkap bentuk dan kontur gambar, sedangkan LBP digunakan untuk mengekstrak fitur tekstur lokal. Kedua fitur ini digabungkan dengan metode fusi berbobot untuk meningkatkan akurasi pengenalan gambar.

## 4. Model Pengenalan Penyakit
Model yang digunakan adalah AlexNet yang telah diimprovisasi. AlexNet adalah model *Convolutional Neural Network (CNN)* yang digunakan untuk klasifikasi gambar. Model ini telah disederhanakan dengan mengurangi jumlah lapisan fully connected dari tiga menjadi dua, dan lapisan dropout digunakan untuk mencegah overfitting. Pembelajaran transfer digunakan untuk mempercepat pelatihan dengan memanfaatkan model yang telah dilatih pada dataset *PlantVillage*.

## 5. Penggunaan Transfer Learning
Pembelajaran transfer diterapkan dengan cara memodifikasi lapisan terakhir dari model AlexNet, yang memungkinkan model mempelajari fitur gambar dari daun tomat yang terinfeksi penyakit.

## 6. Evaluasi dan Eksperimen
Penelitian ini mengevaluasi performa model berdasarkan metrik seperti akurasi, recall, precision, dan nilai F1. Percobaan juga dilakukan untuk membandingkan pengaruh berbagai metode fusi fitur (fusi seri, paralel, dan berbobot) terhadap kinerja pengenalan gambar.
