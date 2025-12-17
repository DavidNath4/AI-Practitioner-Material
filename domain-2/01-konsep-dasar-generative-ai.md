# Domain 2: Konsep Dasar dan Aplikasi Generative AI

## Task Statement 2.1: Menjelaskan Konsep Dasar Generative AI

> **Bobot Ujian: 24%** - Domain ini memiliki bobot tertinggi kedua dalam ujian AWS Certified AI Practitioner, sehingga memerlukan pemahaman mendalam tentang konsep-konsep generative AI dan foundation models.

### 1. Pengenalan Generative AI

#### 1.1 Apa itu Generative AI?

**Generative AI** adalah subset dari deep learning yang berfokus pada pembuatan konten baru dan orisinal, bukan hanya mengklasifikasikan atau menemukan konten yang sudah ada. Seperti deep learning, generative AI adalah teknologi multipurpose yang membantu menghasilkan konten baru dan orisinal daripada menemukan atau mengklasifikasikan konten yang sudah ada.

**Perbedaan dengan AI Tradisional:**
- **AI Tradisional**: Fokus pada klasifikasi dan prediksi berdasarkan data input untuk membuat prediksi
- **Generative AI**: Fokus pada pembuatan konten baru seperti teks, gambar, audio, video, dan bahkan kode

**Cara Kerja:**
Model generative AI mempelajari pola dan representasi dari sejumlah besar data pelatihan, kemudian menggunakan pengetahuan tersebut untuk menghasilkan output yang menyerupai data pelatihan. Model mengambil data atau teks yang Anda input dan memberikan output berupa "tebakan" tentang apa yang seharusnya menjadi kata atau token berikutnya berdasarkan apa yang telah dipelajari.

#### 1.2 Foundation Models

Generative AI menggunakan **foundation models** yang telah dilatih dengan jumlah data yang sangat besar. Model-model ini:
- Mencari pola statistik dalam berbagai modalitas (bahasa alami, gambar, dll)
- Merupakan model neural network yang sangat besar dan kompleks dengan miliaran parameter
- Memiliki miliaran parameter yang dipelajari selama fase pelatihan (pre-training)
- Ukuran model meningkat dengan menambah jumlah parameter yang dapat dilatih
- Semakin banyak parameter, semakin banyak memori yang dimiliki model, sehingga dapat melakukan tugas yang lebih canggih

**Penggunaan Foundation Models:**
- Dapat digunakan langsung (as-is) tanpa modifikasi
- Dapat disesuaikan dengan teknik fine-tuning untuk use case spesifik
- Tersedia pre-trained foundation models seperti di Amazon SageMaker JumpStart

**Komponen Pembentuk Model:**
Model dibangun dengan kombinasi:
1. **Neural Networks**: Arsitektur jaringan saraf
2. **System Resources**: Sumber daya komputasi
3. **Data**: Data pelatihan
4. **Prompts**: Instruksi input

### 2. Transformer Architecture - Inti Generative AI Modern

#### 2.1 Transformer Network

**Transformer** adalah elemen inti dari generative AI modern, diperkenalkan dalam paper "Attention Is All You Need" (2017). Transformer merupakan inovasi yang memungkinkan perkembangan pesat generative AI saat ini.

**Karakteristik Transformer:**
- Digunakan oleh LLM seperti ChatGPT yang dibangun di atas arsitektur transformer
- Di-pre-train dengan jumlah data teks yang sangat besar dari internet
- Membangun basis pengetahuan yang luas melalui proses pre-training
- Dapat di-fine-tune untuk tugas spesifik dengan data tambahan yang relatif sedikit

**Keunggulan Transformer:**
- Dapat memproses instruksi bahasa alami dan melakukan tugas seperti yang dilakukan manusia
- Sangat scalable (dapat diperbesar) dengan arsitektur yang highly scalable
- Memungkinkan akses ke jumlah data pelatihan yang sangat besar
- Mendukung pengembangan sumber daya komputasi yang lebih powerful

#### 2.2 Struktur Arsitektur Transformer

**Komponen Utama:**
- **Encoder**: Memproses input dan menghasilkan embedding atau representasi vektor untuk setiap token
- **Decoder**: Menghasilkan output berdasarkan representasi dari encoder
- Setiap layer terdiri dari dua sublayers
- Menggunakan residual connections dan layer normalization

**Fungsi Arsitektur:**
- Memfasilitasi training dan mencegah overfitting
- Menangkap urutan sequence tanpa operasi recurrent atau convolutional
- Menggunakan positional encoding scheme yang mengkodekan posisi setiap token dalam input sequence
- Membantu model menangkap urutan sequence tanpa memerlukan operasi recurrent atau convolutional

**Proses Inference:**
Selama model inference, transformer:
- Menggunakan self-attention untuk menghitung representasi dari input sequences
- Menangkap long-term dependencies dan contextual relationships
- Melakukan komputasi paralel untuk efisiensi
- Menghasilkan completion untuk input prompt

