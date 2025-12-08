# Governance dan Compliance Regulations untuk Sistem AI

## Pengantar

Kekhawatiran tentang risiko AI telah mendorong pengembangan berbagai standar compliance untuk workload AI. Mengikuti standar-standar ini akan membantu melindungi bisnis dan pelanggan Anda serta memastikan keadilan dalam pengambilan keputusan. Tergantung pada industri perusahaan Anda, Anda mungkin juga perlu mematuhi standar khusus industri tersebut.

## AWS Shared Responsibility Model

### Konsep Dasar

Di AWS, keamanan dan compliance adalah tanggung jawab bersama antara AWS dan pelanggan. AWS menciptakan AWS Shared Responsibility Model untuk menjelaskan pembagian tanggung jawab ini.

**Tanggung Jawab AWS:**
- Memenuhi persyaratan compliance dari cloud dengan mengamankan pusat data fisik dan infrastruktur yang mendasarinya
- Menjaga sertifikasi keamanan dan compliance yang ketat
- Melakukan operasi pusat data, teknologi, dan keamanan

**Tanggung Jawab Pelanggan:**
- Mengamankan workload mereka di cloud untuk memenuhi persyaratan compliance
- Mengkonfigurasi kontrol keamanan dengan benar
- Mengelola proses dan prosedur saat menerapkan dan menjalankan workload di cloud

### AWS Artifact

AWS Artifact adalah layanan yang menyediakan laporan compliance dari auditor pihak ketiga kepada pelanggan. Meskipun Anda tidak dapat mengirim auditor Anda sendiri ke pusat data AWS, Anda dapat memberikan laporan ini kepada mereka.

**Manfaat AWS Artifact:**
- Mengurangi ruang lingkup audit karena kontrol compliance dalam laporan diwariskan oleh pelanggan
- Auditor Anda hanya perlu fokus pada proses dan prosedur Anda
- Menyediakan akses ke berbagai standar keamanan global, regional, dan khusus industri


## Standar Compliance Global

### SOC 2 (Service Organization Controls)

SOC 2 adalah cara untuk memverifikasi bahwa pihak ketiga mengikuti praktik terbaik tertentu. Laporan SOC 2 mencakup kontrol terkait:
- Keamanan (Security)
- Ketersediaan (Availability)
- Integritas pemrosesan (Processing Integrity)
- Kerahasiaan (Confidentiality)
- Privasi (Privacy)

**Implementasi:**
Jika perusahaan ingin mencapai SOC 2 untuk pelanggan mereka, mereka menggunakan laporan AWS SOC 2 sebagai titik awal, kemudian meminta auditor memverifikasi bahwa mereka telah mengkonfigurasi kontrol keamanan yang menjadi tanggung jawab mereka dengan benar.

### ISO 27001

ISO 27001 adalah standar manajemen keamanan internasional yang menentukan praktik terbaik manajemen keamanan dan kontrol keamanan yang komprehensif. Karena AWS telah mencapai sertifikasi untuk compliance dengan standar ini, AWS dapat membantu organisasi pelanggan mendapatkan sertifikasi tersebut.

### Customer Compliance Center

Customer Compliance Center adalah kumpulan sumber daya untuk membantu Anda mempelajari tentang compliance AWS. Di sini Anda dapat:
- Membaca kisah compliance pelanggan tentang bagaimana perusahaan di industri yang diatur menyelesaikan berbagai tantangan compliance, governance, dan audit
- Mengakses whitepaper dan dokumentasi compliance tentang berbagai topik
- Mempelajari jawaban AWS untuk pertanyaan compliance kunci
- Mengakses auditor learning path untuk individu dalam peran auditing, compliance, dan legal

## Standar Compliance untuk AI

### ISO 42001 dan ISO 23894

Kedua standar ini diterbitkan pada tahun 2023 dan menetapkan mekanisme untuk menilai dan mengelola risiko dalam sistem AI.

**Fokus Utama:**
- Menetapkan kerangka kerja bagi organisasi untuk secara sistematis menangani dan mengontrol risiko terkait pengembangan dan penerapan AI
- Menekankan komitmen terhadap praktik AI yang bertanggung jawab
- Mendorong organisasi untuk mengadopsi kontrol khusus untuk sistem AI mereka
- Mendorong interoperabilitas global dan menetapkan fondasi untuk pengembangan dan penerapan AI yang bertanggung jawab

**Catatan Penting:** Meskipun standar compliance sangat direkomendasikan, standar ini bukan persyaratan hukum.


## EU AI Act

EU AI Act adalah regulasi Eropa tentang kecerdasan buatan (AI) dan merupakan regulasi komprehensif pertama tentang AI oleh regulator besar di mana pun. Undang-undang ini menetapkan aplikasi AI ke dalam tiga kategori risiko:

