# Konsep Dasar AI dan Terminologi

## Pengantar

Domain 1 dari AWS Certified AI Practitioner berfokus pada pemahaman konsep-konsep dasar kecerdasan buatan (Artificial Intelligence/AI) dan terminologi yang digunakan dalam ekosistem AI. Materi ini mencakup **Task Statement 1.1: Explain basic AI concepts and terminologies** berdasarkan material transcript resmi dari AWS Skill Builder course.

**Sumber Material:** material-transcript-1-1.txt (5 lessons)
**Exam Weight:** 20% dari total ujian
**AWS Services Covered:** Amazon Bedrock, SageMaker Ground Truth, Amazon Mechanical Turk, AWS DeepRacer

## 1. Apa itu Artificial Intelligence (AI)?

**Artificial Intelligence (AI)** adalah bidang ilmu komputer yang didedikasikan untuk menyelesaikan masalah kognitif yang umumnya dikaitkan dengan kecerdasan manusia, seperti:
- **Learning (Pembelajaran)** - Sistem dapat belajar dari data
- **Creation (Kreasi)** - Menghasilkan konten original
- **Image Recognition (Pengenalan Gambar)** - Memproses dan memahami visual data

### Tujuan AI

Tujuan utama AI adalah menciptakan **self-learning system** yang dapat mengambil makna dari data. Sistem AI modern seperti Alexa dan ChatGPT dapat:
- Merespons pertanyaan dengan bermakna
- Menciptakan konten original seperti teks dan gambar
- Memproses data dalam jumlah besar dengan kecepatan tinggi

### Keunggulan AI

1. **Konsistensi Performa 24/7**: AI dapat bekerja sepanjang waktu tanpa penurunan performa, tidak seperti manusia yang memerlukan istirahat.

2. **Pemrosesan Data Cepat**: AI dapat memproses data dalam jumlah besar dengan sangat cepat, memungkinkan penyelesaian masalah kompleks seperti deteksi fraud secara real-time.

3. **Otomasi Tugas Repetitif**: AI dapat melakukan tugas-tugas yang berulang dan monoton, meningkatkan efisiensi bisnis dengan membebaskan karyawan untuk melakukan pekerjaan yang lebih kreatif.

4. **Pengenalan Pola dan Prediksi**: AI sangat powerful dalam menemukan pola dalam data dan memperkirakan tren, membantu bisnis membuat keputusan yang lebih cerdas dan bereaksi lebih cepat terhadap masalah.

## 2. Machine Learning (ML)

**Machine Learning** adalah cabang dari AI dan ilmu komputer yang berfokus pada penggunaan data dan algoritma untuk meniru cara manusia belajar. ML secara bertahap meningkatkan akurasinya untuk membangun sistem komputer yang belajar dari data.

### Karakteristik Machine Learning

- Model ML dilatih menggunakan dataset besar untuk mengidentifikasi pola dan membuat prediksi
- Contoh aplikasi: rekomendasi produk untuk pelanggan yang berbelanja online
- ML adalah ilmu mengembangkan algoritma dan model statistik yang digunakan sistem komputer untuk melakukan tugas kompleks tanpa instruksi eksplisit

### Cara Kerja Machine Learning

1. **Input Data**: Algoritma ML menerima data sebagai input
2. **Training**: Algoritma dilatih dengan data yang sudah diketahui (known data) yang terdiri dari fitur-fitur
3. **Identifikasi Korelasi**: Algoritma mencari korelasi antara fitur data input dan output yang diharapkan
4. **Penyesuaian Parameter**: Parameter internal model disesuaikan hingga model dapat menghasilkan output yang diharapkan secara konsisten
5. **Inference**: Model yang sudah terlatih dapat membuat prediksi akurat dari data baru yang belum pernah dilihat saat training

## 3. Deep Learning

**Deep Learning** adalah jenis model machine learning yang terinspirasi dari otak manusia, menggunakan lapisan-lapisan neural networks untuk memproses informasi.

### Kemampuan Deep Learning

- Mengenali ucapan manusia
- Mengenali objek dalam gambar
- Pemrosesan bahasa alami yang kompleks
- Klasifikasi gambar tingkat lanjut

### Perbedaan dengan Machine Learning Tradisional

**Machine Learning Tradisional:**
- Bekerja baik dengan data terstruktur dan berlabel
- Memerlukan ekstraksi fitur manual
- Biaya infrastruktur lebih rendah
- Cocok untuk klasifikasi dan sistem rekomendasi

**Deep Learning:**
- Lebih cocok untuk data tidak terstruktur (gambar, video, teks)
- Dapat mengidentifikasi dan mengekstrak fitur secara otomatis
- Memerlukan dataset yang sangat besar (jutaan data)
- Biaya infrastruktur lebih tinggi
- Menggunakan neural networks untuk mensimulasikan kecerdasan manusia

## 4. Aplikasi AI di Berbagai Industri

