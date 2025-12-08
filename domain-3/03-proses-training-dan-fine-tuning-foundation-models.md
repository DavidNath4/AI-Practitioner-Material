# Proses Training dan Fine-Tuning Foundation Models

## Pengantar

Dalam pengembangan aplikasi AI menggunakan foundation models (FM), memahami proses training dan fine-tuning sangat penting. Task Statement 3.3 dari AWS Certified AI Practitioner membahas secara mendalam bagaimana foundation models dilatih, disesuaikan, dan dioptimalkan untuk kebutuhan spesifik organisasi Anda.

## Elemen Kunci dalam Training Foundation Model

Ada tiga elemen utama dalam proses training foundation model:

1. **Pre-training** (Pelatihan Awal)
2. **Fine-tuning** (Penyesuaian Model)
3. **Continuous Pre-training** (Pelatihan Berkelanjutan)

---

## 1. Pre-training: Fondasi Pembelajaran Model

### Apa itu Pre-training?

Pre-training adalah proses kompleks di mana model AI belajar kemampuan dasarnya. Ini adalah tahap pertama dan paling fundamental dalam pengembangan foundation model.

### Sumber Daya yang Dibutuhkan

Pre-training memerlukan investasi sumber daya yang sangat besar:

- **Jutaan GPU (Graphics Processing Units)** untuk komputasi
- **Jutaan jam komputasi** untuk pemrosesan
- **Terabyte hingga Petabyte data** sebagai bahan pembelajaran
- **Triliun token** untuk diproses
- **Trial and error** yang ekstensif
- **Waktu yang signifikan** untuk menyelesaikan proses

### Karakteristik Pre-training

- Menggunakan **self-supervised learning** (pembelajaran tanpa label manual)
- Melatih LLM dengan **jumlah data tidak terstruktur yang sangat besar**
- Model belajar dari jutaan dokumen, video, gambar, file audio, dan berbagai sumber lainnya
- Model mempelajari **fundamental bahasa manusia** dan pola-pola dasar

### Hasil Pre-training

Setelah pre-training, foundation model memiliki pemahaman umum tentang bahasa, konteks, dan berbagai konsep. Namun, model mungkin masih memerlukan penyesuaian untuk:
- Domain atau dataset spesifik organisasi Anda
- Tugas-tugas khusus yang memerlukan reasoning manusia
- Terminologi industri atau jargon teknis tertentu

---

## 2. Fine-tuning: Menyesuaikan Model untuk Kebutuhan Spesifik

### Definisi Fine-tuning

Fine-tuning adalah proses yang **memperluas training model** untuk meningkatkan kemampuan menghasilkan output yang lebih baik untuk tugas spesifik. Ini adalah proses **supervised learning** yang menggunakan dataset berlabel untuk memperbarui bobot (weights) LLM.

### Tujuan Fine-tuning

- Mengadaptasi foundation model ke dataset kustom Anda
- Meningkatkan performa untuk use case spesifik
- Membuat model lebih relevan dengan kebutuhan bisnis Anda

### Instruction-based Fine-tuning

Menggunakan contoh-contoh berlabel untuk meningkatkan performa pada tugas spesifik. LLM dapat melakukan banyak tugas berbeda dalam satu model, tetapi fine-tuning membantu mengoptimalkan performa untuk tugas tertentu.

---

## 3. Jenis-jenis Fine-tuning

### A. Full Fine-tuning

**Definisi:** Setiap parameter dalam model diperbarui melalui supervised learning.

**Karakteristik:**
- Memperbarui semua bobot model
- Memerlukan sumber daya komputasi yang besar
- Memberikan hasil yang sangat disesuaikan

**Komponen Memory yang Dibutuhkan:**
- Parameter model
- Optimizer
- Gradients
- Forward activations
- Temporal memory

Semua komponen ini menambah byte GPU memory untuk setiap parameter model dan meningkatkan biaya komputasi.

### B. Parameter-Efficient Fine-Tuning (PEFT)

**Definisi:** Proses dan teknik yang **membekukan (freeze)** parameter dan bobot LLM original, kemudian hanya melakukan fine-tune pada sejumlah kecil adaptor layers dan parameter yang spesifik untuk tugas tertentu.

**Keuntungan PEFT:**
- Mengurangi kebutuhan komputasi dan memory
- Lebih efisien biaya
- Tetap mempertahankan kemampuan dasar model original
- Hanya melatih subset kecil dari parameter model

**Low-Rank Adaptation (LoRA):**
- Teknik PEFT yang paling populer
- Mempertahankan/membekukan bobot original foundation model
- Membuat trainable low-rank matrices baru di setiap layer arsitektur transformer
- PEFT dan LoRA memodifikasi bobot model, tetapi **tidak memodifikasi representasi**

### C. Representation Fine-Tuning (ReFT)

**Definisi:** Proses fine-tuning yang membekukan base model dan mempelajari intervensi spesifik-tugas pada hidden representations.

**Konsep Dasar:**
- **Linear Representation Hypothesis:** Konsep dikodekan dalam subspace linear dari representasi dalam neural network
- Representasi mengkodekan informasi semantik, mirip dengan embeddings
- Fokus pada memodifikasi representasi, bukan bobot

