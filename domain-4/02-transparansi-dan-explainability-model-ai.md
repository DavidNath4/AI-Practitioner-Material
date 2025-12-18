# Transparansi dan Explainability Model AI

## Pengenalan

Salah satu tantangan terbesar dalam AI adalah membangun kepercayaan melalui pemahaman tentang bagaimana dan mengapa model AI membuat keputusan tertentu. Transparansi dan explainability menjadi kunci penting dalam pengembangan AI yang bertanggung jawab, terutama untuk memenuhi persyaratan regulasi yang melindungi konsumen dari bias dan ketidakadilan.

## Konsep Transparansi Model

**Transparansi** mengukur sejauh mana pemilik dan pemangku kepentingan ML dapat memahami cara kerja model dan alasan di balik output yang dihasilkan. Tingkat transparansi yang diperlukan sering bergantung pada persyaratan regulasi untuk melindungi konsumen dari bias dan ketidakadilan.

## Perbedaan Interpretability vs Explainability

Transparansi memiliki dua dimensi utama yang sering disalahpahami: **interpretability** dan **explainability**. Memahami perbedaan keduanya sangat penting untuk memilih pendekatan yang tepat.

### Interpretability (Kemampuan Interpretasi)

**Interpretability** mengacu pada kemampuan untuk memahami mekanisme internal model secara langsung. Model dengan interpretability tinggi menggunakan algoritma yang mudah dipahami.

**Model dengan Interpretability Tinggi:**
- **Linear Regression**: Algoritma yang sangat mudah dipahami dengan slope dan intercept yang jelas. Dalam bentuk paling dasar, kita dapat melihat kemiringan dan titik potong garis serta bagaimana model menggunakannya
- **Decision Trees**: Menghasilkan aturan-aturan dasar yang dapat dipahami dengan mudah

**Model dengan Interpretability Rendah:**
- **Neural Networks**: Meniru cara kerja otak manusia dengan hampir 100 miliar neuron
- Meskipun kita memahami bahwa otak bekerja melalui sinyal listrik yang merambat melalui jaringan neuron, kita tidak dapat benar-benar memahami bagaimana proses tersebut menghasilkan pemikiran tertentu

### Explainability (Kemampuan Penjelasan)

**Explainability** adalah kemampuan untuk menjelaskan apa yang dilakukan model tanpa harus mengetahui secara pasti bagaimana cara kerjanya. Model yang kurang interpretable masih dapat dijelaskan dengan mengamati outputnya relatif terhadap input tertentu.

**Karakteristik Explainability:**
- Memperlakukan model sebagai "black box"
- Setiap model dapat diamati dan dijelaskan
- Menggunakan pendekatan model-agnostic untuk menjawab pertanyaan dunia nyata
- Tidak mempertimbangkan mekanisme internal model

**Contoh Penerapan:**
- Mengapa email ditandai sebagai spam?
- Mengapa aplikasi pinjaman seseorang ditolak?

**Perbedaan Kunci:**
- **Interpretability**: Mendokumentasikan bagaimana mekanisme internal model mempengaruhi output
- **Explainability**: Tidak mempertimbangkan mekanisme internal, fokus pada hubungan input-output

## Model Transparency Spectrum

Model AI dapat ditempatkan dalam spektrum transparansi dari yang paling interpretable hingga yang paling kompleks:

### Spektrum Transparansi Model

```
Interpretability Tinggi ←→ Interpretability Rendah
(Transparansi Tinggi)      (Transparansi Rendah)

Linear Regression → Decision Trees → Random Forest → Neural Networks → Deep Neural Networks
```

**Karakteristik Spektrum:**
1. **Linear Regression**: Paling mudah diinterpretasi, performa terbatas
2. **Decision Trees**: Aturan yang jelas, mudah dipahami
3. **Random Forest**: Kombinasi decision trees, lebih kompleks
4. **Neural Networks**: Performa tinggi, sulit diinterpretasi
5. **Deep Neural Networks**: Performa tertinggi, paling sulit diinterpretasi


## Pertimbangan dalam Memilih Model

### Kapan Membutuhkan Interpretability?

Saat memulai proyek AI atau ML baru, Anda perlu menentukan apakah interpretability adalah persyaratan bisnis yang wajib (hard business requirement):

- **Jika ada regulasi atau persyaratan bisnis** untuk transparansi model yang lengkap → Pilih model yang interpretable
- **Jika cukup dengan explainability** untuk memenuhi tujuan bisnis → Model kompleks dapat digunakan

