# Kemampuan dan Keterbatasan Generative AI untuk Menyelesaikan Masalah Bisnis

## Pengantar

**Generative AI** dan **Large Language Models (LLM)** merupakan **general-purpose technology** yang memiliki banyak kegunaan di berbagai sektor ekonomi. Sama seperti teknologi serbaguna lainnya seperti **deep learning**, generative AI tidak hanya berguna untuk satu aplikasi saja, tetapi untuk berbagai aplikasi yang berbeda yang mencakup banyak sudut ekonomi.

Dalam kehidupan sehari-hari, kita hampir selalu menggunakan AI:
- Setiap kali melakukan web search, itu adalah AI
- Setiap kali menggunakan kartu kredit, ada AI yang memeriksa apakah benar-benar Anda yang menggunakannya
- Setiap kali mengunjungi amazon.com, AI merekomendasikan produk untuk Anda

Banyak sistem AI telah kompleks dan mahal untuk dibangun. Namun, **generative AI** membuat banyak aplikasi AI menjadi jauh lebih mudah untuk dibangun dengan biaya yang lebih rendah dan lebih cepat.

## Keunggulan Generative AI

### 1. Adaptabilitas (Adaptability)
**Generative AI** dapat menyesuaikan diri dengan berbagai kebutuhan dan konteks bisnis yang berbeda. Model dapat dimodifikasi untuk menyesuaikan dengan domain dan tugas spesifik dengan cara:
- Menyesuaikan algoritma (adjusting algorithms)
- Mengubah struktur model (model structures)

### 2. Responsivitas (Responsiveness)
Teknologi ini mampu memberikan respons yang cepat terhadap berbagai permintaan dan situasi. **Foundation models** dapat menghasilkan berbagai output berdasarkan prompt dengan tingkat akurasi yang tinggi.

### 3. Kesederhanaan (Simplicity)
Banyak sistem AI telah kompleks dan mahal untuk dibangun. Namun, **generative AI** membuat banyak aplikasi AI menjadi jauh lebih mudah untuk dibangun. Generative AI dapat membantu bisnis Anda membangun aplikasi AI yang berharga dengan biaya yang lebih rendah dan lebih cepat.

### Manfaat untuk Bisnis
- **Biaya lebih rendah**: Membangun aplikasi AI yang berharga dengan biaya yang lebih efisien
- **Pengembangan lebih cepat**: Mempercepat proses pengembangan aplikasi AI
- **Aksesibilitas**: Membuat teknologi AI lebih mudah diakses oleh berbagai organisasi
- **Fleksibilitas**: Dapat digunakan untuk berbagai aplikasi yang mencakup banyak sektor ekonomi

## Memahami Kemampuan LLM dengan Analogi Sederhana

### Tes "Anak 10 Tahun"
Untuk memahami apa yang bisa dilakukan oleh **LLM** melalui **prompting**, gunakan pertanyaan ini:

> "Bisakah saya sebagai anak berusia 10 tahun mengikuti instruksi dalam prompt dan menyelesaikan tugas tersebut?"

#### Contoh yang Bisa Dilakukan:
**Tugas**: Membaca email dan menentukan apakah email tersebut adalah keluhan.
- **Jawaban**: Ya, kebanyakan orang (termasuk anak 10 tahun) bisa melakukan ini
- **Kesimpulan**: LLM juga bisa melakukan tugas ini

#### Contoh yang Tidak Bisa Dilakukan:
**Tugas**: Menulis artikel tentang layanan AWS baru tanpa informasi apapun tentang layanan tersebut.
- **Jawaban**: Tidak, kita hanya bisa menulis dokumen generik tanpa detail spesifik
- **Solusi**: Jika kita membaca blog post atau press release tentang topik tersebut, maka kita (dan LLM) bisa menulis dokumen dengan detail yang lebih baik

### Keterbatasan Memori LLM
**Penting untuk dipahami**: Setiap kali Anda melakukan **prompting** pada LLM, model tersebut **tidak mengingat percakapan sebelumnya**. Ini seperti meminta bantuan anak yang berbeda untuk setiap tugas.

