# Metode Keamanan Sistem AI (Security Methods for AI Systems)

## Pengantar Domain 5

Domain 5 dari AWS Certified AI Practitioner berfokus pada keamanan dan tata kelola sistem AI dengan bobot 14% dari total ujian. Task Statement 5.1 secara khusus membahas metode-metode untuk mengamankan sistem AI di lingkungan AWS, mencakup AWS Shared Responsibility Model, IAM fundamentals, enkripsi data, keamanan jaringan, ancaman keamanan spesifik AI, dan fitur keamanan SageMaker.

**Referensi Material:** Domain 5 - Task Statement 5.1 dari material transcript AWS Skill Builder course

## 1. AWS Shared Responsibility Model untuk Sistem AI

### Konsep Dasar

**Definisi:** Keamanan dan kepatuhan di AWS adalah tanggung jawab bersama antara AWS dan pelanggan. Model ini menunjukkan pembagian tanggung jawab pelanggan dan AWS, yang umumnya disebut sebagai tanggung jawab pelanggan (security IN the cloud) dan tanggung jawab AWS (security OF the cloud).

**Infrastruktur Global AWS:**
AWS melindungi dan mengamankan infrastruktur global, termasuk:
- AWS Regions
- Availability Zones  
- Data centers hingga keamanan fisik bangunan
- Hardware, software, dan komponen jaringan yang menjalankan layanan AWS

### Tanggung Jawab AWS (Security OF the Cloud)

AWS bertanggung jawab untuk mengamankan:
- **Infrastruktur Global:** AWS Regions, Availability Zones, dan data centers
- **Keamanan Fisik:** Gedung dan fasilitas data center
- **Hardware dan Software:** Server fisik, host operating systems, lapisan virtualisasi
- **Komponen Jaringan:** AWS networking components yang menjalankan layanan AWS
- **Layanan Terkelola:** Infrastruktur yang mendasari layanan AWS

### Tanggung Jawab Pelanggan (Security IN the Cloud)

Pelanggan bertanggung jawab untuk:
- **Konfigurasi Layanan:** Mengkonfigurasi layanan dan aplikasi dengan benar
- **Keamanan Data:** Memastikan data aman dan terenkripsi
- **Kontrol Akses:** Mengelola dan membatasi akses ke resource
- **Enkripsi:** Menggunakan enkripsi untuk data at rest dan in transit
- **Best Practices:** Mengikuti praktik terbaik keamanan AWS
- **Aplikasi:** Keamanan aplikasi yang berjalan di atas layanan AWS

### Tingkat Tanggung Jawab Berdasarkan Layanan AI/ML

**Contoh 1: Amazon EC2 untuk AI Models**
- **Tanggung Jawab Pelanggan:**
  - Operating system instance
  - Security patches dan updates
  - Scaling policies
  - Keamanan aplikasi AI yang berjalan
  - Konfigurasi security groups
  - Model deployment dan management

**Contoh 2: SageMaker Serverless Inferencing**
- **Tanggung Jawab AWS:**
  - Mengelola seluruh infrastruktur underlying
  - Automatic scaling
  - Patching dan maintenance
- **Tanggung Jawab Pelanggan:**
  - Model artifacts dan data
  - IAM permissions
  - Endpoint configuration
  - Monitoring dan logging

**Prinsip Umum:** Semakin terkelola layanannya, semakin sedikit tanggung jawab pelanggan untuk infrastruktur, namun tanggung jawab untuk data dan konfigurasi tetap ada.


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


## 7. Fitur Keamanan Amazon SageMaker

### Amazon SageMaker Role Manager

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

**1. Service-Owned Keys**
- Dimiliki dan dikelola sepenuhnya oleh layanan AWS
- Digunakan untuk enkripsi default (S3, DynamoDB, SageMaker)
- Tidak ada kontrol pelanggan
- Tidak ada biaya tambahan
- Tidak terlihat di akun pelanggan

**2. AWS-Managed Keys**
- Dikelola oleh AWS untuk akun pelanggan
- Rotasi otomatis setiap tahun
- Tidak dapat mengubah key policies
- Terlihat di akun pelanggan
- Format nama: aws/service-name (contoh: aws/s3)

**3. Customer-Managed Keys**
- **Kontrol Penuh Pelanggan:**
  - Key policies dan IAM policies
  - Key rotation (manual atau otomatis)
  - Enable/disable key
  - Key deletion
