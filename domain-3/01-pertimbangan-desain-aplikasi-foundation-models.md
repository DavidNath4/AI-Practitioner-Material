# Pertimbangan Desain untuk Aplikasi yang Menggunakan Foundation Models

## Pengantar Domain 3

Domain 3 dari AWS Certified AI Practitioner berfokus pada **pertimbangan desain untuk aplikasi yang menggunakan foundation models**. Task Statement 3.1 ini dibagi menjadi empat bagian pembelajaran yang akan membahas berbagai aspek penting dalam memilih dan mengimplementasikan pre-trained models.

---

## Task Statement 3.1: Kriteria Pemilihan Pre-trained Models

### Tujuan Pembelajaran
Memahami kriteria seleksi untuk memilih pre-trained models dengan mempertimbangkan berbagai faktor seperti:
- Biaya (cost)
- Modalitas (modality)
- Latensi (latency)
- Dukungan multibahasa (multilingual)
- Ukuran model (model size)
- Kompleksitas model (model complexity)
- Kustomisasi (customization)
- Panjang input dan output

---

## 1. Pertimbangan Biaya (Cost Considerations)

### Mengapa Biaya Penting?

Pre-trained models memiliki keunggulan dalam machine learning dan AI, namun juga memiliki pertimbangan khusus. Model-model ini berukuran besar dan membutuhkan banyak sumber daya komputasi untuk training dan inference.

### Tantangan Biaya

**Durasi dan biaya training model** adalah pertimbangan penting karena dapat sangat mahal untuk:
- Hardware
- Storage
- Sumber daya komputasi lainnya

### Dilema Akurasi vs Biaya

Pertanyaan yang sering muncul:
> **Apakah Anda memilih model dengan akurasi 98% yang biaya trainingnya ratusan ribu dolar, atau model dengan akurasi 97% yang hanya membutuhkan beberapa ribu dolar?**

**Jawabannya tergantung pada kebutuhan Anda.**

### Prinsip Keseimbangan

Anda perlu menemukan keseimbangan antara:
- **Waktu training**
- **Biaya**
- **Performa model**

**Tujuan utama:** Merancang solusi yang scalable, efisien, dan tidak mengurangi performa model.

### Dampak Kompleksitas

Semakin kompleks sebuah model, semakin besar dampaknya terhadap:
- Biaya pembangunan
- Biaya pemeliharaan
- Keseluruhan lifecycle model

> **Catatan Penting:** Biaya untuk membangun dan memelihara model adalah pertimbangan krusial dalam kesuksesan sebuah proyek AI.

---

## 2. Pertimbangan Latensi dan Kecepatan (Latency Constraints)

### Kebutuhan Real-time

Jika aplikasi AI Anda perlu memproses data dan memberikan hasil secara **real-time**, maka ini menjadi pertimbangan penting dalam pemilihan model.

### Inference Speed

**Inference speed** adalah durasi yang dibutuhkan model untuk:
- Memproses data
- Menghasilkan prediksi

### Contoh Kasus: Sistem Kendaraan Otonom

**Skenario:**
Sistem kendaraan self-driving membutuhkan keputusan instan. Model dengan inference time yang lambat tidak akan memenuhi kebutuhan ini.

**Pertanyaan:** Model apa yang Anda pilih?

**Analisis:**
- Anda mungkin mempertimbangkan **K-Nearest Neighbors (KNN)** yang melakukan sebagian besar pekerjaan komputasinya selama tahap inference
- Namun, model KNN bisa lebih lambat dalam menghasilkan prediksi
- Sistem kendaraan otonom adalah masalah dengan dimensi yang sangat tinggi
- **KNN bukan pilihan terbaik** untuk kasus ini

### Kesimpulan Latensi

Memahami kebutuhan use case Anda dalam hal **inference speed** sangat penting saat memutuskan model AI yang akan digunakan.

---

## 3. Pertimbangan Modalitas (Modalities)

### Apa itu Modalitas?