### Industri Medis
- **Diagnosis Medis**: Membantu membaca X-ray dan scan untuk membuat diagnosis
- **Prediksi Pandemi**: CDC menggunakan AI untuk memprediksi pandemi dan wabah di seluruh dunia
- **Resource Allocation**: Mengirim tenaga medis dan sumber daya ke lokasi yang membutuhkan

### Manufaktur
- **Quality Control**: Koch Industries menggunakan AI dengan computer vision untuk memantau jalur perakitan dan mempertahankan kualitas produk
- **Predictive Maintenance**: Memantau data sensor untuk memprediksi kapan peralatan memerlukan maintenance sebelum gagal
- **Operational Efficiency**: Mengurangi downtime dan meningkatkan produktivitas

### Layanan Pelanggan
- **Intelligent Support**: Sistem chat dan pencarian yang dapat mengenali bahasa pelanggan dan mengarahkan ke solusi yang tepat
- **Product Recommendations**: Rekomendasi produk berdasarkan riwayat aktivitas belanja
- **Automated Assistance**: Mengurangi beban customer service dengan otomasi

### Media dan Entertainment
- **Content Personalization**: Discovery menggunakan AI untuk membuat rekomendasi konten yang dipersonalisasi berdasarkan riwayat tontonan
- **Event Recommendations**: TickeTek menggunakan AI untuk mengirim rekomendasi pertunjukan dan acara yang disesuaikan dengan minat unik pelanggan
- **Content Creation**: AI dapat membantu dalam produksi dan editing konten

### Transportasi
- **Demand Forecasting**: Perusahaan taksi menggunakan AI untuk memposisikan mobil di lokasi dan waktu ketika pelanggan kemungkinan membutuhkannya
- **Route Optimization**: Optimasi rute untuk efisiensi bahan bakar dan waktu
- **Autonomous Systems**: Pengembangan kendaraan otonom

### Keuangan
- **Fraud Detection**: MasterCard dapat mendeteksi transaksi fraud dengan menggunakan AI untuk mendeteksi aktivitas anomali
- **Risk Assessment**: Analisis risiko kredit dan investasi
- **Algorithmic Trading**: Otomasi perdagangan berdasarkan analisis pasar

### Human Resources
- **Resume Processing**: Memproses resume dan mencocokkan kandidat dengan posisi yang terbuka
- **Productivity Enhancement**: Membantu hiring manager menjadi lebih produktif
- **Employee Analytics**: Analisis performa dan kepuasan karyawan

### Marketing
- **Targeted Campaigns**: Menargetkan pelanggan dengan promosi yang kemungkinan besar mereka inginkan
- **Spam Prevention**: Menghindari spam dengan targeting yang lebih akurat
- **Personalization**: Personalisasi komunikasi dan pengalaman pelanggan

## 5. Jenis-Jenis Output AI

### Prediksi (Predictions/Inferences)

**Inference** adalah prediksi yang dibuat oleh AI. Perlu dicatat bahwa inference pada dasarnya adalah "educated guess", sehingga model memberikan hasil probabilistik.

**Contoh - Regression Analysis:**
- Menggunakan teknik yang disebut regression analysis
- Model AI dapat memproses data historis (**time series data**) dan memprediksi nilai masa depan
- **Contoh Praktis**: Toko perlu tahu berapa banyak tenaga penjualan yang dibutuhkan pada hari tertentu untuk melayani pelanggan
- Model AI dapat menganalisis pola di masa lalu dan memperkirakan berapa banyak pelanggan yang akan ada di toko pada hari tertentu di masa depan

**Karakteristik Inference:**
- Bersifat probabilistik, bukan deterministik
- Akurasi tergantung pada kualitas data training
- Dapat digunakan untuk real-time atau batch processing

### Deteksi Anomali (Anomaly Detection)

Karena AI dapat mengenali pola dalam data, AI juga dapat mendeteksi ketika ada penyimpangan dari pola yang diharapkan, yang dikenal sebagai **anomali**.

**Contoh:**
- Jumlah panggilan yang diterima tim customer service mungkin bervariasi sepanjang hari dengan cara yang dapat diprediksi
- Ketika sesuatu terjadi, seperti aplikasi call center offline, AI dapat mendeteksi penurunan panggilan dan memberi tahu departemen IT

### Computer Vision

Aplikasi computer vision menggunakan AI untuk memproses gambar dan video untuk:
- Identifikasi objek
- Pengenalan wajah
- Klasifikasi
- Rekomendasi
- Monitoring
- Deteksi

**Contoh Aplikasi:**
- Model computer vision mendeteksi goresan pada permukaan dan menempatkan kotak merah di sekitarnya pada gambar
- Aplikasi lebih lanjut: model mengidentifikasi bahwa ada kapasitor yang hilang pada circuit board

### Terjemahan Bahasa (Language Translation)

AI dapat menerjemahkan teks dari satu bahasa ke bahasa lain tanpa keterlibatan manusia.

