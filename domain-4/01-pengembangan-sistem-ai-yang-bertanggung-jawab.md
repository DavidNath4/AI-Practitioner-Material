# Pengembangan Sistem AI yang Bertanggung Jawab

## Pengantar

Domain 4 dari AWS Certified AI Practitioner berfokus pada pengembangan sistem AI yang bertanggung jawab (Responsible AI). Task Statement 4.1 secara khusus membahas bagaimana menjelaskan dan mengimplementasikan prinsip-prinsip AI yang bertanggung jawab dalam pengembangan sistem AI.

## Apa itu Responsible AI?

**Responsible AI** adalah seperangkat pedoman dan prinsip untuk memastikan bahwa sistem AI beroperasi dengan cara yang aman, dapat dipercaya, dan bertanggung jawab. Ini bukan hanya tentang membuat AI yang bekerja dengan baik, tetapi juga memastikan AI tersebut bekerja dengan cara yang etis dan adil untuk semua orang.

## Dimensi Inti Responsible AI

### 1. Fairness (Keadilan)

Fairness bertujuan memastikan bahwa model memperlakukan semua orang secara adil dan tidak memihak, terlepas dari:
- Usia mereka
- Tempat tinggal
- Gender
- Etnis atau ras

**Contoh Praktis**: Sebuah sistem AI untuk persetujuan pinjaman harus memberikan kesempatan yang sama kepada semua pemohon, tidak peduli apakah mereka pria atau wanita, muda atau tua.

### 2. Explainability (Dapat Dijelaskan)

Explainability adalah kemampuan untuk menjelaskan dalam istilah manusia mengapa model membuat keputusan tertentu.

**Contoh**: Jika aplikasi pinjaman ditolak, sistem harus bisa menjelaskan alasan utamanya, misalnya:
- "Pendapatan Anda di bawah ambang batas minimum"
- "Rasio utang terhadap pendapatan terlalu tinggi"

### 3. Robustness (Ketahanan)

Robustness memastikan bahwa sistem AI:
- Toleran terhadap kegagalan
- Meminimalkan kesalahan
- Tetap dapat diandalkan dalam berbagai kondisi

Ini penting karena pengguna menaruh kepercayaan mereka pada AI.

### 4. Privacy dan Security (Privasi dan Keamanan)

Dimensi ini terutama tentang:
- Melindungi privasi pengguna
- Tidak mengekspos Personally Identifiable Information (PII)
- Menjaga keamanan data sensitif

**PII** mencakup informasi seperti nama, alamat, nomor telepon, email, dan data pribadi lainnya.

### 5. Governance (Tata Kelola)

Governance mencakup:
- Memenuhi standar industri dan praktik terbaik
- Melakukan audit kepatuhan
- Mengestimasi dan memitigasi risiko dengan tepat
- Memastikan akuntabilitas dalam penggunaan AI

### 6. Transparency (Transparansi)

Transparency melibatkan:
- Memberikan informasi yang jelas tentang kemampuan model
- Menjelaskan keterbatasan model
- Mengungkapkan potensi risiko kepada stakeholder
- **Memastikan pengguna tahu kapan mereka berinteraksi dengan AI**

Poin terakhir sangat penting - pengguna harus selalu diberi tahu jika mereka sedang berbicara dengan chatbot AI, bukan manusia.

## Memahami Bias dan Variance dalam Model AI

### Mengapa Fairness Penting?

Fairness dalam model diukur melalui bias dan variance dari hasil di berbagai kelompok. Ada beberapa masalah yang perlu diwaspadai:

#### 1. Demographic Disparities (Disparitas Demografis)

Ini terjadi ketika ada hasil atau perlakuan yang tidak setara terhadap kelompok berbeda berdasarkan:
- Usia
- Ras
- Jenis kelamin
- Dan karakteristik demografis lainnya

#### 2. Accuracy Bias (Bias Akurasi)

Model bisa menunjukkan bias dengan:
- Lebih akurat untuk beberapa kelompok
- Kurang akurat untuk kelompok lainnya

**Contoh**: Model diagnosa penyakit yang lebih akurat untuk pria daripada wanita.

### Masalah Overfitting dan Underfitting

#### Overfitting