### 1. Risiko yang Tidak Dapat Diterima (Unacceptable Risk)

Aplikasi dan sistem yang menciptakan risiko yang tidak dapat diterima **dilarang sepenuhnya**.

**Contoh aplikasi yang dilarang:**
- Aplikasi social scoring yang mengklasifikasikan individu atau kelompok berdasarkan perilaku sosial
- Database pengenalan wajah yang mengambil gambar wajah dari internet
- Aplikasi yang menyimpulkan emosi di tempat kerja atau institusi pendidikan

### 2. Risiko Tinggi (High-Risk)

Aplikasi berisiko tinggi seperti alat pemindaian CV yang memberi peringkat pelamar kerja tunduk pada persyaratan hukum tertentu.

**Persyaratan untuk aplikasi high-risk:**
- Menetapkan sistem manajemen risiko
- Melakukan tata kelola data (data governance)
- Mendokumentasikan compliance

### 3. Risiko Rendah atau Tidak Terdaftar

Aplikasi yang tidak secara eksplisit dilarang atau terdaftar sebagai risiko tinggi sebagian besar tidak diatur. Sebagian besar sistem AI akan masuk dalam kategori risiko tinggi.

**Catatan Penting:** Bahkan jika Anda tidak akan membuat sistem AI Anda tersedia untuk warga negara EU, regulasi EU sering menjadi standar global, seperti General Data Protection Regulation (GDPR). Oleh karena itu, Anda harus memperhatikan dan berusaha memenuhinya.

## NIST AI Risk Management Framework (RMF)

AI Risk Management Framework (RMF) yang dirilis oleh National Institute of Standards and Technology (NIST) memberikan panduan untuk mempromosikan pengembangan dan penggunaan sistem AI yang dapat dipercaya dan bertanggung jawab.

### Tujuan AI RMF

Menawarkan sumber daya kepada organisasi yang merancang, mengembangkan, menerapkan, atau menggunakan sistem AI untuk membantu mengelola risiko AI. Framework ini bersifat sukarela dan mempromosikan pengembangan dan penggunaan sistem AI yang dapat dipercaya dan bertanggung jawab.

### Empat Fungsi Utama AI RMF

1. **Govern (Mengatur)** - Menetapkan kebijakan dan struktur tata kelola
2. **Map (Memetakan)** - Mengidentifikasi dan mendokumentasikan konteks AI
3. **Measure (Mengukur)** - Menilai dan mengukur risiko AI
4. **Manage (Mengelola)** - Mengelola dan memitigasi risiko AI


## Manajemen Risiko AI

### Formula Estimasi Risiko

Menurut NIST RMF, risiko dapat diestimasi dengan mengalikan kemungkinan terjadinya suatu peristiwa dengan tingkat keparahan konsekuensi jika itu terjadi:

```
Risiko = Kemungkinan (Likelihood) × Tingkat Keparahan (Severity)
```

Menggunakan matriks risiko ini, kita dapat menganggap peristiwa dengan tingkat keparahan rendah dan kemungkinan terjadinya yang jarang sebagai risiko yang sangat rendah.

### Langkah-langkah Estimasi Risiko Sistem AI

1. **Identifikasi Use Case dan Stakeholder**
   - Pertimbangkan bagaimana pengguna tertentu akan menggunakan sistem untuk mencapai tujuan tertentu

2. **Identifikasi Peristiwa Berbahaya**
   - Identifikasi peristiwa berbahaya yang terkait dengan use case
   - Gunakan matriks risiko untuk menentukan risiko untuk setiap peristiwa

3. **Tangani Inherent Risk (Risiko Inheren)**
   - Risiko yang dapat dimitigasi dengan kontrol keamanan dan pemantauan yang tepat
   - Dengan meningkatkan kontrol keamanan, Anda mengurangi kemungkinan terjadinya peristiwa sehingga menurunkan risiko keseluruhannya

4. **Evaluasi Residual Risk (Risiko Sisa)**
   - Risiko yang tersisa setelah mitigasi
   - Fokus pada peringkat risiko sisa tertinggi

5. **Ringkasan Tingkat Risiko**
   - Tentukan peringkat risiko keseluruhan untuk sistem
   - Ditentukan dengan fokus pada peringkat risiko sisa tertinggi

## Algorithmic Accountability Act

Algorithmic Accountability Act telah diperkenalkan beberapa kali untuk dipertimbangkan oleh Kongres Amerika Serikat. Jika diberlakukan, undang-undang ini akan:

**Persyaratan:**
- Mengharuskan perusahaan untuk menilai dampak sistem AI yang mereka gunakan dan jual
- Menciptakan transparansi baru tentang kapan dan bagaimana sistem tersebut digunakan
- Memberdayakan konsumen untuk membuat pilihan yang tepat saat berinteraksi dengan sistem AI