Modalitas mengacu pada jenis data yang dapat diproses oleh model (teks, gambar, audio, video, dll).

### Pertimbangan Utama

1. **Embedding Spesifik**
   - Dalam sebagian besar sistem AI, setiap modalitas memiliki embedding spesifik

2. **Ensemble Methods**
   - Metode ensemble menggabungkan beberapa model untuk mencapai performa yang lebih baik daripada model tunggal

3. **Model Multibahasa**
   - Pertimbangan untuk memilih model multibahasa yang dilatih pada bahasa-bahasa yang relevan

---

## 4. Arsitektur dan Kompleksitas Model

### Pemilihan Arsitektur

Arsitektur yang berbeda memiliki kekuatan dan kelemahan yang berbeda, dan mungkin lebih cocok untuk jenis tugas tertentu.

#### Contoh Arsitektur:

**Convolutional Neural Networks (CNNs)**
- Cocok untuk: **Image recognition**
- Keunggulan: Efektif dalam mengenali pola visual

**Recurrent Neural Networks (RNNs)**
- Cocok untuk: **Natural Language Processing (NLP)**
- Keunggulan: Mampu memproses data sekuensial

### Mengukur Kompleksitas Model

Kompleksitas model dapat diukur dari:
- **Jumlah parameter**
- **Jumlah layer**
- **Jumlah operasi**

### Dampak Kompleksitas

Semua faktor kompleksitas akan mempengaruhi:
- **Kecepatan** (speed)
- **Memori** (memory)
- **Akurasi** (accuracy)

> **Prinsip Penting:** Model yang lebih kompleks memiliki akurasi lebih tinggi, tetapi juga membutuhkan lebih banyak sumber daya komputasi dan data.

---

## 5. Performa dan Metrik Evaluasi

### Subset dari Arsitektur dan Kompleksitas

Performa dan metrik dari pre-trained model perlu dievaluasi pada:
- Dataset asli (original dataset)
- Dataset baru (new dataset)

### Metrik Standar untuk Evaluasi

Anda dapat menggunakan metrik standar untuk mengevaluasi dan membandingkan model yang berbeda:

1. **Accuracy** - Akurasi keseluruhan
2. **Precision** - Ketepatan prediksi positif
3. **Recall** - Kemampuan mendeteksi semua kasus positif
4. **F1 Score** - Harmonic mean dari precision dan recall
5. **RMSE (Root Mean Squared Error)** - Untuk regresi
6. **MAP (Mean Average Precision)** - Untuk deteksi objek
7. **MAE (Mean Absolute Error)** - Untuk regresi

### Tradeoff Antar Metrik

Anda harus mempertimbangkan tradeoff antara metrik-metrik ini dan memilih yang paling relevan untuk tugas Anda.

### Contoh Kasus: Object Detection

**Skenario:** Anda melakukan object detection

**Pertimbangan:**
- Anda mungkin lebih peduli pada **MAP** daripada **accuracy**
- **Alasan:** MAP mengukur seberapa baik model dapat menemukan dan mengklasifikasikan beberapa objek dalam gambar

### Peringatan tentang Accuracy

**Accuracy tidak direkomendasikan** untuk dataset yang:
- Tidak terdistribusi secara merata
- Imbalanced (tidak seimbang)

### Kesimpulan Metrik

Penting untuk memilih metrik atau set metrik yang tepat untuk menilai performa model Anda sebelum memilih model.

---

## 6. Bias dalam Training Data

### Mengapa Bias Penting?

Penting untuk memahami cara:
- **Mitigasi risiko**
- **Mengatasi masalah etika**
- **Membuat keputusan yang informed** tentang pemilihan model dan fine-tuning

### Pertimbangan Bias

Bias yang mungkin ada dalam training data harus diidentifikasi dan dimitigasi untuk memastikan model yang adil dan akurat.

---

## 7. Ketersediaan dan Kompatibilitas Model

### Sumber Pre-trained Models

Anda dapat menemukan banyak pre-trained models secara online, seperti:
- **TensorFlow Hub**
- **PyTorch Hub**
- **Hugging Face**
- Repository lainnya