- **Keuntungan:**
  - Granular access control
  - Audit trail lengkap
  - Cross-account access
  - Custom key specifications
- **Biaya:** Dikenakan biaya per key per bulan

### Perbandingan Customer-Managed vs Service-Managed Keys

| Aspek | Service-Managed | Customer-Managed |
|-------|----------------|------------------|
| **Kontrol** | Tidak ada | Penuh |
| **Biaya** | Gratis | $1/bulan per key |
| **Rotasi** | Otomatis | Dapat dikonfigurasi |
| **Audit** | Terbatas | Lengkap via CloudTrail |
| **Cross-Account** | Tidak | Ya |
| **Key Policies** | Tidak dapat diubah | Dapat dikustomisasi |

### Kapan Menggunakan Customer-Managed Keys

**Gunakan Customer-Managed Keys ketika:**
- Memerlukan kontrol penuh atas encryption keys
- Compliance requirements memerlukan key management
- Perlu cross-account access
- Memerlukan custom key rotation schedule
- Audit trail lengkap diperlukan
- Granular access control diperlukan

**Gunakan Service-Managed Keys ketika:**
- Enkripsi sederhana sudah cukup
- Tidak ada requirements khusus untuk key management
- Ingin mengurangi kompleksitas dan biaya
- Default security sudah memenuhi kebutuhan

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


## 12. Ancaman Keamanan Spesifik AI (AI-Specific Security Threats)

**Referensi Material:** Task Statement 5.1 Lesson 5 - AI systems memiliki kerentanan spesifik yang harus dipahami untuk mendeteksi dan memitigasi potensi ancaman keamanan.

### 1. Data Poisoning (Keracunan Data)

**Konsep:**
Model AI belajar perilakunya dari training data. Jika penyerang jahat (malicious actor) mendapat akses ke training data, mereka dapat memperkenalkan data yang akan mengubah prediksi model.

**Contoh Serangan dari Material Transcript:**
- **Skenario:** Model deteksi fraud dilatih pada transaksi keuangan yang dilabeli sebagai "fraud" dan "not fraud"
- **Serangan:** Penyerang menambahkan transaksi fraudulent tertentu ke data yang dilabeli sebagai "not fraud"
- **Hasil:** Model akan salah mengklasifikasikan transaksi tersebut
- **Dampak:** Penyerang dapat melakukan fraud tanpa terdeteksi oleh sistem

**Strategi Mitigasi:**
- Amankan dan batasi akses ke training data
- Monitor kualitas data secara rutin dengan automated tools
- Validasi data sebelum digunakan untuk training
- Gunakan data validation set yang terpisah
- Implementasi data lineage tracking untuk audit trail

### 2. Adversarial Inputs (Input Adversarial)

**Konsep:**
Bahkan tanpa mendapat akses ke training data, penyerang dapat menyebabkan model membuat kesalahan. Penyerang dapat sedikit memanipulasi input data dengan cara yang akan menyebabkan model salah mengklasifikasinya.

**Contoh Serangan dari Material Transcript:**
- **Skenario:** Perusahaan menggunakan model face recognition untuk mengenali karyawan
- **Serangan:** Penyerang membuat modifikasi halus namun dirancang dengan hati-hati pada gambar mereka
- **Hasil:** Model mengenali mereka sebagai orang lain
- **Dampak:** Akses tidak sah ke sistem perusahaan

**Karakteristik Serangan:**
- Modifikasi sangat halus, tidak terlihat oleh mata manusia
- Dirancang secara khusus untuk menipu model
- Tidak memerlukan akses ke training data
- Dikenal sebagai "adversarial inputs"

**Strategi Mitigasi:**
- Latih model dengan adversarial examples untuk meningkatkan robustness
- Validasi dan inspeksi input data dari pengguna
- Cari pola yang tidak biasa dalam input
- Implementasi input sanitization dan validation
- Monitor untuk anomali dalam input patterns

### 3. Model Inversion (Inversi Model)

**Konsep:**
Penyerang canggih (sophisticated attacker) dapat menyebabkan output model untuk menyimpulkan training data. Dikenal sebagai model inversion, penyerang terus memberi data ke model dan mempelajari output.

**Contoh Serangan dari Material Transcript:**
- **Skenario:** Model facial recognition dilatih pada gambar karyawan, outputnya adalah nama karyawan dan confidence score
- **Serangan:** Penyerang berulang kali memberi model gambar wajah, membuat perubahan hingga output adalah nama karyawan dengan confidence score tinggi
- **Hasil:** Hacker kemudian memiliki gambar yang baik dari karyawan
- **Dampak:** Penyerang dapat menggunakan gambar tersebut untuk menyamar sebagai karyawan