**Implikasi**:
- LLM tidak bisa "dilatih" dari waktu ke waktu tentang spesifikasi bisnis Anda
- LLM tidak bisa belajar gaya penulisan yang Anda inginkan melalui percakapan biasa
- **Solusi**: Gunakan **fine-tuning** untuk melatih model dengan kebutuhan spesifik Anda

## Fine-Tuning dengan Instruksi

### Tujuan Fine-Tuning
**Fine-tuning** dengan instruksi bertujuan untuk:
1. Melatih model lebih lanjut agar lebih memahami prompt yang mirip dengan bahasa manusia
2. Menghasilkan respons yang lebih mirip dengan respons manusia
3. Meningkatkan performa model secara berkelanjutan dibandingkan versi **pre-trained** aslinya
4. Menghasilkan bahasa yang lebih natural

### Fine-Tuning dengan Human Feedback
Untuk menyelaraskan model dengan preferensi manusia dan meningkatkan tiga nilai penting dalam **responsible AI**, kita dapat menambahkan **fine-tuning dengan human feedback**. Pelatihan lebih lanjut ini dapat:
- Meningkatkan **helpfulness**, **honesty**, dan **harmlessness** dari completion
- Mengurangi **toxicity**
- Mengurangi generasi informasi yang salah
- Menyelaraskan model dengan preferensi manusia dengan lebih baik

## Keterbatasan dan Tantangan Generative AI

### 1. Bahasa Toxic dan Perilaku Buruk
**Masalah yang Sering Terjadi**:
- Model menggunakan bahasa **toxic** dalam responsnya
- Memberikan balasan dengan nada agresif dan **combative**
- Menyediakan informasi detail tentang topik berbahaya

**Penyebab**:
Model besar dilatih dengan jumlah data teks yang sangat besar dari internet, di mana bahasa seperti ini sering muncul.

### 2. Halusinasi (Hallucination)
**Definisi**: **Hallucination** adalah ketika LLM memberikan jawaban yang menyesatkan atau salah dengan penuh percaya diri.

**Contoh Kasus**:
- **Pertanyaan**: Tentang saran kesehatan yang sudah terbukti salah untuk penderita diabetes (misalnya, diet fokus karbohidrat adalah kunci kesehatan yang baik)
- **Respons yang Diharapkan**: Model seharusnya membantah informasi yang salah tersebut
- **Respons yang Mungkin Terjadi**: Model memberikan respons yang percaya diri tetapi **sepenuhnya salah**

**Penyebab**: 
LLM dapat memberikan jawaban yang menyesatkan atau tidak benar karena model besar dilatih dengan jumlah data teks yang sangat besar dari internet, di mana informasi yang salah atau menyesatkan sering muncul.

**Solusi**:
Untuk mendapatkan jawaban yang benar, Anda harus **double check** jawaban dengan sumber yang **authoritative** sebelum mengandalkannya.

### 3. Konten Berbahaya
LLM tidak boleh membuat **completion** yang berbahaya, seperti:
- Konten yang **offensive** (menyinggung)
- Konten yang **diskriminatif**
- Konten yang mendorong **illicit criminal behavior** (perilaku kriminal)

**Penyebab**: Masalah ini ada karena model besar dilatih dengan jumlah data teks yang sangat besar dari internet di mana bahasa seperti ini sering muncul.

### 4. Nondeterminism (Ketidakdeterministikan)
**Karakteristik**: Berbeda dengan **machine learning** tradisional yang deterministik, LLM memiliki karakteristik:
- Output bersifat **non-deterministik**
- Evaluasi berbasis bahasa lebih menantang
- Tidak bisa hanya menggunakan metrik sederhana seperti **accuracy**

**Implikasi**: Setiap kali Anda melakukan **prompting** pada LLM, hasilnya mungkin berbeda meskipun menggunakan prompt yang sama.

## Tiga Nilai Penting dalam AI yang Bertanggung Jawab