### Checklist Kompatibilitas

Sebelum memilih model, periksa:

✅ **Kompatibilitas teknis:**
- Apakah model kompatibel dengan framework Anda?
- Apakah kompatibel dengan bahasa pemrograman Anda?
- Apakah kompatibel dengan environment Anda?

✅ **Lisensi dan dokumentasi:**
- Apakah model memiliki lisensi yang sesuai?
- Apakah dokumentasi lengkap tersedia?

✅ **Pemeliharaan:**
- Apakah model diupdate secara berkala?
- Apakah model dipelihara dengan baik?

✅ **Issues dan limitasi:**
- Apakah ada masalah yang diketahui?
- Apakah ada keterbatasan yang perlu diperhatikan?

---

## 8. Kustomisasi dan Explainability

### Kustomisasi Model

Anda mungkin ingin memodifikasi atau memperluas pre-trained model untuk menyesuaikan dengan tugas Anda, seperti:
- Menambahkan layer baru
- Menambahkan class baru
- Menambahkan fitur baru

### Explainability vs Interpretability

#### Interpretability (Transparansi)

**Definisi:** Kemampuan untuk menjelaskan secara matematis (melalui koefisien dan formula) mengapa model membuat prediksi tertentu.

**Karakteristik:**
- Mungkin jika model cukup sederhana
- Foundation models **TIDAK interpretable** by design karena sangat kompleks
- Foundation models sering disebut sebagai **"black boxes"**

#### Explainability (Penjelasan)

**Definisi:** Upaya untuk menjelaskan "black box" dengan mendekatinya secara lokal menggunakan model yang lebih sederhana yang interpretable.

**Perbedaan Kunci:**
- Explainability ≠ Interpretability
- Pre-trained models tidak dapat transparan by design

### Kapan Interpretability Diperlukan?

Jika interpretability adalah kebutuhan, maka pre-trained foundation models mungkin **bukan pilihan terbaik**.

**Model alternatif yang lebih baik untuk explainability:**
- **Linear Regression**
- **Decision Trees**

### Tantangan Kompleksitas

**Keuntungan kompleksitas:**
- Dapat mengungkap pola yang rumit dalam data

**Tantangan kompleksitas:**
- Meningkatkan kesulitan maintenance
- Mengurangi interpretability

### Pertimbangan Kunci Kompleksitas

1. **Performa vs Biaya**
   - Kompleksitas lebih tinggi → performa lebih baik
   - Tetapi juga → biaya lebih tinggi

2. **Explainability**
   - Semakin rumit model → semakin sulit menjelaskan output

3. **Pertimbangan Tambahan:**
   - Hardware constraints
   - Maintenance updates
   - Data privacy
   - Transfer learning
   - Dan lainnya

---

## 9. Inference Parameters

### Apa itu Inference?

**Inference** adalah proses di mana Anda memproses data baru melalui model untuk membuat prediksi. Ini adalah proses menghasilkan output dari input yang Anda berikan ke model.

### Amazon Bedrock dan Inference

Amazon Bedrock memberikan kemampuan untuk menjalankan inference pada foundation model yang Anda pilih.

### Input untuk Inference

**Pertanyaan:** Ketika Anda menjalankan inference, input apa yang Anda berikan?

**Jawaban:**
- **Prompt** - Input yang diberikan ke model untuk menghasilkan respons
- **Inference Parameters** - Set nilai yang dapat disesuaikan untuk membatasi atau mempengaruhi respons model

### Jenis Inference Parameters

Amazon Bedrock foundation models mendukung inference parameters untuk mengontrol **randomness** dan **diversity** dalam respons:

1. **Temperature**
   - Mengontrol tingkat keacakan dalam respons
   - Nilai rendah → respons lebih deterministik
   - Nilai tinggi → respons lebih kreatif/acak

2. **Top K**
   - Membatasi pilihan token ke K token teratas berdasarkan probabilitas