**Teknik Lanjutan - Reverse Model Creation:**
- Dengan cukup pasangan input-output, penyerang dapat membuat model baru yang bekerja terbalik
- Model baru dilatih pada output model asli
- Digunakan untuk menyimpulkan training input data
- Memungkinkan ekstraksi informasi sensitif dari training dataset


### 4. Model Extraction (Ekstraksi Model)

**Konsep:**
Hacker dapat melakukan reverse engineering pada model dan membuat model mereka sendiri yang sangat mirip dengan model asli. Semakin banyak informasi yang dimiliki hacker tentang model, semakin akurat salinan mereka.

**Proses Serangan:**
- Penyerang menganalisis input-output patterns
- Melakukan reverse engineering pada model behavior
- Membuat replika model dengan functionality serupa
- Mencuri intellectual property dan competitive advantage

**Dampak Bisnis:**
- Pencurian intellectual property
- Kompetitor dapat menggunakan model serupa tanpa investasi R&D
- Kehilangan keunggugan kompetitif
- Potensi kerugian finansial yang signifikan

**Strategi Mitigasi:**
- Batasi dan kontrol akses ke model dengan IAM policies
- Jangan berikan informasi yang tidak perlu di output model
- Monitor penggunaan model untuk pola yang mencurigakan
- Implementasi rate limiting untuk API calls
- Gunakan model watermarking jika tersedia

### 5. Prompt Injection (Injeksi Prompt)

**Konsep:**
Large Language Models rentan terhadap jenis serangan yang dikenal sebagai prompt injection. Dalam serangan ini, penyerang memberikan instruksi berbahaya (malicious instructions) ke model dalam prompt dengan tujuan mempengaruhi outputnya.

**Contoh Serangan dari Material Transcript:**
- Penyerang dapat meminta LLM untuk mengabaikan atau mengubah prompt template
- Memungkinkan penyerang mendapatkan informasi sensitif
- Memanipulasi perilaku model untuk tujuan berbahaya
- Bypass security controls yang telah ditetapkan

**Karakteristik Serangan:**
- Memanfaatkan cara LLM memproses dan mengikuti instruksi
- Dapat menimpa (override) security controls
- Sulit dideteksi tanpa monitoring dan filtering yang tepat
- Spesifik untuk generative AI dan LLM systems

**Strategi Mitigasi:**
- **Deteksi Otomatis:** Ajari LLM untuk mendeteksi prompt injection menggunakan key attack patterns
- **Response Filtering:** Return response "prompt attack detected" ketika serangan terdeteksi
- **Input Validation:** Validasi dan sanitasi input pengguna sebelum processing
- **Prompt Templates:** Implementasi prompt templates yang aman dan terstruktur
- **Guardrails:** Gunakan AWS Guardrails for Amazon Bedrock untuk content filtering


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

### Amazon SageMaker Model Monitor untuk Keamanan

**Referensi Material:** Task Statement 5.1 Lesson 5 - SageMaker Model Monitor memonitor kualitas model machine learning Amazon SageMaker di production.

**Fungsi Keamanan:**

1. **Continuous Quality Monitoring:**
   - Monitor kualitas model secara real-time setelah deployment
   - Deteksi dini untuk deviasi kualitas model
   - Setup alert otomatis untuk anomali

2. **Data Drift Detection:**
   - Membandingkan data dan model dengan baselines
   - Menghasilkan statistik dan metrik
   - Visible di SageMaker Studio dan dikirim ke CloudWatch

3. **Security Anomaly Detection:**
   - Monitor untuk perubahan yang tidak biasa dalam prediksi model
   - Investigasi untuk menentukan root cause (kualitas data rendah atau serangan)
   - Tindakan korektif segera

**Komponen Monitoring:**
- **Amazon CloudWatch Logs:** Mengumpulkan file monitoring status model
- **S3 Storage:** Menyimpan log files ke bucket yang ditentukan
- **Automated Alerts:** Notifikasi ketika kualitas model mencapai threshold preset
- **Dashboard Visualization:** Lihat hasil di SageMaker Studio

**Setup Process:**
1. **Enable Data Capture:** Menangkap inference input dan output
2. **Create Baseline:** Menggunakan training dataset sebagai baseline
3. **Schedule Monitoring Jobs:** Generate statistik dan perbandingan
4. **View Results:** Analisis di SageMaker Studio dan ambil tindakan