### 1. Helpfulness (Kegunaan)
AI harus memberikan bantuan yang berguna dan relevan.

### 2. Honesty (Kejujuran)
AI harus memberikan informasi yang akurat dan jujur.

### 3. Harmlessness (Tidak Berbahaya)
AI tidak boleh menyebabkan kerugian atau bahaya.

**Catatan**: Prinsip-prinsip ini merupakan seperangkat prinsip yang memandu pengembang dalam penggunaan AI yang bertanggung jawab. Prinsip-prinsip ini akan dibahas lebih dalam di Domain 4 tentang **Responsible AI**.

## Interpretabilitas Model (Model Interpretability)

### Definisi
**Interpretability** adalah kemudahan untuk memahami prediksi yang dibuat oleh model **machine learning**.

### Trade-off yang Perlu Dipertimbangkan
Ketika memilih model atau algoritma, pertimbangkan **interpretability**. Semakin tinggi interpretabilitas model machine learning, semakin mudah untuk memahami prediksi model, tetapi ada **trade-off** yang perlu dipertimbangkan:

- **Model Performance**: Apa yang diprediksi oleh model
- **Model Interpretability**: Mengapa model membuat prediksi tersebut

### Metode Interpretabilitas Model

#### 1. Intrinsic Analysis (Analisis Intrinsik)
**Karakteristik**:
- Diterapkan pada model dengan kompleksitas rendah
- Model memiliki hubungan sederhana antara variabel input dan prediksi
- Interpretabilitas tinggi tetapi performa mungkin lebih rendah

**Keterbatasan**:
Algoritma tidak mampu menangkap interaksi **non-linear** yang kompleks.

#### 2. Post Hoc Analysis (Analisis Post Hoc)
**Karakteristik**:
- Dapat diterapkan pada model sederhana dan model kompleks (seperti **neural networks**)
- Mampu menangkap interaksi **non-linear**
- Sering bersifat **model agnostic** (tidak tergantung pada jenis model tertentu)
- Menyediakan mekanisme untuk menginterpretasi model yang sudah dilatih berdasarkan input dan output prediksi

**Tingkat Analisis**:
- **Local Level**: Zoom in pada satu data point tunggal
- **Global Level**: Zoom out dan melihat perilaku keseluruhan model

## Metrik Evaluasi untuk Large Language Models

### Tantangan Evaluasi LLM
Pengembang **large language models** menggunakan metrik spesifik untuk menilai performa model dan membandingkannya dengan model lain di dunia. Dalam **machine learning** tradisional, Anda dapat menilai seberapa baik model berkinerja pada **training** dan **validation datasets** di mana output sudah diketahui, dan dapat menghitung metrik dasar seperti **accuracy** yang menyatakan fraksi dari semua prediksi yang benar karena model bersifat deterministik.

Namun dengan **large language models**, output bersifat **non-deterministik** dan evaluasi berbasis bahasa jauh lebih menantang.

### Contoh Kompleksitas Evaluasi
Pertimbangkan dua kalimat ini:
- "I drink coffee" (Saya minum kopi)
- "I do not drink coffee" (Saya tidak minum kopi)

Sebagai manusia, kita dapat melihat dan memahami perbedaan dan persamaannya juga, tetapi ketika Anda melatih model dengan jutaan kalimat, Anda memerlukan cara otomatis dan terstruktur untuk melakukan pengukuran.

### Metrik Evaluasi Utama

#### 1. ROUGE (Recall-Oriented Understudy for Gisting Evaluation)
**Kegunaan**: Menilai kualitas ringkasan yang dihasilkan secara otomatis

**Cara Kerja**: Membandingkan ringkasan yang dihasilkan mesin dengan ringkasan referensi yang dibuat manusia

**Aplikasi**: Terutama untuk tugas **summarization** (peringkasan)

#### 2. BLEU (Bilingual Evaluation Understudy)
**Kegunaan**: Algoritma yang dirancang untuk mengevaluasi kualitas teks hasil terjemahan mesin