### D. Multitask Fine-tuning

**Definisi:** Perluasan dari fine-tuning tugas tunggal untuk melatih model menyelesaikan banyak tugas secara bersamaan.

**Karakteristik:**
- Memerlukan **banyak data**
- Dataset training berisi contoh input dan output untuk **multiple tasks**
- Menghasilkan **instruction-tuned model**

**Contoh Tugas yang Dapat Dipelajari Bersamaan:**
- Review atau rating produk
- Summarization (peringkasan)
- Translating code (menerjemahkan kode)
- Dan tugas-tugas lainnya

**Keuntungan:**
- Menghitung losses dari berbagai contoh untuk memperbarui bobot model
- Membantu **mengurangi dan menghindari catastrophic forgetting**
- Model dapat menyelesaikan banyak tugas berbeda secara simultan

---

## 4. Tantangan dalam Fine-tuning

### Catastrophic Forgetting

**Definisi:** Fenomena di mana proses fine-tuning memodifikasi bobot LLM original, yang dapat meningkatkan performa pada tugas spesifik tetapi **menurunkan performa pada tugas lainnya**.

**Kapan Terjadi:**
- Saat melakukan fine-tuning pada single task
- Ketika seluruh proses fine-tuning memodifikasi bobot model original

**Pertimbangan:**
- Apakah catastrophic forgetting akan berdampak pada use case Anda?
- Jika Anda memerlukan performa yang reliable pada single task, Anda mungkin tidak perlu khawatir bahwa model tidak dapat generalisasi ke tugas lain
- Multitask fine-tuning dapat membantu mengurangi risiko ini

---

## 5. Fine-tuning Khusus

### A. Domain Adaptation Fine-tuning

**Definisi:** Kemampuan menggunakan pre-trained foundation models dan mengadaptasinya ke tugas spesifik dengan menggunakan **data domain-spesifik yang terbatas**.

**Kegunaan:**
- Membantu model bekerja dengan bahasa domain-spesifik
- Menangani industry jargon (jargon industri)
- Memahami technical terms (istilah teknis)
- Memproses specialized data lainnya

**Implementasi di AWS:**
- **Amazon SageMaker JumpStart** menyediakan kemampuan untuk fine-tune large language model
- Khususnya untuk text generation model pada dataset domain-spesifik
- Dapat meningkatkan performa dalam domain tertentu

### B. Reinforcement Learning from Human Feedback (RLHF)

**Definisi:** Menggunakan reinforcement learning untuk fine-tune LLM dengan data feedback manusia agar model lebih selaras dengan preferensi manusia.

**Tujuan:**
- Meningkatkan performa model
- Membantu model lebih memahami prompt yang human-like
- Menghasilkan respons yang lebih human-like
- Menyelaraskan output model dengan preferensi dan nilai-nilai manusia

**Proses:**
- Menggunakan feedback dari manusia sebagai sinyal reward
- Model belajar menghasilkan output yang lebih disukai manusia
- Iterasi berkelanjutan untuk perbaikan

---

## 6. Persiapan Data untuk Fine-tuning

### Langkah-langkah Persiapan Data

#### Langkah 1: Persiapan Training Data

- Gunakan **publicly available datasets** yang sudah terbukti
- Manfaatkan **prompt template libraries** yang berisi banyak template untuk berbagai tugas dan dataset
- Pastikan dataset instruction Anda siap

#### Langkah 2: Pembagian Dataset

Bagi dataset menjadi tiga bagian:
1. **Training split** - untuk melatih model
2. **Validation split** - untuk evaluasi selama proses
3. **Test split** - untuk evaluasi akhir

#### Langkah 3: Proses Fine-tuning

1. Pilih prompts dari training dataset
2. Berikan ke LLM untuk menghasilkan completions
3. Bandingkan distribusi completions dengan training label
4. Hitung **loss** antara dua distribusi token
5. Gunakan calculated loss untuk **memperbarui bobot model**

#### Langkah 4: Evaluasi

- Setelah banyak batch prompt-completion pairs, bobot diperbarui
- Performa model pada tugas meningkat
- Lakukan **evaluation steps** terpisah menggunakan holdout validation dataset
- Dapatkan **validation accuracy**

#### Langkah 5: Evaluasi Akhir

- Setelah fine-tuning selesai, lakukan final performance evaluation
- Gunakan **holdout test dataset**
- Hasil akhir memberikan **test accuracy**

---

## 7. Tools Data Preparation di AWS

AWS menyediakan berbagai tools untuk persiapan data dalam proses fine-tuning:

### A. Amazon SageMaker Canvas
**Untuk:** Low-code data preparation

**Fitur:**
- Membuat data flows yang mendefinisikan ML data pre-processing
- Feature engineering workflows dengan sedikit atau tanpa coding
- Cocok untuk pengguna non-teknis

### B. Amazon SageMaker Studio Classic dengan Amazon EMR
**Untuk:** Data preparation yang perlu scale

