# DCGAN-TensorFlow

Proyek ini mengimplementasikan **Deep Convolutional Generative Adversarial Network (DCGAN)** menggunakan *framework* **TensorFlow** dan **Keras**.

DCGAN adalah tipe *Generative Adversarial Network* yang memanfaatkan arsitektur *Convolutional* pada *Generator* dan *Discriminator* untuk menghasilkan citra sintetis yang berkualitas tinggi dari *latent vector* acak.

## 👤 Informasi Penulis 

* **Nama:** [Putri Regina]
* **NIM:** [41236774]
* **File Utama:** `Model_DCGAN putri regina`

## 🚀 Fitur Utama

1.  **Arsitektur DCGAN:** Penggunaan lapisan `Conv2D` dan `Conv2DTranspose` pada *Discriminator* dan *Generator*.
2.  **Custom Training Loop:** Implementasi pelatihan GAN (Generator dan Discriminator dilatih secara bergantian) menggunakan *Custom Training Loop* (kemungkinan meng-override `train_step`).
3.  **Visualisasi:** Menyertakan fungsi `GANMonitor` untuk memantau perkembangan Generator dalam menghasilkan citra selama pelatihan.

## 🧠 Arsitektur Model

Model DCGAN terdiri dari dua komponen utama:

### 1. Generator

* Menerima *latent vector* (`latent_dim`) sebagai input.
* Menggunakan `Dense` dan `Reshape` untuk membentuk citra awal.
* Menggunakan lapisan `Conv2DTranspose` untuk melakukan *upsampling* (memperbesar dimensi citra) hingga mencapai ukuran output yang diinginkan (misalnya, 32x32 atau 64x64).
* **Aktivasi Output:** `tanh` (jika data dinormalisasi ke rentang [-1, 1]).

### 2. Discriminator

* Menerima citra asli atau citra hasil Generator sebagai input.
* Menggunakan lapisan `Conv2D` untuk melakukan *downsampling* (mengurangi dimensi citra) dan mengekstrak fitur.
* Output adalah prediksi tunggal (`Dense(1)`) yang menentukan probabilitas citra tersebut **Real** atau **Fake**.

## ⚙️ Detail Pelatihan

* **Dataset:** [Tambahkan nama Dataset yang digunakan, contoh: Fashion-MNIST, CIFAR-10, atau Custom Dataset]
* **Dimensi Latent (Latent Dim):** [Tergantung kode, umumnya 100]
* **Epochs:** **500** (Jumlah *epoch* yang disetel dalam kode).
* **Optimizer:** Adam.
    * **Learning Rate Generator (`lr_generator`):** 0.0002
    * **Learning Rate Discriminator (`lr_discriminator`):** 0.0002
    * **Beta 1:** 0.5 (Beta 1 rendah umum digunakan dalam DCGAN).
* **Loss Function:** `BinaryCrossentropy(from_logits=True)`.

**bukti hasil**
<img width="794" height="327" alt="image" src="https://github.com/user-attachments/assets/87a3ce8d-66de-4556-920a-ee8cccf58311" />


