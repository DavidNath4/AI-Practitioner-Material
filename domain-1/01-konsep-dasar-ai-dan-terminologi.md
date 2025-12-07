# Domain 1: Konsep Dasar AI dan Terminologi

## Task Statement 1.1: Menjelaskan Konsep Dasar AI dan Terminologi

### Pengenalan Artificial Intelligence (AI)

Artificial Intelligence (AI) adalah bidang ilmu komputer yang didedikasikan untuk menyelesaikan masalah kognitif yang umumnya dikaitkan dengan kecerdasan manusia, seperti pembelajaran, kreasi, dan pengenalan gambar. Tujuan utama AI adalah menciptakan sistem yang dapat belajar sendiri dan memperoleh makna dari data.

**Karakteristik Utama AI:**
- Dapat merespons pertanyaan dengan cara yang bermakna
- Mampu membuat konten original seperti teks dan gambar
- Dapat memproses data dalam jumlah besar dengan cepat
- Efektif untuk mendeteksi pola dan memprediksi tren
- Dapat melakukan tugas repetitif dan monoton

**Manfaat AI untuk Bisnis:**
- Meningkatkan efisiensi dengan mengotomatisasi tugas repetitif
- Membebaskan karyawan untuk melakukan pekerjaan yang lebih kreatif
- Membantu bisnis membuat keputusan yang lebih cerdas
- Memungkinkan reaksi yang lebih cepat terhadap masalah
- Mendeteksi fraud secara real-time

### Machine Learning (ML)

Machine Learning adalah cabang dari AI dan ilmu komputer yang berfokus pada penggunaan data dan algoritma untuk meniru cara manusia belajar. ML secara bertahap meningkatkan akurasinya untuk membangun sistem komputer yang belajar dari data.

**Cara Kerja Machine Learning:**
1. Model ML dilatih menggunakan dataset besar
2. Model mengidentifikasi pola dalam data
3. Model membuat prediksi berdasarkan pola yang ditemukan
4. Contoh: rekomendasi produk untuk pelanggan yang berbelanja online

**Komponen Utama ML:**
- **Training Data**: Data yang digunakan untuk melatih model
- **Features**: Karakteristik atau kolom dalam data (seperti kolom dalam tabel atau piksel dalam gambar)
- **Algorithm**: Rumus matematika yang mendefinisikan hubungan antara input dan output
- **Model Parameters**: Nilai internal yang disesuaikan selama training
- **Inference**: Prediksi yang dibuat oleh model (pada dasarnya adalah educated guess)

### Deep Learning

Deep Learning adalah jenis model machine learning yang terinspirasi dari otak manusia, menggunakan lapisan neural networks untuk memproses informasi.

**Kemampuan Deep Learning:**
- Mengenali ucapan manusia
- Mengenali objek dalam gambar dan video
- Memproses bahasa alami
- Klasifikasi gambar tingkat lanjut

**Perbedaan dengan Traditional ML:**
- Deep learning menggunakan struktur algoritma yang disebut neural networks
- Terdiri dari lapisan nodes (input layer, hidden layers, output layer)
- Setiap node secara otonom memberikan bobot pada setiap feature
- Lebih cocok untuk data tidak terstruktur (gambar, video, teks)
- Membutuhkan daya komputasi yang lebih besar
- Tidak memerlukan feature extraction manual

### Aplikasi AI di Berbagai Industri

**1. Industri Medis**
- Membaca X-ray dan scan
- Membuat diagnosis
- Memprediksi pandemi dan wabah (contoh: CDC)

**2. Manufaktur**
- Computer vision untuk memonitor assembly lines
- Menjaga kualitas produk
- Memonitor data sensor untuk predictive maintenance
- Contoh: Koch Industries

**3. Customer Service**
- Chatbot dan sistem pencarian
- Mengenali bahasa pelanggan
- Mengarahkan ke solusi yang tepat
- Rekomendasi produk berdasarkan riwayat belanja

**4. Media dan Entertainment**
- Rekomendasi konten yang dipersonalisasi
- Contoh: Discovery menggunakan AI berdasarkan viewing history