> **Catatan untuk Ujian:** Anda tidak perlu memahami detail low-level dari arsitektur transformer, tetapi penting untuk memahami bahwa implementasi kompleks terjadi di balik layar.

### 3. Konsep Fundamental Generative AI

#### 3.1 Terminologi Kunci untuk Ujian

**Konsep yang Harus Dipahami untuk AWS AI Practitioner Exam:**
- **Prompt**: Input yang diberikan ke model, digunakan untuk LLM dan modalitas lain seperti gambar, video
- **Inference**: Proses model menghasilkan output atau completion
- **Completion**: Output yang dihasilkan model sebagai respons terhadap prompt
- **Context Window**: Jendela konteks untuk memproses input, tempat menyediakan contoh atau data tambahan
- **Tokens**: Unit terkecil dari teks yang diproses model, bisa berupa words, phrases, sentences, atau unit lainnya
- **Vocabulary**: Kosakata yang dipahami LLM, setiap input ID mewakili token dalam vocabulary model
- **Tokenizer**: Alat untuk mengubah teks manusia menjadi vektor yang berisi token IDs atau input IDs
- **Prompt Engineering**: Teknik merancang prompt yang efektif untuk mendapatkan completion yang lebih baik

#### 3.2 Dasar Matematika dan Komputasi

Model AI bergantung pada:
- **Statistik dan Aljabar Linear**
- **Probability Modeling**: Pemodelan probabilitas
- **Loss Function**: Fungsi kerugian
- **Matrix Multiplication**: Perkalian matriks

**Alasan Fundamental:** Machine learning lebih suka bekerja dengan angka, bukan teks, gambar, atau video mentah. Sebagian besar ML models, AI models, dan generative AI models mengandalkan statistik dan aljabar linear untuk komputasi mereka, termasuk probability modeling, loss function, dan matrix multiplication yang digunakan dalam operasi deep learning.

### 4. Prompt Engineering dan In-Context Learning

#### 4.1 Prompt Engineering

**Definisi:** Strategi untuk membuat model menghasilkan completion yang lebih baik dengan menyertakan contoh tugas yang ingin dilakukan model. Anda mungkin menghadapi situasi di mana model tidak menghasilkan outcome yang Anda inginkan pada percobaan pertama, dan Anda dapat menggunakan prompt engineering untuk memahami dan menerapkan generative models pada tugas dan use case Anda.

**Strategi Utama:**
- Menyertakan contoh di dalam prompt untuk menunjukkan tugas yang diinginkan
- Memberikan instruksi yang jelas dan spesifik
- Iterasi dan penyempurnaan prompt berdasarkan hasil
- Menggunakan examples yang dapat dimasukkan ke dalam prompt

#### 4.2 In-Context Learning

**Definisi:** Menyediakan contoh atau data tambahan di dalam context window untuk membantu LLM memahami tugas yang diminta. Dengan in-context learning, Anda dapat membantu LLM belajar lebih banyak tentang tugas yang diminta dengan menyertakan contoh atau data tambahan dalam prompt.

**Jenis-jenis In-Context Learning:**
1. **Zero-shot Inference**: Tanpa contoh, hanya instruksi
2. **One-shot Inference**: Satu contoh diberikan dalam prompt
3. **Few-shot Inference**: Beberapa contoh diberikan dalam prompt

**Komponen Prompt:**
- **Instruction**: Instruksi atau perintah
- **Content**: Konten atau materi
- **In-context Learning**: Contoh-contoh untuk pembelajaran (few-shot, zero-shot, one-shot)

#### 4.3 Inference Configuration

**Parameter Konfigurasi Inference** mempengaruhi completion model terhadap prompt. Parameter ini mengontrol bagaimana model menghasilkan output dan dapat disesuaikan untuk mendapatkan hasil yang diinginkan.

**Proses Inference:**
- Input yang Anda kirim ke generative model disebut **prompt**
- Prompt diteruskan ke model selama **inference time** untuk menghasilkan output atau completion
- Text prompt digunakan untuk LLM dan modalitas lain seperti gambar, video, dan lainnya

### 5. Tokenizer dan Vector Representations

#### 5.1 Tokenizer

**Fungsi:** Setiap model generative AI berbasis bahasa memiliki tokenizer yang mengubah teks manusia menjadi vektor yang berisi token IDs atau input IDs.

**Proses Tokenization:**
1. Teks input → Tokenizer → Token IDs
2. Setiap input ID mewakili token dalam vocabulary model
3. Model menggunakan tokenizer untuk mengonversi input text menjadi vektor

#### 5.2 Vector (Vektor)

**Definisi:** Daftar angka yang terurut yang mewakili fitur atau atribut dari suatu entitas atau konsep.

**Dalam Konteks Generative AI:**
- Vektor dapat mewakili kata, frasa, kalimat, atau unit lainnya
- Mengkodekan hubungan antara item dan menangkap asosiasi, analogi, dan hierarki yang bermakna
- Kekuatan representasi vektor terletak pada kemampuan untuk mengkodekan hubungan terkait antara item