**Keunggulan:**
- Melampaui terjemahan kata-per-kata sederhana
- Menganalisis semua elemen teks
- Mengenali bagaimana kata-kata saling mempengaruhi
- Mampu mengkomunikasikan makna frasa secara akurat dalam bahasa target

**Contoh:**
Aplikasi chat customer support di mana pelanggan mengetik dalam bahasa Spanyol sementara support rep mengetik dalam bahasa Inggris. Aplikasi menerjemahkan antara bahasa Inggris dan Spanyol secara real-time.

### Natural Language Processing (NLP)

**Natural Language Processing (NLP)** adalah teknologi yang memungkinkan mesin untuk memahami, menginterpretasikan, dan menghasilkan bahasa manusia dengan cara yang terdengar alami.

**Aplikasi:**
- Teknologi yang menggerakkan perangkat Alexa
- Chatbot yang memungkinkan Anda memesan hotel
- Chatbot memandu pelanggan untuk memberikan informasi yang dibutuhkan untuk membuat reservasi

### Generative AI

**Generative AI** adalah langkah selanjutnya dalam artificial intelligence. Generative AI dapat:
- Melakukan percakapan yang tampak cerdas
- Menghasilkan konten original seperti cerita, gambar, video, dan bahkan musik

**Contoh dengan Amazon Bedrock:**
- Dimulai dengan prompt: "Generate a song from these lyrics: In order to pass the exam, you'll need to know AI"
- Response: Lirik lagu lengkap dengan dua verse, chorus, bridge, dan outro, dan sebagian besar berima

## 6. Machine Learning Fundamentals

### Cara Kerja Machine Learning

**Machine Learning** adalah ilmu mengembangkan algoritma dan model statistik yang digunakan sistem komputer untuk melakukan tugas kompleks tanpa instruksi eksplisit.

**Proses Training ML:**
1. **Input Data**: Algoritma ML menerima data sebagai input yang terdiri dari **features** (fitur)
2. **Training**: Algoritma dilatih dengan **known data** untuk mengidentifikasi korelasi
3. **Parameter Adjustment**: Parameter internal model disesuaikan hingga menghasilkan output yang diharapkan secara konsisten
4. **Inference**: Model yang terlatih dapat membuat prediksi akurat dari data baru

**Features**: Dapat berupa kolom dalam tabel atau pixel dalam gambar yang digunakan sebagai input untuk model.

## 7. Jenis-Jenis Data untuk Machine Learning

### Data Terstruktur (Structured Data)

**Karakteristik:**
- Paling mudah dipahami dan diproses
- Disimpan sebagai baris dalam tabel dengan kolom
- Kolom dapat berfungsi sebagai fitur untuk model ML

**Contoh:**
- File teks seperti CSV
- Database relasional seperti Amazon RDS atau Amazon Redshift
- Dapat di-query menggunakan SQL (Structured Query Language)

**Storage untuk Training:**
Data diekspor ke Amazon S3 (Simple Storage Service) karena:
- Dapat menyimpan jenis data apa pun
- Biaya lebih rendah
- Kapasitas penyimpanan hampir tidak terbatas

### Data Semi-Terstruktur (Semi-Structured Data)

**Karakteristik:**
- Tidak sepenuhnya mengikuti aturan data tabular terstruktur
- Elemen data dapat memiliki atribut yang berbeda atau atribut yang hilang

**Contoh:**
- File teks yang berisi JSON (JavaScript Object Notation)
- Fitur direpresentasikan sebagai key-value pairs
- Amazon DynamoDB dan Amazon DocumentDB dengan kompatibilitas MongoDB

**Storage untuk Training:**
Data diekspor ke Amazon S3

### Data Tidak Terstruktur (Unstructured Data)

**Karakteristik:**
- Data yang tidak sesuai dengan model data tertentu
- Tidak dapat disimpan dalam format tabel

**Contoh:**
- Gambar
- Video
- File teks atau postingan media sosial

**Storage:**
- Biasanya disimpan sebagai objek dalam sistem object storage seperti Amazon S3

**Ekstraksi Fitur:**
Fitur untuk machine learning diturunkan dari objek menggunakan teknik pemrosesan seperti **tokenization**, yang memecah teks menjadi unit individual kata atau frasa.

### Data Time Series

**Karakteristik:**
- Penting untuk melatih model yang perlu memprediksi tren masa depan
- Setiap record data diberi label dengan timestamp
- Disimpan secara berurutan

**Contoh:**
Metrik performa untuk microservice, termasuk:
- Used memory
- CPU percentage
- Transactions per second

**Aplikasi:**
Model machine learning dapat menemukan pola dalam data ini dan menggunakannya untuk secara proaktif scale out infrastruktur untuk layanan sebelum load diperkirakan meningkat.

**Storage:**
Tergantung pada sampling rate, data time series yang ditangkap untuk periode panjang bisa menjadi sangat besar dan disimpan di Amazon S3 untuk training model.

## 8. Proses Training Model Machine Learning

### Algoritma dan Parameter

Untuk membuat model machine learning, kita perlu memulai dengan **algoritma** yang mendefinisikan hubungan matematis antara output dan input.

