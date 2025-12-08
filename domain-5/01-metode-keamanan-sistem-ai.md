# Metode Keamanan Sistem AI (Security Methods for AI Systems)

## Pengantar Domain 5

Domain 5 dari AWS Certified AI Practitioner berfokus pada keamanan dan tata kelola sistem AI. Task Statement 5.1 secara khusus membahas metode-metode untuk mengamankan sistem AI di lingkungan AWS.

## 1. Model Tanggung Jawab Bersama AWS (AWS Shared Responsibility Model)

### Konsep Dasar

Keamanan dan kepatuhan di AWS adalah tanggung jawab bersama antara AWS dan pelanggan. Model ini membagi tanggung jawab menjadi dua kategori utama:

### Tanggung Jawab AWS (Security OF the Cloud)

AWS bertanggung jawab untuk:
- Infrastruktur global (AWS Regions, Availability Zones, data centers)
- Keamanan fisik gedung dan fasilitas
- Hardware, software, dan komponen jaringan
- Host operating system dan lapisan virtualisasi
- Komponen jaringan AWS

### Tanggung Jawab Pelanggan (Security IN the Cloud)

Pelanggan bertanggung jawab untuk:
- Konfigurasi layanan dan aplikasi dengan benar
- Keamanan data
- Pembatasan akses (access control)
- Penggunaan enkripsi
- Mengikuti praktik terbaik keamanan

### Tingkat Tanggung Jawab Berdasarkan Layanan

**Contoh 1: Amazon EC2**
- Pelanggan bertanggung jawab penuh atas:
  - Operating system instance
  - Security patches
  - Scaling
  - Keamanan aplikasi yang berjalan

**Contoh 2: SageMaker Serverless Inferencing**
- AWS mengelola seluruh infrastruktur
- Pelanggan tidak perlu mengelola instance atau scaling policies
- Manajemen minimal dari pelanggan


## 2. AWS Identity and Access Management (IAM)

### Apa itu IAM?

IAM adalah layanan web yang membantu mengelola dan mengamankan akses ke akun dan resource AWS. IAM memungkinkan Anda untuk:
- Membuat dan mengelola pengguna AWS
- Memberikan izin untuk menggunakan layanan
- Mengontrol tindakan yang dapat dilakukan pengguna pada resource

### Karakteristik IAM

**Global Resource**
- IAM tidak spesifik untuk satu Region tertentu
- Dapat digunakan untuk membatasi izin pengguna ke Region tertentu

**Integrasi dengan Layanan AWS**
- Terintegrasi dengan semua layanan AWS
- Mengelola tindakan yang dapat diambil pengguna pada resource

**Dukungan Multi-Factor Authentication (MFA)**
- Dapat ditambahkan ke akun dan pengguna individual
- Memberikan lapisan keamanan tambahan

**Identity Federation**
- Memungkinkan pengguna dengan password dari sistem lain (corporate network, identity provider) mendapatkan akses sementara

**Tanpa Biaya Tambahan**
- IAM adalah fitur gratis dari akun AWS
- Biaya hanya dikenakan saat mengakses layanan AWS lainnya

### AWS Root User

**Definisi dan Karakteristik:**
- Identity pertama yang dibuat saat membuat akun AWS
- Memiliki akses lengkap ke semua layanan dan resource
- Diakses menggunakan email dan password yang digunakan saat membuat akun
- Izinnya TIDAK DAPAT dibatasi

**Best Practices untuk Root User:**

1. **Pilih Password yang Kuat**
   - Gunakan kombinasi karakter yang kompleks
   - Hindari password yang mudah ditebak

2. **Aktifkan Multi-Factor Authentication (MFA)**
   - Wajib untuk keamanan maksimal
   - Aktifkan segera setelah membuat akun

3. **Jangan Pernah Membagikan Kredensial**
   - Jangan bagikan password dan access keys
   - Simpan kredensial dengan aman

4. **Nonaktifkan atau Hapus Access Keys**
   - Access keys root user tidak diperlukan setelah membuat user lain
   - Hapus untuk mengurangi risiko

5. **Gunakan Root User Hanya untuk Tugas Khusus**
   - Manajemen akun billing
   - Tugas administratif tingkat tinggi tertentu
   - Untuk tugas sehari-hari, gunakan IAM user


### Pentingnya Multi-Factor Authentication (MFA)

**Single-Factor Authentication (Username + Password):**
- Bentuk autentikasi paling sederhana dan umum
- Rentan terhadap berbagai serangan:
  - Social engineering
  - Bot dan script otomatis
  - Pencurian password

**Risiko Tanpa MFA:**
- Penghapusan data berharga
- Penyalahgunaan resource (contoh: cryptocurrency mining)
- Tagihan yang tidak terduga dan mahal

**Multi-Factor Authentication (MFA):**
- Memerlukan dua faktor: password + kode dari perangkat MFA
- Bahkan jika password dicuri, akun tetap aman
- Perangkat MFA bisa fisik atau virtual
- **Rekomendasi AWS: Aktifkan MFA segera setelah membuat akun**

### IAM Users

**Definisi:**
- Identity yang dibuat di AWS
- Merepresentasikan orang yang berinteraksi dengan layanan dan resource AWS
- Terdiri dari nama dan kredensial

**Best Practices:**

1. **Buat IAM User Individual**
   - Satu user untuk setiap orang
   - Bahkan jika memerlukan tingkat akses yang sama
   - Jangan berbagi kredensial antar pengguna

2. **Kredensial Unik**
   - Setiap user memiliki kredensial sendiri
   - Mempertahankan visibilitas siapa yang melakukan tindakan