Dengan interpretability, Anda dapat mendokumentasikan bagaimana mekanisme internal model mempengaruhi output, sedangkan explainability tidak mempertimbangkan mekanisme internal. Tingkat explainability ini sering cukup untuk memenuhi tujuan bisnis.

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

**Kesimpulan:** Meskipun transparansi model dapat ditingkatkan dengan memilih algoritma yang kurang kompleks, hal ini biasanya melibatkan kompromi dalam performa model seperti yang ditunjukkan dalam spektrum transparansi di atas.

#### 2. Trade-off Keamanan

**Model Transparan:**
- ❌ Lebih rentan terhadap serangan
- ❌ Hacker memiliki lebih banyak informasi tentang mekanisme internal
- ❌ Lebih mudah menemukan kerentanan

**Model Opaque (Tidak Transparan):**
- ✅ Membatasi penyerang hanya pada informasi dari output model
- ✅ Lebih sulit untuk di-reverse engineer

Dari perspektif keamanan model, kurangnya transparansi memiliki keuntungan. Model AI yang transparan lebih rentan terhadap serangan karena hacker memiliki lebih banyak informasi tentang mekanisme internal dan dapat menemukan kerentanan dalam model. Model yang lebih opaque membatasi penyerang hanya pada apa yang dapat mereka pelajari dari mempelajari output model.

### Risiko Transparansi

1. **Keamanan Artefak Model**: Mengamankan artefak model dengan benar sangat penting untuk model transparan
2. **Paparan Algoritma Proprietary**: Semakin banyak penjelasan perilaku model AI yang dapat diakses penyerang, semakin mudah mereka dapat melakukan reverse engineering terhadap model AI
3. **Privasi Data**: Memastikan privasi data pelanggan sambil mempertahankan transparansi juga dapat menjadi tantangan. Transparansi mungkin memerlukan berbagi detail tentang data yang digunakan untuk melatih model, yang menimbulkan kekhawatiran tentang privasi data


## Tools dan Layanan AWS untuk Transparansi

### 1. Open Source Software

**Open source software** dikembangkan secara kolaboratif dan terbuka. Platform seperti GitHub melayani repositori untuk proyek AI open source ini.

**Keuntungan:**
- Karena semuanya dibagikan, pengguna memperoleh pemahaman tentang konstruksi dan cara kerja internal model, yang memaksimalkan transparansinya
- Karena cara kerja internal model AI terbuka untuk diteliti, hal ini menanamkan kepercayaan pada keadilannya
- Banyak pengguna di seluruh dunia berkontribusi pada proyek open source, yang menghasilkan peningkatan keragaman developer dan mengurangi bias
- Karena lebih banyak orang terlibat dalam pengembangan, masalah dengan bias atau coding lebih mungkin terdeteksi

**Kekhawatiran:**
- Dengan transparansi maksimum melalui proyek open source, beberapa perusahaan memiliki kekhawatiran tentang keamanan model
- Mereka memblokir karyawan mereka dari mengembangkan dengan kode open source atau bahkan menggunakan model yang dikembangkan dengannya
- Mereka lebih memilih pengembangan proprietary dan oleh karena itu, membatasi transparansi model mereka untuk alasan keamanan

### 2. AI Service Cards

Ketika menggunakan model terlatih yang di-hosting oleh AWS, Anda hanya berinteraksi dengan API dan tidak memiliki akses langsung ke model. Jadi AWS perlu transparan tentang bagaimana dimensi inti responsible AI ditangani.

**AI Service Cards** adalah bentuk dokumentasi responsible AI yang menyediakan pelanggan dengan satu tempat untuk mempelajari tentang:
- Use case yang dimaksudkan
- Keterbatasan model
- Pilihan desain responsible AI
- Best practices untuk deployment dan optimasi performa

**AI Service Cards saat ini tersedia untuk beberapa API layanan AI mereka:**
- Matching faces dengan Amazon Rekognition
- Analyzing IDs dengan Amazon Textract
- Detecting PII dengan Amazon Comprehend
- Dan lainnya

**Terdapat juga AI Service Card untuk foundation model Amazon di Amazon Bedrock:**
- Amazon Titan Text

### 3. SageMaker Model Cards

Untuk model yang Anda buat sendiri, **SageMaker Model Cards** membantu mendokumentasikan lifecycle model dari tahap:
- **Designing** (Perancangan)
- **Building** (Pembangunan)
- **Training** (Pelatihan)
- **Evaluation** (Evaluasi)