**Overfitting** terjadi ketika dataset pelatihan tidak representatif terhadap dunia nyata:
- Model hanya berkinerja baik pada input yang menyerupai data pelatihan
- Kelompok yang tidak terwakili dengan baik dalam data pelatihan akan mengalami hasil yang lebih negatif

**Contoh**: Jika model dilatih terutama dengan data dari orang berusia 30-40 tahun, maka akan kurang akurat untuk orang yang lebih muda atau lebih tua.

#### Underfitting

**Underfitting** dapat terjadi untuk beberapa kelompok ketika:
- Tidak ada cukup data pelatihan yang sesuai dengan karakteristik mereka
- Model tidak berkinerja baik untuk kelompok tersebut

### Dampak Bias dan Variance

1. **Erosi Kepercayaan Pengguna**: Output yang bias atau tidak konsisten dapat mengikis kepercayaan pengguna
2. **Masalah Etika**: Sistem AI yang melanggar prinsip keadilan, non-diskriminasi, dan perlakuan yang setara menimbulkan kekhawatiran etis

## Class Imbalance: Penyebab Utama Bias

### Apa itu Class Imbalance?

**Class Imbalance** terjadi ketika nilai fitur memiliki lebih sedikit sampel pelatihan dibandingkan dengan nilai lain dalam dataset.

### Contoh Kasus

Misalkan dalam dataset pelatihan:
- Wanita: 32.4% dari data
- Pria: 67.6% dari data

**Dampaknya**:
- Model melihat lebih banyak data untuk pria selama pelatihan
- Model berkinerja lebih baik dengan inferensi yang terkait dengan pria
- Model bisa overfit pada data wanita karena undersampling
- Tingkat kesalahan lebih tinggi untuk wanita

**Konsekuensi Serius**: Jika ini adalah model untuk memprediksi penyakit, bisa menyebabkan tingkat diagnosis yang tidak akurat lebih tinggi untuk wanita.

## Responsible Datasets: Fondasi Responsible AI

### Prinsip Utama

> **Bias dalam dataset pelatihan akan menjadi bias dalam output**

Oleh karena itu, dataset yang bertanggung jawab harus memiliki karakteristik berikut:

### 1. Inclusivity (Inklusivitas)

- Merepresentasikan populasi, perspektif, dan pengalaman yang beragam
- Memastikan semua kelompok demografis terwakili

### 2. Diversity (Keberagaman)

- Menggabungkan berbagai atribut, fitur, dan variabel
- Menghindari bias dengan memiliki variasi yang luas

### 3. Curated Data Sources (Sumber Data yang Dikurasi)

- Dipilih dengan hati-hati dan bervariasi
- Memastikan kualitas dan integritas data

### 4. Balanced Datasets (Dataset Seimbang)

- Memastikan representasi yang setara dari kelompok berbeda
- Menghindari distribusi yang miring (skewed)

### 5. Privacy Protection (Perlindungan Privasi)

- Menjaga informasi sensitif
- Mematuhi peraturan perlindungan data (seperti GDPR, CCPA)

### 6. Consent and Transparency (Persetujuan dan Transparansi)

- Mendapatkan persetujuan yang terinformasi dari subjek data
- Memberikan informasi yang jelas tentang penggunaan data

### 7. Regular Audits (Audit Berkala)

- Melakukan tinjauan periodik terhadap dataset
- Mengidentifikasi dan mengatasi potensi masalah atau bias

## Praktik Pemilihan Model AI yang Bertanggung Jawab

### 1. Environmental Impact (Dampak Lingkungan)

**Mengapa Penting?**
- Sumber daya komputasi untuk melatih model besar dan kompleks sangat substansial
- Perlu menilai jejak karbon dan konsumsi energi model

**Praktik Terbaik**:
- Pertimbangkan menggunakan model yang sudah dilatih sebagai titik awal
- Ini mengurangi jumlah pelatihan yang dibutuhkan model Anda

### 2. Sustainability (Keberlanjutan)

- Prioritaskan model dengan dampak lingkungan minimal
- Fokus pada viabilitas jangka panjang
- **Prinsip kunci**: Reuse of existing work (penggunaan kembali pekerjaan yang ada)

### 3. Transparency (Transparansi)