**Tujuan:**
Melindungi warga Amerika dari sistem AI yang dapat menyebabkan hasil yang tidak adil dan tidak dapat dijelaskan.

**Contoh:** Konsumen memiliki hak untuk mengetahui mengapa aplikasi pinjaman mereka ditolak dan apakah itu karena bias yang tidak adil dan inheren.


## Explainability dan Transparansi AI

### Konsep Explainability

Karena model generative AI sangat kompleks, sulit untuk memahami bagaimana model mencapai output pada tingkat yang mendalam. Memahami bagaimana sistem AI mencapai output dikenal sebagai **explainability**.

### Tingkat Transparansi Minimum

Sebagai tingkat transparansi minimum, pertimbangkan kapan harus mengungkapkan kepada pengguna Anda bahwa mereka menggunakan generative AI dan tidak berinteraksi dengan manusia. Namun, untuk banyak aplikasi, Anda mungkin perlu lebih dalam dan dapat menjelaskan bagaimana model mencapai inferensi.

### Pendekatan Explainability

#### 1. Model Agnostic Approach (Pendekatan Agnostik Model)

Mengamati perilaku model terkait output dan input. Dengan pendekatan ini, praktisi dapat:
- Menentukan fitur mana yang paling dipertimbangkan
- Memperlakukan model sebagai black box
- Tidak perlu memahami struktur internal model

#### 2. Interpretable Algorithms (Algoritma yang Dapat Diinterpretasikan)

Menggunakan algoritma dan teknik yang lebih dapat diinterpretasikan seperti:
- Decision trees (pohon keputusan)
- Rule-based systems (sistem berbasis aturan)

Dengan pendekatan ini, Anda dapat:
- Mengamati bobot model
- Memahami cara kerja internal model

**Pertimbangan Penting:** Pada tahap awal pengembangan AI dan ML, Anda harus mempertimbangkan trade-off antara interpretability dan performance dengan persyaratan regulasi dalam pikiran.

## Bias Removal dan Algorithmic Accountability

### Tujuan Penghapusan Bias

Alasan utama kedua untuk algorithmic accountability adalah menghilangkan bias dari pengambilan keputusan. Tujuannya adalah memastikan bahwa hasil tidak dipengaruhi oleh penggunaan yang tidak tepat dari berbagai atribut pribadi seseorang.

### Atribut yang Harus Dilindungi

- Ras (Race)
- Jenis kelamin (Sex)
- Identitas gender (Gender Identity)
- Keyakinan agama (Religious Beliefs)
- Afiliasi politik (Political Affiliations)
- Lokasi tempat tinggal (apakah di kota atau komunitas pedesaan)

### Implementasi Penghapusan Bias

Tujuan penghapusan bias ini mengharuskan Anda untuk:
- Menguji bias dalam hasil model
- Memantau bias dalam data pelatihan model
- Melakukan monitoring berkelanjutan

### Amazon SageMaker Clarify

Amazon SageMaker Clarify dapat membantu Anda:
- Memahami bagaimana berbagai variabel mempengaruhi perilaku model
- Memantau bias dan feature attribution drift
- Memberikan transparansi dalam pengambilan keputusan model


## Layanan AWS untuk AI Compliance

### AWS Audit Manager

AWS Audit Manager membantu pelanggan mencapai compliance dengan memetakan persyaratan compliance ke data penggunaan AWS.

**Fungsi Utama:**
- Mengumpulkan bukti compliance atau non-compliance
- Menghasilkan laporan penilaian yang dapat diberikan kepada auditor
- Membuat assessment berdasarkan framework yang dipilih

**Framework:**
Framework adalah pengelompokan kontrol yang terkait dengan audit Anda. Audit Manager memiliki framework bawaan termasuk:
- Generative AI best practices
- SOC 2
- Framework kustom yang dapat Anda definisikan sendiri

**Proses Kerja:**
1. Saat Anda membuat assessment, Audit Manager secara otomatis menilai sumber daya di akun dan layanan AWS Anda berdasarkan kontrol yang didefinisikan dalam framework
2. Mengumpulkan bukti yang relevan dan mengonversinya ke format yang ramah auditor
3. Melampirkan bukti ke kontrol dalam assessment Anda
4. Saat waktu audit tiba, Anda dapat meninjau bukti yang dikumpulkan dan menambahkannya ke laporan assessment
5. Laporan ini membantu Anda menunjukkan bahwa kontrol Anda berfungsi sebagaimana dimaksud

### Guardrails for Amazon Bedrock

Guardrails adalah fitur untuk Amazon Bedrock yang Anda gunakan untuk menerapkan safeguard khusus aplikasi berdasarkan use case dan kebijakan AI yang bertanggung jawab.