3. **Top P (Nucleus Sampling)**
   - Memilih dari token dengan probabilitas kumulatif hingga P

### Parameters untuk Membatasi Panjang Respons

Amazon Bedrock juga mendukung parameters seperti:
- **Response length** - Panjang respons
- **Penalties** - Penalti untuk token tertentu
- **Stop sequences** - Urutan untuk menghentikan generasi

### Best Practices

**Penting untuk:**
- Mempertimbangkan pengaturan parameter yang berbeda
- Bereksperimen untuk menemukan keseimbangan optimal antara:
  - Diversity (keragaman)
  - Coherence (koherensi)
  - Resource efficiency (efisiensi sumber daya)
- Terus memantau dan menyesuaikan parameter di production
- Menjaga performa optimal
- Menyesuaikan dengan kebutuhan yang berkembang

---

## 10. Prompt Engineering Fundamentals

### Definisi Prompt

Menurut AWS, **prompt** adalah:
> Set input spesifik yang disediakan oleh Anda (user) yang memandu LLMs untuk menghasilkan respons atau output yang sesuai untuk tugas atau instruksi tertentu.

### Memperkaya Prompt dengan Data Kontekstual

Anda dapat menambahkan data kontekstual dari database internal Anda untuk memperkaya prompt.

### Integrasi dengan Data Stores

Anda dapat mengintegrasikan data domain-specific tambahan dari:
- Data stores
- Vector data stores

Data ini menambahkan input yang relevan secara semantik ke prompt Anda.

### Retrieval Augmented Generation (RAG)

Metode ini disebut **Retrieval Augmented Generation (RAG)**, yang akan dibahas lebih detail di bagian selanjutnya.

---

## 11. Memilih Model yang Tepat

### Prinsip Utama

> **Model AI terbaik untuk Anda tergantung pada kebutuhan, sumber daya, dan batasan Anda. Ini semua tentang menemukan keseimbangan yang tepat untuk memenuhi tujuan dan kebutuhan proyek Anda.**

### Untuk Persiapan Ujian

Pastikan Anda memahami **tradeoff biaya** dari berbagai pendekatan kustomisasi foundation model:

1. **Pre-training** - Melatih model dari awal
2. **Fine-tuning** - Menyesuaikan model yang sudah ada
3. **In-context learning** - Pembelajaran melalui contoh dalam prompt
4. **RAG** - Retrieval Augmented Generation

---

## 12. Vector Databases

### Apa itu Vector Database?

**Vector database** adalah koleksi data yang disimpan sebagai representasi matematis.

**Analogi:** Seperti spreadsheet Excel yang menyimpan data dalam format numerik.

### Karakteristik Vector Database

Vector databases menyimpan data terstruktur dan tidak terstruktur, seperti:
- Teks
- Gambar

Data disimpan dengan **vector embeddings**.

### Apa itu Vector Embeddings?

**Vector embeddings** adalah:
- Cara untuk mengkonversi kata, kalimat, dan data lainnya menjadi angka
- Representasi numerik dari data yang merepresentasikan makna dan hubungan

### Bagaimana Vector Database Dibuat?

Vector database diisi dengan dense vectors melalui proses:
1. Memproses input data (umumnya data teks)
2. Menggunakan ML model (umumnya embedding model)

> **Penting:** Machine learning model adalah prasyarat untuk membuat vector database dan teknologi indexing itu sendiri.

### Perbedaan Vector Database vs ML Model

**Pertanyaan:** Apa perbedaan antara vector database dan machine learning model?

**Jawaban:**
- **Vector Database:** Koleksi data yang disimpan sebagai representasi matematis
- **ML Model:** Alat yang digunakan untuk membuat vector embeddings

### Peran Vector Databases

Vector databases adalah **referensi faktual** dari aplikasi berbasis foundation model, membantu model mengambil data yang dapat dipercaya.

### Penggunaan oleh Foundation Models

Foundation models menggunakan vector databases sebagai sumber data eksternal untuk:
- Meningkatkan kemampuan mereka
- Memperkuat pencarian (search)
- Meningkatkan rekomendasi
- Memperbaiki use case text generation