**Contoh - Linear Regression:**
```
Persamaan: y = mx + b
Atau dalam kasus tinggi dan berat: h = mw + b

Dimana:
- w = variabel independen (berat)
- h = variabel dependen (tinggi)  
- m = slope (kemiringan)
- b = intercept
```

**Parameter model** (m dan b) disesuaikan secara iteratif selama proses training untuk menemukan model yang paling sesuai.

### Proses Training Iteratif

**Langkah-langkah Training:**
1. **Initialization**: Set parameter awal
2. **Forward Pass**: Hitung prediksi dengan parameter saat ini
3. **Error Calculation**: Bandingkan prediksi dengan actual output
4. **Parameter Update**: Sesuaikan parameter untuk mengurangi error
5. **Iteration**: Ulangi hingga konvergensi atau kriteria berhenti tercapai

### Model Artifacts

Proses training menghasilkan **model artifacts**, yang terdiri dari:
- **Trained parameters**: Nilai parameter yang telah dioptimasi
- **Model definition**: Deskripsi cara menghitung inference
- **Metadata**: Informasi tambahan tentang model

**Storage di AWS:**
- Model artifacts disimpan di **Amazon S3**
- Dikemas bersama dengan **inference code** untuk deployment
- **Inference code**: Software yang mengimplementasikan model dengan membaca artifacts

## 9. Opsi Hosting Model

### Real-Time Inference

**Karakteristik:**
- Endpoint selalu tersedia untuk menerima inference request secara real-time
- Ideal untuk online inference yang memiliki persyaratan low latency dan high throughput
- Model di-deploy pada persistent endpoint untuk menangani aliran request yang berkelanjutan
- Client mengirim input data ke model dan menerima kembali inference dengan sangat cepat

**Kelebihan:**
- Response time sangat cepat
- Cocok untuk aplikasi interaktif

**Kekurangan:**
- Compute resources selalu berjalan, biaya lebih tinggi

### Batch Inference

**Karakteristik:**
- Cocok untuk offline processing ketika data dalam jumlah besar tersedia di awal
- Tidak memerlukan persistent endpoint
- Ketika Anda membutuhkan sejumlah besar inference dan tidak masalah menunggu hasilnya

**Contoh Kasus:**
- Anda memiliki data penjualan historis dan ingin memperkirakan inventory yang dibutuhkan untuk bulan depan untuk setiap produk dalam katalog
- Input data model dapat diproses sekaligus pada jadwal bulanan
- Hasil dapat digunakan untuk menghasilkan laporan

**Kelebihan:**
- Lebih cost-effective untuk volume besar
- Computing resources hanya berjalan saat memproses batch, kemudian shut down

**Perbedaan Utama:**
Dengan batch, computing resources hanya berjalan saat memproses batch, kemudian shut down. Dengan real-time inferencing, beberapa compute resources selalu berjalan dan tersedia untuk memproses request.

## 10. Gaya Machine Learning (ML Styles)

### Supervised Learning (Pembelajaran Terawasi)

**Definisi:**
Anda melatih model dengan data yang sudah diberi label sebelumnya (pre-labeled).

**Contoh:**
- Menunjukkan model gambar ikan, dan ini diberi label sebagai "fish"
- Dalam dataset yang sama, menyertakan gambar hewan lain seperti manatee, dan ini diberi label sebagai "not fish"
- Training data menentukan input dan desired output dari algoritma

**Cara Kerja:**
1. Untuk masalah klasifikasi gambar, model akan melihat pixel gambar dan mengenali cluster dan pola
2. Parameter internal algoritma disesuaikan selama proses training
3. Berlanjut hingga model berhasil mengidentifikasi gambar yang diberi label "fish" sebagai ikan, dan mengidentifikasi yang lain sebagai non-fish

**Output:**
Model menghasilkan probabilitas bahwa gambar adalah ikan (inference tidak selalu 100% akurat).

**Tantangan:**
- Labeling data memerlukan banyak usaha manusia
- Model mungkin perlu dilatih dengan ribuan atau jutaan gambar sebelum dapat membuat prediksi yang reliable

**Solusi AWS:**
- **Amazon SageMaker Ground Truth**: Layanan labeling yang dapat memanfaatkan crowdsourcing
- **Amazon Mechanical Turk**: Menyediakan akses ke pool besar tenaga kerja terjangkau yang tersebar di seluruh dunia (500,000+ independent contractors)

### Unsupervised Learning (Pembelajaran Tidak Terawasi)

**Definisi:**
Algoritma unsupervised learning dilatih pada data yang memiliki fitur tetapi tidak diberi label.

**Kemampuan:**
- Menemukan pola
- Mengelompokkan data ke dalam cluster
- Membagi data menjadi sejumlah grup tertentu

**Use Cases:**
- Pattern recognition
- Anomaly detection
- Secara otomatis mengelompokkan data ke dalam kategori