**Fitur Content Filters:**
- Menyediakan filter konten dengan threshold yang dapat dikonfigurasi untuk memfilter konten berbahaya
- Kategori: hate (kebencian), insults (penghinaan), sexual (seksual), dan violence (kekerasan)

**Denied Topics:**
Menggunakan deskripsi bahasa alami yang singkat, Guardrails memungkinkan Anda untuk:
- Mendefinisikan serangkaian topik yang harus dihindari dalam konteks aplikasi Anda
- Secara opsional memberikan beberapa frasa contoh untuk membantu guardrails mengenali topik
- Mendeteksi dan memblokir input pengguna dan respons FM yang masuk dalam topik yang dibatasi

**PII Detection:**
Guardrails memungkinkan Anda untuk:
- Mendeteksi Personally Identifiable Information (PII) dalam input pengguna dan respons FM
- Secara selektif menolak input yang mengandung PII
- Menyunting (redact) PII dalam respons FM berdasarkan use case

**Implementasi:**
- Anda dapat mengonfigurasi threshold di berbagai kategori untuk memfilter interaksi berbahaya
- Guardrails akan secara otomatis mengevaluasi query pengguna dan respons FM untuk mendeteksi dan membantu mencegah konten yang masuk dalam kategori yang dibatasi

**Contoh Penggunaan:**
- Situs e-commerce dapat merancang asisten online-nya untuk menghindari penggunaan bahasa yang tidak pantas seperti hate speech atau penghinaan
- Jika Anda ingin memblokir model Anda dari memberikan nasihat investasi, Anda dapat menambahkan denied topic dan menjelaskannya dalam istilah sederhana
- Anda dapat menentukan dua pesan untuk diberikan sebagai respons: satu ketika prompt diblokir dan satu ketika respons oleh model diblokir
- Contoh respons: "Kami mohon maaf, tetapi topik itu di luar area keahlian kami."


### AWS Config

AWS Config membantu Anda menyadari jika ada perubahan dalam konfigurasi sumber daya yang membuatnya tidak compliant.

**Fungsi Utama:**
- Menyediakan inventaris terperinci dari konfigurasi saat ini dari sumber daya AWS
- Menangkap dan merekam perubahan dalam snapshot riwayat konfigurasi setiap kali terjadi perubahan konfigurasi sumber daya
- Mengevaluasi perubahan dengan configuration rules
- Jika perubahan tidak compliant dengan rules, dapat secara otomatis diperbaiki dengan AWS Systems Manager automation document

**Configuration Rules:**
- Anda dapat memilih untuk menggunakan rules yang sudah dibuat sebelumnya
- Atau membuat custom rule menggunakan Lambda function

**Conformance Packs:**
Conformance packs mengemas bersama AWS Config rules dan tindakan remediasi untuk membantu menerapkan rules dan remediasi untuk memenuhi kebutuhan compliance Anda.

**Conformance Packs yang Berguna:**
1. **Operational Best Practices for AI and ML** - Praktik terbaik operasional untuk AI dan ML
2. **Security Best Practices for Amazon SageMaker** - Praktik terbaik keamanan untuk Amazon SageMaker

Anda dapat membuat conformance pack sendiri atau memilih dari library template conformance pack.

### Amazon Inspector

Sementara AWS Config memantau konfigurasi pada tingkat sumber daya, Amazon Inspector bekerja pada tingkat aplikasi.

**Fungsi Utama:**
- Memeriksa aplikasi dan container untuk kerentanan keamanan
- Mendeteksi penyimpangan dari praktik terbaik keamanan
- Menjalankan penilaian keamanan otomatis

**Pemeriksaan yang Dilakukan:**
- Akses terbuka ke instance EC2
- Instalasi versi perangkat lunak yang rentan
- Kerentanan keamanan lainnya

**Output:**
Setelah Amazon Inspector melakukan penilaian, ia memberikan Anda daftar temuan keamanan yang:
- Diprioritaskan berdasarkan tingkat keparahan
- Menyertakan deskripsi terperinci dari setiap masalah keamanan
- Memberikan rekomendasi tentang cara memperbaikinya

### AWS Trusted Advisor

AWS Trusted Advisor membantu Anda mengoptimalkan biaya, meningkatkan kinerja, meningkatkan keamanan dan ketahanan, serta beroperasi dalam skala di cloud.

**Kategori Pemeriksaan:**
1. **Cost Optimization** - Optimasi biaya
2. **Performance** - Kinerja
3. **Resilience** - Ketahanan
4. **Security** - Keamanan
5. **Operational Excellence** - Keunggulan operasional
6. **Service Limits** - Batas layanan

**Cara Kerja:**
- Trusted Advisor terus mengevaluasi lingkungan AWS Anda menggunakan pemeriksaan praktik terbaik di seluruh kategori
- Merekomendasikan tindakan untuk memperbaiki penyimpangan dari praktik terbaik
- Memberikan panduan proaktif untuk meningkatkan lingkungan AWS Anda