- Berikan informasi yang jelas tentang kemampuan model
- Jelaskan keterbatasan model
- Ungkapkan potensi risiko
- Pastikan pengguna tahu kapan mereka menggunakan AI

### 4. Accountability (Akuntabilitas)

- Tetapkan garis tanggung jawab yang jelas untuk hasil model AI
- Pastikan ada yang bertanggung jawab atas keputusan yang dibuat oleh AI

### 5. Stakeholder Engagement (Keterlibatan Stakeholder)

- Libatkan perspektif yang beragam dalam proses pemilihan model
- Pertimbangkan input dari berbagai pihak dalam proses deployment

## Amazon SageMaker Clarify: Alat untuk Mengukur dan Memonitor Bias

### Apa itu SageMaker Clarify?

**Amazon SageMaker Clarify** adalah layanan AWS yang membantu Anda mengurangi bias dengan mendeteksi potensi bias pada:
1. Tahap persiapan data
2. Setelah pelatihan model
3. Pada model yang sudah di-deploy

### Cara Kerja SageMaker Clarify

#### Explainability (Kemampuan Menjelaskan)

SageMaker Clarify meningkatkan explainability dengan:
- Melihat input dan output model
- Memperlakukan model sebagai "black box"
- Menentukan kepentingan relatif dari setiap fitur

**Contoh Penjelasan**:
"Aplikasi pinjaman ditolak karena dua fitur terpenting - pendapatan dan utang yang belum dibayar - tidak memenuhi ambang batas."

#### Keunggulan Pendekatan Black Box

Karena SageMaker Clarify memperlakukan model sebagai black box:
- Dapat memahami dasar prediksi tanpa memahami cara kerja internal
- Dapat menjelaskan model deep learning
- Dapat menjelaskan model computer vision
- Dapat menjelaskan model natural language processing (NLP)
- Bekerja dengan data tidak terstruktur

### Arsitektur SageMaker Clarify

SageMaker Clarify menggunakan **processing jobs** untuk memeriksa dataset dan model:

```
┌─────────────────────────────────────────────────────────┐
│  SageMaker Clarify Processing Job                       │
│                                                           │
│  ┌───────────────────────────────────────────────────┐  │
│  │  SageMaker Clarify Processing Container          │  │
│  │                                                     │  │
│  │  1. Mendapat input dataset & konfigurasi          │  │
│  │  2. Mengirim request ke model container           │  │
│  │  3. Mengambil prediksi model                      │  │
│  │  4. Menghitung & menyimpan hasil analisis         │  │
│  └───────────────────────────────────────────────────┘  │
│                                                           │
│         ↕                                    ↕            │
│  ┌─────────────┐                    ┌──────────────┐    │
│  │  Amazon S3  │                    │    Model     │    │
│  │   Bucket    │                    │  Container   │    │
│  │             │                    │  (Endpoint)  │    │
│  │ • Input     │                    └──────────────┘    │
│  │ • Output    │                                         │
│  └─────────────┘                                         │
└─────────────────────────────────────────────────────────┘
```

### Output dari SageMaker Clarify

Hasil analisis disimpan di S3 bucket dan mencakup:
1. **File JSON** dengan metrik bias dan atribusi fitur global
2. **Laporan visual** yang mudah dibaca
3. **File tambahan** untuk atribusi fitur lokal

Anda dapat mengunduh hasil dari lokasi output dan melihatnya.

## Metrik Bias pada Training Dataset

### 1. Balanced Dataset Metric

**Tujuan**: Menghindari kesalahan yang terjadi untuk kelas tertentu

**Contoh Masalah**:
Model ML yang dilatih terutama dengan data dari individu berusia menengah mungkin kurang akurat saat membuat prediksi untuk orang yang lebih muda dan lebih tua.

### 2. Label Imbalance

**Masalah**: Ketidakseimbangan terjadi ketika label lebih menyukai hasil positif untuk satu kelas daripada yang lain

**Contoh**:
Data pelatihan mungkin menunjukkan pola yang tidak diinginkan di mana pinjaman disetujui pada tingkat yang lebih tinggi untuk individu berusia menengah.

### 3. Demographic Disparity Metric

**Definisi**: Metrik ini menunjukkan apakah kelas tertentu memiliki proporsi hasil yang ditolak lebih besar dalam dataset daripada hasil yang diterima.