**Keunggulan:**
- Training data tidak memerlukan labeling, sehingga setup lebih mudah
- Dapat digunakan untuk membersihkan dan memproses data untuk pemodelan lebih lanjut secara otomatis

**Contoh Aplikasi:**

1. **Clustering:**
   - Mengidentifikasi berbagai jenis network traffic untuk memprediksi potensi insiden keamanan
   - Segmentasi pelanggan berdasarkan perilaku

2. **Anomaly Detection:**
   - Model ML memeriksa data yang dikumpulkan dari sensor
   - Dapat mendeteksi bahwa sensor suhu di sumur minyak mungkin gagal jika data yang dilaporkan jauh di luar rentang normal
   - Deteksi fraud dalam transaksi keuangan

### Reinforcement Learning (Pembelajaran Penguatan)

**Definisi:**
Metode machine learning yang berfokus pada pengambilan keputusan otonom oleh agen (agent).

**Cara Kerja:**
- Agent mengambil tindakan dalam environment untuk mencapai tujuan tertentu
- Model belajar melalui trial and error
- Training tidak memerlukan labeled input
- Tindakan yang membawa agent lebih dekat ke pencapaian tujuan diberi reward
- Untuk mendorong pembelajaran selama training, learning agent harus diizinkan kadang-kadang mengejar tindakan yang mungkin tidak menghasilkan reward

**Contoh - AWS DeepRacer:**
Amazon menawarkan mobil balap model bernama **AWS DeepRacer** yang dapat Anda ajarkan untuk mengemudi di lintasan balap. Ini adalah platform pembelajaran untuk memahami reinforcement learning.

**Komponen DeepRacer:**
- **Agent**: Mobil DeepRacer
- **Environment**: Lintasan balap
- **Action**: Mobil bergerak maju, belok kiri/kanan, mengatur kecepatan
- **Goal**: Tetap di lintasan dan menyelesaikan course seefisien mungkin
- **Reward**: Diberikan ketika mobil tetap di lintasan dan mencapai checkpoint

**Perbedaan dengan Unsupervised Learning:**
- Keduanya bekerja tanpa labeled data
- Unsupervised learning menerima input tanpa output yang ditentukan selama proses training
- Reinforcement learning memiliki predetermined end goal
- Meskipun mengambil pendekatan eksplorasi, eksplorasi terus divalidasi dan ditingkatkan untuk meningkatkan probabilitas mencapai end goal

## 11. Masalah Umum dalam Machine Learning

### Overfitting (Kelebihan Fitting)

**Definisi:**
Ketika model berkinerja lebih baik pada training data daripada pada data baru.

**Contoh:**
- Kita melatih model untuk mengenali gambar ikan dengan gambar ikan yang berenang di air
- Model yang di-deploy mungkin melihat gambar ikan yang sedikit berbeda, seperti ikan di luar air, dan tidak mengenalinya sebagai ikan
- Model terlalu cocok dengan training data, sehingga ketika melihat sesuatu yang sedikit berbeda, model berpikir probabilitasnya rendah bahwa itu adalah ikan

**Penyebab:**
- Training data tidak cukup beragam
- Training terlalu lama sehingga model mulai menekankan fitur yang tidak penting (noise)

**Solusi:**
Biasanya cara terbaik untuk memperbaiki model yang overfitting adalah melatihnya dengan data yang lebih beragam.

### Underfitting (Kekurangan Fitting)

**Definisi:**
Jenis error yang terjadi ketika model tidak dapat menentukan hubungan yang bermakna antara input dan output data.

**Karakteristik:**
- Model yang underfit memberikan hasil yang tidak akurat untuk training dataset dan data baru

**Penyebab:**
- Model belum dilatih cukup lama
- Dataset tidak cukup besar

**Sweet Spot:**
Data scientist mencoba menemukan sweet spot untuk waktu training di mana model tidak underfit atau overfit.

### Bias

**Definisi:**
Ketika ada disparitas dalam performa model di berbagai grup. Hasil condong mendukung atau menentang outcome untuk kelas tertentu.

**Contoh - Aplikasi Pinjaman:**
Pertimbangkan model machine learning untuk secara otomatis menyetujui aplikasi pinjaman:

**Skenario:**
- Training data memiliki contoh aplikasi pinjaman yang harus disetujui dan yang tidak
- Jika training data tidak memiliki cukup aplikasi dari populasi yang beragam, model dapat mempelajari pola yang bias terhadap grup tertentu

**Kasus Spesifik:**
- Aplikasi pinjaman berisi fitur seperti pendapatan pelanggan, riwayat pekerjaan, usia, jenis kelamin, dan lokasi
- Misalkan tidak ada aplikasi yang disetujui dari wanita berusia 25 tahun yang tinggal di Wisconsin dalam training data
- Model dapat mempelajari bahwa aplikasi tersebut tidak boleh disetujui, meskipun fitur lain seperti pendapatan dan riwayat pekerjaan mereka memenuhi syarat

**Solusi:**

1. **Kualitas dan Kuantitas Data:**
   - Kualitas model tergantung pada kualitas dan kuantitas data yang mendasarinya