### Keamanan Network dengan VPC

**Referensi Material:** Task Statement 5.1 Lesson 4 - Pelanggan bertanggung jawab mengelola konfigurasi keamanan infrastruktur cloud mereka.

**Default Behavior dan Risiko:**
- SageMaker Studio dan Notebook instances diluncurkan di VPC yang dikelola SageMaker
- Direct internet access diizinkan secara default
- **Risiko:** Kemungkinan download kode berbahaya yang dapat mengirim data keluar

**Best Practice - Gunakan VPC Sendiri:**

1. **Buat VPC di Akun Anda:**
   - Konfigurasi VPC sesuai kebutuhan keamanan
   - Tentukan subnet dan routing yang aman

2. **Specify VPC saat Launch:**
   - Untuk SageMaker Studio
   - Untuk Notebook instances
   - Elastic Network Interface (ENI) dibuat di VPC Anda

3. **Network Controls:**
   - Security Groups untuk traffic control
   - Network Access Control Lists (NACLs)
   - Network Firewalls untuk advanced filtering

**VPC-Only Mode:**
- Tentukan "VPC only" untuk network access type
- Mencegah SageMaker memberikan akses internet ke notebook instances
- Maksimal security dengan trade-off connectivity

**VPC Interface Endpoints dengan AWS PrivateLink:**

**Konsep:**
- Menghubungkan VPC langsung ke layanan AWS tanpa melalui internet publik
- Menggunakan AWS PrivateLink untuk koneksi private
- Semua traffic tetap di private network AWS

**Layanan yang Didukung untuk AI/ML:**
- Amazon S3 (untuk data dan model artifacts)
- Amazon CloudWatch (untuk monitoring dan logging)
- SageMaker Runtime (untuk inference)
- SageMaker API (untuk management operations)
- AWS KMS (untuk key management)

**Keuntungan:**
- **Keamanan Maksimal:** Traffic tidak pernah melewati internet publik
- **Compliance:** Memenuhi requirements untuk data yang sangat sensitif
- **Performance:** Latensi rendah dan bandwidth tinggi
- **Cost Control:** Mengurangi data transfer costs

**Implementasi:**
1. Buat VPC Interface Endpoints untuk layanan yang diperlukan
2. Configure security groups untuk endpoints
3. Update route tables jika diperlukan
4. Test connectivity dari SageMaker instances

**Best Practice:**
- Gunakan untuk workload yang memerlukan keamanan tinggi
- Combine dengan VPC-only mode untuk isolasi maksimal
- Monitor endpoint usage dan performance
- Implement least privilege access untuk endpoints

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


## Ringkasan Task Statement 5.1: Metode Keamanan Sistem AI

### Konsep Kunci yang Harus Dipahami

**1. AWS Shared Responsibility Model untuk AI Systems**
- **AWS (Security OF the Cloud):** Infrastruktur, hardware, software, networking components
- **Pelanggan (Security IN the Cloud):** Konfigurasi layanan, keamanan data, kontrol akses, enkripsi
- **Tingkat Tanggung Jawab:** Bervariasi berdasarkan layanan (EC2 vs SageMaker Serverless)

**2. IAM Fundamentals untuk AI/ML**
- **Root User:** Harus dilindungi dengan MFA, gunakan hanya untuk tugas administratif
- **IAM Users:** Individual users dengan kredensial unik
- **IAM Groups:** Organisasi users berdasarkan job function
- **IAM Roles:** Temporary credentials untuk enhanced security
- **IAM Policies:** Identity-based dan resource-based policies
- **Multi-Factor Authentication (MFA):** Wajib untuk keamanan maksimal

**3. Data Encryption dengan AWS KMS**
- **Encryption at Rest:** Data tersimpan di storage
- **Encryption in Transit:** Data yang bergerak melalui jaringan (TLS/HTTPS)
- **Service-Owned Keys:** Default encryption, tidak ada kontrol pelanggan
- **AWS-Managed Keys:** Dikelola AWS, rotasi otomatis
- **Customer-Managed Keys:** Kontrol penuh, granular access control

**4. Network Security dengan VPC dan PrivateLink**
- **VPC Configuration:** Gunakan VPC sendiri untuk kontrol maksimal
- **VPC-Only Mode:** Mencegah internet access untuk keamanan tinggi
- **VPC Interface Endpoints:** Private connectivity ke layanan AWS
- **AWS PrivateLink:** Traffic tidak melewati internet publik
- **Security Groups dan NACLs:** Network-level access control