**5. Transportasi**
- Memposisikan kendaraan di lokasi dan waktu yang tepat
- Contoh: perusahaan taksi menggunakan AI untuk demand forecasting

**6. Keuangan**
- Deteksi transaksi fraud
- Mendeteksi aktivitas anomali
- Contoh: MasterCard menggunakan AI untuk fraud detection

**7. Human Resources**
- Memproses resume
- Mencocokkan kandidat dengan posisi yang tersedia
- Meningkatkan produktivitas hiring manager

**8. Marketing**
- Targeting pelanggan dengan promosi yang relevan
- Menghindari spam
- Contoh: TickeTek mengirim rekomendasi acara yang disesuaikan

### Teknik dan Aplikasi AI

**1. Regression Analysis**
Model AI dapat memproses data historis (time series data) dan memprediksi nilai masa depan.
- Contoh: toko memprediksi jumlah salespeople yang dibutuhkan berdasarkan pola masa lalu
- Output disebut inference (prediksi probabilistik)

**2. Anomaly Detection**
AI dapat mendeteksi penyimpangan dari pola yang diharapkan.
- Contoh: mendeteksi penurunan jumlah panggilan ke call center ketika aplikasi offline
- Sistem dapat mengirim notifikasi ke IT department

**3. Computer Vision**
Aplikasi yang menggunakan AI untuk memproses gambar dan video.
- Object identification dan facial recognition
- Classification, recommendation, monitoring, detection
- Contoh: mendeteksi goresan pada permukaan, mengidentifikasi komponen yang hilang pada circuit board

**4. Language Translation**
AI dapat menerjemahkan teks dari satu bahasa ke bahasa lain tanpa keterlibatan manusia.
- Lebih dari sekadar word-to-word translation
- Menganalisis semua elemen teks
- Mengenali bagaimana kata-kata saling mempengaruhi
- Contoh: aplikasi customer support chat dengan real-time translation

**5. Natural Language Processing (NLP)**
Memungkinkan mesin untuk memahami, menginterpretasi, dan menghasilkan bahasa manusia dengan cara yang natural.
- Teknologi yang menggerakkan Alexa devices
- Chatbot untuk booking hotel
- Contoh: chatbot meminta informasi yang dibutuhkan untuk membuat reservasi

**6. Generative AI**
Langkah berikutnya dalam artificial intelligence yang dapat:
- Melakukan percakapan yang tampak intelligent
- Menghasilkan konten original (cerita, gambar, video, musik)
- Bekerja dengan prompt sebagai input
- Contoh: Amazon Bedrock menghasilkan lirik lagu lengkap dari prompt sederhana

### Tipe Data untuk Machine Learning

**1. Structured Data**
- Paling mudah dipahami dan diproses
- Disimpan sebagai baris dalam tabel dengan kolom
- Kolom dapat berfungsi sebagai features untuk model ML
- Format: CSV files, relational databases (Amazon RDS, Amazon Redshift)
- Dapat di-query menggunakan SQL
- Untuk training, di-export ke Amazon S3

**2. Semi-Structured Data**
- Tidak sepenuhnya mengikuti aturan data tabular
- Elemen dapat memiliki atribut yang berbeda atau atribut yang hilang
- Format: JSON (JavaScript Object Notation)
- Features direpresentasikan sebagai key-value pairs
- Database: Amazon DynamoDB, Amazon DocumentDB
- Untuk training, di-export ke Amazon S3

**3. Unstructured Data**
- Tidak mengikuti model data spesifik
- Tidak dapat disimpan dalam format tabel
- Contoh: gambar, video, text files, social media posts
- Disimpan sebagai objects di Amazon S3
- Features diturunkan dari objects menggunakan teknik seperti tokenization

**4. Time Series Data**
- Penting untuk melatih model yang memprediksi tren masa depan
- Setiap record diberi label timestamp
- Disimpan secara sequential
- Contoh: performance metrics untuk microservice (memory, CPU, transactions per second)
- Dapat digunakan untuk proactive scaling