**Contoh Hubungan Vektor:**
Perbedaan vektor antara "manatee" dan "dugong" mungkin mirip dengan perbedaan antara "great hammerhead shark" dan "hammerhead shark".

**Analogi Praktis:** Vektor seperti spreadsheet Excel - daftar angka menunjukkan lokasi spesifik dalam ruang tertentu (vector database), sama seperti nomor kolom dan baris menunjukkan sel tertentu dalam spreadsheet.

#### 5.3 Embeddings

**Definisi:** Representasi vektor numerik dari entitas apa pun yang menangkap makna semantik dari token (teks, gambar, video, atau audio). Embeddings juga disebut "embedding vectors".

**Karakteristik Embeddings:**
- Mengkodekan makna dan konteks token dalam kumpulan teks yang besar
- Memungkinkan model merepresentasikan dan memahami bahasa manusia secara statistik
- Token yang lebih dekat dalam ruang vektor memiliki makna semantik yang lebih mirip
- Model dapat menghasilkan teks berdasarkan hubungan antara vektor-vektor ini

**Proses Embedding:**
1. Tokenizer mengubah input text menjadi vektor
2. **Embedding vector** adalah set input IDs yang diperlukan untuk mendapatkan representasi dimensi tinggi dari setiap token
3. Embeddings diteruskan ke **self-attention layers** yang merupakan komponen kunci lain dari transformer

### 6. Self-Attention Mechanism - Inovasi Kunci Transformer

#### 6.1 Inovasi Self-Attention

**Self-Attention** adalah mekanisme kunci dalam transformer yang membantu model menimbang pentingnya bagian-bagian berbeda dari input saat menghasilkan setiap output token. Ini merupakan inovasi utama dari transformer yang membedakannya dari arsitektur sebelumnya.

**Keunggulan Self-Attention:**
- Menangkap **long-range dependencies** (dependensi jarak jauh)
- Memahami hubungan kontekstual yang sulit dipelajari dengan arsitektur sebelumnya
- Lebih baik dari arsitektur sebelumnya seperti **Recurrent Neural Networks (RNNs)**
- Memungkinkan komputasi paralel yang lebih efisien

#### 6.2 Cara Kerja Self-Attention

**Proses Self-Attention:**
1. Menghitung set vektor **query**, **key**, dan **value** untuk setiap input token
2. Menggunakan **dot products** antara vektor-vektor ini untuk menentukan attention weights
3. Output untuk setiap token adalah **weighted sum** dari value vectors, di mana weights berasal dari attention scores
4. Proses diulang dalam **multiple layers** sehingga model dapat membangun representasi kompleks dari input

**Hasil:**
- Model dapat menangkap long-term dependencies dan contextual relationships
- Memungkinkan model memahami hubungan antar kata dalam kalimat yang panjang

#### 6.3 Position Embeddings

**Fungsi:** Transformer juga memperkenalkan konsep **position embeddings** yang mengkodekan posisi relatif dari setiap token dalam sequence.

**Manfaat Position Embeddings:**
- Membantu model membedakan token identik yang muncul di posisi berbeda
- Penting untuk memahami struktur kalimat dan urutan kata
- Memungkinkan model menangkap urutan sequence tanpa memerlukan operasi recurrent atau convolutional

**Implementasi:**
- Menggunakan positional encoding scheme yang mengkodekan posisi setiap token dalam input sequence
- Membantu model memahami struktur dan urutan dalam bahasa

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
Para peneliti menemukan bahwa semakin besar model, semakin besar kemungkinan model tersebut bekerja tanpa additional in-context learning atau further training. Karena kemampuan model meningkat seiring dengan ukuran, hal ini mendukung pengembangan model yang semakin besar.

**Faktor Pendukung Pertumbuhan Model:**
1. **Arsitektur transformer yang highly scalable**
2. **Akses ke jumlah data pelatihan yang sangat besar (enormous amounts of data)**
3. **Pengembangan sumber daya komputasi yang lebih powerful**

#### 8.2 Tantangan dan Keterbatasan

**Pertanyaan Kritis:**
- Apakah kita bisa terus menambah parameter untuk meningkatkan performa dan membuat model lebih pintar?
- **Jawaban:** Melatih model besar sangat sulit dan mahal
- Mungkin sulit untuk terus melatih model yang semakin besar secara berkelanjutan

**Pertanyaan Menarik:**
- Ke mana arah pertumbuhan model ini akan mengarah?
- Bagaimana mengatasi kompleksitas dan biaya yang terus meningkat?

**Implikasi:**
- Perlu keseimbangan antara ukuran model dan efisiensi
- Pentingnya optimasi arsitektur dan teknik training
- Pertimbangan biaya komputasi dan sumber daya

### 9. Pre-training Process - Fondasi Pembelajaran Model

#### 9.1 Pembelajaran Statistik Bahasa

**LLM mengkodekan representasi statistik mendalam dari bahasa:**
- Pemahaman dikembangkan selama **fase pre-training** ketika model belajar dari jumlah data tidak terstruktur yang sangat besar
- Model belajar dari data yang bisa mencapai **gigabytes, terabytes, bahkan petabytes** teks
- Data diambil dari berbagai sumber termasuk internet dan teks besar yang telah dirakit khusus untuk melatih language models

