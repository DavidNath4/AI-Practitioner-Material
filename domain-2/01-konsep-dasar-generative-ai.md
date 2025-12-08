# Domain 2: Konsep Dasar dan Aplikasi Generative AI

## Task Statement 2.1: Menjelaskan Konsep Dasar Generative AI

### 1. Pengenalan Generative AI

#### 1.1 Apa itu Generative AI?

**Generative AI** adalah subset dari deep learning yang berfokus pada pembuatan konten baru dan orisinal, bukan hanya mengklasifikasikan atau menemukan konten yang sudah ada.

**Perbedaan dengan AI Tradisional:**
- **AI Tradisional**: Fokus pada klasifikasi dan prediksi berdasarkan data input
- **Generative AI**: Fokus pada pembuatan konten baru seperti teks, gambar, audio, video, dan bahkan kode

**Cara Kerja:**
Model generative AI mempelajari pola dan representasi dari sejumlah besar data pelatihan, kemudian menggunakan pengetahuan tersebut untuk menghasilkan output yang menyerupai data pelatihan.

#### 1.2 Foundation Models

Generative AI menggunakan **foundation models** yang telah dilatih dengan jumlah data yang sangat besar. Model-model ini:
- Mencari pola statistik dalam berbagai modalitas (bahasa alami, gambar, dll)
- Merupakan model neural network yang sangat besar dan kompleks
- Memiliki miliaran parameter yang dipelajari selama fase pelatihan (pre-training)
- Semakin banyak parameter, semakin banyak memori yang dimiliki model
- Dapat melakukan tugas yang lebih canggih dengan lebih banyak parameter

**Penggunaan Foundation Models:**
- Dapat digunakan langsung (as-is)
- Dapat disesuaikan dengan teknik fine-tuning untuk use case spesifik

### 2. Komponen Inti Model Generative AI

#### 2.1 Elemen Pembentuk Model

Model dibangun dengan kombinasi:
1. **Neural Networks**: Arsitektur jaringan saraf
2. **System Resources**: Sumber daya komputasi
3. **Data**: Data pelatihan
4. **Prompts**: Instruksi input

**Proses Kerja Model:**
- Model menerima data atau teks yang Anda input
- Memberikan output berupa prediksi kata atau token berikutnya
- Output adalah "tebakan" berdasarkan apa yang telah dipelajari

#### 2.2 Transformer Network

**Transformer** adalah elemen inti dari generative AI modern, diperkenalkan dalam paper "Attention Is All You Need" (2017).

**Karakteristik Transformer:**
- Digunakan oleh LLM seperti ChatGPT
- Di-pre-train dengan jumlah data teks yang sangat besar dari internet
- Membangun basis pengetahuan yang luas melalui proses pre-training
- Dapat di-fine-tune untuk tugas spesifik dengan data tambahan yang relatif sedikit

**Keunggulan:**
- Dapat memproses instruksi bahasa alami
- Melakukan tugas seperti yang dilakukan manusia
- Sangat scalable (dapat diperbesar)

### 3. Konsep Penting dalam Generative AI

#### 3.1 Terminologi Kunci

**Konsep yang Harus Dipahami untuk Ujian:**
- **Prompt**: Input yang diberikan ke model
- **Inference**: Proses model menghasilkan output
- **Completion**: Output yang dihasilkan model
- **Context Window**: Jendela konteks untuk memproses input
- **Tokens**: Unit terkecil dari teks yang diproses model
- **Vocabulary**: Kosakata yang dipahami LLM
- **Tokenizer**: Alat untuk mengubah teks menjadi token
- **Prompt Engineering**: Teknik merancang prompt yang efektif

#### 3.2 Dasar Matematika

Model AI bergantung pada:
- **Statistik dan Aljabar Linear**
- **Probability Modeling**: Pemodelan probabilitas
- **Loss Function**: Fungsi kerugian
- **Matrix Multiplication**: Perkalian matriks

**Alasan:** Machine learning lebih suka bekerja dengan angka, bukan teks, gambar, atau video mentah.

### 4. Prompt Engineering dan In-Context Learning

#### 4.1 Prompt Engineering

**Definisi:** Strategi untuk membuat model menghasilkan completion yang lebih baik dengan menyertakan contoh tugas yang ingin dilakukan model.