2. **Penyesuaian Bobot Fitur:**
   - Jika model menunjukkan bias, bobot fitur yang memperkenalkan noise dapat disesuaikan langsung oleh data scientist
   - Contoh: Dapat sepenuhnya menghapus pertimbangan gender oleh model

3. **Identifikasi Fairness Constraints:**
   - Fairness constraints, seperti diskriminasi usia dan jenis kelamin, harus diidentifikasi di awal sebelum membuat model

4. **Inspeksi dan Evaluasi:**
   - Training data harus diperiksa dan dievaluasi untuk potensi bias
   - Model perlu terus dievaluasi dengan memeriksa hasilnya untuk fairness


## 12. Deep Learning: Neural Networks

### Struktur Neural Networks

**Neural Networks** adalah struktur algoritma yang didasarkan pada struktur otak manusia.

**Analogi dengan Otak Manusia:**
- Di otak kita, sel-sel otak yang disebut neuron membentuk jaringan kompleks
- Mereka mengirim sinyal listrik satu sama lain untuk membantu kita memproses informasi
- Dalam model deep learning, kita menggunakan modul software yang disebut **nodes** untuk mensimulasikan perilaku neuron

### Arsitektur Deep Neural Networks

**Komponen:**
1. **Input Layer**: Lapisan untuk menerima data input
2. **Hidden Layers**: Beberapa lapisan tersembunyi untuk pemrosesan
3. **Output Layer**: Lapisan untuk menghasilkan output

**Cara Kerja:**
1. Setiap node dalam neural network secara otonom memberikan bobot (weights) untuk setiap fitur
2. Informasi mengalir melalui jaringan dalam arah forward dari input ke output
3. Selama training, perbedaan antara predicted output dan actual output dihitung
4. Bobot neuron disesuaikan berulang kali untuk meminimalkan error

### Keunggulan Deep Learning

**Ekstraksi Fitur Otomatis:**
- Model deep learning tidak memerlukan fitur yang relevan diberikan kepada mereka
- Mereka dapat mengidentifikasi pola dalam gambar dan mengekstrak fitur penting sendiri

**Kekuatan Computer Vision:**
- Deep learning dapat unggul dalam tugas seperti klasifikasi gambar dan natural language processing
- Dapat mengidentifikasi hubungan kompleks antara objek data

### Pertimbangan Biaya dan Data

**Kebutuhan Data:**
- Mungkin memerlukan jutaan gambar sebelum dapat secara akurat mendeteksi dan melabeli objek dalam gambar

**Biaya Infrastruktur:**
- Infrastruktur komputasi untuk melatih model deep learning berulang kali pada dataset besar akan lebih mahal daripada pendekatan tradisional

**Ketersediaan Cloud Computing:**
- Konsep deep learning dengan neural networks telah ada sejak lama
- Namun, daya komputasi yang diperlukan tidak layak untuk sebagian besar bisnis hingga kedatangan cloud computing berbiaya rendah
- Karena sekarang siapa pun dapat dengan mudah menggunakan sumber daya komputasi yang powerful di cloud, neural networks telah menjadi pendekatan algoritma standar untuk computer vision

### Kapan Menggunakan Traditional ML vs Deep Learning

**Traditional Machine Learning:**
- Umumnya berkinerja baik dan efisien untuk mengidentifikasi pola dari data terstruktur dan data berlabel
- Contoh: sistem klasifikasi dan rekomendasi
- Kasus: Perusahaan ponsel dapat menggunakan ML untuk memprediksi kapan pelanggan akan berganti operator berdasarkan data churn pelanggan sebelumnya

**Deep Learning:**
- Lebih cocok untuk data tidak terstruktur seperti gambar, video, dan teks
- Tugas untuk deep learning termasuk klasifikasi gambar dan natural language processing
- Diperlukan ketika ada kebutuhan untuk mengidentifikasi hubungan kompleks antara pixel dan kata
- Contoh: Solusi deep learning dapat menganalisis mention media sosial atau feedback produk untuk menentukan sentimen pengguna

**Ringkasan Perbedaan:**
- Kedua jenis machine learning menggunakan algoritma statistik
- Hanya deep learning yang menggunakan neural networks untuk mensimulasikan kecerdasan manusia
- Model deep learning self-learn patterns, sehingga tidak memerlukan banyak pekerjaan dalam memilih dan mengekstrak fitur
- Namun, biaya infrastruktur mereka jauh lebih tinggi

## 13. Generative AI dan Large Language Models

### Apa itu Generative AI?

**Generative AI** adalah langkah selanjutnya dalam artificial intelligence yang dapat:
- Melakukan percakapan yang tampak cerdas
- Menghasilkan konten original seperti cerita, gambar, video, dan bahkan musik
- Dicapai dengan menggunakan model deep learning yang telah di-pre-train pada dataset yang sangat besar

### Transformer Neural Networks