3. **Default: Tanpa Izin**
   - User baru tidak memiliki izin apapun
   - Harus secara eksplisit diberikan izin yang diperlukan

4. **Principle of Least Privilege**
   - Berikan hanya izin yang diperlukan untuk menyelesaikan tugas
   - Jangan memberikan izin berlebihan

## 3. IAM Policies

### Apa itu IAM Policy?

IAM Policy adalah dokumen JSON yang mengizinkan atau menolak izin ke layanan dan resource AWS. Policy memungkinkan kustomisasi tingkat akses pengguna ke resource.

### Contoh IAM Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:StartInstances",
        "ec2:StopInstances"
      ],
      "Resource": "*"
    }
  ]
}
```

Policy di atas mengizinkan pengguna untuk memulai dan menghentikan EC2 instances.


### IAM Groups

**Definisi:**
- Kumpulan IAM users
- Ketika policy ditetapkan ke group, semua user dalam group mendapat izin tersebut

**Keuntungan Menggunakan Groups:**
- Mengelola izin lebih mudah untuk banyak user
- Organisasi berdasarkan fungsi pekerjaan
- Efisien untuk skala besar (contoh: 3,000 users)

**Contoh Organisasi Groups:**

1. **Developer Group**
   - Untuk tim pengembang software
   - Izin untuk development resources

2. **QA Group**
   - Untuk tim testing
   - Izin untuk testing environments

3. **Admin Group**
   - Untuk administrator
   - Izin administratif

**Karakteristik IAM Groups:**
- Satu group dapat memiliki banyak users
- Satu user dapat menjadi anggota banyak groups
- Groups TIDAK DAPAT menjadi anggota groups lain (no nesting)

**Best Practice:**
- Tetapkan policies ke groups
- Tetapkan ke users hanya untuk izin unik yang spesifik

### IAM Roles

**Masalah dengan Long-Lived Credentials:**
- Policies yang ditetapkan ke users dan groups menggunakan kredensial jangka panjang
- Jika dikompromikan, orang lain dapat menggunakannya
- Contoh: Developer lupa menghapus AWS credentials dari kode yang dibagikan

**Solusi: IAM Roles**

**Definisi:**
- Identity yang dapat diasumsikan oleh orang atau layanan AWS
- Memberikan akses sementara ke resource atau layanan AWS lainnya
- Kredensial keamanan sementara yang otomatis kedaluwarsa

**Siapa yang Dapat Menggunakan Roles:**
- IAM user
- Layanan AWS
- User yang diautentikasi oleh external identity provider

**Komponen IAM Role:**

1. **Trust Policy**
   - Menentukan entitas mana yang dapat mengasumsikan role
   - Mengontrol siapa yang dapat menggunakan role

2. **Permissions Policy**
   - Menentukan tindakan apa yang dapat dilakukan
   - Sama seperti policy untuk users dan groups


### Identity-Based vs Resource-Based Policies

**Identity-Based Policies:**
- Ditetapkan pada IAM users, groups, dan roles
- Mengontrol apa yang identity dapat lakukan

**Resource-Based Policies:**
- Ditetapkan pada resource (contoh: S3 bucket)
- Mengontrol siapa yang dapat mengakses resource

**Evaluasi Izin:**
- Izin yang dihasilkan adalah total dari kedua jenis policy
- Jika tindakan diizinkan oleh salah satu atau kedua policy, AWS mengizinkan tindakan
- **Explicit deny** di salah satu policy akan menimpa allow

## 4. Identity Federation dengan AWS IAM Identity Center

### Apa itu Identity Federation?

Identity Federation adalah metode di mana pengguna mengautentikasi dengan identity provider eksternal (seperti Active Directory), kemudian diberikan kredensial sementara untuk AWS.

### AWS IAM Identity Center

**Fitur Utama:**

1. **External Identity Provider**
   - Dapat menggunakan Active Directory
   - Atau membuat directory di IAM Identity Center

2. **Workforce Users/Identities**
   - Istilah untuk pengguna yang diautentikasi
   - Diarahkan ke portal setelah autentikasi

3. **Portal Akses Terpusat**
   - Pilih akses ke AWS console
   - Atau dapatkan temporary access keys
   - Untuk akun AWS yang memiliki izin

**Keuntungan untuk Multi-Account:**
- Tidak perlu mengelola IAM users di setiap akun
- Tambahkan users ke AWS Identity Center
- Kelola izin untuk semua akun di satu repository pusat

**Manajemen Izin:**
- Organisasi users ke dalam groups
- Tetapkan permission sets di tingkat group
- Menggunakan roles untuk memberikan izin sementara

**Rekomendasi AWS:**
- Gunakan IAM Identity Center untuk mengelola users
- Lebih baik daripada IAM users tradisional
- Menggunakan temporary credentials (best practice)


## 5. Audit dan Logging dengan AWS CloudTrail

### Pentingnya Audit

Untuk mengaudit dan memvalidasi konfigurasi keamanan, Anda harus dapat mencatat dan meninjau tindakan yang diambil pengguna.

### AWS CloudTrail

**Fungsi Utama:**
- Menangkap API calls dan event terkait
- Dibuat oleh atau atas nama akun AWS Anda
- Mengirimkan log files ke Amazon S3 bucket yang Anda tentukan

**Integrasi dengan Amazon SageMaker:**

**Yang Dicatat:**
- Semua API calls untuk SageMaker (kecuali invoking endpoints)
- Pembuatan training job
- Pembuatan notebook instance
- Tindakan administratif lainnya

**Informasi yang Dapat Ditemukan:**
- Request yang dibuat ke SageMaker
- IP address dari mana request dibuat
- Siapa yang membuat request
- Kapan request dibuat
- Detail tambahan lainnya

**Manfaat:**
- Audit trail lengkap
- Investigasi insiden keamanan
- Compliance dan regulatory requirements
- Analisis penggunaan resource

## 6. Keamanan Data di Amazon S3

### Tanggung Jawab Pelanggan

Berdasarkan AWS Shared Responsibility Model, pelanggan bertanggung jawab untuk:
- Mengelola akses ke data mereka
- Menjaga training data dan artifacts tetap private dan aman

### Amazon S3 Block Public Access

**Fitur:**
- Memblokir akses publik ke semua objek
- Dapat diaktifkan di tingkat bucket atau account

**Tingkat Implementasi:**

1. **Bucket Level**
   - Beberapa bucket di akun mungkin terbuka untuk publik
   - Kontrol per bucket

2. **Account Level**
   - Tidak ada bucket (existing atau baru) yang dapat memberikan akses publik
   - Perlindungan menyeluruh

**Cara Kerja:**
- Ketika diaktifkan, akan menimpa izin publik yang diberikan oleh:
  - Bucket policies
  - Access Control Lists (ACLs)
- Memberikan lapisan keamanan tambahan


## 7. Amazon SageMaker Role Manager

### Tujuan

Menyederhanakan pembuatan IAM roles yang memberikan izin untuk melakukan aktivitas ML, tanpa harus membuat permissions policies secara manual.

### Komponen Utama

**Three Pre-Configured Role Personas:**

1. **Data Scientist Persona**
   - Untuk pengembangan dan eksperimen machine learning umum
   - Menggunakan SageMaker untuk development
   - Akses ke data dan compute resources

2. **MLOps Persona**
   - Mengelola models, pipelines, experiments, dan endpoints
   - TIDAK memerlukan akses ke data di Amazon S3
   - Fokus pada operasional dan deployment

3. **SageMaker Compute Persona**
   - Untuk membuat role yang digunakan SageMaker compute resources
   - Melakukan tugas seperti training dan inference
   - Role untuk service, bukan untuk user

**Predefined Permissions untuk 12 ML Activities:**
- Izin untuk mengakses layanan lain:
  - Amazon S3
  - AWS Glue
  - Amazon Athena
  - Amazon CloudWatch
- Izin untuk mengelola dan memonitor:
  - SageMaker models
  - Endpoints
  - Training jobs
  - Pipelines
  - Experiments

### Cara Menggunakan

1. **Pilih Persona**
   - Pilih persona yang sesuai dengan kebutuhan
   - Aktivitas yang sesuai akan dipilih secara otomatis

2. **Kustomisasi (Opsional)**
   - Dapat mengaktifkan atau menonaktifkan aktivitas tertentu
   - Menyesuaikan dengan kebutuhan spesifik

3. **Tambahkan IAM Policies (Opsional)**
   - Dapat menambahkan policies tambahan jika diperlukan
   - Untuk izin yang tidak tercakup dalam predefined permissions

4. **Otomatis Membuat Permissions Policy**
   - SageMaker Role Manager membuat policy untuk Anda
   - Tidak perlu menulis JSON policy secara manual

**Keuntungan:**
- Mengurangi kompleksitas
- Mengikuti best practices
- Mempercepat setup
- Mengurangi kesalahan konfigurasi


## 8. Enkripsi Data (Data Encryption)

### Pentingnya Enkripsi

Enkripsi adalah tanggung jawab pelanggan untuk menjaga keamanan data dan merupakan persyaratan umum dalam standar compliance.

### Jenis Enkripsi

**1. Encryption at Rest (Data Tersimpan)**
- Mengenkripsi data yang disimpan di storage
- Bahkan jika seseorang mengakses storage volume, mereka tidak dapat membaca data
- Memerlukan encryption keys untuk dekripsi

**2. Encryption in Transit (Data Bergerak)**
- Mengenkripsi data saat ditransmisikan melalui jaringan
- Melindungi data dari intersepsi
- Menggunakan protokol seperti TLS/HTTPS

### Encryption Keys

**Fungsi:**
- Digunakan bersama dengan algoritma enkripsi
- Mengenkripsi data sebelum ditulis ke storage
- Diperlukan untuk mendekripsi data

**Keamanan:**
- Akses ke data saja tidak cukup untuk membacanya
- Harus memiliki akses ke encryption keys

### Metode Enkripsi

**Client-Side Encryption:**
- Pelanggan mengenkripsi data sebelum mengirim ke layanan AWS
- Kontrol penuh atas proses enkripsi
- Lebih kompleks untuk diimplementasikan

**Server-Side Encryption:**
- Layanan AWS mengenkripsi data
- Cara termudah untuk memastikan enkripsi diterapkan dengan benar
- Biasanya opsi yang diaktifkan saat mengkonfigurasi resource
- Konsisten dan otomatis

### Default Encryption di AWS Services

**Layanan dengan Enkripsi Default:**
- Amazon S3
- Amazon DynamoDB
- Amazon SageMaker

**SageMaker Encryption:**
- Mengenkripsi semua data di ML storage volumes
- Termasuk:
  - Notebook instances
  - SageMaker jobs
  - Endpoints

**Service-Owned Keys:**
- Layanan dengan enkripsi default menggunakan keys milik service
- Bukan milik pelanggan
- Tidak ada kontrol atas keys


## 9. AWS Key Management Service (AWS KMS)

### Apa itu AWS KMS?

Layanan untuk membuat, mengelola, dan menggunakan encryption keys di akun AWS Anda.

### Fitur Utama

**Kontrol Penuh:**
- Keys milik akun Anda
- Bukan service-owned keys
- Kontrol penuh atas lifecycle keys

**Manajemen Keys:**
- Membuat keys
- Mengelola keys
- Menggunakan keys untuk enkripsi/dekripsi

**Kontrol Akses dengan IAM:**
- Menggunakan IAM policies untuk mengontrol penggunaan keys
- Menentukan user atau service mana yang dapat mengakses key
- Lapisan perlindungan tambahan untuk data

### Contoh Lapisan Keamanan Berlapis

Misalkan seseorang secara tidak sengaja diberikan izin read ke S3 bucket Anda:
- Mereka tidak akan dapat membaca data
- Kecuali mereka juga memiliki izin untuk menggunakan AWS KMS key
- Key diperlukan untuk mendekripsi data

### Jenis Keys di AWS KMS

**1. AWS-Managed Keys**
- Dikelola oleh AWS
- Rotasi otomatis
- Tidak dapat mengubah key policies

**2. Customer-Managed Keys**
- Dikelola oleh pelanggan
- Kontrol penuh atas:
  - Key policies
  - IAM policies
  - Key rotation
  - Enable/disable key

### Integrasi dengan Layanan AWS

**Amazon S3 dan SageMaker:**
- Menggunakan keys mereka sendiri secara default
- Dapat menentukan AWS KMS key untuk digunakan
- Memberikan kontrol lebih besar

### TLS untuk Enkripsi in Transit

**Semua AWS Service Endpoints:**
- Mendukung TLS (Transport Layer Security)
- Membuat koneksi HTTPS yang aman
- Untuk membuat API requests

**Amazon S3 dan SageMaker:**
- Semua requests melalui APIs dan console menggunakan koneksi terenkripsi
- HTTPS secara default
- Keamanan in transit otomatis


### SageMaker Distributed Training

**Default Behavior:**
- Inter-node traffic TIDAK dienkripsi secara default
- Menggunakan multiple nodes dalam cluster

**Opsi Enkripsi:**
- Tersedia opsi untuk mengaktifkan enkripsi inter-node
- Mungkin diperlukan untuk data yang sangat sensitif

**Trade-off:**
- Mengaktifkan enkripsi dapat meningkatkan waktu training
- Terutama untuk algoritma deep learning
- Pertimbangkan kebutuhan keamanan vs performa

## 10. Amazon Macie

### Apa itu Amazon Macie?

Layanan keamanan yang menggunakan machine learning dan pattern matching untuk menemukan dan melindungi data sensitif di Amazon S3.

### Fitur Utama

**1. Inventory Otomatis S3 Buckets:**
- Evaluasi berkelanjutan terhadap S3 buckets
- Menghasilkan inventory otomatis:
  - Ukuran bucket
  - Status bucket
  - Private atau public access
  - Shared access dengan akun AWS lain
  - Status enkripsi

**2. Deteksi Data Sensitif:**
- Menggunakan ML dan pattern matching
- Mengidentifikasi Personally Identifiable Information (PII):
  - Nomor kartu kredit
  - Nama
  - Alamat
  - Nomor social security
  - Data pribadi lainnya

**3. Alert dan Integrasi:**
- Menghasilkan alert otomatis
- Dapat diintegrasikan ke ML workflow
- Mengambil tindakan remediasi otomatis

### Best Practice untuk PII

**Penghapusan PII dari Training Data:**
- PII harus dihapus pada tahap ingestion dan transformation
- Tidak ada alasan untuk melatih model dengan:
  - Nomor kartu kredit
  - Nama pribadi
  - Alamat
  - Nomor social security

**Tindakan Jika Macie Menemukan PII:**
- Macie akan memberikan alert
- Jika ada di training data, HARUS dihapus
- Mencegah kebocoran data pribadi
- Memenuhi persyaratan compliance


## 11. Virtual Private Cloud (VPC) untuk SageMaker

### Tanggung Jawab Pelanggan

Pelanggan bertanggung jawab untuk mengelola konfigurasi keamanan infrastruktur cloud mereka.

### Default Behavior SageMaker

**SageMaker Studio dan Notebook Instances:**
- Diluncurkan di VPC yang dikelola oleh SageMaker
- Direct internet access diizinkan secara default
- Memungkinkan download package populer dari internet

**Risiko Default Configuration:**
- Risiko mendownload kode berbahaya
- Kode berbahaya dapat mengirim data keluar melalui internet
- Potensi kebocoran data

### Best Practice: Gunakan VPC Sendiri

**Langkah-langkah:**

1. **Buat VPC di Akun Anda**
   - Konfigurasi VPC sesuai kebutuhan keamanan
   - Tentukan subnet dan routing

2. **Tentukan VPC Saat Meluncurkan SageMaker**
   - Untuk SageMaker Studio
   - Untuk Notebook instances

3. **Elastic Network Interface (ENI)**
   - Dibuat di VPC Anda
   - Dihubungkan ke notebook instance

**Kontrol yang Diperoleh:**
- Mengontrol traffic yang dapat mengakses internet
- Menggunakan Security Groups
- Network Access Control Lists (NACLs)
- Network Firewalls

### VPC-Only Mode

**Konfigurasi:**
- Tentukan "VPC only" untuk network access type
- Mencegah SageMaker memberikan akses internet ke notebook instances

**Implikasi:**
- SageMaker Studio biasanya mencapai layanan melalui public network:
  - Amazon S3
  - Amazon CloudWatch
  - SageMaker Runtime
  - SageMaker API
- Dalam VPC-only mode, public endpoints tidak dapat dijangkau

### VPC Interface Endpoints

**Solusi untuk VPC-Only Mode:**
- Menggunakan VPC interface endpoints
- Menghubungkan VPC langsung ke layanan AWS
- Menggunakan AWS PrivateLink

**Cara Kerja:**
- Semua traffic tetap di private network
- Tidak melewati internet publik
- SageMaker Studio di VPC dapat mengakses layanan eksternal melalui VPC interface endpoints

**Keuntungan:**
- Keamanan maksimal
- Compliance dengan regulasi
- Kontrol penuh atas network traffic
- Mengurangi risiko eksfiltrasi data


## 12. Kerentanan Keamanan Spesifik AI (AI-Specific Security Vulnerabilities)

### 1. Data Poisoning (Keracunan Data)

**Konsep:**
- Model AI belajar perilakunya dari training data
- Jika penyerang mendapat akses ke training data, mereka dapat memanipulasinya

**Contoh Serangan:**
- **Skenario:** Model deteksi fraud dilatih pada transaksi keuangan yang dilabeli sebagai fraud dan not fraud
- **Serangan:** Penyerang menambahkan transaksi fraudulent tertentu yang dilabeli sebagai not fraud
- **Hasil:** Model akan salah mengklasifikasikan transaksi tersebut
- **Dampak:** Penyerang dapat melakukan fraud tanpa terdeteksi

**Mitigasi:**
- Amankan dan batasi akses ke training data
- Monitor kualitas data secara rutin
- Validasi data sebelum digunakan untuk training
- Gunakan data validation set yang terpisah

### 2. Adversarial Inputs (Input Adversarial)

**Konsep:**
- Penyerang memanipulasi input data dengan cara yang halus namun dirancang dengan hati-hati
- Menyebabkan model salah mengklasifikasi

**Contoh Serangan:**
- **Skenario:** Perusahaan menggunakan model face recognition untuk mengenali karyawan
- **Serangan:** Penyerang membuat modifikasi halus pada gambar mereka
- **Hasil:** Model mengenali mereka sebagai orang lain
- **Dampak:** Akses tidak sah ke sistem

**Karakteristik:**
- Modifikasi sangat halus, tidak terlihat oleh mata manusia
- Dirancang secara khusus untuk menipu model
- Tidak memerlukan akses ke training data

**Mitigasi:**
- Latih model dengan adversarial input
- Validasi dan inspeksi input dari pengguna
- Cari pola yang tidak biasa
- Implementasi input sanitization

### 3. Model Inversion (Inversi Model)

**Konsep:**
- Penyerang canggih dapat menyebabkan output model untuk menyimpulkan training data
- Dengan terus memberi data ke model dan mempelajari output

**Contoh Serangan:**
- **Skenario:** Model face recognition dilatih pada gambar karyawan, output adalah nama dan confidence score
- **Serangan:** Penyerang berulang kali memberi gambar wajah dengan perubahan
- **Hasil:** Ketika output adalah nama karyawan dengan confidence score tinggi, penyerang memiliki gambar yang baik dari karyawan
- **Dampak:** Penyerang dapat berpura-pura menjadi karyawan

**Teknik Lanjutan:**
- Dengan cukup pasangan input-output, penyerang dapat membuat model baru yang bekerja terbalik
- Model baru dilatih pada output model asli
- Digunakan untuk menyimpulkan training input data


### 4. Model Extraction (Ekstraksi Model)

**Konsep:**
- Penyerang melakukan reverse engineering pada model
- Membuat model mereka sendiri yang sangat mirip dengan model asli

**Faktor yang Mempengaruhi:**
- Semakin banyak informasi yang dimiliki penyerang tentang model
- Semakin akurat salinan mereka

**Dampak:**
- Pencurian intellectual property
- Kompetitor dapat menggunakan model serupa
- Kehilangan keunggulan kompetitif

**Mitigasi:**
- Batasi dan kontrol akses ke model
- Jangan berikan informasi yang tidak perlu di output model
- Monitor penggunaan model untuk pola yang mencurigakan

### 5. Prompt Injection (Injeksi Prompt)

**Konsep:**
- Serangan khusus untuk Large Language Models (LLMs)
- Penyerang memberikan instruksi berbahaya ke model dalam prompt
- Tujuan: mempengaruhi output model

**Contoh Serangan:**
- Penyerang dapat meminta LLM untuk mengabaikan atau mengubah prompt template
- Memungkinkan penyerang mendapatkan informasi sensitif
- Memanipulasi perilaku model

**Karakteristik:**
- Memanfaatkan cara LLM memproses instruksi
- Dapat bypass security controls
- Sulit dideteksi tanpa monitoring yang tepat

**Mitigasi:**
- Ajari LLM untuk mendeteksi prompt injection menggunakan pola serangan kunci
- Return response "prompt attack detected"
- Validasi dan sanitasi input pengguna
- Implementasi prompt templates yang aman


## 13. Strategi Mitigasi Keamanan AI

### Prinsip Keamanan Berlapis

Pelanggan yang men-deploy sistem AI harus secara proaktif memitigasi potensi serangan dengan:

### 1. Mengamankan dan Membatasi Akses

**Data dan Models:**
- Terapkan principle of least privilege
- Konfigurasi permissions policies yang tepat
- Blokir public access
- Gunakan IAM roles dan policies

**Enkripsi:**
- Enkripsi data dan artifacts sebagai lapisan perlindungan tambahan
- Gunakan AWS KMS untuk kontrol keys
- Enkripsi at rest dan in transit

**Kontrol Akses Model:**
- Batasi dan kontrol akses ke model
- Blokir reverse engineering
- Monitor akses yang tidak biasa

### 2. Validasi dan Inspeksi Input

**Input Data dari Users:**
- Harus diinspeksi dan divalidasi
- Cari pola yang tidak biasa
- Implementasi input sanitization

**Deteksi Prompt Injection untuk LLMs:**
- Ajari LLM mendeteksi pola serangan
- Gunakan key attack patterns
- Return response "prompt attack detected"

**Best Practice:**
- Jangan berikan informasi yang tidak perlu di output model
- Penyerang mungkin menggunakannya untuk menyimpulkan informasi tentang model

### 3. Training dengan Adversarial Input

**Tujuan:**
- Membantu model menghindari ditipu
- Meningkatkan robustness model

**Implementasi:**
- Sertakan adversarial examples dalam training data
- Latih model untuk mengenali dan menolak adversarial inputs
- Update model secara berkala

### 4. Frequent Re-training

**Manfaat:**
- Melatih model secara berkala dengan data baru
- Kerusakan dari corrupted training data akan dibatalkan
- Model tetap up-to-date dengan pola terbaru

**Best Practice:**
- Simpan set data terpisah untuk validasi
- Validasi model setelah setiap re-training
- Deploy hanya setelah validasi berhasil


### 5. Monitoring dan Deteksi Anomali

**Scan dan Monitor Data:**
- Rutin scan data untuk kualitas
- Deteksi anomali sebelum digunakan untuk training
- Gunakan automated tools

**Monitor Prediksi Model:**
- Prediksi model bisa berubah dari pola historis
- Harus diinvestigasi untuk menentukan root cause:
  - Kualitas data rendah?
  - Serangan?
- Ambil tindakan korektif segera

**Investigasi Perubahan:**
- Analisis penyebab perubahan performa
- Periksa kualitas data input
- Cek untuk tanda-tanda serangan

## 14. Amazon SageMaker Model Monitor

### Apa itu SageMaker Model Monitor?

Layanan untuk memonitor kualitas model machine learning Amazon SageMaker yang ada di production.

### Fitur Utama

**1. Continuous Monitoring:**
- Monitor kualitas model secara real-time
- Setelah model di-deploy ke production environment

**2. Automated Alert System:**
- Setup alert otomatis untuk deviasi kualitas model
- Deteksi:
  - Data drift
  - Anomali
  - Penurunan performa

**3. Monitoring Data Quality:**
- Membandingkan data dan model dengan baselines
- Menghasilkan statistik dan metrik
- Visible di SageMaker Studio
- Dikirim ke Amazon CloudWatch

### Komponen Monitoring

**Amazon CloudWatch Logs:**
- Mengumpulkan file monitoring status model
- Memberikan notifikasi ketika kualitas model mencapai threshold preset
- Menyimpan log files ke S3 bucket yang Anda tentukan

**Visualisasi:**
- Lihat hasil di SageMaker Studio
- Dashboard untuk monitoring
- Grafik dan metrik

### Manfaat

**Early Detection:**
- Deteksi dini deviasi model
- Tindakan proaktif

**Maintain Quality:**
- Mempertahankan kualitas model yang di-deploy
- Meningkatkan kualitas secara berkelanjutan

**Prompt Actions:**
- Dengan deteksi dini, dapat mengambil tindakan segera
- Mencegah masalah menjadi lebih besar


### Monitoring Data Quality dengan SageMaker Model Monitor

**Langkah-langkah Setup:**

1. **Enable Data Capture**
   - Menangkap inference input dan output
   - Dari inference endpoint atau batch transform job
   - Menyimpan data di S3

2. **Create Baseline**
   - Biasanya menggunakan training dataset
   - Baseline untuk perbandingan

3. **Schedule Data Quality Monitoring Jobs**
   - Menghasilkan statistik untuk baseline dataset
   - Menghasilkan statistik untuk current dataset yang dianalisis
   - Membandingkan keduanya

4. **View Results**
   - Lihat hasil di SageMaker Studio
   - Analisis deviasi
   - Ambil tindakan jika diperlukan

### Monitoring Model Performance

**Proses Serupa untuk Model Quality:**

1. **Gunakan Labeled Data untuk Baseline**
   - Data yang sudah dilabeli
   - Representatif dari expected performance

2. **Model Quality Job Runs**
   - Membandingkan inferences dengan label data
   - Dari SageMaker Ground Truth untuk input yang sama
   - Evaluasi performa

3. **Performance Evaluation**
   - Metrik seperti accuracy, precision, recall
   - Perbandingan dengan baseline
   - Deteksi degradasi performa

4. **View Results in SageMaker Studio**
   - Dashboard performa
   - Visualisasi metrik
   - Alert untuk threshold violations

**Keuntungan:**
- Deteksi model drift
- Identifikasi penurunan performa
- Tindakan korektif tepat waktu
- Mempertahankan kualitas model di production


## 15. Model Governance dan Tracking

### Pentingnya Tracking Artifacts

Melacak semua artifacts yang digunakan untuk produksi model adalah persyaratan esensial untuk:
- Mereproduksi model
- Memenuhi persyaratan regulatory
- Memenuhi persyaratan kontrol

### Artifacts yang Harus Di-track

**1. Source Code**
- **Repository:** GitHub, AWS CodeCommit
- **Automatic Versioning:** Otomatis menyimpan versi source code
- **Konten:**
  - Training code
  - Inference code
  - Experiments
  - Notebooks

**2. Datasets**
- **Storage:** Amazon S3
- **Organization:** Partisi dengan prefixes
- **Identifikasi:** Uniquely identify training dataset
- **Versioning:** Track perubahan dataset

**3. Container Images**
- **Storage:** Amazon Elastic Container Registry (ECR)
- **Identification:** Unique ID untuk setiap image
- **Tagging:** Dapat ditag dengan informasi tambahan
- **Versioning:** Track versi container

**4. Training Jobs**
- **SageMaker Automatic Tracking:**
  - Unique identifier untuk setiap training job
  - Metadata seperti hyperparameters
  - Unique identifiers untuk:
    - Container
    - Dataset
    - Model output

**5. Model Versions**
- **Storage:** Model catalog menggunakan SageMaker Model Registry
- **Organization:** Model groups dengan versi berbeda
- **Metadata:** Training metrics dan informasi lainnya

**6. Endpoints**
- **Unique Identifier:** Setiap endpoint memiliki ID unik
- **Metadata:** Model yang digunakan
- **Tracking:** Otomatis sebagai bagian dari endpoint configuration


## 16. Amazon SageMaker Model Registry

### Apa itu Model Registry?

Katalog untuk menyimpan dan mengelola versi model dalam model groups.

### Fitur Utama

**Model Groups:**
- Berisi versi berbeda dari satu model
- Organisasi yang terstruktur
- Mudah untuk menemukan versi spesifik

**Model Packages:**
- Setiap model package dalam group sesuai dengan trained model
- Berisi semua informasi yang diperlukan untuk deployment

**Metadata Management:**
- Associate dan view model metadata
- Training metrics
- Hyperparameters
- Dataset yang digunakan
- Container image

**Direct Deployment:**
- Model dapat di-deploy langsung dari registry
- Streamline deployment process
- Konsistensi deployment

**Model Status:**
- **Pending:** Model sedang dalam review
- **Approved:** Model disetujui untuk production
- **Rejected:** Model ditolak
- Mempertahankan status untuk governance

### Keuntungan

- Centralized model management
- Version control untuk models
- Audit trail lengkap
- Simplified deployment
- Governance dan compliance

## 17. Amazon SageMaker Model Cards

### Apa itu Model Cards?

Dokumentasi untuk mencatat, mengambil, dan membagikan informasi esensial model dari konsepsi hingga deployment.

### Siapa yang Menggunakan?

**Risk Managers:**
- Menilai risiko model
- Memastikan compliance
- Review intended uses

**Data Scientists:**
- Dokumentasi proses development
- Berbagi insights
- Kolaborasi tim

**ML Engineers:**
- Informasi deployment
- Technical specifications
- Performance metrics


### Informasi yang Dicatat

**1. Intended Model Uses:**
- Tujuan penggunaan model
- Use cases yang sesuai
- Batasan penggunaan

**2. Risk Ratings:**
- Penilaian risiko
- Kategori risiko
- Mitigasi yang diperlukan

**3. Training Details:**
- Dataset yang digunakan
- Hyperparameters
- Training configuration
- Training duration

**4. Evaluation Results:**
- Metrik performa
- Test results
- Validation results
- Bias assessment

### Karakteristik

**Immutable Record:**
- Catatan yang tidak dapat diubah
- Audit trail permanen
- Compliance documentation

**Export to PDF:**
- Dapat diekspor ke format PDF
- Mudah dibagikan dengan stakeholders
- Professional documentation

**Sharing:**
- Berbagi dengan relevant stakeholders
- Transparansi
- Kolaborasi

### Manfaat

- Dokumentasi lengkap
- Transparansi model
- Memenuhi regulatory requirements
- Memfasilitasi model governance
- Memudahkan audit

## 18. Amazon SageMaker ML Lineage Tracking

### Apa itu ML Lineage Tracking?

Fitur yang secara otomatis membuat representasi grafis dari semua elemen end-to-end ML workflow Anda.

### Fungsi Utama

**1. Automatic Creation:**
- Otomatis membuat tracking entities
- Untuk trial components
- Associated trials dan experiments

**2. Graphical Representation:**
- Visualisasi workflow
- Hubungan antar komponen
- Flow dari data ke model


### Use Cases

**1. Model Governance:**
- Establish governance policies
- Track compliance
- Audit trail

**2. Reproduce Workflow:**
- Kemampuan untuk mereproduksi hasil
- Debugging
- Troubleshooting

**3. Work History:**
- Maintain record of work history
- Dokumentasi proses
- Knowledge transfer

### Integrasi dengan SageMaker Jobs

**Supported Jobs:**
- Processing jobs
- Training jobs
- Batch transform jobs

**Automatic Tracking:**
- Tidak perlu konfigurasi manual
- Otomatis track semua komponen
- Metadata lengkap

### Query Capabilities

**Discover Relationships:**
- Query lineage data
- Temukan hubungan antar entities

**Contoh Queries:**

1. **Retrieve Models by Dataset:**
   - Temukan semua model yang menggunakan dataset tertentu
   - Analisis dampak perubahan dataset

2. **Retrieve Datasets by Container:**
   - Temukan datasets yang menggunakan container image artifact tertentu
   - Track dependencies

3. **Trace Model Origin:**
   - Dari model kembali ke source data
   - Lengkap dengan semua transformasi

### Manfaat

- Transparansi penuh workflow
- Reproducibility
- Compliance dan audit
- Impact analysis
- Debugging yang lebih mudah

## 19. Amazon SageMaker Feature Store

### Apa itu Feature?

Feature adalah data property yang digunakan sebagai salah satu input untuk:
- Melatih model
- Membuat prediksi dengan model

**Contoh:**
- Dapat mendeskripsikan kolom dalam data table
- Atribut dari data


### Apa itu Feature Store?

Centralized store untuk features dan associated metadata, sehingga features dapat dengan mudah ditemukan dan digunakan kembali.

### Masalah yang Dipecahkan

**Tanpa Feature Store:**
- Pekerjaan berulang dalam data processing
- Curation work yang repetitif
- Sulit untuk berbagi features antar tim
- Tidak ada standarisasi

**Dengan Feature Store:**
- Mengurangi kompleksitas
- Mudah create, share, dan manage features
- Accelerate ML development
- Standarisasi features

### Fitur Utama

**1. Centralized Repository:**
- Satu tempat untuk semua features
- Metadata lengkap
- Easy discovery

**2. Feature Groups:**
- Organisasi features dalam groups
- Workflow pipelines untuk konversi raw data ke features
- Otomatis menambahkan ke feature groups

**3. Lineage Tracking:**
- View lineage dari feature group
- Informasi tentang execution code
- Data sources yang digunakan
- Bagaimana data diingest

**4. Point-in-Time Queries:**
- Retrieve state dari setiap feature pada waktu historis tertentu
- Penting untuk reproducibility
- Analisis temporal

### Workflow

1. **Create Workflow Pipelines:**
   - Convert raw data ke features
   - Automated processing

2. **Add to Feature Groups:**
   - Organize features
   - Associate metadata

3. **Discover and Reuse:**
   - Tim lain dapat menemukan features
   - Reuse untuk model mereka
   - Konsistensi antar models

### Manfaat

- Mengurangi pekerjaan repetitif
- Accelerate development
- Improve collaboration
- Ensure consistency
- Better feature management


## 20. Amazon SageMaker Model Dashboard

### Apa itu Model Dashboard?

Portal terpusat yang dapat diakses dari SageMaker console untuk melihat, mencari, dan menjelajahi semua model di akun Anda.

### Fitur Utama

**1. Aggregated Information:**
- Mengagregasi informasi terkait model dari beberapa fitur:
  - Model Monitor
  - Model Cards
  - Model Registry
  - Lineage Tracking

**2. Visualization:**
- Visualisasi workflow lineage
- Track endpoint performance
- Grafik dan metrik

**3. Model Deployment Tracking:**
- Track model mana yang di-deploy untuk inference
- Apakah digunakan dalam batch transform jobs
- Atau hosted di endpoints

### Monitoring Capabilities

**Real-time Performance Tracking:**
- Jika setup monitors menggunakan Model Monitor
- Track performa model saat membuat real-time predictions
- Pada live data

**Threshold Violations:**
- Temukan model yang melanggar threshold yang Anda set untuk:
  - Data quality
  - Model quality
  - Bias
  - Explainability

**Comprehensive Presentation:**
- Presentasi lengkap dari semua monitoring results
- Cepat identifikasi model yang tidak memiliki metrik dikonfigurasi
- Dashboard yang user-friendly

### Use Cases

**1. Model Discovery:**
- Cari model spesifik
- Explore semua model di akun
- Filter berdasarkan kriteria

**2. Performance Monitoring:**
- Monitor performa real-time
- Identifikasi issues
- Track trends

**3. Compliance Checking:**
- Pastikan semua model memiliki monitoring
- Verify metrics dikonfigurasi
- Audit compliance

**4. Quick Issue Identification:**
- Cepat temukan model dengan masalah
- Prioritize remediation
- Proactive management

### Manfaat

- Centralized view semua models
- Simplified management
- Proactive monitoring
- Better governance
- Improved compliance
- Quick troubleshooting


## Ringkasan Task Statement 5.1

### Konsep Kunci yang Harus Dipahami

**1. Shared Responsibility Model**
- AWS bertanggung jawab untuk keamanan OF the cloud
- Pelanggan bertanggung jawab untuk keamanan IN the cloud
- Pemahaman pembagian tanggung jawab sangat penting

**2. Identity and Access Management**
- IAM adalah fondasi keamanan AWS
- Root user harus dilindungi dengan MFA
- Gunakan IAM users, groups, dan roles dengan principle of least privilege
- IAM Identity Center untuk multi-account management

**3. Enkripsi dan Key Management**
- Enkripsi at rest dan in transit adalah wajib
- AWS KMS untuk kontrol penuh atas encryption keys
- Banyak layanan AWS mengenkripsi secara default

**4. Network Security**
- Gunakan VPC sendiri untuk kontrol maksimal
- VPC-only mode untuk keamanan tinggi
- VPC interface endpoints untuk private connectivity

**5. AI-Specific Vulnerabilities**
- Data poisoning
- Adversarial inputs
- Model inversion
- Model extraction
- Prompt injection

**6. Monitoring dan Governance**
- CloudTrail untuk audit logging
- SageMaker Model Monitor untuk quality monitoring
- Model Registry untuk version control
- Model Cards untuk dokumentasi
- ML Lineage Tracking untuk reproducibility
- Feature Store untuk feature management
- Model Dashboard untuk centralized management

### Best Practices Keamanan AI

1. **Selalu gunakan MFA** untuk semua akun penting
2. **Terapkan principle of least privilege** untuk semua akses
3. **Enkripsi semua data** at rest dan in transit
4. **Monitor secara kontinyu** untuk anomali dan drift
5. **Validasi input** dari pengguna
6. **Train dengan adversarial examples** untuk robustness
7. **Re-train secara berkala** dengan data baru
8. **Track semua artifacts** untuk reproducibility
9. **Dokumentasi lengkap** dengan Model Cards
10. **Gunakan VPC** untuk network isolation

### Persiapan Ujian

Untuk Task Statement 5.1, pastikan Anda memahami:
- Cara kerja IAM dan komponen-komponennya
- Perbedaan antara identity-based dan resource-based policies
- Cara menggunakan AWS KMS untuk enkripsi
- Kerentanan keamanan spesifik AI dan cara mitigasinya
- Fitur-fitur SageMaker untuk governance dan monitoring
- Best practices untuk mengamankan ML workflows

---

**Catatan:** Materi ini mencakup Task Statement 5.1 dari Domain 5. Lesson berikutnya akan membahas Task Statement 5.2 dan topik-topik lanjutan dalam keamanan dan governance sistem AI.