**Strategi:**
- Menyertakan contoh di dalam prompt
- Memberikan instruksi yang jelas dan spesifik
- Iterasi dan penyempurnaan prompt

#### 4.2 In-Context Learning

**Definisi:** Menyediakan contoh atau data tambahan di dalam context window untuk membantu LLM memahami tugas yang diminta.

**Jenis-jenis:**
1. **Zero-shot Inference**: Tanpa contoh, hanya instruksi
2. **One-shot Inference**: Satu contoh diberikan
3. **Few-shot Inference**: Beberapa contoh diberikan

**Komponen Prompt:**
- Instruksi (instruction)
- Konten (content)
- In-context learning (contoh-contoh)

#### 4.3 Inference Configuration

Parameter konfigurasi inference mempengaruhi completion model terhadap prompt. Ini mengontrol bagaimana model menghasilkan output.

### 5. Tokenizer dan Vector Representations

#### 5.1 Tokenizer

**Fungsi:** Setiap model generative AI berbasis bahasa memiliki tokenizer yang mengubah teks manusia menjadi vektor yang berisi token IDs atau input IDs.

**Proses:**
1. Teks input → Tokenizer → Token IDs
2. Setiap input ID mewakili token dalam vocabulary model

#### 5.2 Vector (Vektor)

**Definisi:** Daftar angka yang terurut yang mewakili fitur atau atribut dari suatu entitas atau konsep.

**Dalam Konteks Generative AI:**
- Vektor dapat mewakili kata, frasa, kalimat, atau unit lainnya
- Mengkodekan hubungan antara item
- Menangkap asosiasi, analogi, dan hierarki yang bermakna

**Analogi:** Vektor seperti spreadsheet Excel - daftar angka menunjukkan lokasi spesifik dalam ruang tertentu (vector database), sama seperti nomor kolom dan baris menunjukkan sel tertentu dalam spreadsheet.

#### 5.3 Embeddings

**Definisi:** Representasi vektor numerik dari entitas apa pun yang menangkap makna semantik dari token (teks, gambar, video, atau audio).

**Karakteristik:**
- Disebut juga "embedding vectors"
- Mengkodekan makna dan konteks token dalam kumpulan teks yang besar
- Model dapat merepresentasikan dan memahami bahasa manusia secara statistik
- Token yang lebih dekat dalam ruang vektor memiliki makna semantik yang lebih mirip

**Proses:**
1. Tokenizer mengubah input text menjadi vektor
2. Embedding vector adalah set input IDs untuk mendapatkan representasi dimensi tinggi dari setiap token
3. Embeddings diteruskan ke self-attention layers

### 6. Self-Attention Mechanism

#### 6.1 Inovasi Transformer

**Self-Attention** adalah mekanisme kunci dalam transformer yang membantu model menimbang pentingnya bagian-bagian berbeda dari input saat menghasilkan setiap output token.

**Keunggulan:**
- Menangkap dependensi jarak jauh (long-range dependencies)
- Memahami hubungan kontekstual
- Lebih baik dari arsitektur sebelumnya seperti Recurrent Neural Networks (RNNs)

#### 6.2 Cara Kerja Self-Attention

**Proses:**
1. Menghitung set vektor **query**, **key**, dan **value** untuk setiap input token
2. Menggunakan dot products antara vektor-vektor ini untuk menentukan attention weights
3. Output untuk setiap token adalah weighted sum dari value vectors
4. Proses diulang dalam multiple layers untuk membangun representasi kompleks dari input

#### 6.3 Position Embeddings

**Fungsi:** Mengkodekan posisi relatif dari setiap token dalam sequence.

**Manfaat:**
- Membantu model membedakan token identik yang muncul di posisi berbeda
- Penting untuk memahami struktur kalimat dan urutan kata

### 7. Arsitektur Transformer

#### 7.1 Komponen Utama

**Struktur:**
- **Encoder**: Memproses input
- **Decoder**: Menghasilkan output
- Setiap layer terdiri dari dua sublayers
- Menggunakan residual connections dan layer normalization

**Fungsi:**
- Memfasilitasi training
- Mencegah overfitting
- Menangkap urutan sequence tanpa operasi recurrent atau convolutional

#### 7.2 Proses Inference

Selama model inference, transformer:
- Menggunakan self-attention untuk menghitung representasi dari input sequences
- Menangkap long-term dependencies
- Melakukan komputasi paralel
- Menghasilkan completion untuk input prompt