## Data Governance

### Definisi Data Governance

Data governance adalah kombinasi dari people (orang), process (proses), dan technology (teknologi) yang digunakan untuk mengelola availability (ketersediaan), usability (kegunaan), integrity (integritas), dan security (keamanan) data sistem enterprise.

**Tujuan:** Data governance yang efektif memastikan data konsisten dan dapat dipercaya tanpa disalahgunakan.

### Tiga Komponen Utama Data Governance

#### 1. Curation (Kurasi)

**Definisi:** Mengidentifikasi dan mengelola sumber data paling berharga Anda pada skala besar.

**Sumber Data:**
- Databases (basis data)
- Data lakes
- Data warehouses

**Manfaat:**
- Membatasi proliferasi dan transformasi aset data kritis
- Memastikan data akurat, segar, dan bebas dari informasi sensitif
- Pengguna dapat memiliki kepercayaan dalam keputusan berbasis data

#### 2. Discovery and Understanding (Penemuan dan Pemahaman)

**Definisi:** Memahami data dalam konteks sehingga pengguna dapat menemukan dan memahami makna data mereka untuk menggunakannya dengan percaya diri untuk mendorong nilai bisnis.

**Komponen:**
- **Data Catalog Terpusat:** Data dapat ditemukan dengan mudah
- **Request Access:** Akses dapat diminta
- **Business Decisions:** Data dapat digunakan untuk membuat keputusan bisnis

#### 3. Protection (Perlindungan)

**Definisi:** Mampu mencapai keseimbangan yang tepat antara privasi data, keamanan, dan akses.

**Prinsip:**
- Penting untuk dapat mengatur data di seluruh batas organisasi
- Menggunakan alat yang intuitif untuk pengguna bisnis dan teknik
- Memperlakukan data sebagai aset strategis

### Implementasi Data Governance

**Langkah Awal:**
1. Mulai dengan domain data yang diperlukan untuk berhasil dengan inisiatif bisnis yang ditargetkan
2. Definisikan peran dan tanggung jawab data governance utama
3. Pertimbangkan segregation of duties (pemisahan tugas)
4. Tetapkan peran kunci kepada individu yang sesuai dalam organisasi Anda

**Peran Kunci:**

#### Data Owner (Pemilik Data)
- Orang tingkat eksekutif yang membuat keputusan kebijakan data
- Termasuk kebijakan regulasi dan compliance
- Memutuskan siapa yang memiliki akses ke data (misalnya, data klaim, data pelanggan)
- Memiliki hubungan langsung dengan data steward

#### Data Steward
- Orang dari bisnis yang memiliki pengetahuan terperinci tentang data
- Terlibat dalam detail proyek sehari-hari
- Membantu memahami masalah data yang mungkin menyebabkan tantangan dengan inisiatif bisnis
- Menyelesaikan tugas harian untuk proyek
- Tanggung jawab dari semua personel bisnis yang berhadapan dengan data

#### IT (Information Technology)
- Membantu menavigasi sistem yang menghasilkan dan mengonsumsi data
- Menyediakan data steward dengan alat dan kemampuan yang tepat
- Bertanggung jawab untuk mengelola dan menerapkan alat data governance di AWS


### Komponen Data Governance

#### Data Profiling

**Definisi:** Data diperiksa secara sistematis untuk menentukan apakah ada yang salah dengan data dan untuk memahami karakteristik data untuk berbagai tujuan.

**Fungsi:**
- Menentukan kualitas data
- Mengidentifikasi masalah dalam data
- Memahami struktur dan konten data

#### Data Catalog

**Definisi:** Memastikan bahwa data tersedia untuk orang yang memerlukan akses ke data tersebut.

**Manfaat:**
- Penemuan data yang mudah
- Manajemen akses terpusat
- Metadata terorganisir

#### Data Lineage

**Definisi:** Mengidentifikasi dari mana elemen data tertentu berasal dan bagaimana data dipindahkan, ditransformasi, dan disimpan.

**Pentingnya:**
Ketika konsumen data melihat data dalam laporan, mereka sering mempertanyakan:
- Dari mana data berasal
- Perhitungan apa yang dibuat sepanjang jalan
- Bagaimana data berubah dari waktu ke waktu

### AWS Glue DataBrew

AWS Glue DataBrew adalah alat persiapan data visual yang dapat digunakan pengguna untuk membersihkan dan menormalisasi data tanpa menulis kode apa pun.

#### Fitur Data Profiling

**Fungsi:**
- Menjalankan profiling jobs terhadap dataset Anda untuk membuat data profile
- Profile memberitahu Anda tentang bentuk data yang ada, termasuk:
  - Konteks konten
  - Struktur data
  - Hubungannya