**Contoh Kasus - Penerimaan Perguruan Tinggi**:
- Pelamar wanita: 46% dari pelamar yang ditolak
- Pelamar wanita: hanya 32% dari pelamar yang diterima

**Kesimpulan**: Ini menunjukkan demographic disparity karena tingkat penolakan wanita melebihi tingkat penerimaan wanita.

## Metrik Bias pada Trained Model

### 1. Difference in Positive Proportions in Predictions (DPPL)

**Fungsi**: Menunjukkan apakah model memprediksi hasil positif secara berbeda untuk setiap kelas

**Analisis**:
- Metrik ini dapat dibandingkan dengan label imbalance dalam data pelatihan
- Tujuannya adalah melihat apakah bias dalam proporsi positif berubah setelah pelatihan
- Atau apakah bias juga ada dalam data

### 2. Specificity Difference

**Definisi Specificity**: Mengukur seberapa sering model dengan benar memprediksi hasil negatif

**Contoh Bias**:
Jika specificity lebih rendah untuk pria berusia menengah daripada kelompok usia lain, model menunjukkan bias terhadap kelompok usia lain.

### 3. Recall Difference

**Definisi Recall**: True Positive Rate (TPR) - mengukur seberapa sering model dengan benar memprediksi kasus yang seharusnya menerima hasil positif

**Metrik**: Perbedaan dalam recall model antara dua kelas

**Interpretasi**:
- Jika tingkat recall tinggi untuk satu kelas tetapi rendah untuk kelas lain
- Perbedaan ini memberikan ukuran bias
- Setiap perbedaan dalam recall adalah bentuk bias potensial

### 4. Accuracy Difference

**Masalah**: Akurasi model juga bisa berbeda antara kelas, dan perbedaan ini adalah bentuk bias

**Metrik**: Perbedaan antara akurasi prediksi untuk kelas yang berbeda

**Penyebab**: Hasil ini dapat terjadi ketika data mengandung class imbalance

### 5. Treatment Equality

**Definisi**: Perbedaan dalam rasio false negative terhadap false positive

**Insight Penting**:
Bahkan jika akurasi model sama untuk dua kelas, rasio ini bisa memiliki perbedaan.

**Contoh - Persetujuan Pinjaman**:
- Lebih banyak penolakan pinjaman yang salah untuk satu kelas
- Lebih banyak persetujuan pinjaman yang salah untuk kelas lain

Ini adalah dua hasil yang sangat berbeda yang menunjukkan bias antara kelas. Perbedaan dalam jenis kesalahan yang terjadi untuk kelas berbeda dapat merupakan bias.

## Tantangan dan Risiko Generative AI

### 1. Hallucination (Halusinasi)

**Definisi**: Halusinasi terjadi ketika model membuat sesuatu yang mungkin terdengar faktual, tetapi sebenarnya fiksi.

**Penyebab**: AI model mencoba mengisi celah ketika ada sesuatu yang hilang dalam data pelatihannya.

**Kasus Nyata - Tahun 2023**:
- Pengacara mengajukan brief yang berisi kutipan dan sitasi kasus
- Mereka mendapatkan informasi dari generative AI
- Kasus dan sitasi tersebut ternyata palsu
- Pengadilan menolak kasus klien
- Pengacara dan firma mereka dikenai sanksi dan denda

**Dampak**: Tergantung bagaimana konten yang dihasilkan digunakan, halusinasi bisa menjadi bencana.

### 2. Intellectual Property Issues (Masalah Kekayaan Intelektual)

#### Fakta Penting tentang AI-Generated Works

**Karya yang dihasilkan AI tidak dapat dilindungi hak cipta** karena bukan karya manusia.

#### Risiko Pelanggaran Hak Cipta

**Masalah 1**: Model generative AI mungkin dilatih dengan data yang dilindungi oleh:
- Hak cipta (copyrights)
- Paten (patents)
- Merek dagang (trademarks)

Data ini kemudian dapat disertakan dalam output.

**Masalah 2**: Pengguna dapat mengirimkan karya berhak cipta sebagai input, dan generative AI dapat membuat turunan tanpa lisensi.

