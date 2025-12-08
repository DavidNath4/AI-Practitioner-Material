# Transparansi dan Explainability Model AI

## Pengenalan

Salah satu tantangan terbesar dalam AI adalah membangun kepercayaan melalui pemahaman tentang bagaimana dan mengapa model AI membuat keputusan tertentu. Transparansi dan explainability menjadi kunci penting dalam pengembangan AI yang bertanggung jawab.

## Konsep Transparansi Model

**Transparansi** mengukur sejauh mana pemilik dan pemangku kepentingan ML dapat memahami cara kerja model dan alasan di balik output yang dihasilkan.

### Dua Dimensi Transparansi

#### 1. Interpretability (Kemampuan Interpretasi)

Interpretability mengacu pada kemampuan untuk memahami mekanisme internal model secara langsung.

**Model dengan Interpretability Tinggi:**
- **Linear Regression**: Algoritma yang sangat mudah dipahami dengan slope dan intercept yang jelas
- **Decision Trees**: Menghasilkan aturan-aturan dasar yang dapat dipahami dengan mudah

**Model dengan Interpretability Rendah:**
- **Neural Networks**: Meniru cara kerja otak manusia dengan hampir 100 miliar neuron
- Meskipun kita memahami bahwa otak bekerja melalui sinyal listrik, sulit memahami bagaimana proses tersebut menghasilkan pemikiran tertentu

#### 2. Explainability (Kemampuan Penjelasan)

Explainability adalah kemampuan untuk menjelaskan apa yang dilakukan model tanpa harus mengetahui secara pasti bagaimana cara kerjanya.

**Karakteristik Explainability:**
- Memperlakukan model sebagai "black box"
- Setiap model dapat diamati dan dijelaskan
- Menggunakan pendekatan model-agnostic untuk menjawab pertanyaan dunia nyata

**Contoh Penerapan:**
- Mengapa email ditandai sebagai spam?
- Mengapa aplikasi pinjaman seseorang ditolak?


## Pertimbangan dalam Memilih Model

### Kapan Membutuhkan Interpretability?

Saat memulai proyek AI atau ML baru, Anda perlu menentukan apakah interpretability adalah persyaratan bisnis yang wajib:

- **Jika ada regulasi atau persyaratan bisnis** untuk transparansi model yang lengkap → Pilih model yang interpretable
- **Jika cukup dengan explainability** untuk memenuhi tujuan bisnis → Model kompleks dapat digunakan

### Trade-off dalam Transparansi Model

#### 1. Trade-off Performa

**Model Sederhana (Transparansi Tinggi):**
- ✅ Mudah diinterpretasi
- ❌ Kemampuan dan performa terbatas

**Contoh:**
Model terjemahan bahasa sederhana yang hanya mengganti kata per kata dan mengikuti aturan grammar dasar akan menghasilkan terjemahan yang kurang lancar.

**Model Kompleks (Transparansi Rendah):**
- ✅ Performa tinggi
- ✅ Dapat memahami konteks kalimat secara menyeluruh
- ❌ Sulit diinterpretasi

**Neural network** untuk terjemahan dapat menghasilkan terjemahan yang jauh lebih lancar karena memahami konteks keseluruhan kalimat.

**Kesimpulan:** Meningkatkan transparansi model biasanya melibatkan kompromi dalam performa model.

#### 2. Trade-off Keamanan

**Model Transparan:**
- ❌ Lebih rentan terhadap serangan
- ❌ Hacker memiliki lebih banyak informasi tentang mekanisme internal
- ❌ Lebih mudah menemukan kerentanan

**Model Opaque (Tidak Transparan):**
- ✅ Membatasi penyerang hanya pada informasi dari output model
- ✅ Lebih sulit untuk di-reverse engineer

### Risiko Transparansi

1. **Keamanan Artefak Model**: Model transparan memerlukan pengamanan yang lebih ketat terhadap artefak model
2. **Paparan Algoritma Proprietary**: Semakin banyak penjelasan yang dapat diakses, semakin mudah model di-reverse engineer
3. **Privasi Data**: Transparansi mungkin memerlukan berbagi detail tentang data training, yang menimbulkan kekhawatiran privasi