**Catatan untuk Ujian:** Anda tidak perlu memahami detail low-level dari arsitektur transformer, tetapi penting untuk memahami bahwa implementasi kompleks terjadi di balik layar.

### 8. Scaling dan Model Growth

#### 8.1 Hubungan Ukuran dan Kemampuan

**Temuan Penelitian:**
- Model yang lebih besar cenderung bekerja lebih baik tanpa in-context learning tambahan
- Kemampuan model meningkat seiring ukuran
- Mendorong pengembangan model yang lebih besar

**Faktor Pendukung:**
1. Arsitektur transformer yang sangat scalable
2. Akses ke jumlah data pelatihan yang sangat besar
3. Pengembangan sumber daya komputasi yang lebih powerful

#### 8.2 Tantangan

**Pertanyaan Penting:**
- Apakah kita bisa terus menambah parameter untuk meningkatkan performa?
- **Jawaban:** Melatih model besar sangat sulit dan mahal
- Mungkin sulit untuk terus melatih model yang lebih besar

### 9. Pre-training Process

#### 9.1 Pembelajaran Statistik Bahasa

**LLM mengkodekan representasi statistik mendalam dari bahasa:**
- Pemahaman dikembangkan selama fase pre-training
- Model belajar dari jumlah data tidak terstruktur yang sangat besar
- Data bisa mencapai gigabytes, terabytes, bahkan petabytes teks
- Data diambil dari berbagai sumber termasuk internet

#### 9.2 Self-Supervised Learning

**Proses:**
1. Model menginternalisasi pola dan struktur dalam bahasa
2. Pola membantu model menyelesaikan training objective
3. Training objective tergantung pada arsitektur model
4. Model weights diperbarui untuk meminimalkan loss dari training objective

#### 9.3 Encoder dan Embeddings

**Fungsi Encoder:**
- Menghasilkan embedding atau representasi vektor untuk setiap token
- Memproses input menjadi format yang dapat dipahami model

**Kebutuhan Komputasi:**
- Pre-training memerlukan komputasi yang sangat besar
- Menggunakan Graphics Processing Units (GPUs)

#### 9.4 Data Quality Curation

**Proses Penting:**
- Data dari situs publik seperti internet perlu diproses
- Tujuan: meningkatkan kualitas, mengatasi bias, menghapus konten berbahaya
- **Estimasi:** Hanya 1-3% token yang digunakan untuk pre-training setelah kurasi kualitas data
- Penting untuk menentukan berapa banyak data yang perlu dikumpulkan

### 10. Unimodal vs Multimodal

#### 10.1 Unimodal Generative AI

**Definisi:** Model yang bekerja dengan satu modalitas data.

**Contoh:**
- **LLMs**: Input dan output berupa teks
- Hanya memproses satu jenis data

#### 10.2 Multimodal Generative AI

**Definisi:** Model yang dapat memahami dan memproses berbagai sumber data dan memberikan prediksi yang lebih robust.

**Modalitas Tambahan:**
- Gambar (image)
- Video
- Audio

**Keunggulan:**
- Pemahaman data yang lebih beragam
- Prediksi yang lebih robust
- Kemampuan reasoning lintas model
- Lebih mirip dengan kecerdasan manusia

**Use Cases Multimodal:**
- Marketing
- Image captioning (membuat caption gambar)
- Product design
- Customer service
- Chatbots
- Avatars

### 11. Multimodal Tasks dan Diffusion Models

#### 11.1 Contoh Tugas Multimodal

**1. Image Captioning**
- Model menghasilkan deskripsi teks dari gambar

**2. Visual Question Answering**
- Model menjawab pertanyaan tentang konten gambar

**3. Text-to-Image Synthesis**
- Menghasilkan gambar dari deskripsi tekstual
- **Contoh Model:** DALL-E, Stable Diffusion, Midjourney
- Dapat membuat gambar realistis dan beragam dari prompt bahasa alami

#### 11.2 Diffusion Models

**Definisi:** Kelas model generative yang belajar membalikkan proses noising bertahap.

**Fungsi:**
- Mendukung berbagai tugas untuk model multimodal
- Image generation (pembuatan gambar)
- Upscaling (meningkatkan resolusi)
- Inpainting (mengisi bagian gambar yang hilang)