### Kemampuan Tambahan Vector Databases

Vector databases menambahkan kemampuan untuk:
- **Efficient and fast lookup** - Pencarian cepat dan efisien
- **Data management** - Manajemen data
- **Fault tolerance** - Toleransi kesalahan
- **Authentication** - Autentikasi
- **Access control** - Kontrol akses
- **Query engine** - Mesin query

---

## 13. Knowledge Bases for Amazon Bedrock

### Apa itu Knowledge Bases?

**Knowledge bases for Amazon Bedrock** memberikan kemampuan untuk:
- Mengumpulkan data sources ke dalam repository informasi
- Membangun aplikasi yang memanfaatkan Retrieval Augmented Generation (RAG)

### Keuntungan

Dengan knowledge bases, Anda dapat membangun aplikasi yang menggunakan RAG untuk menghasilkan respons yang lebih akurat dan kontekstual.

---

## 14. Retrieval Augmented Generation (RAG)

### Definisi RAG

**RAG** adalah teknik di mana retrieval informasi dari data sources memperkuat (augments) generasi respons model.

### Tujuan RAG

RAG meningkatkan language models untuk:
- Mengambil (retrieve) pengetahuan eksternal
- Menggunakan pengetahuan eksternal selama proses generasi

### Komponen RAG

RAG menggabungkan dua komponen:

1. **Retriever Component**
   - Mencari melalui knowledge base
   - Mengambil informasi yang relevan

2. **Generator Component**
   - Menghasilkan output berdasarkan informasi yang diambil
   - Mengkombinasikan informasi dengan prompt

### Keuntungan RAG

Kombinasi ini membantu model mengakses:
- Pengetahuan yang up-to-date
- Pengetahuan domain-specific
- Pengetahuan di luar training data mereka

---

## 15. Cara Kerja RAG dengan Vector Database

### Alur Kerja RAG

Mari kita lihat contoh penggunaan vector database dalam dunia nyata:

**Langkah 1: Query Encoding**
- Ketika Anda ingin query model, prompt dilewatkan ke **query encoder**
- Query encoder meng-encode atau meng-embed data ke format yang sama dengan data eksternal

**Langkah 2: Vector Database Search**
- Embedding dilewatkan ke vector database untuk mencari
- Vector database mengembalikan embeddings serupa yang telah diproses melalui model

**Langkah 3: Data Retrieval**
- Embeddings tersebut kemudian dilampirkan ke query baru Anda
- Dapat juga dipetakan kembali ke lokasi aslinya

**Langkah 4: Augmentation**
- Jika vector database menemukan data serupa, retriever mengambil data tersebut
- LLM menggabungkan atau memperkuat data/teks baru dengan prompt asli

**Langkah 5: Generation**
- Prompt dikirim ke LLM untuk mengembalikan completion
- Hasil akhir adalah respons yang lebih akurat dan kontekstual

---

## 16. Mengatasi Hallucinations dengan RAG

### Masalah Hallucinations

Generative LLMs dapat rentan terhadap **hallucinations**, yaitu:
> Situasi di mana model menghasilkan respons yang terdengar masuk akal tetapi faktanya salah.

### Solusi: RAG

RAG menyelesaikan masalah ini dengan:
- Melengkapi generative LLMs dengan knowledge base eksternal
- Knowledge base biasanya dibangun menggunakan vector database
- Diisi dengan artikel pengetahuan yang di-encode menjadi vector

### Amazon Bedrock RAG

Amazon Bedrock menawarkan model RAG yang terintegrasi dengan custom knowledge bases.

### Aplikasi RAG

RAG menemukan aplikasi di berbagai domain:
- **Question-answering** - Sistem tanya jawab
- **Dialect systems** - Sistem dialog
- **Content generation** - Generasi konten menggunakan pengetahuan eksternal

Semua aplikasi ini memberikan respons yang akurat dan relevan secara kontekstual.

