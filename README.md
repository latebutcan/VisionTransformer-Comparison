# Vision Transformer Comparison

Repository ini berisi tugas eksplorasi Mata Kuliah Deep Learning untuk membandingkan performa tiga arsitektur Vision Transformer pada tugas klasifikasi citra.

- **Nama:** Rayhan Fadel Irwanto
- **NIM:** 122140236
- **Mata Kuliah:** Deep Learning
- **Topik:** Perbandingan Model Vision Transformer (ViT, Swin, DeiT)

Proyek ini mengimplementasikan dan membandingkan tiga varian model Transformer menggunakan teknik *Transfer Learning* pada dataset **IF25-4041**. Fokus utama adalah menganalisis *trade-off* antara akurasi, jumlah parameter, dan waktu inferensi.

Model yang Dibandingkan:
1. **ViT Tiny** (`vit_tiny_patch16_224`) - Representasi Transformer murni.
2. **Swin Transformer Tiny** (`swin_tiny_patch4_window7_224`) - Representasi Hierarchical Transformer.
3. **DeiT Tiny** (`deit_tiny_patch16_224`) - Representasi Distilled Transformer.

*Catatan: Varian "Tiny" dipilih untuk efisiensi sumber daya dan mencegah memory crash pada Google Colab.*

Cara Menjalankan Kode (Google Colab)

Kode ini dirancang untuk dijalankan secara menyeluruh di Google Colab dengan dukungan GPU. Ikuti langkah-langkah berikut:

### 1. Persiapan Environment
1. Buka file `.ipynb` di repository ini.
2. Klik tombol **"Open in Colab"** (jika ada) atau download dan upload manual ke Google Colab.
3. **PENTING:** Ubah Runtime ke GPU.
   - Klik menu `Runtime` > `Change runtime type`.
   - Pilih **T4 GPU**.

### 2. Upload Dataset
Kode ini memiliki fitur **otomatis ekstrak dan reorganisasi dataset**.
1. Siapkan file dataset Anda dengan nama **`IF25-4041-dataset.zip`**.
2. Di Google Colab, buka panel **Files** (ikon folder di sebelah kiri).
3. **Drag & Drop** file `.zip` tersebut ke area file.
4. Tunggu hingga proses upload selesai 100%.

### 3. Eksekusi
1. Klik menu **Runtime** > **Run all** (atau `Ctrl+F9`).
2. Script akan otomatis melakukan:
   - Instalasi library (`timm`, `grad-cam`).
   - Ekstraksi dan penataan ulang folder dataset berdasarkan `train.csv`.
   - Training 3 model berturut-turut.
   - Menampilkan tabel perbandingan dan visualisasi Attention Map.

Fitur Kode
- **Auto-Dataset Setup:** Otomatis membaca CSV dan memindahkan gambar ke folder kelas masing-masing.
- **Memory Optimization:** Menggunakan `Batch Size = 16` dan `Workers = 0` untuk mencegah sesi crash di Colab gratis.
- **Visualisasi:** Dilengkapi dengan Kurva Training, Confusion Matrix, dan **Grad-CAM Visualization** (Bonus).

Requirements
Library berikut akan diinstall otomatis di dalam notebook:
- `torch` & `torchvision`
- `timm` (PyTorch Image Models)
- `grad-cam`
- `scikit-learn`
- `matplotlib` & `seaborn`
- `pandas`

---
**Institut Teknologi Sumatera (ITERA) - 2025**