**Karakteristik Transformer:**
- Mengubah input sequence (dalam Gen AI dikenal sebagai **prompt**) menjadi output sequence (response terhadap prompt)
- Neural networks tradisional memproses elemen sequence secara berurutan satu kata pada satu waktu
- **Transformers memproses sequence secara paralel**, yang mempercepat training dan memungkinkan dataset yang jauh lebih besar untuk digunakan
- Berdasarkan paper "Attention Is All You Need"

### Large Language Models (LLMs)

**Karakteristik:**
- Berisi **miliaran parameter/fitur**
- Menangkap berbagai pengetahuan manusia yang luas
- Dengan semua training ini, model besar sangat fleksibel dalam tugas yang dapat mereka lakukan
- **Outperform** pendekatan ML lainnya untuk natural language processing

**Keunggulan LLMs:**
1. **Pemahaman Bahasa:**
   - Unggul dalam memahami bahasa manusia
   - Dapat membaca artikel panjang dan merangkumnya

2. **Generasi Teks:**
   - Hebat dalam menghasilkan teks yang mirip dengan cara manusia menulis
   - Baik dalam terjemahan bahasa
   - Dapat menulis cerita, surat, artikel, dan puisi original

3. **Pemrograman:**
   - Mengetahui bahasa pemrograman komputer
   - Dapat menulis kode untuk software developer

4. **Fleksibilitas:**
   - Sangat fleksibel dalam berbagai tugas
   - Dapat beradaptasi dengan berbagai domain

### Amazon Bedrock

**Amazon Bedrock** adalah layanan AWS untuk mengakses dan menggunakan foundation models untuk generative AI.

**Cara Kerja:**
1. Mulai dengan prompt
2. Model menghasilkan response yang komprehensif
3. Dapat menghasilkan berbagai jenis konten (teks, kode, gambar, musik)

**Contoh dari Material Transcript:**
- **Prompt**: "Generate a song from these lyrics: In order to pass the exam, you'll need to know AI"
- **Response**: Lirik lagu lengkap dengan dua verse, chorus, bridge, dan outro, dan sebagian besar berima

**Foundation Models Available:**
- Amazon Titan models
- Meta models
- Leading AI startups models

### Mencoba Generative AI

Untuk mencoba Amazon Bedrock secara gratis, Anda dapat membangun AI app sendiri di **partyrock.aws**.

## 14. Rangkuman Konsep Kunci

### Hierarki AI

```
Artificial Intelligence (AI)
    ├── Machine Learning (ML)
    │   ├── Supervised Learning
    │   ├── Unsupervised Learning
    │   └── Reinforcement Learning
    └── Deep Learning
        ├── Neural Networks
        ├── Computer Vision
        ├── Natural Language Processing (NLP)
        └── Generative AI
            └── Large Language Models (LLMs)
```

### Terminologi Penting

| Istilah | Definisi |
|---------|----------|
| **AI** | Sistem komputer yang dapat melakukan tugas yang memerlukan kecerdasan manusia |
| **Machine Learning** | Sistem yang belajar dari data tanpa diprogram secara eksplisit |
| **Deep Learning** | ML menggunakan neural networks dengan banyak lapisan |
| **Neural Network** | Model yang terinspirasi dari struktur otak manusia |
| **Inference** | Prediksi yang dibuat oleh model AI |
| **Training** | Proses mengajarkan model untuk mengenali pola |
| **Features** | Atribut atau karakteristik data yang digunakan untuk training |
| **Model Artifacts** | Output dari proses training (parameters, definition, metadata) |
| **Overfitting** | Model terlalu cocok dengan training data |
| **Underfitting** | Model tidak dapat menemukan pola yang bermakna |
| **Bias** | Disparitas dalam performa model di berbagai grup |
| **Supervised Learning** | Training dengan data berlabel |
| **Unsupervised Learning** | Training dengan data tidak berlabel |
| **Reinforcement Learning** | Training melalui trial and error dengan reward system |
| **Generative AI** | AI yang dapat menghasilkan konten original |
| **LLM** | Large Language Model - model bahasa dengan miliaran parameter |
| **Prompt** | Input yang diberikan ke generative AI |
| **Transformer** | Arsitektur neural network yang memproses sequence secara paralel |

### Layanan AWS yang Disebutkan

1. **Amazon S3** - Simple Storage Service untuk menyimpan training data dan model artifacts
2. **Amazon RDS** - Relational Database Service untuk data terstruktur
3. **Amazon Redshift** - Data warehouse untuk analitik
4. **Amazon DynamoDB** - NoSQL database untuk data semi-terstruktur
5. **Amazon DocumentDB** - Document database dengan kompatibilitas MongoDB
6. **Amazon SageMaker Ground Truth** - Layanan untuk labeling data
7. **Amazon Mechanical Turk** - Crowdsourcing platform untuk labeling
8. **AWS DeepRacer** - Platform untuk belajar reinforcement learning
9. **Amazon Bedrock** - Layanan untuk mengakses foundation models
10. **PartyRock.aws** - Platform untuk membangun AI app secara gratis