**Cara Kerja**: Membandingkan terjemahan mesin dengan terjemahan yang dibuat manusia

**Aplikasi**: Terutama untuk tugas **machine translation** (terjemahan mesin)

**Catatan**: **ROUGE** dan **BLEU** adalah dua metrik evaluasi yang banyak digunakan untuk tugas yang berbeda. Pembahasan lebih detail tentang ROUGE dan BLEU akan dilanjutkan di **task statement 3.4**.


## Pemilihan Model Generative AI yang Tepat

### Faktor-Faktor yang Perlu Dipertimbangkan
Bagaimana Anda memilih arsitektur model yang tepat untuk memastikan kesuksesan proyek **generative AI** Anda? Saat memilih model **generative AI** yang sesuai, pertimbangkan berbagai faktor seperti:

1. **Model Type** (Tipe Model)
2. **Performance** (Performa)  
3. **Requirements** (Kebutuhan)
4. **Capabilities** (Kemampuan)
5. **Constraints** (Batasan)
6. **Compliance** (Kepatuhan)

### Pentingnya Pemilihan Model yang Tepat
Ketika berbicara tentang **data generation**, penting untuk memilih model yang paling sesuai karena dapat secara signifikan mempengaruhi kualitas data. Setiap model memiliki kelebihan dan kekurangan tergantung pada kompleksitas dan kualitas data yang diinginkan.

### Jenis Konten yang Dapat Dihasilkan Foundation Models
**Generative AI foundation models** dirancang untuk menghasilkan berbagai jenis konten, seperti:
- **Text dan Chat**: Percakapan dan teks tertulis
- **Images**: Gambar dan visual
- **Code**: Kode pemrograman
- **Video**: Konten video
- **Embeddings**: Representasi vektor dari data

### Modifikasi Model
Anda dapat memodifikasi model-model ini untuk menyesuaikan dengan domain dan tugas spesifik dengan cara:
- Menyesuaikan algoritma (**adjusting the algorithms**)
- Mengubah struktur model (**model structures**)

## Model-Model Generative AI untuk Data Generation

Model yang paling banyak digunakan untuk **data generation** adalah:

### 1. VAE (Variational Autoencoder)
**Karakteristik**:
- Salah satu model yang paling banyak digunakan
- Cocok untuk kasus penggunaan tertentu

### 2. GAN (Generative Adversarial Networks)
**Karakteristik**:
- Model yang sangat populer
- Menggunakan dua **neural networks** yang saling berkompetisi

### 3. Autoregressive Models
**Karakteristik**:
- Menghasilkan data secara berurutan
- Efektif untuk berbagai jenis data

### Pertimbangan Pemilihan Model
**Penting**: Setiap model memiliki kelebihan dan kekurangan tergantung pada:
- Kompleksitas data
- Kualitas data yang diinginkan

**Catatan**: Ini hanya beberapa jenis model **generative AI** dan penelitian serta pengembangan yang berkelanjutan menghasilkan model generative yang lebih baru dan lebih canggih.

## Perkembangan Foundation Models

### Pertumbuhan Pesat
- Jumlah dan ukuran **foundation models** di pasar telah tumbuh dengan sangat cepat
- Puluhan model sekarang tersedia
- Menurut AWS, daftar **prominent foundation models** yang dirilis sejak 2018 terus bertambah

### Karakteristik Foundation Models
**Definisi**: **Foundation models** adalah model yang dilatih dengan **huge, unlabeled broad datasets** (dataset yang sangat besar, tidak berlabel, dan luas), yang menjadi dasar kemampuan **generative AI**.

**Perbedaan dengan ML Tradisional**:
- **Ukuran**: Secara signifikan lebih besar daripada model **machine learning** tradisional
- **Fungsi**: Model ML tradisional umumnya digunakan untuk fungsi yang lebih spesifik
- **Penggunaan**: FMs digunakan sebagai **baseline starting point** untuk mengembangkan dan membuat model

