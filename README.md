# Leaf Disease Segmentation

Proyek ini bertujuan untuk melakukan **segmentasi area penyakit pada daun** menggunakan pendekatan berbasis **pengolahan citra digital (Image Processing)**. Fokus utama adalah untuk meningkatkan akurasi segmentasi dengan beberapa metode **preprocessing**, seperti *CLAHE* dan *Gaussian Blur*, serta evaluasi kinerja model menggunakan metrik **IoU** dan **Dice Score**.

## 🔍 Deskripsi Singkat

Pada citra daun, area yang terinfeksi sering kali memiliki warna dan tekstur yang berbeda dibandingkan bagian sehat. Proyek ini melakukan:
- Konversi dari BGR ke HSV
- Penerapan CLAHE pada channel V
- Gaussian Blurring untuk mengurangi noise
- Thresholding (Otsu)
- Operasi morfologi (opening dan closing)
- Evaluasi dengan IoU dan Dice Score terhadap ground truth

## 📁 Dataset

Dataset yang digunakan merupakan kumpulan citra daun beserta ground truth dari area penyakitnya, yang dapat diakses melalui:
👉 [Leaf Disease Segmentation Dataset on Kaggle](https://www.kaggle.com/datasets/fakhrealam9537/leaf-disease-segmentation-dataset)

Dataset berisi:
- `Images/`: Folder gambar daun asli
- `Masks/`: Folder berisi ground truth mask (biner) dari area terinfeksi

## ⚙️ Tahapan Segmentasi

1. **Preprocessing**
   - Resize gambar menjadi 256x256
   - Konversi BGR ke HSV
   - Aplikasi **CLAHE (Contrast Limited Adaptive Histogram Equalization)** pada V channel
   - Gaussian Blur untuk mengurangi noise

2. **Thresholding & Morfologi**
   - Thresholding Otsu digunakan untuk mendapatkan area penyakit
   - Morphological *Opening* untuk menghapus noise kecil
   - Morphological *Closing* untuk menyambungkan bagian yang terputus

3. **Evaluasi**
   - Digunakan metrik **Intersection over Union (IoU)** dan **Dice Score**
   - Evaluasi dilakukan terhadap setiap citra dan dihitung rata-rata performanya

## 📊 Hasil Evaluasi

| Metode Preprocessing | Rata-rata IoU | Rata-rata Dice |
|----------------------|---------------|----------------|
| Tanpa Gaussian Blur  | 0.3074        | 0.4150         |
| Dengan Gaussian Blur | 0.3120        | 0.4191         |

Walaupun hasil blur secara visual terlihat lebih *kabur*, evaluasi kuantitatif menunjukkan adanya peningkatan performa segmentasi.

## 🛠 Tools dan Library

- Python
- OpenCV
- NumPy
- Matplotlib
- scikit-image

## 💡 Catatan

- Proyek ini bersifat non-deep learning, menggunakan pendekatan **klasik segmentasi citra**.
- Cocok untuk pemahaman awal tentang *Image Processing* dan Computer Vision di bidang pertanian digital.

## 📬 Kontak

Jika ingin berdiskusi atau kolaborasi, silakan hubungi:
**Mochammad Edo Pramudya**  
Mahasiswa Sains Data, Universitas Negeri Surabaya  
📧 edopramudua174@gmail.com