### Proses Training Machine Learning

**1. Algorithm dan Model**
- Algorithm mendefinisikan hubungan matematika antara output dan input
- Contoh sederhana: linear regression y = mx + b
- Slope (m) dan intercept (b) adalah model parameters
- Parameters disesuaikan secara iteratif selama training

**2. Training Process**
- Mencari parameter values yang meminimalkan errors
- Error adalah jarak antara data points dan line (dalam linear regression)
- Ketika training selesai, model siap untuk inference

**3. Model Artifacts**
Training menghasilkan:
- Trained parameters
- Model definition (cara menghitung inference)
- Metadata lainnya
- Disimpan di Amazon S3
- Dikemas bersama inference code untuk membuat deployable model

### Opsi Hosting Model

**1. Real-time Inference**
- Endpoint selalu tersedia untuk menerima inference requests
- Ideal untuk online inferences dengan low latency dan high throughput
- Model di-deploy pada persistent endpoint
- Client mengirim input data dan menerima inference dengan cepat
- Compute resources selalu running

**2. Batch Inference**
- Cocok untuk offline processing
- Ketika data dalam jumlah besar tersedia di awal
- Tidak memerlukan persistent endpoint
- Lebih cost-effective untuk large number of inferences
- Contoh: forecast inventory bulanan untuk setiap produk
- Computing resources hanya running saat memproses batch, kemudian shutdown

### Machine Learning Styles

**1. Supervised Learning**
- Melatih model dengan data yang sudah di-label
- Training data menentukan input dan desired output
- Contoh: klasifikasi gambar ikan (labeled "fish" dan "not fish")
- Model melihat pixels dan mengenali clusters dan patterns
- Parameters disesuaikan hingga model berhasil mengidentifikasi dengan benar
- Output adalah probability (bukan selalu 100% akurat)

**Tantangan:**
- Membutuhkan labeling data (bisa ribuan gambar)
- Solusi: Amazon SageMaker Ground Truth dengan Amazon Mechanical Turk

**2. Unsupervised Learning**
- Training dengan data yang memiliki features tapi tidak di-label
- Dapat mengenali pola dan mengelompokkan data ke dalam clusters
- Use cases: pattern recognition, anomaly detection, automatic grouping
- Setup lebih straightforward karena tidak perlu labeling
- Dapat membersihkan dan memproses data secara otomatis

**Contoh Aplikasi:**
- Clustering: mengidentifikasi tipe network traffic untuk prediksi security incidents
- Anomaly detection: mendeteksi sensor yang failing (contoh: temperature sensor di oil well)

**3. Reinforcement Learning**
- Fokus pada autonomous decision making oleh agent
- Agent mengambil actions dalam environment untuk mencapai goals
- Belajar melalui trial and error
- Tidak memerlukan labeled input
- Actions yang mendekatkan ke goal diberi reward
- Agent harus diizinkan untuk explore actions yang mungkin tidak menghasilkan reward

**Contoh: AWS DeepRacer**
- Car adalah agent
- Track adalah environment
- Action adalah car bergerak forward
- Goal adalah stay on track dan finish secepat mungkin

**Perbedaan Unsupervised vs Reinforcement:**
- Unsupervised: menerima inputs tanpa specified outputs
- Reinforcement: memiliki predetermined end goal
- Reinforcement: exploratory approach yang terus divalidasi dan ditingkatkan

### Masalah dalam Machine Learning

**1. Overfitting**
- Model perform lebih baik pada training data daripada new data
- Model tidak generalize dengan baik
- Terlalu fit dengan training data
- Contoh: model ikan hanya mengenali ikan di air, tidak mengenali ikan di luar air
- Solusi: train dengan data yang lebih diverse
- Bisa terjadi jika training terlalu lama (model emphasize noise)

**2. Underfitting**
- Model tidak dapat menentukan meaningful relationship antara input dan output
- Memberikan hasil tidak akurat untuk training dataset dan new data
- Terjadi jika training tidak cukup lama atau dataset tidak cukup besar
- Data scientists mencari sweet spot untuk training time