#### 9.2 Self-Supervised Learning

**Proses Self-Supervised Learning:**
1. Model **menginternalisasi pola dan struktur dalam bahasa** melalui pembelajaran mandiri
2. Pola-pola ini membantu model menyelesaikan **training objective**
3. Training objective tergantung pada arsitektur model yang digunakan
4. **Model weights** diperbarui untuk meminimalkan loss dari training objective

**Karakteristik:**
- Tidak memerlukan data berlabel secara eksplisit
- Model belajar dari struktur inherent dalam data
- Memungkinkan pembelajaran dari dataset yang sangat besar

#### 9.3 Encoder dan Embeddings

**Fungsi Encoder:**
- Menghasilkan **embedding atau representasi vektor** untuk setiap token
- Memproses input menjadi format yang dapat dipahami dan diproses model
- Mengubah teks mentah menjadi representasi numerik

**Kebutuhan Komputasi:**
- Pre-training memerlukan **komputasi yang sangat besar**
- Menggunakan **Graphics Processing Units (GPUs)** untuk pemrosesan paralel
- Memerlukan infrastruktur komputasi yang powerful dan mahal

#### 9.4 Data Quality Curation - Proses Kritis

**Proses Kurasi Data:**
- Data dari situs publik seperti internet perlu diproses dengan hati-hati
- **Tujuan kurasi:** meningkatkan kualitas, mengatasi bias, menghapus konten berbahaya
- Proses filtering dan cleaning yang ekstensif

**Statistik Penting:**
- **Estimasi:** Hanya **1-3% token** yang digunakan untuk pre-training setelah kurasi kualitas data
- Estimasi ini penting untuk menentukan berapa banyak data yang perlu dikumpulkan untuk pre-training model
- Menunjukkan pentingnya kualitas data dibandingkan kuantitas semata

**Implikasi:**
- Kurasi data adalah langkah kritis yang mempengaruhi kualitas model
- Proses yang sangat selektif dalam memilih data training
- Pentingnya perencanaan data collection yang matang

### 10. Unimodal vs Multimodal - Evolusi Kemampuan Model

#### 10.1 Unimodal Generative AI

**Definisi:** Model yang bekerja dengan satu modalitas data.

**Karakteristik Unimodal:**
- **LLMs**: Input dan output berupa teks, merupakan contoh unimodal generative AI
- Hanya memproses satu jenis data secara spesifik
- Fokus pada satu domain data tertentu

#### 10.2 Multimodal Generative AI

**Definisi:** Multimodal adalah menambahkan modalitas lain seperti image, video, atau audio. Model multimodal dapat memahami berbagai sumber data yang beragam dan memberikan prediksi yang lebih robust.

**Modalitas yang Didukung:**
- **Text** (teks)
- **Image** (gambar)
- **Video**
- **Audio**

**Keunggulan Multimodal:**
- Pemahaman data yang lebih beragam dan komprehensif
- Prediksi yang lebih robust dan akurat
- **Cross-model reasoning, translation, search, dan creation** yang lebih mirip dengan kecerdasan manusia
- Kemampuan kolaboratif yang menambah reasoning lintas model

**Use Cases Multimodal:**
- **Marketing** dan advertising
- **Image captioning** (membuat caption gambar)
- **Product design** dan development
- **Customer service** yang lebih interaktif
- **Chatbots** dengan kemampuan multimedia
- **Avatars** dan virtual assistants

#### 10.3 Kemampuan Multimodal

**Model multimodal dapat memproses dan menghasilkan berbagai jenis data, tetapi juga dapat melakukan operasi ini dalam kombinasi satu sama lain.** Kemampuan kolaboratif ini menambahkan cross-model reasoning, translation, search, dan creation yang lebih mirip dengan kecerdasan manusia.

### 11. Multimodal Tasks dan Diffusion Models

#### 11.1 Contoh Tugas Multimodal

**1. Image Captioning**
- Model menghasilkan deskripsi teks dari gambar
- Menggabungkan pemahaman visual dan kemampuan bahasa

**2. Visual Question Answering**
- Model menjawab pertanyaan tentang konten gambar
- Memerlukan pemahaman visual dan reasoning

**3. Text-to-Image Synthesis**
- Menghasilkan gambar dari deskripsi tekstual
- **Contoh Model:** DALL-E, Stable Diffusion, Midjourney
- Dapat membuat gambar realistis dan beragam dari natural language prompts

#### 11.2 Diffusion Models - Kelas Model Generative Canggih

**Definisi:** Diffusion models adalah kelas model generative yang belajar membalikkan proses noising bertahap (gradual noising process).

**Fungsi Utama:**
- Mendukung berbagai tugas untuk model multimodal
- **Image generation** (pembuatan gambar)
- **Upscaling** (meningkatkan resolusi)
- **Inpainting** (mengisi bagian gambar yang hilang)