---

## 17. AWS Services untuk Vector Databases

### Layanan AWS yang Mendukung Embeddings

AWS menyediakan berbagai layanan yang membantu menyimpan embeddings dalam vector databases:

1. **Amazon OpenSearch Service**
2. **Amazon Aurora**
3. **Redis**
4. **Amazon Neptune**
5. **Amazon DocumentDB** (dengan kompatibilitas MongoDB)
6. **Amazon RDS** (dengan PostgreSQL)

---

## 18. Amazon OpenSearch Service

### Kemampuan OpenSearch

**OpenSearch search engine** memberikan:
- **Low-latency search** - Pencarian dengan latensi rendah
- **Aggregations** - Agregasi data
- **OpenSearch dashboards** - Alat visualisasi dan dashboarding

### Plugins OpenSearch

OpenSearch memiliki plugins yang menyediakan kemampuan advanced:
- **Alerting** - Sistem peringatan
- **Fine-grained access control** - Kontrol akses yang detail
- **Observability** - Kemampuan observasi
- **Security monitoring** - Monitoring keamanan
- **Vector storage and processing** - Penyimpanan dan pemrosesan vector

### Vector Database Capabilities

Dengan kemampuan vector database OpenSearch Service, Anda dapat mengimplementasikan:

1. **Semantic Search**
   - Pencarian berbasis makna
   - Meningkatkan hasil pencarian menggunakan embeddings berbasis bahasa

2. **RAG dengan LLMs**
   - Retrieval Augmented Generation

3. **Recommendation Engines**
   - Mesin rekomendasi

4. **Media Search**
   - Pencarian media

### Semantic Search

Dengan semantic search, Anda dapat meningkatkan hasil yang diambil dengan menggunakan embeddings berbasis bahasa pada dokumen pencarian.

### Workshop Example

Ada workshop example untuk meningkatkan relevansi pencarian dengan ML di Amazon OpenSearch Service yang mengeksplorasi perbedaan antara:
- **Keyword search** - Pencarian berbasis kata kunci
- **Semantic search** - Pencarian berbasis makna

Workshop ini menggunakan model **BERT (Bidirectional Encoder Representations from Transformers)** yang:
- Di-host oleh Amazon SageMaker
- Menghasilkan vectors
- Menyimpannya di OpenSearch

---

## 19. Amazon OpenSearch Serverless

### Vector Engine

**Vector engine dari Amazon OpenSearch Serverless** menyediakan:
- Kemampuan penyimpanan vector
- Kemampuan pencarian vector

### Keuntungan Serverless

Membantu membangun:
- **ML-augmented search experiences** - Pengalaman pencarian yang diperkuat ML
- **Generative AI applications** - Aplikasi generative AI

**Tanpa harus mengelola infrastruktur vector database.**

### Fully Managed RAG

Dengan **fully managed RAG** yang ditawarkan oleh **knowledge bases for Amazon Bedrock**, Anda dapat:
- Menghubungkan foundation models (FMs) secara aman ke data perusahaan Anda
- Data disimpan sebagai embeddings di vector engine
- Menghasilkan respons yang lebih relevan, spesifik konteks, dan akurat
- **Tanpa perlu terus-menerus re-training FM**

---

## 20. Amazon RDS for PostgreSQL

### pgvector Extension

**Amazon RDS for PostgreSQL** mendukung **pgvector extension** untuk:
- Menyimpan embeddings
- Melakukan pencarian yang efisien

### Opsi Advanced

Ada lebih banyak opsi yang tersedia untuk vectors yang lebih advanced.

---

## 21. Ukuran Model dan Kemampuan

### Prinsip Ukuran Model

> **Model yang lebih besar dari arsitektur apa pun biasanya lebih mampu melaksanakan tugasnya dengan baik.**

### Temuan Penelitian

Peneliti telah menemukan bahwa:
- Semakin besar model → semakin mungkin bekerja dengan baik
- Model besar dapat bekerja tanpa:
  - Additional in-context learning
  - Further training