**Kasus Nyata - Getty Images vs Stable Diffusion (2023)**:
- Getty Images menggugat pembuat Stable Diffusion
- Stable Diffusion adalah model generative AI text-to-image
- Tuduhan: Melanggar penggunaan lebih dari 12 juta foto
- Termasuk caption dan metadata terkait dalam membangun model

### 3. Discriminatory Bias (Bias Diskriminatif)

**Risiko**: Output model yang bias dapat menyebabkan perlakuan diskriminatif atau tidak adil terhadap individu atau kelompok.

**Kasus Nyata - Equal Employment Opportunity Commission**:
- Menggugat tiga perusahaan
- Menggunakan program perekrutan AI yang mendiskriminasi pelamar yang lebih tua
- Program secara otomatis menolak pelamar jika:
  - Wanita berusia di atas 55 tahun
  - Pria berusia di atas 60 tahun

### 4. Toxic Content (Konten Beracun)

**Kemampuan**: Model generative AI mampu menghasilkan konten yang ofensif, mengganggu, atau bahkan cabul jika konten tersebut ada dalam data pelatihan mereka.

**Dampak Nyata**:
- Masalah kesehatan mental dan emosional pengguna
- Peningkatan kecenderungan kekerasan terhadap individu tertentu
- Kekerasan terhadap kelompok marginal

### 5. Data Privacy (Privasi Data)

**Risiko**: Data sensitif yang masuk ke dalam large language model dapat bocor dan dimasukkan ke dalam outputnya.

**Jenis Informasi yang Berisiko**:
- PII (Personally Identifiable Information)
- Kekayaan intelektual
- Rahasia dagang
- Catatan kesehatan

**Cara Masuknya Data**:
- Ada dalam data pelatihan
- Di-input sebagai prompt oleh pengguna

**Masalah Fundamental**: Setelah FM dilatih atau melihat beberapa data, Anda tidak bisa membuatnya lupa dengan menghapus data tersebut.

### 6. Reputational Damage (Kerusakan Reputasi)

Semua risiko di atas dapat mengakibatkan:
- Hilangnya kepercayaan pelanggan
- Kerusakan reputasi karena praktik AI yang tidak bertanggung jawab
- Konsekuensi yang tidak diinginkan

## Amazon Bedrock Guardrails: Perlindungan untuk Foundation Models

### Apa itu Guardrails?

Untuk foundation models di Amazon Bedrock, Anda dapat mengkonfigurasi **guardrails** untuk memfilter dan memblokir konten yang tidak pantas.

### Fitur Content Filters

Anda dapat menggunakan guardrails untuk mendefinisikan ambang batas untuk filter konten:
- **Hate** (Kebencian)
- **Insults** (Penghinaan)
- **Sexual content** (Konten seksual)
- **Violence** (Kekerasan)

### Topic Blocking

Anda juga dapat memblokir topik sepenuhnya:
- Gunakan plaintext untuk mendeskripsikan topik yang harus ditolak
- Definisikan topik-topik yang tidak boleh dibahas oleh model

### Cara Kerja Guardrails

```
User Prompt
    ↓
┌─────────────────┐
│   Guardrails    │ ← Cek prompt
│   (Prompt)      │
└─────────────────┘
    ↓
    ├─→ Tidak Lolos → Violation Response (ke User)
    │
    ↓ Lolos
┌─────────────────┐
│  Foundation     │
│     Model       │
└─────────────────┘
    ↓
┌─────────────────┐
│   Guardrails    │ ← Cek response
│   (Response)    │
└─────────────────┘
    ↓
    ├─→ Tidak Lolos → Blocked
    │
    ↓ Lolos
Response ke User
```

**Poin Penting**:
1. Ketika pengguna mengirimkan prompt, harus melewati guardrails terlebih dahulu
2. Jika prompt tidak diizinkan, pengguna menerima respons pelanggaran yang Anda konfigurasi
3. Prompt tidak pernah sampai ke model
4. Guardrails dapat diatur pada prompt DAN respons model
5. Jika prompt lolos guardrail, respons masih bisa diblokir

## SageMaker Clarify: Evaluasi Large Language Models

### Fitur Evaluation Jobs

SageMaker Clarify memiliki kemampuan untuk menjalankan **evaluation jobs** dari large language models sehingga Anda dapat membandingkan model.

### Jenis Task yang Didukung