### Kemampuan Foundation Models
**Foundation models** dapat digunakan untuk:
- Menginterpretasi dan memahami bahasa (**interpret and understand language**)
- Melakukan **conversational messaging** (percakapan)
- Membuat dan menghasilkan gambar (**create and generate images**)
- Menghasilkan berbagai output berdasarkan prompt dengan tingkat akurasi tinggi

### Spesialisasi Model
Berbagai **foundation models** memiliki spesialisasi di area yang berbeda:

**Contoh**:
- **Stable Diffusion** (by Stability AI): Sangat baik untuk **image generation**
- **GPT-4**: Digunakan oleh ChatGPT untuk **natural language processing**

## Metrik Bisnis untuk Aplikasi Generative AI

### Pentingnya Metrik Bisnis
Untuk memastikan kesuksesan aplikasi **generative AI**, kita perlu memahami metrik atau **Key Performance Indicators (KPIs)** yang tepat untuk mengevaluasi performa, dampak, dan kesuksesan aplikasi **generative AI** kita.

### Jenis-Jenis Metrik Bisnis

Contoh metrik bisnis untuk aplikasi **generative AI** meliputi:

#### 1. Cross-Domain Performance
Mengevaluasi transfer dan aplikasi pengetahuan serta keterampilan di berbagai domain untuk menghasilkan atau memprediksi data dan konten lintas domain.

#### 2. Efficiency (Efisiensi)
Mengukur seberapa efisien sistem bekerja dalam menghasilkan output.

#### 3. Conversion Rate (Tingkat Konversi)
Persentase pengguna yang melakukan tindakan yang diinginkan.

#### 4. Average Revenue Per User (ARPU)
Rata-rata pendapatan yang dihasilkan per pengguna.

#### 5. Accuracy (Akurasi)
Tingkat ketepatan output yang dihasilkan.

#### 6. Customer Lifetime Value (CLTV)
Nilai total yang diharapkan dari seorang pelanggan selama hubungan mereka dengan bisnis.

### Manfaat Tracking Metrik
Dengan melacak, memantau, dan menganalisis metrik bisnis yang tepat, Anda dapat:
- **Belajar dari masa lalu**: Memahami apa yang berhasil dan tidak berhasil
- **Memantau masa kini**: Melihat performa saat ini secara real-time
- **Merencanakan masa depan**: Membuat keputusan strategis berdasarkan data

**Kompleksitas Analisis**: Menganalisis sejumlah besar data bisnis untuk meramalkan nilai masa depan atau mendeteksi **outlier** dan memahami akar penyebabnya adalah kompleks, memakan waktu, dan tidak selalu akurat.

## Tantangan dan Peluang Foundation Models

### Tantangan Utama

**Foundation models** menciptakan peluang dan tantangan bagi organisasi. Beberapa di antaranya adalah:

#### 1. Kualitas Output
**Masalah**:
- Memastikan **high-quality outputs** yang selaras dengan kebutuhan bisnis
- Meminimalkan **hallucinations** atau informasi palsu

**Pentingnya**: Kualitas output dari FMs akan menentukan adopsi dan penggunaan, terutama dalam aplikasi yang berhadapan langsung dengan pelanggan seperti **chatbots**.

#### 2. Integrasi dengan Sistem Bisnis
**Kebutuhan**: Agar benar-benar berguna dalam konteks **enterprise**, FMs perlu:
- Terintegrasi dan beroperasi dengan sistem bisnis yang ada dan **workflows**
- Mengakses data dari **databases**
- Menggunakan sistem **ERP (Enterprise Resource Planning)**
- Menggunakan sistem **CRM (Customer Relationship Management)**

#### 3. Kebutuhan Sumber Daya
**Untuk mendapatkan nilai bisnis yang nyata, organisasi memerlukan**:
- **Keterampilan Teknis**: Karyawan dengan keterampilan teknis yang kuat untuk mengimplementasikan, menyesuaikan, dan memelihara FMs
- **Sumber Daya Komputasi**: Sumber daya komputasi dan infrastruktur untuk deploy model secara **cost-effective**
- **Memastikan Nilai**: Memastikan bahwa pelanggan menerima nilai dari implementasi