**Fitur Auto-populate:**
Ketika Anda membuat model card, SageMaker secara otomatis mengisi (autopopulates) detail tentang model yang dilatih SageMaker dalam card tersebut. Misalnya, detail ini dapat mencakup:
- Bagaimana model dilatih
- Dataset yang digunakan
- Container yang digunakan

SageMaker Model Cards menyediakan dokumentasi komprehensif yang membantu dalam transparansi dan akuntabilitas model custom yang Anda kembangkan.

### 4. SageMaker Clarify

Selain melaporkan bias, **SageMaker Clarify model processing jobs** juga dapat melaporkan explainability.

#### Feature Attribution dengan Shapley Values

**SageMaker Clarify** menyediakan feature attributions berdasarkan konsep **Shapley Values**. Anda dapat menggunakan Shapley Values untuk menentukan kontribusi yang dibuat setiap fitur terhadap prediksi model.

**Visualisasi:**
- Bar chart menunjukkan empat fitur paling berdampak yang digunakan oleh model
- Membantu memahami fitur mana yang paling mempengaruhi keputusan model

#### Partial Dependence Plot

**Jenis analisis lain yang tersedia di SageMaker Clarify** adalah partial dependence plot.

**Fungsi:**
- Plot ini menunjukkan bagaimana prediksi model berubah untuk nilai yang berbeda dari suatu fitur
- Contoh: Dalam kasus ini, plot melihat fitur "age" (usia)
- Membantu memahami hubungan antara fitur individual dan output model


## Human-Centered AI

### Konsep Dasar

**Human-Centered AI** mengacu pada desain sistem AI yang memprioritaskan kebutuhan dan nilai-nilai manusia. Sekarang mari kita fokus pada bagaimana kita bisa mendapatkan lebih banyak keterlibatan manusia dalam pengembangan dan desain AI.

### Karakteristik Human-Centered AI

**1. Kolaborasi Interdisipliner**
- Dalam human-centered AI, desainer dan developer terlibat dalam kolaborasi interdisipliner
- Sering melibatkan psikolog, ahli etika, dan domain experts untuk mengumpulkan perspektif dan keahlian yang beragam

**2. Keterlibatan Pengguna**
- Pengguna terlibat dalam proses pengembangan
- Memastikan bahwa AI akan benar-benar bermanfaat dan user-friendly

**3. Tujuan Utama**
- Tujuan human-centered AI adalah untuk meningkatkan kemampuan manusia daripada menggantikannya
- Selaras dengan prinsip ethical AI yang telah kita diskusikan

**4. Integrasi Manusia di Setiap Tahap**
- Menggabungkan manusia di setiap tahap pengembangan untuk memastikan bahwa AI:
  - Transparan
  - Dapat dijelaskan (explainable)
  - Adil dan tidak bias
  - Menjaga privasi

### Amazon Augmented AI (Amazon A2I)

**Amazon Augmented AI atau Amazon A2I** menggabungkan review manusia untuk sampel inferensi yang dibuat oleh layanan AI AWS atau model kustom.

#### Cara Kerja

**1. Konfigurasi Review:**
- Anda dapat mengkonfigurasi Amazon A2I untuk mengirim inferensi dengan confidence score rendah ke reviewer manusia sebelum mengirimkannya ke klien
- Feedback mereka kemudian dapat ditambahkan ke data training untuk melatih ulang model

**2. Audit Model:**
- Selain mereview inferensi dengan confidence rendah, Anda dapat meminta reviewer manusia mereview prediksi acak sebagai cara untuk mengaudit model

**3. Pilihan Reviewer:**
- Dengan Amazon A2I, Anda dapat menggunakan pool reviewer di organisasi Anda sendiri atau menggunakan Mechanical Turk
- Anda dapat mengkonfigurasi berapa banyak reviewer yang perlu mereview setiap prediksi

#### Contoh Use Case

**Deteksi Konten Eksplisit dengan Amazon Rekognition:**
- Pertimbangkan bahwa Anda menggunakan Amazon Rekognition untuk mendeteksi gambar yang mengandung konten eksplisit atau ofensif
- Manusia dapat mereview prediksi dari Amazon Rekognition yang memiliki confidence rendah untuk memastikan bahwa konten eksplisit tidak lolos
- Ini memastikan akurasi yang lebih tinggi dalam moderasi konten


## Reinforcement Learning from Human Feedback (RLHF)

### Definisi

**Reinforcement Learning from Human Feedback (RLHF)** adalah teknik standar industri untuk memastikan large language models menghasilkan konten yang:
- **Truthful** (Benar/Jujur)
- **Harmless** (Tidak Berbahaya)
- **Helpful** (Bermanfaat)

