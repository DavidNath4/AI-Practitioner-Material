# Proses Training dan Fine-Tuning Foundation Models

## Pengantar

Dalam pengembangan aplikasi AI menggunakan foundation models (FM), memahami proses training dan fine-tuning sangat penting. Task Statement 3.3 dari AWS Certified AI Practitioner membahas secara mendalam bagaimana foundation models dilatih, disesuaikan, dan dioptimalkan untuk kebutuhan spesifik organisasi Anda.

*Referensi: Material Transcript 3-3 - Training dan Fine-tuning Foundation Models*

## Elemen Kunci dalam Training Foundation Model

Berdasarkan material transcript AWS, ada tiga elemen utama dalam proses training foundation model:

1. **Pre-training** (Pelatihan Awal)
2. **Fine-tuning** (Penyesuaian Model)  
3. **Continuous Pre-training** (Pelatihan Berkelanjutan)

---

## 1. Pre-training: Fondasi Pembelajaran Model

### Apa itu Pre-training?

Pre-training adalah proses kompleks di mana **generative AI models belajar kemampuan dasarnya**. Ini adalah tahap pertama dan paling fundamental dalam pengembangan foundation model.

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
- Model belajar dari **jutaan dokumen, video, gambar, file audio, dan berbagai sumber lainnya**
- Model mempelajari **fundamental bahasa manusia** dan pola-pola dasar

### Hasil Pre-training

Meskipun foundation models telah dilatih pada jutaan dokumen, video, gambar, file audio dan lainnya, serta telah mempelajari fundamental bahasa manusia, mereka mungkin masih memerlukan:
- **Additional training atau instructions** untuk domain dan dataset spesifik Anda
- **Pembelajaran untuk melakukan human tasks dan reasoning**
- Penyesuaian untuk terminologi industri atau jargon teknis tertentu

---

## 2. Fine-tuning: Menyesuaikan Model untuk Kebutuhan Spesifik

### Perbedaan Pre-training vs Fine-tuning

**Pre-training:**
- Menggunakan **self-supervised learning**
- Melatih LLM dengan **huge amounts of unstructured data**
- Model belajar kemampuan dasar dan fundamental bahasa

**Fine-tuning:**
- Adalah proses **supervised learning**
- Menggunakan **dataset of labeled examples** untuk memperbarui weights LLM
- **Memperluas training model** untuk meningkatkan generation completions untuk tugas spesifik

### Definisi Fine-tuning

Fine-tuning adalah proses yang **extends the training of the model** untuk meningkatkan kemampuan menghasilkan output yang lebih baik untuk tugas spesifik. Ini adalah proses **supervised learning** yang menggunakan dataset berlabel untuk memperbarui bobot (weights) LLM.

### Tujuan Fine-tuning

- **Mengadaptasi foundation models ke custom datasets dan use cases Anda**
- Meningkatkan performa untuk use case spesifik
- Membuat model lebih relevan dengan kebutuhan bisnis Anda

### Instruction-based Fine-tuning

**Instruction-based fine-tuning** menggunakan **labeled examples untuk performance improvements pada specific tasks**. 

**Pertimbangan Penting:**
- **LLMs dapat melakukan many different tasks dalam single model**
- Namun, jika aplikasi Anda perlu melakukan single task, Anda dapat fine-tune pre-trained model untuk improve performance untuk tasks specific ke use cases Anda
- Fine-tuning membantu mengoptimalkan performa untuk tugas tertentu

---

## 3. Jenis-jenis Fine-tuning

### A. Full Fine-tuning

**Definisi:** **Every parameter dalam model diperbarui melalui supervised learning**.

**Karakteristik:**
- Memperbarui semua bobot model
- Memerlukan sumber daya komputasi yang besar
- Memberikan hasil yang sangat disesuaikan

**Komponen Memory yang Dibutuhkan:**
Ketika Anda train dan tune foundation model, Anda load:
- **Model parameters**
- **Optimizer** memory
- **Gradients**
- **Forward activations**
- **Temporal memory**