**Data Quality Rules:**
- Anda dapat mendefinisikan aturan kualitas data
- Aturan ini divalidasi selama profiling untuk mendeteksi masalah dengan data

**Jenis Dataset yang Didukung:**
- Data yang disimpan di Amazon S3
- Relational databases
- Data warehouses

#### Fitur Data Lineage

**Fungsi:**
- Melacak data Anda dalam antarmuka visual untuk menentukan asalnya
- Menunjukkan bagaimana data mengalir melalui entitas yang berbeda dari mana asalnya
- Anda dapat melihat:
  - Asal data
  - Entitas lain yang mempengaruhinya
  - Apa yang terjadi padanya dari waktu ke waktu
  - Di mana data disimpan


### Data Quality Management

**Definisi:** Menangani masalah kualitas data yang ditemukan dalam data profiling atau melalui cara lain.

**Pendekatan:**
- Jika memungkinkan, kita perlu sampai ke akar penyebab masalah kualitas data
- Memerlukan pengetahuan bisnis dan teknis tentang data dan perannya dalam inisiatif yang ditargetkan
- Jika masalah melibatkan sumber, kita harus memberi tahu dan melaporkan masalah kepada data steward dan pengguna bisnis yang dapat memperbaiki masalah

### Data Integration

**Definisi:** Mengumpulkan dan menggabungkan data dari berbagai sumber.

**Tujuan:**
- Memastikan bahwa data dari sumber yang berbeda terhubung bersama secara koheren
- Data dapat digabungkan untuk mendapatkan gambaran yang lebih lengkap

### AWS Glue Data Catalog

**Fungsi:**
- Menyimpan metadata tentang sumber data Anda
- Metadata mencakup informasi tentang lokasi dan skema, termasuk tipe data dan definisi tabel

**Cara Mengisi Data Catalog:**
1. **Manual:** Anda dapat mengisi data catalog secara manual
2. **Otomatis:** Anda dapat mendefinisikan AWS Glue crawler job yang memindai sumber data dan mengisi catalog secara otomatis

### AWS Glue Data Quality

**Fungsi:**
- Mengevaluasi objek yang disimpan dalam AWS Glue Data Catalog
- Menawarkan cara yang mudah bagi non-coder untuk menyiapkan aturan kualitas data
- Termasuk merekomendasikan aturan kualitas
- Secara otomatis menggunakan machine learning untuk mendeteksi anomali data

**Proses:**
1. Setelah Anda mendefinisikan rule set, Anda menjalankan AWS Glue Data Quality job
2. Anda kemudian meninjau hasil di console yang menunjukkan aturan mana yang lulus atau tidak lulus

### Data Security

**Definisi:** Mendefinisikan siapa yang dapat memiliki akses ke data dan kapan mereka harus memiliki akses ke data.

**Contoh:**
- Data pelanggan tertentu perlu dapat diakses secara otomatis oleh peran tertentu seperti customer service atau sales
- Biasanya, data steward membantu mengaktifkan akses berbasis peran dan sementara yang dipandu oleh keputusan kebijakan yang ditetapkan oleh data owner

### Compliance

**Definisi:** Memahami regulasi pemerintah dan memastikan bahwa kita mematuhi regulasi tersebut.

**Implementasi:**
- Untuk memastikan compliance, data owner harus bekerja dengan tim keamanan dan legal untuk membuat keputusan kebijakan untuk domain data sensitif
- Aturan sering memerlukan interpretasi, penilaian, dan pengetahuan tentang bagaimana data digunakan dalam bisnis

### Data Lifecycle Management

**Definisi:** Bersikap disengaja tentang menyimpan data untuk akses yang mudah dan biaya yang dioptimalkan.

**Prinsip:**
Data governance adalah tentang membuat data tersedia untuk orang dan aplikasi yang tepat ketika mereka membutuhkannya, sambil menjaga data tetap aman dengan kontrol yang sesuai.

**Keseimbangan:**
- **Terlalu banyak kontrol:** Data Anda menjadi terkunci dalam silo dan sulit digunakan untuk wawasan dan inovasi yang dapat membantu bisnis
- **Tidak cukup kontrol:** Data dan bisnis Anda berisiko


## AWS Lake Formation

### Fungsi Utama

AWS Lake Formation memungkinkan Anda mengelola kontrol akses fine-grained untuk data lake yang dibangun di Amazon S3 dan dikatalogkan menggunakan AWS Glue Data Catalog.

**Kontrol Akses:**
- Permissions Lake Formation ditegakkan menggunakan kontrol granular pada tingkat kolom, baris, dan sel
- Berlaku di seluruh layanan analytics dan machine learning AWS

### Cara Kerja

1. **Identifikasi Data Stores:**
   - Identifikasi data stores yang ada di Amazon S3
   - Atau relational dan NoSQL databases
   - Pindahkan data ke data lake Anda