**Cara Kerja:**
1. Mulai dengan random noise
2. Iteratif melakukan de-noise untuk menghasilkan output yang koheren
3. Model memprediksi noise yang ditambahkan di setiap langkah
4. Dikondisikan pada output yang sebagian di-denoise dari langkah sebelumnya

#### 11.3 Tiga Komponen Utama Diffusion Models

**Untuk Ujian, Pahami:**
1. **Forward Diffusion**: Proses menambahkan noise
2. **Reverse Diffusion**: Proses menghilangkan noise
3. **Stable Diffusion**: Implementasi khusus

#### 11.4 Stable Diffusion

**Perbedaan dengan Model Lain:**
- Tidak menggunakan pixel space dari gambar
- Menggunakan reduced definition latent space
- Menggunakan Gaussian noise untuk encode gambar
- Menggunakan noise predictor dengan reverse diffusion process untuk recreate gambar

**Kemudahan Penggunaan:**
- Dapat dengan mudah menghasilkan gambar dari teks
- Tersedia melalui Amazon SageMaker JumpStart

#### 11.5 Keunggulan Diffusion Models

**Dibandingkan dengan Generative Adversarial Networks (GANs) dan Variational Autoencoders (VAEs):**
- Menghasilkan output berkualitas lebih tinggi
- Lebih beragam dan konsisten
- Lebih stabil dan mudah dilatih

**Contoh Diffusion Models:**
- **Stable Diffusion**: Image generation
- **Whisper**: Speech recognition dan translation
- **AudioLM**: Audio generation

### 12. AWS Services untuk Multimodal dan Diffusion Models

**Amazon SageMaker:**
- Mendukung deep learning frameworks (TensorFlow, PyTorch)
- Memiliki modul pre-built untuk bekerja dengan data multimodal

**Pre-trained Models:**
- Stable Diffusion tersedia
- Dapat di-fine-tune dan di-deploy dengan beberapa baris kode

**Layanan AWS Lainnya:**
- Menyediakan berbagai tools untuk membangun dan men-deploy model multimodal dan diffusion

### 13. Use Cases Generative AI

#### 13.1 Text Generation

**Kemampuan:**
- Menulis atau menulis ulang teks untuk berbagai audiens
- Mengadaptasi dokumen teknis menjadi bahasa yang lebih sederhana

**Contoh:**
- Mengubah dokumen teknis tentang spesifikasi perangkat scuba diving
- Menggunakan istilah yang lebih sederhana untuk pemula sertifikasi scuba diving

#### 13.2 Text Summarization

**Kemampuan:**
- Mengambil informasi panjang dan menghasilkan output singkat
- Mempertahankan ide utama

**Contoh Aplikasi:**
- Meringkas dokumentasi teknis
- Laporan keuangan
- Dokumen legal
- Artikel berita

#### 13.3 AWS Services untuk Content Creation

**Amazon Bedrock dan Amazon Titan:**
- Pre-trained models untuk teks, gambar, audio generation
- Dapat di-fine-tune untuk use case spesifik

**Amazon SageMaker:**
- Mendukung code generation dan completion

**Amazon Q Developer (formerly CodeWhisperer):**
- Code generation dan completion

**Amazon Sumerian:**
- Virtual production dan 3D content creation

#### 13.4 Use Cases Lainnya

**Berbagai Aplikasi:**
- Information extraction (ekstraksi informasi)
- Question answering (menjawab pertanyaan)
- Classification (klasifikasi)
- Identifying harmful content (identifikasi konten berbahaya)
- Translation (terjemahan)
- Recommendation engines (mesin rekomendasi)
- Personalized marketing and ads (marketing dan iklan personal)
- Chatbots
- Customer service agents
- Search (pencarian)

#### 13.5 Code Generation

**Definisi:** Aplikasi generative AI untuk mempercepat pengembangan software.

**Kemampuan:**
- Menghasilkan code snippets fungsional
- Bahkan program lengkap dari deskripsi bahasa alami
- Mengotomasi tugas programming rutin
- Code completions
- Menerjemahkan kode antar bahasa berbeda

**Amazon Q Developer:**
- Menghasilkan saran kode real-time
- Dari snippets hingga fungsi lengkap
- Berdasarkan komentar dan kode yang ada

**Keuntungan AWS:**
- AWS menangani infrastruktur underlying
- Data management
- Model training
- Inference
- Anda fokus pada use case dan aplikasi spesifik