**Dampak Resource:**
- Komponen-komponen ini dapat **add additional bytes of GPU memory untuk setiap model parameter**
- Juga dapat **increase compute costs dari fine-tuning process**

### B. Parameter-Efficient Fine-Tuning (PEFT)

**Definisi:** **Parameter-efficient fine-tuning (PEFT)** adalah **process dan set of techniques yang freeze atau preserve parameters dan weights dari original LLM** dan **fine-tune atau train small number dari task-specific adaptor layers dan parameters**.

**Keuntungan PEFT:**
- **PEFT reduces compute dan memory yang dibutuhkan** karena fine-tuning small set dari model parameters
- Lebih efisien biaya
- Tetap mempertahankan kemampuan dasar model original
- Hanya melatih subset kecil dari parameter model

**Low-Rank Adaptation (LoRA):**
- **LoRA adalah popular PEFT technique**
- **Preserves atau freezes original weights dari foundation model**
- **Creates new trainable low-rank matrices ke setiap layer dari transformer architecture**
- **PEFT dan LoRA modify weights dari model Anda, tetapi tidak modify representations**

### C. Representation Fine-Tuning (ReFT)

**Definisi:** **Representation fine-tuning (ReFT)** adalah **fine-tuning process yang freezes base model dan learns task-specific interventions pada hidden representations**.

**Konsep Dasar:**
- **Representations encode semantic information similar ke embeddings**
- **Linear Representation Hypothesis:** **Concepts are encoded dalam linear subspaces of representation dalam neural network**
- Fokus pada memodifikasi representasi, bukan bobot
- Berbeda dengan PEFT/LoRA yang modify weights, ReFT fokus pada representations

### D. Multitask Fine-tuning

**Definisi:** **Multitask fine-tuning adalah extension dari fine-tuning single task**. Multitask fine-tuning untuk melatih model menyelesaikan banyak tugas secara bersamaan.

**Karakteristik:**
- **Multitask fine-tuning requires lot of data**
- **Training dataset has examples of inputs dan outputs untuk multiple tasks**
- Menghasilkan **instruction-tuned model** yang telah learned how to complete many different tasks simultaneously

**Contoh Tugas yang Dapat Dipelajari Bersamaan:**
- **Reviews atau ratings** produk
- **Summarization** (peringkasan)
- **Translating code** (menerjemahkan kode)
- Dan tugas-tugas lainnya

**Keuntungan:**
- **Calculate losses dari examples untuk update weights dari model**
- **Helps mitigate dan avoid catastrophic forgetting**
- Model dapat menyelesaikan banyak tugas berbeda secara simultan

---

## 4. Tantangan dalam Fine-tuning

### Catastrophic Forgetting

**Definisi:** **Catastrophic forgetting happens ketika whole fine-tuning process modifies weights dari original LLM**. Ini dapat **improve performance dari single task fine-tuning, tetapi can degrade performance pada other tasks**.

**Kapan Terjadi:**
- **Possible limitation dari fine-tuning pada single task**
- Ketika seluruh proses fine-tuning memodifikasi bobot model original

**Pertimbangan Penting:**
- **Decide whether catastrophic forgetting akan impact use case Anda**
- **Jika Anda need reliable performance pada single task, maka Anda might not be concerned bahwa model can't generalize ke other tasks**
- **Multitask fine-tuning dapat membantu mitigate dan avoid catastrophic forgetting**

---

## 5. Fine-tuning Khusus

### A. Domain Adaptation Fine-tuning

**Definisi:** **Domain adaptation fine-tuning gives you ability untuk use pre-trained foundation models dan adapt them ke specific tasks dengan using limited domain-specific data**.

**Kegunaan:**
- **Help model Anda work dengan domain-specific language** seperti:
  - **Industry jargon** (jargon industri)
  - **Technical terms** (istilah teknis)
  - **Specialized data** lainnya

**Implementasi di AWS:**
- **Amazon SageMaker JumpStart provides capability untuk fine-tune large language model**
- **Particularly text generation model pada domain-specific dataset**
- **Fine-tune models dengan custom dataset untuk improve performance dalam specific domains**

### B. Reinforcement Learning from Human Feedback (RLHF)