**Cara Kerja Diffusion Models:**
1. **Mulai dengan random noise**
2. **Iteratif melakukan de-noise** untuk menghasilkan output yang koheren seperti high-quality image atau audio clip
3. Model **memprediksi noise** yang ditambahkan di setiap langkah
4. **Dikondisikan pada output** yang sebagian di-denoise dari langkah sebelumnya

#### 11.3 Tiga Komponen Utama Diffusion Models

**Untuk Ujian AWS AI Practitioner, Pahami:**
1. **Forward Diffusion**: Proses menambahkan noise secara bertahap
2. **Reverse Diffusion**: Proses menghilangkan noise secara iteratif
3. **Stable Diffusion**: Implementasi khusus yang efisien

#### 11.4 Stable Diffusion - Implementasi Efisien

**Perbedaan dengan Model Lain:**
- **Tidak menggunakan pixel space** dari gambar
- Menggunakan **reduced definition latent space** untuk efisiensi
- Menggunakan **Gaussian noise** untuk encode gambar
- Menggunakan **noise predictor** dengan reverse diffusion process untuk recreate gambar

**Kemudahan Penggunaan:**
- Dapat dengan mudah menghasilkan gambar dari teks
- **Tersedia melalui Amazon SageMaker JumpStart**
- Dapat di-fine-tune dan di-deploy dengan beberapa baris kode

#### 11.5 Keunggulan Diffusion Models

**Dibandingkan dengan Generative Adversarial Networks (GANs) dan Variational Autoencoders (VAEs):**
- **Menghasilkan output berkualitas lebih tinggi**
- **Lebih beragam dan konsisten** dalam hasil
- **Lebih stabil dan mudah dilatih**
- Memberikan kontrol yang lebih baik terhadap kualitas dan keragaman gambar

**Contoh Diffusion Models:**
- **Stable Diffusion**: Image generation
- **Whisper**: Speech recognition dan translation
- **AudioLM**: Audio generation

#### 11.6 AWS Support untuk Diffusion Models

**AWS menyediakan berbagai layanan dan tools untuk membangun dan men-deploy multimodal dan diffusion models:**
- **Amazon SageMaker** mendukung deep learning frameworks seperti TensorFlow dan PyTorch dengan modul pre-built untuk bekerja dengan data multimodal
- **Pre-trained models** seperti Stable Diffusion tersedia dan dapat di-fine-tune serta di-deploy dengan mudah

### 12. AWS Services untuk Multimodal dan Diffusion Models

**Amazon SageMaker:**
- Mendukung deep learning frameworks (TensorFlow, PyTorch)
- Memiliki modul pre-built untuk bekerja dengan data multimodal

**Pre-trained Models:**
- Stable Diffusion tersedia
- Dapat di-fine-tune dan di-deploy dengan beberapa baris kode

**Layanan AWS Lainnya:**
- Menyediakan berbagai tools untuk membangun dan men-deploy model multimodal dan diffusion

### 13. Use Cases Generative AI - Aplikasi Praktis

#### 13.1 Text Generation

**Large Language Models (LLMs) adalah jenis generative AI yang dapat diterapkan pada berbagai domain masalah atau tugas tanpa perlu di-fine-tune.**

**Kemampuan Text Generation:**
- Menulis atau menulis ulang teks untuk berbagai audiens
- Mengadaptasi dokumen teknis menjadi bahasa yang lebih sederhana dan mudah dipahami

**Contoh Praktis:**
- Mengubah dokumen teknis tentang **design dan specifications untuk scuba diving buoyancy device**
- Menggunakan istilah yang lebih sederhana untuk orang yang baru memulai **sertifikasi scuba diving**
- Adaptasi konten untuk berbagai tingkat keahlian pembaca

#### 13.2 Text Summarization

**Kemampuan:**
- Mengambil informasi yang relatif panjang dan menghasilkan output singkat
- Mempertahankan ide utama dan informasi penting

**Contoh Aplikasi:**
- Meringkas **dokumentasi teknis**
- **Laporan keuangan**
- **Dokumen legal**
- **Artikel berita**
- Berbagai jenis dokumen panjang lainnya

#### 13.3 AWS Services untuk Content Creation

**Amazon Bedrock dan Amazon Titan:**
- Pre-trained models untuk **text, image, audio generation**
- Dapat di-fine-tune untuk use case spesifik
- Managed service untuk generative AI applications

**Amazon SageMaker:**
- Mendukung **code generation dan completion**
- Platform ML yang komprehensif

**Amazon Q Developer (formerly Amazon CodeWhisperer):**
- **Code generation dan completion** real-time
- Menghasilkan saran kode dari snippets hingga fungsi lengkap

**Amazon Sumerian:**
- **Virtual production dan 3D content creation**
- Untuk aplikasi immersive

#### 13.4 Use Cases Lainnya