### 14. Arsitektur Generative AI

**Untuk Ujian, Pahami Berbagai Arsitektur:**

1. **Generative Adversarial Networks (GANs)**
2. **Variational Autoencoders (VAEs)**
3. **Transformers**

**Penting:**
- Setiap arsitektur memiliki keunggulan dan keterbatasan unik
- Evaluasi objektif dan dataset sebelum memilih arsitektur yang sesuai

### 15. Generative AI Project Lifecycle

#### 15.1 Framework Lifecycle

**Tahapan Proyek dari Konsepsi hingga Peluncuran:**

1. **Identify Use Case** (Identifikasi Use Case)
2. **Experiment and Select** (Eksperimen dan Pilih)
3. **Adapt, Align, and Augment** (Adaptasi, Selaraskan, dan Augmentasi)
4. **Evaluate** (Evaluasi)
5. **Deploy and Iterate** (Deploy dan Iterasi)
6. **Monitor** (Monitor)

#### 15.2 Stage 1: Define and Develop

**Tahap Pertama - Define Objectives:**
- Definisikan objektif
- Kumpulkan data
- Proses data
- Pilih model
- Latih dan kembangkan model

**Tahap Kedua - Develop Model:**
- Feature engineering
- Building (membangun)
- Testing (menguji)
- Validating (validasi)
- Optimizing (optimasi)
- Scaling (penskalaan)

**Tahap Ketiga - Deploy and Maintain:**
- Model evaluation
- Deployment
- Feedback
- Updates
- Security
- Scalability

#### 15.3 Foundation Model Lifecycle (Exam Guide)

**Tahapan Menurut Exam Guide:**
1. **Data Selection** (Pemilihan Data)
2. **Model Selection** (Pemilihan Model)
3. **Pre-training** (Pra-pelatihan)
4. **Fine-tuning** (Penyesuaian)
5. **Evaluation** (Evaluasi)
6. **Deployment** (Penerapan)
7. **Feedback** (Umpan Balik)

#### 15.4 Langkah Paling Penting: Define Scope

**Mendefinisikan Scope:**
- Langkah paling penting dalam proyek
- Definisikan scope seakurat dan sesempit mungkin
- Pikirkan fungsi LLM dalam aplikasi spesifik Anda

**Pertanyaan Kunci:**
- Apakah model perlu melakukan banyak tugas berbeda?
- Apakah tugas spesifik seperti named entity recognition?
- Model hanya perlu bagus di satu hal?

**Manfaat:**
- Menghemat waktu
- Menghemat biaya komputasi

#### 15.5 Keputusan Awal: Train vs Existing Model

**Pilihan:**
1. Melatih model sendiri dari awal (from scratch)
2. Bekerja dengan existing base model

**Pertimbangan:**
- Kebutuhan spesifik aplikasi
- Sumber daya yang tersedia
- Waktu pengembangan
- Biaya

### 16. Model Performance dan Training

#### 16.1 Assess Performance

**Langkah Setelah Pemilihan Model:**
- Menilai performa model
- Menyelesaikan training tambahan jika diperlukan

#### 16.2 Prompt Engineering sebagai Langkah Awal

**Strategi:**
- Mulai dengan prompt engineering
- Menggunakan in-context learning
- Menggunakan contoh yang sesuai dengan tugas dan use case
- Mencoba one-shot atau few-shot inferences

#### 16.3 Fine-tuning

**Kapan Menggunakan:**
- Jika model tidak perform dengan baik bahkan dengan one- atau few-shot inference
- Proses supervised learning

**Proses:**
- Melatih model dengan data spesifik
- Menyesuaikan model untuk tugas tertentu

#### 16.4 Reinforcement Learning from Human Feedback (RLHF)

**Tujuan:**
- Memastikan model berperilaku baik
- Selaras dengan preferensi manusia dalam deployment

**Pentingnya:**
- Model menjadi lebih capable
- Semakin penting untuk memastikan perilaku yang baik

#### 16.5 Evaluation

**Aspek Penting:**
- Menggunakan berbagai metrik dan benchmark
- Menentukan seberapa baik model perform
- Menentukan seberapa baik model selaras dengan preferensi Anda