**Definisi:** **RLHF uses reinforcement learning untuk fine-tune LLM dengan human feedback data untuk better align model dengan human preferences**.

**Tujuan:**
- **Improve performance dari model Anda**
- **Help it better understand human-like prompts untuk generate human-like responses**
- Menyelaraskan output model dengan preferensi dan nilai-nilai manusia

**Proses:**
- Menggunakan **reinforcement learning untuk fine-tune LLM dengan human feedback data**
- Model belajar menghasilkan output yang lebih disukai manusia
- **Better align model dengan human preferences**

---

## 6. Persiapan Data untuk Fine-tuning

### Langkah-langkah Persiapan Data

#### Langkah 1: Persiapan Training Data

**First step adalah prepare your training data:**
- **Many publicly available datasets dan prompt template libraries** telah digunakan untuk train large language models
- **Prompt template libraries include many templates untuk different tasks dan datasets**
- **After your instruction dataset is ready**, Anda dapat melanjutkan ke langkah berikutnya

#### Langkah 2: Pembagian Dataset

**Divide dataset menjadi training, validation, dan test splits:**
1. **Training split** - untuk melatih model
2. **Validation split** - untuk evaluasi selama proses
3. **Test split** - untuk evaluasi akhir

#### Langkah 3: Proses Fine-tuning

**During fine-tuning:**
1. **Select prompts dari training dataset Anda**
2. **Pass them ke LLM untuk generate completions**
3. **Compare distribution of completions dan training label**
4. **Calculate loss antara two token distributions**
5. **Use calculated loss untuk update model's weights**

#### Langkah 4: Evaluasi

- **After many batches of prompt-completion pairs, update weights** sehingga model's performance pada task improves
- **Define separate evaluation steps untuk measure LLM's performance** menggunakan **holdout validation dataset**
- **Get validation accuracy**

#### Langkah 5: Evaluasi Akhir

- **After you've completed fine-tuning, perform final performance evaluation** menggunakan **holdout test dataset**
- **This last result akan give you test accuracy**

---

## 7. AWS Tools untuk Data Preparation

**Dalam machine learning, data preparation adalah collecting, pre-processing, dan organizing raw data Anda untuk model Anda.** AWS menyediakan berbagai tools untuk persiapan data dalam proses fine-tuning:

### A. Amazon SageMaker Canvas
**Untuk:** **Low-code data preparation**

**Fitur:**
- **Create data flows yang define ML data pre-processing Anda**
- **Feature engineering workflows yang use little to no coding**
- Cocok untuk pengguna non-teknis

### B. Amazon SageMaker Studio Classic dengan Amazon EMR
**Untuk:** **Data preparation yang needs to scale**

**Fitur:**
- **Amazon SageMaker Studio Classic provides built-in integration dengan Amazon EMR**
- **Use open source frameworks** seperti:
  - **Apache Spark**
  - **Apache Hive**
  - **Presto**
- Dapat menangani data dalam skala besar

### C. AWS Glue Interactive Sessions
**Untuk:** **Serverless data preparation**

**Fitur:**
- **Apache Spark-based serverless engine dari AWS Glue Interactive Sessions**
- **Aggregate, transform, dan prepare data dari multiple sources dalam SageMaker Studio Classic**
- Tidak perlu mengelola infrastructure

### D. Jupyter Lab dalam SageMaker Studio
**Untuk:** **Data preparation menggunakan SQL**

**Fitur:**
- **Use Structured Query Language (SQL) dalam SageMaker Studio untuk data preparation**
- **Use Jupyter Lab**
- Familiar bagi data analysts dan engineers

### E. Amazon SageMaker Feature Store
**Untuk:** **Data preparation untuk feature discovery dan storage**

**Fitur:**
- **Use Amazon SageMaker Feature Store untuk search, discover, dan retrieve features untuk model training**
- **Provide centralized repository untuk store feature data dalam standardized format**
- Memudahkan reuse features across projects

### F. Amazon SageMaker Clarify
**Untuk:** **Data preparation yang needs to detect bias dalam data Anda**