**3. Bias**
- Disparitas dalam performance model across different groups
- Hasil condong mendukung atau menentang outcome untuk class tertentu
- Contoh: model loan approval bias terhadap grup tertentu karena training data tidak diverse

**Penyebab Bias:**
- Training data tidak memiliki cukup contoh dari diverse population
- Model belajar pattern yang bias terhadap grup tertentu
- Features seperti gender, age, location dapat memperkenalkan bias

**Mengatasi Bias:**
- Kualitas dan kuantitas data yang baik
- Adjust weight dari features yang memperkenalkan noise
- Remove consideration dari features tertentu (contoh: gender)
- Identifikasi fairness constraints di awal (age, sex discrimination)
- Inspect dan evaluate training data untuk potential bias
- Continually evaluate model results untuk fairness

### Deep Learning Neural Networks

**Struktur Neural Networks:**
- Berdasarkan struktur otak manusia
- Neurons (brain cells) membentuk complex network
- Dalam deep learning: software modules disebut nodes
- Nodes mensimulasikan behavior neurons

**Lapisan Neural Networks:**
- Input layer
- Several hidden layers
- Output layer
- Setiap node autonomously assigns weights ke setiap feature
- Information flows forward dari input ke output
- Weights disesuaikan berulang kali untuk meminimalkan error

**Keunggulan Deep Learning:**
- Excel pada tasks seperti image classification dan NLP
- Dapat mengidentifikasi complex relationship antara data objects
- Tidak memerlukan relevant features diberikan secara manual
- Dapat identify patterns dan extract important features sendiri

**Pertimbangan:**
- Membutuhkan computing power yang besar (sekarang viable dengan cloud computing)
- Mungkin memerlukan millions of pictures untuk training
- Infrastructure cost lebih tinggi dari traditional approach
- Keputusan menggunakan traditional ML atau deep learning tergantung tipe data

**Kapan Menggunakan Traditional ML:**
- Data terstruktur dan labeled
- Classification dan recommendation systems
- Contoh: prediksi customer churn

**Kapan Menggunakan Deep Learning:**
- Data tidak terstruktur (images, videos, text)
- Image classification dan NLP
- Complex relationships antara pixels dan words
- Contoh: analisis sentiment dari social media

### Generative AI dan Large Language Models

**Generative AI:**
- Menggunakan deep learning models yang pre-trained pada extremely large datasets
- Menggunakan transformer neural networks
- Transformer mengubah input sequence (prompt) menjadi output sequence (response)
- Memproses sequence secara parallel (lebih cepat dari sequential processing)

**Large Language Models (LLMs):**
- Mengandung billions of features
- Menangkap wide range of human knowledge
- Sangat fleksibel dalam tasks yang dapat dilakukan
- Outperform ML approaches lain untuk NLP

**Kemampuan LLMs:**
- Memahami bahasa manusia dengan sangat baik
- Membaca artikel panjang dan merangkumnya
- Menghasilkan teks seperti cara manusia menulis
- Language translation
- Menulis original stories, letters, articles, poetry
- Mengetahui programming languages dan dapat menulis code

**Contoh Platform:**
- Amazon Bedrock untuk build AI applications
- PartyRock.aws untuk mencoba build AI app gratis

### Kesimpulan

Domain 1 Task Statement 1.1 mencakup fundamental concepts dari AI, ML, dan Deep Learning. Pemahaman yang solid tentang konsep-konsep ini sangat penting untuk AWS Certified AI Practitioner exam. Key takeaways:

1. AI adalah field yang luas dengan berbagai aplikasi praktis
2. Machine Learning adalah subset dari AI yang fokus pada learning from data
3. Deep Learning menggunakan neural networks untuk complex pattern recognition
4. Berbagai tipe data memerlukan pendekatan yang berbeda
5. Supervised, unsupervised, dan reinforcement learning memiliki use cases yang berbeda
6. Overfitting, underfitting, dan bias adalah masalah yang harus diatasi
7. Generative AI dan LLMs membuka possibilities baru dalam AI applications