**Berbagai Aplikasi Generative AI:**
- **Information extraction** (ekstraksi informasi)
- **Question answering** (menjawab pertanyaan)
- **Classification** (klasifikasi)
- **Identifying harmful content** (identifikasi konten berbahaya)
- **Translation** (terjemahan)
- **Recommendation engines** (mesin rekomendasi)
- **Personalized marketing and ads** (marketing dan iklan personal)
- **Chatbots** dan conversational AI
- **Customer service agents**
- **Search** (pencarian) yang lebih intelligent

#### 13.5 Code Generation - Developer Tool

**Definisi:** Code generation adalah aplikasi generative AI untuk mempercepat pengembangan software.

**Kemampuan Code Generation:**
- Menghasilkan **functional code snippets** dan bahkan **entire programs** dari natural language descriptions atau examples
- Membantu mengotomasi **routine programming tasks**
- **Code completions** yang intelligent
- **Menerjemahkan kode** antar bahasa berbeda
- Mempercepat development workflow

**Amazon Q Developer:**
- Menghasilkan **real-time code suggestions**
- Range dari snippets hingga **full functions**
- Berdasarkan **comments dan existing code**
- Terintegrasi dengan development environment

**Keuntungan AWS:**
- **AWS menangani underlying infrastructure, data management, model training, dan inference**
- **Anda fokus pada use case dan aplikasi spesifik**
- Tidak perlu mengelola kompleksitas infrastruktur ML

### 14. Arsitektur Generative AI

**Untuk AWS AI Practitioner Exam, Pahami Berbagai Arsitektur:**

1. **Generative Adversarial Networks (GANs)**
2. **Variational Autoencoders (VAEs)**  
3. **Transformers**

**Prinsip Penting:**
- **Setiap arsitektur memiliki keunggulan dan keterbatasan unik**
- **Evaluasi objektif dan dataset** sebelum memilih arsitektur yang sesuai untuk use case spesifik
- Pemahaman karakteristik masing-masing arsitektur penting untuk pemilihan yang tepat

**Pertimbangan Pemilihan:**
- Jenis data yang akan diproses
- Kualitas output yang diinginkan
- Kompleksitas training dan deployment
- Sumber daya komputasi yang tersedia

### 15. Generative AI Project Lifecycle

#### 15.1 Framework Lifecycle

**Framework ini memetakan tugas-tugas yang diperlukan untuk membawa proyek Anda dari konsepsi hingga peluncuran:**

1. **Identify Use Case** (Identifikasi Use Case)
2. **Experiment and Select** (Eksperimen dan Pilih)
3. **Adapt, Align, and Augment** (Adaptasi, Selaraskan, dan Augmentasi)
4. **Evaluate** (Evaluasi)
5. **Deploy and Iterate** (Deploy dan Iterasi)
6. **Monitor** (Monitor)

#### 15.2 Stage 1: Define and Develop

**Tahap Pertama - Define Objectives:**
- **Definisikan objektif** dengan jelas
- **Kumpulkan data** yang relevan
- **Proses data** untuk kualitas
- **Pilih model** yang sesuai
- **Latih dan kembangkan model**

**Tahap Kedua - Develop Model:**
- **Feature engineering**
- **Building** (membangun)
- **Testing** (menguji)
- **Validating** (validasi)
- **Optimizing** (optimasi)
- **Scaling** (penskalaan)

**Tahap Ketiga - Deploy and Maintain:**
- **Model evaluation**
- **Deployment**
- **Feedback**
- **Updates**
- **Security**
- **Scalability**

#### 15.3 Foundation Model Lifecycle (AWS Exam Guide)

**Tahapan Menurut AWS Exam Guide:**
1. **Data Selection** (Pemilihan Data)
2. **Model Selection** (Pemilihan Model)
3. **Pre-training** (Pra-pelatihan)
4. **Fine-tuning** (Penyesuaian)
5. **Evaluation** (Evaluasi)
6. **Deployment** (Penerapan)
7. **Feedback** (Umpan Balik)

#### 15.4 Langkah Paling Penting: Define Scope

**Mendefinisikan Scope:**
- **Langkah paling penting dalam proyek apa pun**
- Definisikan scope **seakurat dan sesempit mungkin**
- Pikirkan **fungsi LLM dalam aplikasi spesifik Anda**

**Pertanyaan Kunci untuk Scoping:**
- Apakah Anda perlu model yang dapat melakukan **banyak tugas berbeda**, termasuk long-form text generation?
- Apakah tugas **lebih spesifik** seperti **named entity recognition**, sehingga model hanya perlu bagus di satu hal?
- Apa fungsi spesifik yang dibutuhkan dalam aplikasi Anda?

**Manfaat Scoping yang Baik:**
- **Menghemat waktu** development
- **Menghemat biaya komputasi** yang signifikan
- Fokus pada kebutuhan yang benar-benar penting

#### 15.5 Keputusan Awal: Train vs Existing Model

**Pilihan Fundamental:**
1. **Melatih model sendiri dari awal** (train from scratch)
2. **Bekerja dengan existing base model**

**Pertimbangan Keputusan:**
- Kebutuhan spesifik aplikasi
- Sumber daya yang tersedia
- Waktu pengembangan
- Biaya dan kompleksitas