### Peluang
**Foundation models** menciptakan peluang besar untuk:
- Otomasi proses bisnis
- Peningkatan produktivitas
- Inovasi produk dan layanan
- Pengalaman pelanggan yang lebih baik

## Metrik Kualitas Output

**Output quality metrics** meliputi:

### 1. Relevance (Relevansi)
Seberapa relevan output dengan kebutuhan atau pertanyaan pengguna.

### 2. Accuracy (Akurasi)
Tingkat ketepatan dan kebenaran informasi yang dihasilkan.

### 3. Coherence (Koherensi)
Seberapa logis dan konsisten output yang dihasilkan.

### 4. Appropriateness (Kesesuaian)
Seberapa sesuai output dengan konteks dan situasi.

**Hasil**: Semua metrik ini berkontribusi pada **overall user satisfaction** (kepuasan pengguna secara keseluruhan).

### Pengukuran Kualitas Output
Kualitas output Anda harus diukur dengan standar yang telah ditentukan sebelumnya untuk memastikan bahwa sistem AI memenuhi persyaratan efisiensi.

## Metrik Efisiensi

### Dampak pada Workflow
**Efficiency** berdampak pada **generative AI workflow** dan dapat dilacak dengan metrik seperti:

#### 1. Task Completion Rates (Tingkat Penyelesaian Tugas)
Persentase tugas yang berhasil diselesaikan oleh sistem.

#### 2. Reduction in Manual Efforts (Pengurangan Upaya Manual)
Seberapa banyak pekerjaan manual yang dapat dikurangi.

**Kontribusi**: Memberikan kontribusi langsung pada **operational productivity** (produktivitas operasional).

#### 3. Error Rate (Tingkat Kesalahan)
**Pentingnya**: Tingkat kesalahan yang rendah membantu menjaga:
- Akurasi aplikasi AI
- Kredibilitas aplikasi AI

## Evaluasi Return on Investment (ROI)

### Pertimbangan Finansial
Organisasi perlu mengevaluasi:
- **Potential ROI**: Return on investment yang diharapkan
- **Cost vs Benefits**: Menimbang biaya dan manfaat dari FMs
- **Aplikasi**: Mempertimbangkan konteks aplikasi spesifik

### Metrik untuk Perbandingan
Penting untuk memahami metrik untuk membandingkan:
- **Operational Costs**: Biaya operasional
- **Efficiencies Gained**: Efisiensi yang diperoleh

## Strategi Memaksimalkan Customer Lifetime Value (CLTV)

CLTV adalah metrik kunci untuk scaling bisnis Anda. Apa saja strategi untuk memaksimalkan customer lifetime value?

### 1. Loyalty Programs (Program Loyalitas)
Memberikan insentif kepada pelanggan setia.

### 2. Creating Brand Loyalty (Membangun Loyalitas Merek)
Membangun hubungan jangka panjang dengan pelanggan.

### 3. Collecting Feedback (Mengumpulkan Feedback)
Mendengarkan dan merespons masukan pelanggan.

### 4. Cross-Selling
Menawarkan produk atau layanan tambahan yang relevan.

### 5. Personalized Experiences (Pengalaman Personal)
Menyesuaikan pengalaman dengan preferensi individual pelanggan.

### Metrik untuk Cross-Domain Performance
Anda juga memerlukan metrik untuk **cross-domain performance** untuk mengevaluasi transfer dan aplikasi pengetahuan serta keterampilan di berbagai domain untuk menghasilkan atau memprediksi data dan konten lintas domain.

## Evolusi dan Pemantauan Berkelanjutan

### Pentingnya Evaluasi Berkelanjutan
**Ingat**: AI terus berkembang, oleh karena itu pastikan Anda:

1. **Measure (Mengukur)**: Mengukur performa model secara teratur
2. **Monitor (Memantau)**: Memantau metrik secara real-time
3. **Review (Meninjau)**: Meninjau hasil dan temuan
4. **Reevaluate (Mengevaluasi Ulang)**: Mengevaluasi ulang model secara berkala