2. **Katalog Data:**
   - Katalog data menggunakan AWS Glue Data Catalog
   - Siapkan permissions

3. **Akses Data:**
   - Pengguna mencoba mengakses data menggunakan integrated analytical engine seperti:
     - Amazon Athena
     - AWS Glue
     - Amazon EMR
     - Amazon Redshift
   - AWS Glue Data Catalog memeriksa permissions dengan Lake Formation sebelum memberikan akses

**Manfaat:**
- Membantu Anda memecah data dalam silo
- Menggabungkan berbagai jenis data terstruktur dan tidak terstruktur ke dalam repositori terpusat
- Kontrol akses yang granular dan aman

## Amazon S3 Storage Classes

### Konsep Lifecycle Management

Data pelatihan untuk model Anda biasanya disimpan di S3 buckets. Setelah menggunakannya untuk melatih model Anda, Anda mungkin tidak perlu mengaksesnya lagi, tetapi masih perlu menyimpannya untuk alasan compliance.

### Kelas Penyimpanan S3

#### 1. S3 Standard
- **Penggunaan:** Data yang sering diakses
- **Karakteristik:** Akses cepat, biaya penyimpanan standar

#### 2. S3 Standard-IA (Infrequent Access)
- **Penggunaan:** Data yang jarang diakses tetapi harus dapat diambil dengan cepat saat dibutuhkan
- **Biaya:** Lebih murah untuk penyimpanan, lebih mahal untuk pengambilan dibandingkan S3 Standard

#### 3. S3 One Zone-IA
- **Penggunaan:** Data yang jarang diakses dan tidak memerlukan redundansi multi-AZ
- **Biaya:** Lebih murah dari S3 Standard-IA

#### 4. S3 Intelligent-Tiering
- **Penggunaan:** Data dengan pola akses yang tidak diketahui atau berubah
- **Fitur:** Secara otomatis memindahkan objek yang jarang diakses ke tier infrequent access yang lebih murah

#### 5. S3 Glacier Storage Classes
- **Penggunaan:** Data yang jarang diakses dan digunakan terutama untuk menyimpan data dalam arsip jangka panjang untuk retensi data atau alasan compliance
- **Opsi:** Kelas S3 Glacier yang berbeda menyediakan opsi untuk seberapa cepat Anda dapat mengambil data Anda dari arsip saat dibutuhkan


### Lifecycle Rules

**Definisi:** Ketika Anda mengetahui pola akses data Anda, Anda harus membuat lifecycle rules pada bucket Anda.

**Fungsi:**
- Rules akan memindahkan data Anda ke tier infrequent access dan archive saat kondisi rule terpenuhi
- Untuk setiap lifecycle rule, Anda menentukan:
  - Target storage class
  - Jumlah hari setelah pembuatan bahwa data harus ditransisikan

**Opsi Tambahan:**
- Anda juga dapat memilih untuk membuat rule yang menghapus data ketika tidak lagi perlu disimpan

**Contoh Lifecycle Rule:**

```
Hari 0: Data dibuat di S3 Standard
↓
Hari 5: Transisi ke S3 Standard-IA
↓
Hari 120: Transisi ke S3 Glacier Deep Archive
↓
5 Tahun: Data dihapus
```

Anda dapat membuat lifecycle rule yang:
1. Mentransisikan data Anda dari S3 Standard ke S3 Standard-IA 5 hari setelah pembuatan
2. Kemudian memindahkan data ke S3 Glacier Deep Archive 120 hari setelah pembuatan
3. Menghapus data setelah 5 tahun

## Implementasi Strategi AI Governance

### Langkah 1: Identifikasi Scope Tanggung Jawab

Strategi AI governance dimulai dengan mengidentifikasi scope tanggung jawab Anda. Tanggung jawab ini dapat mencakup:

1. **Governance and Compliance** - Tata kelola dan kepatuhan
2. **Legal and Privacy** - Hukum dan privasi
3. **Risk Management** - Manajemen risiko
4. **Implementing Security Controls** - Implementasi kontrol keamanan
5. **Model Resilience** - Ketahanan model

### Generative AI Security Scoping Matrix

Matrix ini menunjukkan peningkatan tingkat scope, tergantung pada cara AI dikonsumsi atau diimplementasikan.

#### Scope 1 dan 2: Konsumsi Aplikasi Pihak Ketiga
- **Tanggung Jawab:** Paling sedikit
- **Karakteristik:** Anda mengonsumsi aplikasi consumer atau enterprise pihak ketiga
- **Contoh:** Menggunakan aplikasi AI yang sudah jadi

#### Scope 3, 4, dan 5: Membangun Solusi AI Sendiri
- **Tanggung Jawab:** Lebih besar
- **Karakteristik:** 
  - Anda membangun solusi AI Anda sendiri
  - Data Anda dapat digunakan dalam training, fine-tuning, atau output model