**Sifat Iteratif:**
- Tahap development dengan adapting dan aligning sangat iteratif
- Mulai dengan prompt engineering
- Evaluasi outputs
- Gunakan fine-tuning untuk meningkatkan performa
- Selalu revisit dan evaluasi prompt engineering

### 17. Deployment dan Infrastructure

#### 17.1 Deployment

**Ketika Model Siap:**
- Model memenuhi kebutuhan performa
- Model well-aligned dengan tujuan
- Siap untuk di-deploy

**Proses Deployment:**
- Deploy ke infrastruktur Anda
- Integrasi dengan aplikasi
- Optimasi model untuk deployment
- Optimasi compute resources
- Memastikan aplikasi memberikan pengalaman yang baik untuk users

#### 17.2 Additional Infrastructure

**Pertimbangan Penting:**
- Infrastruktur tambahan yang diperlukan aplikasi untuk bekerja
- Keterbatasan fundamental dari LLMs

**Keterbatasan LLMs yang Sulit Diatasi:**
1. **Hallucinations**: Menciptakan informasi ketika jawaban tidak diketahui
2. **Limited Ability**: Kemampuan terbatas dengan reasoning kompleks dan matematika

**Solusi:**
- Sulit diatasi hanya melalui training
- Memerlukan infrastruktur dan strategi tambahan

### 18. Best Practices dan Rekomendasi

#### 18.1 Workflow yang Disarankan

**Urutan Langkah:**
1. Definisikan scope dengan jelas dan sempit
2. Pilih antara train from scratch atau existing model
3. Mulai dengan prompt engineering
4. Evaluasi hasil
5. Jika perlu, lakukan fine-tuning
6. Pertimbangkan RLHF untuk alignment
7. Evaluasi dengan metrik yang sesuai
8. Deploy dan monitor
9. Iterasi berdasarkan feedback

#### 18.2 Tips untuk Ujian

**Konsep yang Harus Dikuasai:**
- Perbedaan antara AI tradisional dan generative AI
- Cara kerja transformer dan self-attention
- Tokenizer, embeddings, dan vectors
- Unimodal vs multimodal
- Diffusion models dan komponennya
- Berbagai use cases generative AI
- Project lifecycle dan tahapannya
- Prompt engineering dan in-context learning
- Fine-tuning dan RLHF
- Keterbatasan LLMs

**Arsitektur yang Perlu Dipahami:**
- Transformers
- GANs (Generative Adversarial Networks)
- VAEs (Variational Autoencoders)
- Diffusion Models

**AWS Services yang Relevan:**
- Amazon Bedrock
- Amazon Titan
- Amazon SageMaker
- Amazon Q Developer
- Amazon Sumerian

---

## Ringkasan Poin Kunci

### Konsep Fundamental
- Generative AI adalah subset deep learning yang membuat konten baru
- Foundation models dilatih dengan data sangat besar dan memiliki miliaran parameter
- Transformer adalah arsitektur inti dengan self-attention mechanism
- Model bekerja dengan mengubah teks menjadi tokens, embeddings, dan vectors

### Proses dan Lifecycle
- Pre-training menggunakan data sangat besar dan memerlukan GPU
- Fine-tuning menyesuaikan model untuk tugas spesifik
- RLHF memastikan model selaras dengan preferensi manusia
- Deployment memerlukan optimasi dan infrastruktur tambahan

### Modalitas dan Use Cases
- Unimodal: satu jenis data (contoh: LLM untuk teks)
- Multimodal: berbagai jenis data (teks, gambar, audio, video)
- Diffusion models untuk image generation berkualitas tinggi
- Use cases: text generation, summarization, code generation, chatbots, dll

### AWS Services
- Amazon Bedrock dan Titan untuk pre-trained models
- SageMaker untuk training dan deployment
- Amazon Q Developer untuk code generation
- Berbagai tools untuk multimodal dan diffusion models

### Best Practices
- Definisikan scope dengan jelas dan sempit
- Mulai dengan prompt engineering
- Evaluasi secara iteratif
- Pertimbangkan keterbatasan LLMs (hallucinations, reasoning)
- Gunakan metrik dan benchmark yang sesuai

---

**Catatan:** Materi ini mencakup Task Statement 2.1 dari Domain 2 AWS Certified AI Practitioner. Pastikan untuk memahami konsep-konsep ini dengan baik karena merupakan fondasi untuk memahami generative AI dan aplikasinya di AWS.