**Rekomendasi:**
Segera setelah Anda puas dan telah **scoped model requirements** cukup untuk memulai development, Anda siap untuk memulai. Keputusan pertama adalah apakah akan melatih model sendiri dari scratch atau bekerja dengan existing base model.

### 16. Model Performance dan Training

#### 16.1 Assess Performance

**Langkah Setelah Pemilihan Model:**
- **Menilai performa model** terhadap kebutuhan aplikasi
- **Menyelesaikan training tambahan** jika diperlukan untuk aplikasi Anda

#### 16.2 Prompt Engineering sebagai Langkah Awal

**Strategi Awal:**
- **Mulai dengan prompt engineering** - ini sering kali dapat membuat model perform dengan baik
- Menggunakan **in-context learning** dengan contoh yang sesuai dengan tugas dan use case
- Mencoba **one-shot atau few-shot inferences**
- Evaluasi hasil sebelum melanjutkan ke teknik yang lebih kompleks

#### 16.3 Fine-tuning

**Kapan Menggunakan Fine-tuning:**
- Jika model **tidak perform sebaik yang Anda butuhkan** bahkan dengan one- atau few-shot inference
- Ketika prompt engineering tidak memberikan hasil yang diinginkan

**Proses Fine-tuning:**
- Merupakan **supervised learning process**
- Melatih model dengan data spesifik untuk tugas tertentu
- Menyesuaikan model untuk use case spesifik

#### 16.4 Reinforcement Learning from Human Feedback (RLHF)

**Tujuan RLHF:**
- Memastikan model **berperilaku baik** dalam deployment
- **Selaras dengan preferensi manusia** dalam penggunaan praktis

**Pentingnya RLHF:**
- Seiring model menjadi **lebih capable**, semakin penting untuk memastikan mereka berperilaku dengan baik
- Teknik fine-tuning tambahan untuk alignment
- Membantu memastikan model berperilaku sesuai ekspektasi

#### 16.5 Evaluation - Aspek Kritis

**Aspek Penting Evaluation:**
- Menggunakan **berbagai metrik dan benchmark**
- Menentukan **seberapa baik model perform**
- Menentukan **seberapa baik model selaras** dengan preferensi Anda

**Sifat Iteratif Development:**
- Tahap development dengan **adapting dan aligning sangat iteratif**
- **Mulai dengan prompt engineering** dan evaluasi outputs
- **Gunakan fine-tuning** untuk meningkatkan performa
- **Selalu revisit dan evaluasi prompt engineering** untuk mendapatkan performa yang dibutuhkan

**Workflow yang Disarankan:**
1. Mulai dengan prompt engineering
2. Evaluasi hasil
3. Jika perlu, lakukan fine-tuning
4. Kembali evaluasi prompt engineering
5. Ulangi hingga mendapat performa yang diinginkan

### 17. Deployment dan Infrastructure

#### 17.1 Deployment

**Ketika Model Siap untuk Deployment:**
- Model **memenuhi kebutuhan performa** Anda
- Model **well-aligned** dengan tujuan aplikasi
- Siap untuk di-deploy ke production

**Proses Deployment:**
- **Deploy ke infrastruktur** Anda
- **Integrasi dengan aplikasi** yang ada
- **Optimasi model untuk deployment** dan compute resources
- Memastikan **aplikasi memberikan pengalaman yang baik untuk users**

#### 17.2 Additional Infrastructure - Pertimbangan Kritis

**Pertimbangan Penting:**
- **Infrastruktur tambahan** yang diperlukan aplikasi untuk bekerja dengan baik
- **Keterbatasan fundamental dari LLMs** yang perlu diatasi

**Keterbatasan LLMs yang Sulit Diatasi Melalui Training Saja:**
1. **Hallucinations**: Menciptakan informasi ketika jawaban tidak diketahui (inventing information when the answer is unknown)
2. **Limited Ability**: Kemampuan terbatas dengan **complex reasoning dan mathematics**

**Solusi untuk Keterbatasan:**
- **Sulit diatasi hanya melalui training** alone
- Memerlukan **infrastruktur dan strategi tambahan**
- Perlu pendekatan arsitektur yang lebih komprehensif

**Langkah Terakhir yang Sangat Penting:**
Pertimbangkan **infrastruktur tambahan** apa pun yang akan diperlukan aplikasi Anda untuk bekerja. Ingat bahwa beberapa keterbatasan fundamental LLMs dapat sulit diatasi hanya melalui training.

### 18. Best Practices dan Rekomendasi

#### 18.1 Workflow yang Disarankan

**Urutan Langkah Optimal:**
1. **Definisikan scope** dengan jelas dan sempit
2. **Pilih antara train from scratch atau existing model**
3. **Mulai dengan prompt engineering** sebagai langkah pertama
4. **Evaluasi hasil** dari prompt engineering
5. **Jika perlu, lakukan fine-tuning** untuk meningkatkan performa
6. **Pertimbangkan RLHF** untuk alignment dengan preferensi manusia
7. **Evaluasi dengan metrik yang sesuai** dan benchmark
8. **Deploy dan monitor** performa dalam production
9. **Iterasi berdasarkan feedback** dan hasil monitoring