**Fitur:**
- Integrasi built-in dengan Amazon EMR
- Mendukung open source frameworks:
  - Apache Spark
  - Apache Hive
  - Presto
- Dapat menangani data dalam skala besar

### C. AWS Glue Interactive Sessions
**Untuk:** Serverless data preparation

**Fitur:**
- Apache Spark-based serverless engine
- Aggregate, transform, dan prepare data dari multiple sources
- Dapat digunakan dalam SageMaker Studio Classic
- Tidak perlu mengelola infrastructure

### D. Jupyter Lab dalam SageMaker Studio
**Untuk:** Data preparation menggunakan SQL

**Fitur:**
- Menggunakan Structured Query Language (SQL)
- Familiar bagi data analysts dan engineers
- Fleksibel untuk berbagai operasi data

### E. Amazon SageMaker Feature Store
**Untuk:** Feature discovery dan storage

**Fitur:**
- Search, discover, dan retrieve features untuk model training
- Centralized repository untuk menyimpan feature data
- Format standar untuk konsistensi
- Memudahkan reuse features across projects

### F. Amazon SageMaker Clarify
**Untuk:** Deteksi bias dalam data

**Fitur:**
- Menganalisis data dan mendeteksi potential biases
- Mendeteksi imbalanced representations
- Mengidentifikasi labeling biases antar grup (gender, race, age, dll)
- Membantu memastikan fairness dalam model

### G. Amazon SageMaker Ground Truth
**Untuk:** Data labeling

**Fitur:**
- Mengelola data labeling workflows
- Untuk training datasets yang memerlukan label
- Mendukung human labeling dan automated labeling
- Quality control untuk label accuracy

---

## 8. Continuous Pre-training: Pembelajaran Berkelanjutan

### Mengapa Continuous Pre-training Penting?

Continuous pre-training sangat penting dalam generative AI karena beberapa alasan:

#### 1. Output Non-deterministik

- Output dari generative AI models bersifat **non-deterministik**
- Membuat validasi menjadi lebih sulit
- Perlu metrics, benchmarks, dan datasets yang tepat untuk evaluasi

#### 2. Evaluasi Kemampuan Model

Penting untuk:
- Memilih metrics yang tepat
- Menggunakan benchmarks yang sesuai
- Memastikan model tidak menghasilkan **harmful outputs**
- Evaluasi berkelanjutan terhadap capabilities model

#### 3. Peningkatan Kemampuan Model

Ketika model terus dilatih pada data dari berbagai topik, genre, dan konteks:
- Model menjadi **lebih powerful** seiring waktu
- Belajar menggunakan **out-of-domain data** dengan lebih baik
- Mengakumulasi **wider knowledge** dan adaptability
- Menciptakan nilai lebih untuk organisasi

### Continuous Pre-training di Amazon Bedrock

**Implementasi:**
- Membantu melatih **Amazon Titan Text Express** dan **Amazon Titan Text Lite FMs**
- Dapat customize model menggunakan **unlabeled data** Anda sendiri
- Dilakukan dalam **secure dan managed environment**
- Tidak perlu mengelola infrastructure training yang kompleks

**Keuntungan:**
- Model tetap up-to-date dengan data terbaru
- Meningkatkan relevansi untuk use case spesifik
- Mempertahankan keamanan data organisasi
- Proses yang managed dan simplified

---

## Kesimpulan

Proses training dan fine-tuning foundation models adalah aspek kritis dalam pengembangan aplikasi AI yang efektif. Memahami berbagai metode fine-tuning, tantangan seperti catastrophic forgetting, dan tools yang tersedia di AWS akan membantu Anda:

1. Memilih pendekatan fine-tuning yang tepat untuk use case Anda
2. Mengoptimalkan penggunaan sumber daya komputasi
3. Mempersiapkan data dengan efektif
4. Mengevaluasi dan meningkatkan performa model secara berkelanjutan
5. Memanfaatkan layanan AWS untuk mempercepat development cycle

Dengan pemahaman yang solid tentang konsep-konsep ini, Anda akan lebih siap untuk mengimplementasikan solusi AI yang powerful dan disesuaikan dengan kebutuhan spesifik organisasi Anda.

---

## Poin-poin Penting untuk Ujian

- **Pre-training** menggunakan self-supervised learning dengan data tidak terstruktur dalam jumlah besar
- **Fine-tuning** adalah supervised learning yang menggunakan labeled examples
- **PEFT** lebih efisien daripada full fine-tuning dalam hal komputasi dan memory
- **LoRA** adalah teknik PEFT yang populer
- **Catastrophic forgetting** adalah risiko saat fine-tuning pada single task
- **Multitask fine-tuning** membantu mengurangi catastrophic forgetting
- **Domain adaptation fine-tuning** berguna untuk industry-specific language
- **RLHF** menyelaraskan model dengan preferensi manusia
- AWS menyediakan berbagai tools untuk data preparation (SageMaker Canvas, EMR, Glue, dll)
- **Continuous pre-training** penting untuk menjaga model tetap powerful dan adaptable
- Amazon Bedrock mendukung continuous pre-training untuk Amazon Titan models