**Tujuan**: Memastikan bahwa Anda memenuhi persyaratan dan tujuan bisnis Anda.

## Evolusi dan Pemantauan Berkelanjutan

### Pentingnya Evaluasi Berkelanjutan
**Ingat**: AI terus berkembang, oleh karena itu pastikan Anda:

1. **Measure (Mengukur)**: Mengukur performa model secara teratur
2. **Monitor (Memantau)**: Memantau metrik secara real-time
3. **Review (Meninjau)**: Meninjau hasil dan temuan
4. **Reevaluate (Mengevaluasi Ulang)**: Mengevaluasi ulang model secara berkala

**Tujuan**: Memastikan bahwa Anda memenuhi persyaratan dan tujuan bisnis Anda.

## Ringkasan Poin-Poin Penting

### Kemampuan Generative AI
✅ **General-purpose technology** dengan banyak aplikasi di berbagai sektor ekonomi
✅ **Adaptability**: Dapat menyesuaikan dengan berbagai kebutuhan bisnis
✅ **Responsiveness**: Memberikan respons cepat dengan akurasi tinggi
✅ **Simplicity**: Lebih mudah dan murah dibandingkan sistem AI tradisional
✅ Dapat menghasilkan berbagai jenis konten (text, images, code, video, embeddings)

### Keterbatasan Generative AI
❌ **Non-deterministic**: Output berbeda meskipun prompt sama
❌ **Hallucinations**: Dapat menghasilkan informasi yang salah dengan percaya diri
❌ **Toxic content**: Mungkin menghasilkan konten berbahaya atau diskriminatif
❌ **No memory**: Tidak mengingat percakapan sebelumnya tanpa fine-tuning
❌ Memerlukan validasi dengan sumber **authoritative**

### Model Selection Factors
- **Model Type**: VAE, GAN, Autoregressive models
- **Performance**: Akurasi dan kualitas output
- **Requirements**: Kebutuhan bisnis spesifik
- **Capabilities**: Kemampuan model untuk tugas tertentu
- **Constraints**: Batasan teknis dan sumber daya
- **Compliance**: Kepatuhan terhadap regulasi

### Business Metrics
- **Cross-domain performance**
- **Efficiency** dan **task completion rates**
- **Conversion rate** dan **ARPU**
- **Accuracy** dan **CLTV**
- **Output quality metrics**: relevance, accuracy, coherence, appropriateness

### Evaluation Metrics
- **ROUGE**: Untuk **summarization** tasks
- **BLEU**: Untuk **machine translation** tasks
- **Interpretability**: Trade-off antara performance dan explainability

### Best Practices
1. Gunakan tes "anak 10 tahun" untuk memahami kemampuan LLM
2. Selalu **double check** jawaban dengan sumber yang dapat dipercaya
3. Implementasikan **fine-tuning** untuk kebutuhan spesifik
4. Terapkan **fine-tuning dengan human feedback** untuk meningkatkan kualitas
5. Pilih model yang sesuai dengan **model selection factors**
6. Ukur dan pantau **business metrics** secara berkelanjutan
7. Evaluasi **ROI** dan **cost-benefit** secara teratur
8. **Measure, monitor, review, dan reevaluate** model secara berkala

### Prinsip Responsible AI
- **Helpfulness**: Memberikan bantuan yang berguna dan relevan
- **Honesty**: Memberikan informasi yang akurat dan jujur
- **Harmlessness**: Tidak menyebabkan kerugian atau bahaya

---

**Catatan**: Materi ini merupakan bagian dari persiapan ujian **AWS Certified AI Practitioner (AIF-C01)** Domain 2 - **Task Statement 2.2** tentang memahami kemampuan dan keterbatasan **generative AI** untuk menyelesaikan masalah bisnis. Konten ini diintegrasikan dari **material transcript 2-2** yang mencakup advantages, limitations, model selection factors, business metrics, dan evaluation methods.