**5. AI-Specific Security Threats**
- **Data Poisoning:** Manipulasi training data untuk mengubah prediksi model
- **Adversarial Inputs:** Input yang dimanipulasi untuk menipu model
- **Model Inversion:** Ekstraksi training data dari model output
- **Model Extraction:** Reverse engineering untuk mencuri intellectual property
- **Prompt Injection:** Serangan khusus untuk Large Language Models

**6. SageMaker Security Features**
- **SageMaker Role Manager:** Simplified IAM role creation dengan pre-configured personas
- **SageMaker Model Monitor:** Continuous monitoring untuk quality dan security anomalies
- **VPC Integration:** Network isolation dan private connectivity
- **Data Capture:** Monitoring inference input/output untuk security analysis

### Best Practices Keamanan AI (Berdasarkan Material Transcript)

**Proactive Security Measures:**
1. **Secure and Limit Access:** Terapkan principle of least privilege dengan IAM policies
2. **Enable MFA:** Wajib untuk root user dan critical accounts
3. **Encrypt All Data:** At rest dan in transit menggunakan AWS KMS
4. **Use VPC Configuration:** Gunakan VPC sendiri dengan VPC-only mode untuk keamanan tinggi
5. **Block Public Access:** Gunakan S3 Block Public Access untuk mencegah data exposure

**AI-Specific Security Practices:**
6. **Validate Input Data:** Inspeksi dan validasi input dari users untuk unusual patterns
7. **Train with Adversarial Examples:** Meningkatkan robustness model terhadap adversarial attacks
8. **Frequent Re-training:** Train model secara berkala dengan data baru untuk undo corrupted data damage
9. **Monitor Model Predictions:** Gunakan SageMaker Model Monitor untuk deteksi anomali dan drift
10. **Limit Model Information:** Jangan berikan informasi yang tidak perlu di model output

**Governance dan Compliance:**
11. **Track All Artifacts:** Gunakan Model Registry, Model Cards, dan ML Lineage Tracking
12. **Audit Logging:** Enable CloudTrail untuk semua API calls
13. **Continuous Monitoring:** Setup automated alerts untuk security deviations
14. **Documentation:** Gunakan Model Cards untuk immutable record of model information
15. **Network Isolation:** Implementasi VPC interface endpoints untuk private connectivity

### Persiapan Ujian AWS AI Practitioner

**Fokus Utama untuk Task Statement 5.1:**

1. **AWS Shared Responsibility Model:**
   - Pahami pembagian tanggung jawab antara AWS dan pelanggan
   - Ketahui perbedaan tanggung jawab berdasarkan jenis layanan (EC2 vs SageMaker)

2. **IAM Fundamentals:**
   - Root user best practices dan MFA requirements
   - IAM users, groups, roles, dan policies
   - Identity-based vs resource-based policies
   - IAM Identity Center untuk workforce identities

3. **Data Encryption:**
   - Encryption at rest vs in transit
   - Service-owned vs AWS-managed vs customer-managed keys
   - AWS KMS capabilities dan use cases
   - Default encryption di layanan AWS

4. **Network Security:**
   - VPC configuration untuk SageMaker
   - VPC-only mode dan trade-offs
   - VPC interface endpoints dan AWS PrivateLink
   - Security groups dan network access controls

5. **AI-Specific Security Threats:**
   - Data poisoning attack scenarios
   - Adversarial inputs dan model manipulation
   - Model inversion dan data extraction
   - Prompt injection untuk LLMs
   - Mitigation strategies untuk setiap threat

6. **SageMaker Security Features:**
   - SageMaker Role Manager personas dan permissions
   - Model Monitor untuk security anomaly detection
   - VPC integration dan private connectivity
   - Audit logging dengan CloudTrail

**Tips Ujian:**
- Fokus pada practical scenarios dan use cases
- Pahami kapan menggunakan customer-managed vs service-managed keys
- Ketahui AI-specific threats dan appropriate mitigation strategies
- Understand trade-offs antara security dan usability
- Familiar dengan SageMaker security features dan best practices

---

**Referensi Material:** Task Statement 5.1 dari Domain 5 - Security, Compliance, and Governance (14% bobot ujian)
**Sumber:** Material transcript AWS Skill Builder course untuk AWS Certified AI Practitioner