## Tools dan Layanan AWS untuk Transparansi

### 1. Open Source Software

**Keuntungan:**
- Dikembangkan secara kolaboratif dan terbuka (contoh: GitHub)
- Pengguna dapat memahami konstruksi dan cara kerja internal model
- Memaksimalkan transparansi
- Meningkatkan kepercayaan terhadap keadilan model
- Kontribusi dari banyak pengguna global menghasilkan keragaman developer dan mengurangi bias
- Masalah bias atau coding lebih mudah terdeteksi

**Kekhawatiran:**
- Beberapa perusahaan khawatir tentang keamanan model
- Memblokir karyawan dari menggunakan atau mengembangkan dengan open source
- Lebih memilih pengembangan proprietary untuk alasan keamanan

### 2. AI Service Cards

Ketika menggunakan model terlatih yang di-hosting oleh AWS, Anda hanya berinteraksi dengan API tanpa akses langsung ke model. AWS menyediakan **AI Service Cards** sebagai bentuk dokumentasi responsible AI.

**Informasi yang Disediakan:**
- Use case yang dimaksudkan
- Keterbatasan model
- Pilihan desain responsible AI
- Best practices untuk deployment dan optimasi performa

**Contoh AI Service Cards:**
- Matching faces dengan Amazon Rekognition
- Analyzing IDs dengan Amazon Textract
- Detecting PII dengan Amazon Comprehend
- Amazon Titan Text (foundation model di Amazon Bedrock)

### 3. SageMaker Model Cards

Untuk model yang Anda buat sendiri, **SageMaker Model Cards** membantu mendokumentasikan lifecycle model dari tahap:
- Designing
- Building
- Training
- Evaluation

**Fitur Auto-populate:**
SageMaker secara otomatis mengisi detail tentang model yang dilatih, termasuk:
- Cara model dilatih
- Dataset yang digunakan
- Container yang digunakan

### 4. SageMaker Clarify

Selain melaporkan bias, **SageMaker Clarify** juga dapat melaporkan explainability.

#### Feature Attribution dengan Shapley Values

**Shapley Values** digunakan untuk menentukan kontribusi setiap fitur terhadap prediksi model.

**Visualisasi:**
- Bar chart menunjukkan 4 fitur paling berdampak yang digunakan model
- Membantu memahami fitur mana yang paling mempengaruhi keputusan model

#### Partial Dependence Plot

**Fungsi:**
- Menunjukkan bagaimana prediksi model berubah untuk nilai berbeda dari suatu fitur
- Contoh: Menganalisis pengaruh fitur "age" terhadap prediksi


## Human-Centered AI

### Konsep Dasar

**Human-Centered AI** mengacu pada desain sistem AI yang memprioritaskan kebutuhan dan nilai-nilai manusia.

### Karakteristik Human-Centered AI

**1. Kolaborasi Interdisipliner**
- Melibatkan psikolog, ahli etika, dan domain experts
- Mengumpulkan perspektif dan keahlian yang beragam

**2. Keterlibatan Pengguna**
- Pengguna terlibat dalam proses pengembangan
- Memastikan AI benar-benar bermanfaat dan user-friendly

**3. Tujuan Utama**
- Meningkatkan kemampuan manusia, bukan menggantikannya
- Selaras dengan prinsip ethical AI

**4. Integrasi Manusia di Setiap Tahap**
- Memastikan AI transparan
- Memastikan AI dapat dijelaskan (explainable)
- Memastikan AI adil dan tidak bias
- Menjaga privasi

### Amazon Augmented AI (Amazon A2I)

**Amazon A2I** menggabungkan review manusia untuk sampel inferensi yang dibuat oleh layanan AI AWS atau model kustom.

#### Cara Kerja

**1. Konfigurasi Review:**
- Mengirim inferensi dengan confidence score rendah ke reviewer manusia sebelum dikirim ke klien
- Feedback dapat ditambahkan ke data training untuk melatih ulang model