## 15. Tips untuk Ujian AWS Certified AI Practitioner

### Konsep yang Harus Dikuasai

1. **Perbedaan antara AI, ML, dan Deep Learning**
   - Pahami hierarki dan hubungan antar konsep
   - Ketahui kapan menggunakan masing-masing approach

2. **Jenis-jenis Learning**
   - Supervised vs Unsupervised vs Reinforcement
   - Kapan menggunakan masing-masing
   - Contoh use case untuk setiap jenis

3. **Jenis-jenis Data**
   - Structured, Semi-structured, Unstructured, Time Series
   - Layanan AWS yang sesuai untuk setiap jenis data
   - Cara menyimpan dan memproses setiap jenis data

4. **Proses ML Lifecycle**
   - Data collection dan preparation
   - Training dan validation
   - Deployment (Real-time vs Batch)
   - Monitoring dan maintenance

5. **Masalah Umum**
   - Overfitting dan cara mengatasinya
   - Underfitting dan cara mengatasinya
   - Bias dan cara mendeteksi serta mengatasinya

6. **Generative AI**
   - Cara kerja LLMs
   - Transformer architecture
   - Amazon Bedrock dan use cases

7. **Layanan AWS**
   - Pahami layanan storage (S3)
   - Pahami layanan database (RDS, DynamoDB, DocumentDB, Redshift)
   - Pahami layanan AI/ML (SageMaker, Bedrock, DeepRacer)

### Strategi Belajar

1. **Praktik Hands-on**
   - Coba Amazon Bedrock di PartyRock.aws
   - Eksplorasi AWS DeepRacer
   - Buat project sederhana dengan SageMaker

2. **Pahami Use Cases**
   - Pelajari contoh aplikasi di berbagai industri
   - Pahami kapan menggunakan solusi tertentu
   - Kenali trade-offs antara berbagai approach

3. **Fokus pada Terminologi**
   - Pastikan memahami definisi setiap istilah
   - Ketahui perbedaan antara istilah yang mirip
   - Gunakan istilah dengan benar dalam konteks

4. **Review Konsep Dasar**
   - Jangan skip konsep fundamental
   - Bangun pemahaman dari dasar ke advanced
   - Hubungkan konsep satu dengan yang lain

---

## 16. AWS Services Mapping dan Exam Cues

### AWS Services yang Disebutkan dalam Material Transcript

| Service | Exam Cue | Use Case |
|---------|-----------|----------|
| **Amazon S3** | "primary source for training data", "object storage" | Menyimpan training data dan model artifacts |
| **Amazon RDS** | "relational database", "structured data" | Database untuk data terstruktur |
| **Amazon Redshift** | "data warehouse" | Analytics dan data warehousing |
| **Amazon DynamoDB** | "NoSQL", "semi-structured data" | Database untuk data semi-terstruktur |
| **Amazon DocumentDB** | "MongoDB compatibility" | Document database |
| **Amazon SageMaker Ground Truth** | "data labeling service" | Labeling data untuk supervised learning |
| **Amazon Mechanical Turk** | "crowdsourcing", "500,000+ contractors" | Human workforce untuk labeling |
| **AWS DeepRacer** | "reinforcement learning", "model race car" | Platform pembelajaran RL |
| **Amazon Bedrock** | "foundation models", "generative AI" | Akses ke foundation models |
| **PartyRock.aws** | "build AI app for free" | Platform prototyping generative AI |

### Key Exam Concepts dari Material Transcript

**Terminologi Penting:**
- **Inference**: Prediksi yang dibuat AI (educated guess, probabilistic)
- **Features**: Kolom dalam tabel atau pixel dalam gambar
- **Model Artifacts**: Trained parameters + model definition + metadata
- **Supervised Learning**: Training dengan labeled data
- **Unsupervised Learning**: Training tanpa labels
- **Reinforcement Learning**: Learning melalui trial and error dengan rewards
- **Overfitting**: Model performs better pada training data daripada new data
- **Underfitting**: Model tidak dapat menentukan meaningful relationship
- **Bias**: Disparitas dalam performa model across different groups

**Data Types:**
- **Structured**: Rows dan columns (CSV, RDS, Redshift)
- **Semi-structured**: JSON, key-value pairs (DynamoDB, DocumentDB)
- **Unstructured**: Images, video, text (S3)
- **Time Series**: Data dengan timestamp untuk trend prediction

**Hosting Options:**
- **Real-time Inference**: Persistent endpoint, low latency
- **Batch Inference**: Offline processing, cost-effective

---

**Catatan:** Materi ini disusun berdasarkan material-transcript-1-1.txt dari AWS Skill Builder course untuk AWS Certified AI Practitioner (AIF-C01). Semua contoh dan terminologi mengikuti standar AWS resmi.ntuk AWS Certified AI Practitioner (AIF-C01). Pastikan untuk terus mempelajari materi lainnya dan berlatih dengan soal-soal latihan untuk persiapan ujian yang optimal.