### Implikasi

Model besar memiliki keuntungan dalam:
- Kemampuan generalisasi
- Performa pada berbagai tugas
- Kemampuan zero-shot dan few-shot learning

---

## 22. Agents for Amazon Bedrock

### Keterbatasan Foundation Models

Foundation models dapat:
- Memahami queries
- Merespons queries berdasarkan pengetahuan pre-trained mereka

Namun, mereka **tidak dapat menyelesaikan tugas dunia nyata** seperti:
- Memesan penerbangan
- Memproses purchase order

### Mengapa Foundation Models Terbatas?

Tugas-tugas dunia nyata membutuhkan:
- Data spesifik organisasi
- Workflows spesifik
- Biasanya memerlukan custom programming

### Apa itu Agents?

**Agents for Amazon Bedrock** adalah kemampuan AI yang fully managed dari AWS untuk membantu Anda membangun aplikasi foundation models.

### Kemampuan Agents

Agents dapat:

1. **Otomatis memecah tugas**
   - Breakdown tasks secara otomatis
   - Generate orchestration logic yang diperlukan
   - Menulis custom code

2. **Koneksi aman ke databases**
   - Terhubung secara aman melalui APIs
   - Mengakses data organisasi

3. **Ingest dan struktur data**
   - Meng-ingest data
   - Menyusun data untuk konsumsi mesin
   - Memperkaya dengan detail kontekstual

4. **Menghasilkan respons yang lebih akurat**
   - Menghasilkan respons yang lebih akurat
   - Memenuhi requests dengan lebih baik

### Definisi Teknis Agents

**Agents** adalah:
> Perangkat lunak tambahan yang mengorkestrasikan prompt completion workflows dan interaksi antara user requests, foundation model, dan sumber data eksternal atau aplikasi.

### Fungsi Agents

Agents secara otomatis:
- Memanggil APIs untuk mengambil tindakan
- Memanggil knowledge bases untuk melengkapi informasi untuk tindakan tersebut

### Contoh Penggunaan

Anda dapat membuat agent yang membantu pelanggan memproses reservasi untuk liburan scuba diving Anda berikutnya.

---

## Ringkasan Task Statement 3.1

Task Statement 3.1 mencakup pertimbangan desain yang komprehensif untuk aplikasi yang menggunakan foundation models, meliputi:

1. **Kriteria Pemilihan Model**
   - Biaya, latensi, modalitas, ukuran, kompleksitas

2. **Evaluasi dan Metrik**
   - Accuracy, precision, recall, F1, RMSE, MAP, MAE

3. **Bias dan Etika**
   - Mitigasi risiko dan masalah etika

4. **Kompatibilitas dan Maintenance**
   - Ketersediaan, lisensi, dokumentasi, updates

5. **Explainability**
   - Interpretability vs explainability

6. **Inference Parameters**
   - Temperature, Top K, Top P, response length

7. **Prompt Engineering**
   - Desain prompt yang efektif

8. **Vector Databases dan RAG**
   - Penyimpanan embeddings, retrieval augmented generation

9. **AWS Services**
   - OpenSearch, Aurora, RDS, Neptune, DocumentDB

10. **Agents**
    - Orchestration untuk tugas multi-step

---

## Tips untuk Ujian AWS Certified AI Practitioner

✅ Pahami tradeoff biaya dari berbagai pendekatan kustomisasi foundation model

✅ Ketahui perbedaan antara interpretability dan explainability

✅ Pahami cara kerja RAG dan kapan menggunakannya

✅ Kenali berbagai AWS services untuk vector databases

✅ Pahami peran agents dalam menyelesaikan tugas multi-step

✅ Ketahui berbagai inference parameters dan dampaknya

✅ Pahami metrik evaluasi yang tepat untuk berbagai use cases

---

**Catatan:** Materi ini adalah bagian dari persiapan ujian AWS Certified AI Practitioner (AIF-C01). Pastikan untuk mempelajari juga domain lainnya dan berlatih dengan soal-soal latihan.