#### 18.2 Tips untuk AWS AI Practitioner Exam

**Konsep Fundamental yang Harus Dikuasai:**
- **Perbedaan antara AI tradisional dan generative AI**
- **Cara kerja transformer dan self-attention mechanism**
- **Tokenizer, embeddings, dan vectors** - bagaimana teks diubah menjadi representasi numerik
- **Unimodal vs multimodal** - perbedaan dan use cases
- **Diffusion models dan komponennya** (forward, reverse, stable diffusion)
- **Berbagai use cases generative AI** (text generation, summarization, code generation, dll)
- **Project lifecycle dan tahapannya** - dari scoping hingga deployment
- **Prompt engineering dan in-context learning** (zero-shot, one-shot, few-shot)
- **Fine-tuning dan RLHF** - kapan dan bagaimana menggunakannya
- **Keterbatasan LLMs** (hallucinations, complex reasoning)

**Arsitektur yang Perlu Dipahami:**
- **Transformers** - arsitektur inti generative AI modern
- **GANs (Generative Adversarial Networks)**
- **VAEs (Variational Autoencoders)**
- **Diffusion Models** - untuk image generation

**AWS Services yang Relevan untuk Exam:**
- **Amazon Bedrock** - managed service untuk foundation models
- **Amazon Titan** - foundation models dari Amazon
- **Amazon SageMaker** - platform ML komprehensif
- **Amazon Q Developer** - code generation dan completion
- **Amazon SageMaker JumpStart** - pre-trained models dan solutions

#### 18.3 Fokus Khusus untuk Domain 2 (24% Bobot Exam)

**Prioritas Tinggi:**
- **Foundation model concepts** dan cara kerjanya
- **Transformer architecture** dan self-attention
- **AWS generative AI services** dan use cases
- **Multimodal capabilities** dan diffusion models
- **Project lifecycle** dan best practices

---

## Ringkasan Poin Kunci untuk AWS AI Practitioner Exam

### Konsep Fundamental (Bobot Tinggi - 24%)
- **Generative AI** adalah subset deep learning yang membuat konten baru, bukan mengklasifikasi
- **Foundation models** dilatih dengan data sangat besar (gigabytes-petabytes) dan memiliki miliaran parameter
- **Transformer** adalah arsitektur inti dengan **self-attention mechanism** (paper "Attention Is All You Need")
- Model bekerja dengan mengubah teks menjadi **tokens → embeddings → vectors** untuk pemrosesan

### Proses dan Lifecycle
- **Pre-training** menggunakan data sangat besar, memerlukan GPU, hanya 1-3% token digunakan setelah kurasi
- **Fine-tuning** menyesuaikan model untuk tugas spesifik melalui supervised learning
- **RLHF** memastikan model selaras dengan preferensi manusia dalam deployment
- **Deployment** memerlukan optimasi dan infrastruktur tambahan untuk mengatasi keterbatasan LLM

### Modalitas dan Use Cases
- **Unimodal**: satu jenis data (LLM untuk teks)
- **Multimodal**: berbagai jenis data (teks, gambar, audio, video) dengan cross-model reasoning
- **Diffusion models** untuk image generation berkualitas tinggi (forward, reverse, stable diffusion)
- **Use cases**: text generation, summarization, code generation, chatbots, image captioning, dll

### AWS Services (Penting untuk Exam)
- **Amazon Bedrock** dan **Amazon Titan** untuk pre-trained foundation models
- **Amazon SageMaker** dan **SageMaker JumpStart** untuk training dan deployment
- **Amazon Q Developer** untuk code generation dan completion
- **Amazon Sumerian** untuk virtual production dan 3D content

### Best Practices dan Project Lifecycle
- **Define scope** dengan jelas dan sempit (langkah paling penting)
- **Mulai dengan prompt engineering** (zero-shot, one-shot, few-shot)
- **Evaluasi secara iteratif** dengan metrik dan benchmark yang sesuai
- **Pertimbangkan keterbatasan LLMs** (hallucinations, complex reasoning, mathematics)
- **Gunakan existing models** vs train from scratch berdasarkan kebutuhan

### Konsep Teknis Kunci
- **Self-attention**: menangkap long-range dependencies dan contextual relationships
- **Position embeddings**: mengkodekan posisi token dalam sequence
- **In-context learning**: menyediakan contoh dalam prompt untuk pembelajaran
- **Inference parameters**: mengontrol bagaimana model menghasilkan output
- **Data quality curation**: proses penting yang hanya menyisakan 1-3% token untuk training

---

**Catatan Penting:** Materi ini mencakup **Task Statement 2.1** dari **Domain 2** AWS Certified AI Practitioner dengan **bobot 24%**. Konsep-konsep ini merupakan fondasi untuk memahami generative AI dan aplikasinya di AWS. Fokus pada pemahaman mendalam karena domain ini memiliki bobot tertinggi kedua dalam ujian.