- **Tanggung Jawab Anda:**
  - Mengklasifikasikan data dan model untuk risiko
  - Mengimplementasikan threat modeling
  - Membatasi akses
  - Mengimplementasikan kontrol keamanan
  - Memastikan ketahanan endpoint model

### Contoh Perubahan Tanggung Jawab Governance dan Compliance

Tanggung jawab untuk governance dan compliance berubah seiring dengan peningkatan scope:

**Scope 1-2 (Aplikasi Pihak Ketiga):**
- Tanggung jawab minimal
- Vendor menangani sebagian besar compliance

**Scope 3-5 (Solusi Custom):**
- Tanggung jawab penuh
- Anda harus mengelola semua aspek compliance


### Pendekatan Pemilihan Solusi AI

**Prinsip Utama:** Cari solusi dari kiri ke kanan, dimulai dengan layanan AI yang sudah terlatih penuh.

#### Urutan Prioritas:

1. **Fully Trained AI Services (Scope 1-2)**
   - **Contoh:** Amazon Comprehend, Amazon Translate
   - **Keuntungan:** Tanggung jawab governance minimal
   - **Kapan Digunakan:** Jika layanan ini memiliki semua data dan fungsionalitas yang Anda butuhkan

2. **Pre-trained Models (Scope 3)**
   - **Contoh:** Amazon Bedrock
   - **Keuntungan:** Dapat ditingkatkan dengan Retrieval Augmented Generation (RAG)
   - **Kapan Digunakan:** Jika layanan fully trained tidak memenuhi kebutuhan

3. **Pre-trained Models with Fine-tuning (Scope 4-5)**
   - **Contoh:** Model yang tersedia di SageMaker JumpStart
   - **Keuntungan:** Dapat di-fine-tune dengan data Anda sendiri
   - **Kapan Digunakan:** Jika Anda memerlukan customization yang lebih dalam

**Manfaat Meminimalkan Scope:**
Meminimalkan scope Anda akan meminimalkan tanggung jawab Anda untuk:
- Governance dan compliance
- Legal dan privacy
- Risk management
- Implementing security controls
- Model resilience

### Langkah 2: Dokumentasi Kebijakan AI Governance

Setelah scope Anda ditentukan, langkah selanjutnya adalah:

#### Dokumentasi Kebijakan
- Dokumentasikan kebijakan AI governance Anda
- Latih karyawan Anda tentang tanggung jawab mereka
- Tanggung jawab sesuai dengan peran pekerjaan dan tingkat akses mereka

#### Isi Kebijakan
Kebijakan ini mencakup:
- Menetapkan standar untuk data governance
- Permintaan akses (access requests)
- Transparansi model (model transparency)

#### Panduan Kebijakan
- Gunakan compliance dan sertifikasi yang diperlukan bisnis untuk memandu kebijakan dan praktik terbaik
- Definisikan mekanisme untuk memantau kinerja sistem AI, compliance, dan bias
- Tentukan tindakan berdasarkan threshold yang telah ditentukan sebelumnya

### Langkah 3: Review dan Revisi Berkelanjutan

**Proses Berkelanjutan:**
- Sering meninjau hasil
- Merevisi kebijakan yang ada sesuai kebutuhan
- Memastikan keselarasan dengan tujuan bisnis dan keamanan AI

**Tujuan:**
- Memastikan kebijakan tetap relevan
- Menyesuaikan dengan perubahan teknologi dan regulasi
- Menjaga keselarasan dengan tujuan bisnis

## Ringkasan

Governance dan compliance untuk sistem AI adalah aspek kritis yang memerlukan:

1. **Pemahaman Standar:** Memahami berbagai standar compliance global dan regional (ISO, SOC 2, EU AI Act, NIST RMF)

2. **Manajemen Risiko:** Mengidentifikasi, mengukur, dan mengelola risiko AI secara sistematis

3. **Transparansi dan Explainability:** Memastikan sistem AI dapat dijelaskan dan transparan dalam pengambilan keputusan

4. **Penghapusan Bias:** Menguji dan memantau bias dalam model dan data pelatihan

5. **Layanan AWS:** Memanfaatkan layanan AWS seperti Audit Manager, Guardrails, Config, Inspector, dan Trusted Advisor untuk compliance

6. **Data Governance:** Mengelola data dengan baik melalui curation, discovery, dan protection

7. **Strategi Implementasi:** Mengidentifikasi scope, mendokumentasikan kebijakan, dan melakukan review berkelanjutan

Dengan mengikuti praktik terbaik ini, organisasi dapat membangun dan menerapkan sistem AI yang bertanggung jawab, aman, dan compliant dengan regulasi yang berlaku.