**Fitur:**
- **Use Amazon SageMaker Clarify untuk analyze data Anda dan detect potential biases across multiple facets**
- **SageMaker Clarify dapat help detect whether training data contains imbalanced representations atau labeling biases between groups** seperti gender, race, atau age
- Membantu memastikan fairness dalam model

### G. Amazon SageMaker Ground Truth
**Untuk:** **Data yang needs to be labeled**

**Fitur:**
- **Use SageMaker Ground Truth untuk manage data labeling workflows untuk training datasets Anda**
- Mendukung human labeling dan automated labeling
- Quality control untuk label accuracy

---

## 8. Continuous Pre-training: Pembelajaran Berkelanjutan

### Mengapa Continuous Pre-training Penting?

**Continuous pre-training juga important dengan generative AI untuk few reasons:**

#### 1. Output Non-deterministik

- **Output dari generative AI models adalah non-deterministic**
- **Makes validation more difficult**
- **Important untuk choose metrics, benchmarks, dan datasets yang help evaluate capabilities dari models dan ensure bahwa it doesn't create harmful outputs**

#### 2. Evaluasi Kemampuan Model

Penting untuk:
- Memilih metrics yang tepat
- Menggunakan benchmarks yang sesuai
- Memastikan model tidak menghasilkan **harmful outputs**
- Evaluasi berkelanjutan terhadap capabilities model

#### 3. Peningkatan Kemampuan Model

**When you continually pre-train models pada data across different topics, genres, dan context:**
- **Over time, models become more powerful**
- **They learn how to use out-of-domain data better dengan accumulating wider knowledge dan adaptability**
- **This capability creates value untuk organization Anda**

### Continuous Pre-training di Amazon Bedrock

**Implementasi:**
- **Continued pre-training dalam Amazon Bedrock helps you train Amazon Titan Text Express dan Amazon Titan Text Lite FMs**
- **Customize them dengan using your own unlabeled data dalam secure dan managed environment**
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

### Key Elements Training Foundation Model
- **Pre-training** menggunakan **self-supervised learning** dengan **huge amounts of unstructured data**
- **Fine-tuning** adalah **supervised learning** yang menggunakan **dataset of labeled examples** untuk update weights LLM
- **Continuous pre-training** important untuk maintain model capabilities

### Fine-tuning Methods
- **Full fine-tuning:** Every parameter dalam model diperbarui melalui supervised learning
- **PEFT (Parameter-Efficient Fine-Tuning):** Freeze original LLM parameters, fine-tune small number task-specific adaptor layers
- **LoRA (Low-Rank Adaptation):** Popular PEFT technique yang preserves original weights, creates new trainable low-rank matrices
- **ReFT (Representation Fine-Tuning):** Freezes base model, learns task-specific interventions pada hidden representations
- **Multitask fine-tuning:** Extension dari single task fine-tuning, requires lot of data

### Key Challenges dan Solutions
- **Catastrophic forgetting:** Happens ketika fine-tuning modifies weights dari original LLM, dapat degrade performance pada other tasks
- **Multitask fine-tuning** helps mitigate dan avoid catastrophic forgetting
- **Domain adaptation fine-tuning:** Use pre-trained foundation models untuk adapt ke specific tasks dengan limited domain-specific data
- **RLHF:** Uses reinforcement learning untuk fine-tune LLM dengan human feedback data

### AWS Tools untuk Data Preparation
- **Amazon SageMaker Canvas:** Low-code data preparation
- **Amazon SageMaker Studio Classic + EMR:** Data preparation yang needs to scale dengan Apache Spark, Hive, Presto
- **AWS Glue Interactive Sessions:** Serverless Apache Spark-based engine
- **Amazon SageMaker Feature Store:** Feature discovery dan storage
- **Amazon SageMaker Clarify:** Detect bias dalam data
- **Amazon SageMaker Ground Truth:** Data labeling workflows

### Continuous Pre-training
- **Output generative AI models adalah non-deterministic**, makes validation more difficult
- **Continually pre-train models** pada data across different topics makes models more powerful over time
- **Amazon Bedrock** supports continued pre-training untuk **Amazon Titan Text Express dan Titan Text Lite FMs**