Dapat menjalankan empat jenis task berbeda:
1. **Text Generation** (Generasi Teks)
2. **Text Classification** (Klasifikasi Teks)
3. **Question and Answering** (Tanya Jawab)
4. **Text Summarization** (Ringkasan Teks)

### Lima Dimensi Evaluasi

#### 1. Prompt Stereotyping

**Fungsi**: Mengukur probabilitas model Anda menyertakan bias dalam responsnya

**Jenis Bias yang Diukur**:
- Ras
- Gender
- Orientasi seksual
- Agama
- Usia
- Kewarganegaraan
- Disabilitas
- Penampilan fisik
- Status sosial ekonomi

#### 2. Toxicity (Toksisitas)

**Memeriksa model untuk**:
- Referensi seksual
- Komentar kasar, tidak masuk akal, penuh kebencian, atau agresif
- Kata-kata kotor
- Penghinaan
- Rayuan
- Serangan terhadap identitas
- Ancaman

#### 3. Factual Knowledge (Pengetahuan Faktual)

**Fungsi**: Memeriksa kebenaran respons model

**Tujuan**: Mendeteksi halusinasi dan memastikan informasi yang akurat

#### 4. Semantic Robustness (Ketahanan Semantik)

**Fungsi**: Memeriksa apakah output model berubah karena:
- Typo kata kunci
- Perubahan acak ke huruf besar
- Penambahan atau penghapusan acak spasi putih

**Tujuan**: Memastikan model tetap konsisten meskipun ada variasi kecil dalam input

#### 5. Accuracy (Akurasi)

**Fungsi**: Membandingkan output model dengan respons yang diharapkan

**Contoh**:
- Mengklasifikasikan data dengan benar
- Meringkas data dengan benar

### Opsi Dataset dan Workforce

#### Dataset
- Gunakan **built-in prompt dataset** yang disediakan
- Atau **supply your own** (sediakan dataset Anda sendiri)

#### Human Workforce
Anda dapat mendapatkan workforce manusia untuk memberikan feedback:
- Karyawan
- Subject matter experts (ahli materi pelajaran)

## Amazon Bedrock: Evaluasi Pre-trained LLMs

### Kemampuan yang Sama di Bedrock Console

Jika Anda menggunakan Amazon Bedrock, kemampuan evaluasi yang sama tersedia di **Bedrock console** untuk membantu mengevaluasi pre-trained LLMs di Amazon Bedrock.

### Keuntungan

- Interface yang user-friendly
- Evaluasi model tanpa perlu coding
- Perbandingan model yang mudah
- Metrik yang sama dengan SageMaker Clarify

## Kesimpulan

Pengembangan sistem AI yang bertanggung jawab adalah aspek kritis dalam implementasi AI modern. Dengan memahami dan menerapkan prinsip-prinsip responsible AI, menggunakan alat seperti SageMaker Clarify dan Amazon Bedrock Guardrails, serta secara proaktif mengidentifikasi dan mengatasi bias, kita dapat membangun sistem AI yang tidak hanya powerful tetapi juga adil, transparan, dan dapat dipercaya.

**Poin-poin Kunci untuk Diingat**:

1. Responsible AI mencakup enam dimensi utama: Fairness, Explainability, Robustness, Privacy & Security, Governance, dan Transparency

2. Bias dalam dataset pelatihan akan menjadi bias dalam output - oleh karena itu dataset yang bertanggung jawab adalah fondasi

3. Class imbalance adalah penyebab utama bias model

4. SageMaker Clarify membantu mendeteksi dan mengukur bias pada berbagai tahap: persiapan data, setelah pelatihan, dan pada model yang di-deploy

5. Generative AI memiliki risiko khusus: halusinasi, masalah kekayaan intelektual, bias diskriminatif, konten beracun, dan privasi data

6. Amazon Bedrock Guardrails memberikan perlindungan dengan memfilter prompt dan respons yang tidak pantas

7. Evaluasi berkelanjutan menggunakan metrik seperti prompt stereotyping, toxicity, factual knowledge, semantic robustness, dan accuracy sangat penting

Dengan pemahaman yang mendalam tentang konsep-konsep ini, Anda akan siap untuk mengembangkan dan mengelola sistem AI yang bertanggung jawab di AWS.