### Konsep Dasar Reinforcement Learning

Ingat bahwa teknik reinforcement learning melatih model untuk membuat keputusan yang memaksimalkan reward, yang membuat output mereka lebih akurat.

### Cara Kerja RLHF

#### 1. Integrasi Human Feedback

**RLHF menggabungkan feedback manusia dalam fungsi reward**, sehingga model ML dapat melakukan tugas yang lebih selaras dengan:
- Tujuan manusia (human goals)
- Keinginan manusia (human wants)
- Kebutuhan manusia (human needs)

#### 2. Reward Model

**Untuk menggunakan teknik ini, Anda melatih model terpisah yang berfungsi sebagai reward model.**

**Proses Training Reward Model:**

**Langkah 1: Pengumpulan Data**
- **Reward model dilatih oleh manusia** yang mereview multiple responses dari large language model untuk prompt yang sama
- Manusia menunjukkan response yang mereka preferensikan
- **Preferensi mereka menjadi training data untuk reward model**

**Langkah 2: Training Reward Model**
- Reward model dilatih menggunakan preferensi manusia
- **Ketika dilatih, reward model dapat memprediksi seberapa tinggi manusia akan menilai suatu prompt response**

**Langkah 3: Refinement**
- **Large language model kemudian menggunakan reward model untuk menyempurnakan responsnya untuk reward maksimum**
- Tujuan: Memaksimalkan reward berdasarkan preferensi manusia

### Implementasi dengan SageMaker Ground Truth

**Mengumpulkan preferensi dari manusia untuk RLHF dapat dicapai dengan paling mudah menggunakan SageMaker Ground Truth**, yang telah kita diskusikan ketika membahas pelabelan data training.

#### Contoh Workflow

**Proses Review:**
1. **Dalam screenshot ini, Anda dapat melihat bahwa human workers disajikan dengan multiple responses**
2. **Diminta untuk meranking setiap response berdasarkan clarity (kejelasan)**
3. Ranking ini digunakan sebagai training data untuk reward model

**Keuntungan:**
- Proses pengumpulan feedback terstruktur dan sistematis
- Dapat melibatkan banyak reviewer untuk konsistensi
- Integrasi langsung dengan pipeline ML AWS
- Interface yang user-friendly untuk human reviewers

## Kesimpulan

Transparansi dan explainability adalah aspek krusial dalam pengembangan AI yang bertanggung jawab. Memahami perbedaan antara interpretability dan explainability, serta trade-off antara transparansi, performa, dan keamanan membantu dalam memilih model yang tepat untuk kebutuhan bisnis. 

AWS menyediakan berbagai tools untuk mendukung pengembangan AI yang transparan dan dapat dijelaskan:
- **AI Service Cards** untuk dokumentasi layanan AWS
- **SageMaker Model Cards** untuk dokumentasi model custom
- **SageMaker Clarify** untuk explainability analysis
- **Amazon A2I** untuk human review
- **SageMaker Ground Truth** untuk RLHF implementation

Human-centered AI principles dan RLHF memastikan bahwa sistem AI tidak hanya transparan tetapi juga selaras dengan nilai-nilai dan kebutuhan manusia.

## Poin-Poin Penting untuk Ujian

### Konsep Fundamental
1. **Perbedaan Interpretability vs Explainability**:
   - Interpretability: Memahami mekanisme internal model
   - Explainability: Menjelaskan output tanpa memahami mekanisme internal
2. **Model Transparency Spectrum**: Linear Regression → Decision Trees → Neural Networks
3. **Trade-off utama**: Transparansi tinggi = Performa lebih rendah, Keamanan lebih rendah

### AWS Tools dan Services
4. **AI Service Cards**: Dokumentasi responsible AI untuk layanan AWS yang di-host
5. **SageMaker Model Cards**: Dokumentasi lifecycle model custom (designing, building, training, evaluation)
6. **SageMaker Clarify**: 
   - Feature attribution dengan Shapley values
   - Partial Dependence Plot untuk analisis fitur
7. **Amazon A2I**: Human review untuk inferensi dengan confidence rendah, audit model
8. **SageMaker Ground Truth**: Tool untuk mengumpulkan human feedback untuk RLHF

### Human-Centered AI
9. **Human-Centered AI**: Desain AI yang memprioritaskan kebutuhan manusia, kolaborasi interdisipliner
10. **RLHF**: Teknik untuk membuat LLM lebih truthful, harmless, dan helpful menggunakan reward model
11. **Open Source Benefits**: Transparansi maksimum, deteksi bias lebih baik, keragaman developer