**2. Audit Model:**
- Reviewer manusia dapat mereview prediksi acak sebagai cara audit model

**3. Pilihan Reviewer:**
- Menggunakan pool reviewer dari organisasi sendiri
- Menggunakan Amazon Mechanical Turk
- Mengkonfigurasi berapa banyak reviewer yang perlu mereview setiap prediksi

#### Contoh Use Case

**Deteksi Konten Eksplisit dengan Amazon Rekognition:**
- Amazon Rekognition mendeteksi gambar yang mengandung konten eksplisit atau ofensif
- Manusia mereview prediksi dengan confidence rendah
- Memastikan konten eksplisit tidak lolos dari deteksi


## Reinforcement Learning from Human Feedback (RLHF)

### Definisi

**RLHF** adalah teknik standar industri untuk memastikan large language models menghasilkan konten yang:
- Truthful (Benar/Jujur)
- Harmless (Tidak Berbahaya)
- Helpful (Bermanfaat)

### Konsep Dasar Reinforcement Learning

Teknik reinforcement learning melatih model untuk membuat keputusan yang memaksimalkan reward, sehingga output menjadi lebih akurat.

### Cara Kerja RLHF

#### 1. Integrasi Human Feedback

RLHF menggabungkan feedback manusia dalam fungsi reward, sehingga model ML dapat melakukan tugas yang lebih selaras dengan:
- Tujuan manusia
- Keinginan manusia
- Kebutuhan manusia

#### 2. Reward Model

**Proses Training Reward Model:**

**Langkah 1: Pengumpulan Data**
- Manusia mereview multiple responses dari large language model untuk prompt yang sama
- Manusia menunjukkan response yang mereka preferensikan
- Preferensi ini menjadi training data untuk reward model

**Langkah 2: Training Reward Model**
- Reward model dilatih menggunakan preferensi manusia
- Setelah dilatih, reward model dapat memprediksi seberapa tinggi manusia akan menilai suatu prompt response

**Langkah 3: Refinement**
- Large language model menggunakan reward model untuk menyempurnakan responsnya
- Tujuan: Memaksimalkan reward

### Implementasi dengan SageMaker Ground Truth

**SageMaker Ground Truth** adalah cara paling mudah untuk mengumpulkan preferensi dari manusia untuk RLHF.

#### Contoh Workflow

**Proses Review:**
1. Human workers disajikan dengan multiple responses
2. Diminta untuk meranking setiap response berdasarkan kriteria tertentu (contoh: clarity/kejelasan)
3. Ranking ini digunakan sebagai training data untuk reward model

**Keuntungan:**
- Proses pengumpulan feedback terstruktur
- Dapat melibatkan banyak reviewer
- Integrasi langsung dengan pipeline ML

## Kesimpulan

Transparansi dan explainability adalah aspek krusial dalam pengembangan AI yang bertanggung jawab. Memahami trade-off antara transparansi, performa, dan keamanan membantu dalam memilih model yang tepat untuk kebutuhan bisnis. AWS menyediakan berbagai tools seperti AI Service Cards, SageMaker Model Cards, SageMaker Clarify, Amazon A2I, dan SageMaker Ground Truth untuk mendukung pengembangan AI yang transparan dan dapat dijelaskan.

## Poin-Poin Penting untuk Ujian

1. **Transparansi = Interpretability + Explainability**
2. **Trade-off utama**: Transparansi tinggi = Performa lebih rendah, Keamanan lebih rendah
3. **AI Service Cards**: Dokumentasi responsible AI untuk layanan AWS
4. **SageMaker Model Cards**: Dokumentasi lifecycle model custom
5. **SageMaker Clarify**: Feature attribution (Shapley values) dan Partial Dependence Plot
6. **Amazon A2I**: Human review untuk inferensi dengan confidence rendah
7. **RLHF**: Teknik untuk membuat LLM lebih truthful, harmless, dan helpful
8. **SageMaker Ground Truth**: Tool untuk mengumpulkan human feedback untuk RLHF
