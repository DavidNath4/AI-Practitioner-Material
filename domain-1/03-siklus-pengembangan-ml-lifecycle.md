# Siklus Pengembangan Machine Learning (ML Development Lifecycle)

## Pengantar

Materi ini membahas **Task Statement 1.3: Describe the ML development lifecycle** dari Domain 1 AWS Certified AI Practitioner berdasarkan material transcript resmi dari AWS Skill Builder course. Machine Learning Development Lifecycle adalah serangkaian tahapan yang saling terhubung, dimulai dari mendefinisikan tujuan bisnis hingga mengoperasikan model ML yang telah di-deploy.

**Sumber Material:** material-transcript-1-3.txt (7 lessons)
**Exam Weight:** 20% dari total ujian
**Focus:** ML pipeline, AWS services, MLOps, monitoring, metrics

### Konsep Kunci dari Material Transcript

**Machine Learning Pipeline** adalah serangkaian langkah yang saling terhubung yang dimulai dengan tujuan bisnis dan berakhir dengan mengoperasikan model ML yang telah di-deploy. Pipeline ini terdiri dari:
1. Mendefinisikan masalah bisnis
2. Mengumpulkan dan mempersiapkan data training
3. Melatih model
4. Deploy model
5. Monitoring model

**Karakteristik Penting:**
- Beberapa tahapan merupakan proses iteratif yang diulang hingga objektif tertentu tercapai
- Model ML bersifat dinamis dan perlu di-retrain secara berkala dengan data baru
- Dievaluasi terus-menerus dan disesuaikan atau dibangun ulang sesuai kebutuhan
- Banyak yang lebih suka menganggap ML pipeline sebagai lifecycle, dimana bagian atau bahkan seluruhnya diulang bahkan setelah model di-deploy

## 1. Pipeline Machine Learning

### Konsep Dasar Pipeline ML

Pipeline ML terdiri dari beberapa tahapan utama:
1. **Mendefinisikan masalah bisnis**
2. **Mengumpulkan dan mempersiapkan data training**
3. **Melatih model**
4. **Deploy model**
5. **Monitoring model**

Beberapa tahapan ini merupakan proses iteratif yang diulang hingga objektif tertentu tercapai. Model ML bersifat dinamis dan perlu di-retrain secara berkala dengan data baru, dievaluasi terus-menerus, dan disesuaikan atau dibangun ulang sesuai kebutuhan.

### Tahap 1: Mendefinisikan Tujuan Bisnis

#### Prinsip Fundamental dari Material Transcript

**Pengembangan model ML harus selalu dimulai dengan mengidentifikasi tujuan bisnis.** Organisasi yang mempertimbangkan ML harus memiliki ide yang jelas tentang masalah yang akan diselesaikan dan nilai bisnis yang akan diperoleh.

#### Langkah-langkah Penting:

**a. Identifikasi Masalah dan Nilai Bisnis**
- Organisasi harus memiliki pemahaman yang jelas tentang masalah yang akan diselesaikan
- Tentukan nilai bisnis yang akan diperoleh
- **Lebih dari sekedar ide**, Anda harus bisa mengukur nilai bisnis terhadap objektif bisnis dan kriteria kesuksesan yang spesifik
- **Tanpa kriteria kesuksesan yang jelas, Anda tidak akan bisa mengevaluasi model atau bahkan menentukan apakah ML adalah solusi terbaik**

**b. Alignment dengan Stakeholder**
- Dapatkan konsensus dari stakeholder untuk mendapatkan kesepakatan tentang tujuan proyek
- Setelah menentukan kriteria kesuksesan, evaluasi kemampuan organisasi untuk bergerak menuju target
- Target harus dapat dicapai dan menyediakan jalur yang jelas menuju production

**c. Evaluasi Kelayakan ML**
- Tentukan apakah ML adalah pendekatan yang tepat untuk mencapai tujuan bisnis
- Evaluasi semua opsi yang tersedia untuk mencapai tujuan
- Tentukan seberapa akurat hasil yang diharapkan sambil mempertimbangkan biaya dan skalabilitas dari setiap pendekatan

**d. Evaluasi Ketersediaan Data**
- Pastikan tersedia data training yang relevan dan berkualitas tinggi dalam jumlah yang cukup untuk algoritma
- Evaluasi data dengan cermat untuk memastikan sumber data yang tepat tersedia dan dapat diakses
- Formulasikan pertanyaan ML dalam bentuk: input, output yang diinginkan, dan metrik performa yang akan dioptimalkan

**e. Investigasi Opsi dan Analisis Cost-Benefit**
- Dengan masalah ML dalam pikiran, investigasi semua opsi yang tersedia
- **Mulai dengan solusi paling sederhana sebelum menentukan bahwa kompleksitas lebih tinggi diperlukan untuk memenuhi objektif bisnis**
- Ingat untuk melakukan analisis cost-benefit untuk melihat apakah proyek harus pindah ke fase berikutnya

### Opsi Solusi ML di AWS (Berdasarkan Material Transcript)

**AWS telah memperkenalkan sejumlah AI services untuk mendemokratisasi ML dan membuatnya dapat diakses oleh siapa saja.** Mereka telah mengidentifikasi banyak use case umum dan mengembangkan model ML yang mudah, dapat dikonsumsi, dan fully trained yang di-host sepenuhnya oleh mereka.

#### 1. AI Services (Fully Managed) - Prioritas Pertama
**Karakteristik:**
- Karena services ini pay-as-you-go, masuk akal untuk mengevaluasinya untuk melihat apakah mereka dapat memenuhi tujuan bisnis
- Banyak services ini memungkinkan Anda untuk menyesuaikan output mereka

**Contoh:**
- **Amazon Comprehend**: Untuk analisis teks dan NLP, Anda dapat membuat custom classifier yang menggunakan kategori Anda sendiri dengan menyediakan data training Anda

#### 2. Foundation Models dengan Amazon Bedrock - Untuk Generative AI
**Use Case:** Untuk use case generative AI
**Approach:** Amazon Bedrock memungkinkan Anda mulai dengan foundation model yang fully trained. Anda dapat fine-tune model ini dengan data Anda sendiri menggunakan transfer learning

#### 3. Pre-trained Models dengan SageMaker JumpStart - Transfer Learning
**SageMaker JumpStart menyediakan:**
- Pre-trained AI foundation models
- Task-specific models untuk computer vision dan natural language processing problem types
- Pre-trained pada large public datasets
- Opsi untuk fine-tuning model dengan incremental training menggunakan dataset Anda sendiri (proses yang dikenal sebagai transfer learning)
- **Menggunakan pre-trained model adalah penghematan besar dalam biaya dan waktu pengembangan dibanding membuat custom model dari awal**

#### 4. Training dari Awal - Pendekatan Paling Kompleks
**Karakteristik:**
- **Pendekatan paling sulit dan mahal**
- Seperti yang akan kita lihat di bagian selanjutnya, ini bukan hanya yang paling menantang secara teknis, tetapi juga memerlukan tanggung jawab paling besar untuk security dan compliance

## 2. Pengumpulan dan Pemrosesan Data Training

### Tahap Pengumpulan Data

#### Identifikasi dan Pengumpulan Data (Dari Material Transcript)

**Mulai dengan mengidentifikasi data yang dibutuhkan dan menentukan opsi untuk mengumpulkan data.**

**Pertanyaan Kunci yang Harus Dijawab:**
- Data training apa yang Anda butuhkan untuk mengembangkan model Anda?
- Di mana data dihasilkan dan disimpan?
- Apakah ini streaming data atau apakah Anda dapat memuat dalam batch process?
- Apakah data sudah dilabeli atau bagaimana Anda akan bisa melabelinya?

**Proses ETL (Extract, Transform, Load):**
- Untuk mengumpulkan data, Anda perlu mengkonfigurasi proses yang dikenal sebagai extract, transform, dan load (ETL)
- Mengumpulkan data dari kemungkinan multiple sources dan menyimpannya di centralized repository
- **Ingat bahwa model harus di-retrain secara berkala dengan data baru, jadi proses Anda perlu repeatable**

**Labeling Data - Tantangan Utama:**
- **Ini bisa menjadi salah satu bagian terpanjang dalam proses karena data yang dilabeli dengan akurat kemungkinan belum tersedia**
- Memerlukan waktu dan effort yang signifikan untuk menyelesaikan

### Tahap Persiapan Data

#### Data Pre-processing (Dari Material Transcript)

**Data preparation mencakup data pre-processing dan feature engineering.**

**Exploratory Data Analysis (EDA):**
- EDA dengan visualization tools dapat membantu untuk dengan cepat mendapatkan pemahaman yang lebih dalam tentang data
- Anda dapat menggunakan data wrangling tools untuk analisis data interaktif dan untuk mempersiapkan data untuk model building

**Data Cleaning:**
- Data dengan missing atau anomalous values mungkin perlu difilter atau diperbaiki
- PII data harus di-mask atau dihapus

#### Pembagian Dataset (Dataset Splitting)

**Setelah pre-processing data Anda, Anda hampir siap untuk mulai training. Tetapi pertama, Anda perlu memutuskan cara terbaik untuk membagi data Anda.**

**Rekomendasi Umum dari Material Transcript:**
- Biasanya, Anda perlu membuat tiga dataset dari data yang tersedia
- **Rekomendasi umum adalah sekitar 80% dari data harus digunakan untuk training model**
- **10% harus disisihkan untuk evaluasi model**
- **10% untuk melakukan final test sebelum deploy model ke production**

#### Feature Engineering

**Tujuan Utama:**
- **Akhirnya, Anda perlu menentukan karakteristik dataset mana yang harus digunakan sebagai features untuk melatih model**
- Ini adalah subset yang relevan dan berkontribusi untuk meminimalkan error rate dari trained model
- **Anda harus mengurangi features dalam training data Anda hanya pada yang dibutuhkan untuk inference**

**Manfaat Optimasi Features:**
- Features dapat dikombinasikan untuk lebih mengurangi jumlah features
- **Mengurangi jumlah features mengurangi jumlah memory dan computing power yang dibutuhkan untuk training**

### AWS Services untuk Data Ingestion dan Preparation

#### AWS Glue

**Fitur Utama:**
- Fully managed ETL service
- Buat dan jalankan ETL job dengan beberapa klik di AWS Management Console
- AWS Glue discovers data dan menyimpan metadata (table definition dan schema) di AWS Glue Data Catalog

**Kemampuan:**
- Generate code untuk execute data transformations dan data loading processes
- Built-in transformations: dropping duplicate records, filling missing values, splitting dataset
- Extract, transform, dan load data dari berbagai data stores

**Data Sources yang Didukung:**
- Relational databases
- Data warehouses
- Cloud services
- Streaming services: Amazon MSK (Managed Streaming for Apache Kafka), Amazon Kinesis

**AWS Glue Data Catalog:**
- Berisi references ke data yang digunakan sebagai sources dan targets ETL jobs
- Tables include index ke location, schema, dan runtime metrics
- Informasi digunakan untuk create dan monitor ETL jobs
- Jalankan crawler untuk inventory data di data stores
- **Penting**: Source data tidak ditulis ke Data Catalog, hanya metadata (location dan schema)

**AWS Glue ETL Jobs:**
- Menggunakan informasi dari Data Catalog
- Collect, transform, dan store data di target data store (biasanya S3 bucket)

#### AWS Glue DataBrew

**Karakteristik:**
- Visual data preparation tool
- Clean dan normalize data tanpa menulis code
- Interactively discover, visualize, clean, dan transform raw data

**Fitur:**
- Smart suggestions untuk identify data quality issues
- Save transformation steps dalam recipe yang dapat diupdate atau digunakan kembali
- Deploy recipe secara berkelanjutan

**Built-in Transformations (250+):**
- Removing nulls
- Replacing missing values
- Fixing schema inconsistencies
- Creating column-based functions
- Dan lainnya

**Data Quality:**
- Define rule sets
- Run profiling jobs untuk evaluate data quality

#### Amazon SageMaker Ground Truth

**Tujuan:**
- Membantu build high-quality training datasets untuk ML models
- Supervised ML memerlukan large, high-quality labeled dataset

**Active Learning:**
- Menggunakan ML model untuk label training data
- Automatically label data yang bisa dilabel
- Sisanya diberikan ke human workforce

**Workforce Options:**
1. **Amazon Mechanical Turk**: 500,000+ independent contractors
2. **Private Workforce**: Karyawan atau kontraktor internal sendiri

#### Amazon SageMaker Canvas

**Kemampuan:**
- Prepare, featurize, dan analyze data
- Simplify feature engineering process dengan single visual interface

**SageMaker Data Wrangler:**
- Data selection tool untuk pilih raw data dari berbagai data sources
- Import dengan single click
- 300+ built-in transformations
- Normalize, transform, dan combine features tanpa menulis code

#### Amazon SageMaker Feature Store

**Fungsi:**
- Centralized store untuk features dan associated metadata
- Features dapat easily discovered dan reused
- Mudah create, share, dan manage features untuk ML development

**Manfaat:**
- Accelerate proses dengan mengurangi repetitive data processing
- Mengurangi curation work untuk convert raw data menjadi features
- Create workflow pipelines yang convert raw data ke features
- Add features ke feature groups

## 3. Training, Tuning, dan Evaluasi Model

### Proses Training Model (Dari Material Transcript)

#### Konsep Dasar Training

**Fase Training, Tuning, dan Evaluating:**
Dalam fase ini, kita mengajarkan model melalui proses iteratif training, tuning, dan evaluating. Selama training, machine learning algorithm meng-update set angka yang dikenal sebagai parameters atau weights.

**Tujuan Training:**
Tujuannya adalah meng-update parameters dalam model sedemikian rupa sehingga inference cocok dengan expected output.

**Mengapa Proses Iteratif?**
- **Ini tidak bisa dilakukan dalam satu iterasi, karena algorithm belum belajar**
- Algorithm tidak memiliki pengetahuan tentang bagaimana changing weights akan menggeser output lebih dekat ke expected value
- Oleh karena itu, algorithm mengamati weights dan outputs dari iterasi sebelumnya
- Menggeser weights ke arah yang menurunkan error dalam generated output

**Stopping Criteria:**
Proses iteratif ini berhenti ketika:
- Defined number of iterations telah dijalankan, atau
- Change in error berada di bawah target value

#### Running Experiments dan Hyperparameters

**Best Practice untuk Multiple Algorithms:**
- Biasanya ada multiple algorithms untuk dipertimbangkan untuk model
- **Best practice adalah menjalankan banyak training jobs secara parallel, dengan menggunakan different algorithms dan settings**
- Ini dikenal sebagai running experiments, yang membantu Anda mendarat pada best-performing solution

**Hyperparameters:**
- Setiap algorithm memiliki set external parameters yang mempengaruhi performanya, yang dikenal sebagai hyperparameters
- Ini diset oleh data scientists sebelum training model
- Termasuk menyesuaikan hal-hal seperti berapa banyak neural layers dan nodes yang akan ada dalam deep learning model
- **Optimal values untuk hyperparameters hanya bisa ditentukan dengan menjalankan multiple experiments dengan different settings**

### Training dengan Amazon SageMaker (Dari Material Transcript)

#### Membuat Training Job

**Untuk melatih model Anda menggunakan SageMaker, Anda membuat training job yang menjalankan training code Anda pada fleet ML compute instances yang dikelola oleh SageMaker.**

**Spesifikasi yang Dibutuhkan untuk Training Job:**
1. **URL S3 bucket** yang berisi training data Anda
2. **Compute resources** yang ingin Anda gunakan untuk training
3. **Output bucket** untuk model artifacts
4. **Algorithm** dengan memberikan SageMaker path ke Docker container image yang berisi training algorithm:
   - Di Amazon Elastic Container Registry (Amazon ECR), Anda dapat menentukan lokasi SageMaker provided algorithms dan deep learning containers
   - Atau lokasi custom container Anda yang berisi custom algorithm
5. **Hyperparameters** yang dibutuhkan oleh algorithm

**Proses Training:**
- Setelah Anda membuat training job, SageMaker meluncurkan ML compute instances
- Menggunakan training code dan training dataset untuk melatih model
- Menyimpan resulting model artifacts dan outputs lainnya di S3 bucket yang Anda tentukan untuk tujuan tersebut

#### Amazon SageMaker Experiments

**Konteks dari Material Transcript:**
**Kita telah melihat bahwa machine learning adalah proses iteratif. Anda perlu bereksperimen dengan multiple combinations data, algorithms, dan parameters, sambil mengamati impact dari incremental changes pada model accuracy. Eksperimentasi iteratif ini dapat menghasilkan thousands of model training runs dan model versions.**

**Fitur SageMaker Experiments:**
- Amazon SageMaker Experiments adalah capability dari Amazon SageMaker yang memungkinkan Anda create, manage, analyze, dan compare ML experiments Anda
- **Experiment adalah group of training runs, masing-masing dengan different inputs, parameters, dan configurations**
- Fitur visual interface untuk browse active dan past experiments Anda
- Compare runs pada key performance metrics
- Identify best-performing models

#### Amazon SageMaker Automatic Model Tuning (AMT)

**Definisi dan Tujuan:**
- Amazon SageMaker automatic model tuning (AMT), juga dikenal sebagai hyperparameter tuning
- **Menemukan best version dari model dengan menjalankan banyak training jobs pada dataset Anda**

**Cara Kerja AMT:**
- Untuk melakukan ini, AMT menggunakan algorithm dan ranges of hyperparameters yang Anda spesifikasi
- Kemudian memilih hyperparameter values yang membuat model yang perform terbaik, **as measured by metric yang Anda pilih**

**Contoh Implementasi:**
- Misalkan Anda melakukan tuning binary classification model
- Anda dapat memiliki automatic model tuning menemukan kombinasi hyperparameters yang memaksimalkan metric yang dikenal sebagai area under the curve

**Konfigurasi Tuning Job:**
- Untuk menggunakan automatic model tuning, Anda mengkonfigurasi tuning job yang menjalankan several training jobs inside loop
- Anda menentukan completion criteria sebagai number of jobs yang no longer improving metric
- Job akan berjalan sampai completion criteria terpenuhi

## 4. Deployment Model untuk Inference (Dari Material Transcript)

### Pilihan Deployment

**Sekarang kita memiliki fully trained, tuned, dan evaluated model, kita perlu membuatnya tersedia untuk digunakan.**

#### Batch vs Real-time Inference

**Keputusan Pertama: Batch atau Real-time Inferencing**

**Batch Inference:**
- Untuk ketika Anda membutuhkan large number of inferences dan okay untuk menunggu hasil
- **Contoh: batch process berjalan overnight pada data yang dikumpulkan dari previous day sales**
- **Ini adalah pendekatan paling cost-effective karena cloud computing resources hanya berjalan sekali per hari**

**Real-time Inference:**
- Dengan real-time inference, Anda deploy model sehingga dapat merespons requests segera
- **Contoh: ketika menggunakan generative AI**
- **Clients berinteraksi dengan model Anda dengan menggunakan REST application programming interface (API)**

#### API Interaction dan Arsitektur

**Konsep API:**
- **API adalah set actions yang tersedia melalui HTTP connection**

**Contoh Workflow:**
- Web application dapat mengirim POST request yang berisi input data
- Endpoint Anda akan meneruskan request ke compute resource yang menjalankan model
- Resulting model output dikirim kembali ke client dalam response ke request

**Contoh Arsitektur dari Material Transcript:**
- **Amazon API Gateway dapat berfungsi sebagai interface dengan clients dan meneruskan requests ke AWS Lambda function yang menjalankan model**
- **Dalam kedua kasus, inference code dan model artifacts biasanya di-deploy sebagai Docker container**

### Compute Options untuk Inference (Dari Material Transcript)

#### Docker Container Deployment

**Versatility Docker Containers:**
- **Docker containers sangat versatile dan dapat dijalankan pada any compute resource dengan container runtime installed**

**AWS Options untuk Container Deployment:**
- Di AWS, ini bisa termasuk:
  - AWS Batch
  - Amazon Elastic Container Service (Amazon ECS)
  - Amazon Elastic Kubernetes Service (Amazon EKS)
  - AWS Lambda
  - Amazon Elastic Compute Cloud (Amazon EC2)
  - Dan lainnya

**Considerations untuk Self-Managed:**
- **Tergantung pada service, opsi ini akan mengharuskan Anda untuk configure dan manage inference endpoint**
- Yang mungkin juga termasuk managing updates, patches, scalability, network routing, dan security

#### Amazon SageMaker Hosting - Reduced Operational Overhead

**Keuntungan SageMaker Hosting:**
- **Untuk reduced operational overhead, Anda dapat memilih untuk host model Anda dengan Amazon SageMaker**
- **Amazon SageMaker dapat secara otomatis deploy model Anda pada hosted endpoints yang dikelola sepenuhnya atas nama Anda**

**Setup Process:**
- Untuk menggunakan SageMaker inferencing, Anda hanya perlu mengarahkan SageMaker ke model artifacts Anda di S3 bucket
- Dan Docker container image di Amazon ECR
- Anda memilih inference option mana seperti batch, asynchronous, serverless, atau real time
- **SageMaker membuat endpoint dan menginstall model code Anda**

**Infrastructure Management:**
- Untuk real-time, asynchronous, dan batch inference, SageMaker menjalankan model pada EC2 ML instances, yang dapat berada di dalam auto scaling group
- Anda memilih number dan instance type dari ML instances yang ingin Anda gunakan
- **Ada juga inference recommender tool dalam SageMaker yang dapat menguji different configuration options dengan model Anda, sehingga Anda dapat memilih yang terbaik**
- Untuk serverless inference option, SageMaker menjalankan code Anda pada Lambda functions

### SageMaker Inference Options (Dari Material Transcript)

**Ketika Anda membuat endpoint atau endpoint configuration, Anda harus memilih inference option. Amazon SageMaker mendukung empat option types. Pilihan terbaik tergantung pada business requirements dari ML inference workload Anda. Endpoints ini fully managed dan mendukung auto scaling.**

#### 1. Batch Transform
**Karakteristik:**
- **Batch transform menyediakan offline inference untuk large datasets**
- **Berguna ketika menjalankan inference jika persistent endpoint tidak diperlukan dan Anda dapat menunggu hasil**
- **Dapat mendukung large datasets yang berukuran gigabytes**

#### 2. Asynchronous Inference
**Ideal Untuk:**
- **Asynchronous inference ideal ketika Anda ingin queue request dan memiliki large payloads dengan processing times**
- **SageMaker akan scale endpoint Anda down ke zero sehingga Anda tidak dikenakan biaya untuk periods tanpa requests**

#### 3. Serverless Inference
**Karakteristik:**
- **Serverless inference dapat digunakan untuk serve model inference requests in real time tanpa directly provisioning compute instances atau configuring scaling policies untuk handle traffic variations**
- **Karena menggunakan Lambda, Anda hanya membayar ketika functions berjalan atau pre-provisioned**
- **Jadi ini adalah pilihan yang baik jika model Anda memiliki periods tanpa requests**

#### 4. Real-time Inference
**Ideal Untuk:**
- **Real-time inference ideal untuk inference workloads dimana Anda membutuhkan real-time interactive responses dari model Anda**
- **Gunakan real-time inference untuk persistent dan fully managed endpoint REST API yang dapat handle sustained traffic**
- **Backed by instance type pilihan Anda**
- **ML instances tetap tersedia untuk menerima requests dan mengembalikan response in real time**

**Considerations untuk Real-time:**
- Pilih number dan instance type dari ML instances
- Inference recommender tool dapat test different configuration options
- Auto scaling support tersedia

## 5. Monitoring Model di Production (Dari Material Transcript)

### Pentingnya Monitoring

**Realitas Model Performance:**
**Tidak peduli seberapa bagus model Anda perform awalnya, model performance bisa menurun seiring waktu karena alasan seperti data quality, model quality, dan model bias.**

**Tahap Final ML Pipeline:**
**Tahap final dari ML pipeline adalah monitoring model Anda.**

### Komponen Monitoring System

**Sistem monitoring model harus:**
1. **Capture data**
2. **Compare data dengan training set**
3. **Define rules untuk detect issues**
4. **Send alerts**

**Monitoring Schedule:**
**Proses ini berulang pada:**
- **Defined schedule** ketika initiated by event
- **Atau ketika initiated by human intervention**

**Pendekatan Praktis:**
**Untuk sebagian besar ML models, pendekatan scheduled sederhana untuk re-training daily, weekly, atau monthly biasanya cukup.**

### Types of Drift

**Sistem monitoring harus mendetect data dan concept drifts, initiate alert, dan mengirimkannya ke alarm manager system, yang bisa secara otomatis memulai re-training cycle.**

#### Data Drift
- **Data drift adalah ketika ada significant changes pada data distribution dibandingkan dengan data yang digunakan untuk training**

#### Concept Drift
- **Concept drift adalah ketika properties dari target variables berubah**
- **Any kind of drift menghasilkan model performance degradation**

### Amazon SageMaker Model Monitor

**Fungsi Utama:**
- **Amazon SageMaker Model Monitor, yang merupakan capability dari Amazon SageMaker, monitors models in production dan detects errors sehingga Anda dapat mengambil remedial actions**

**Cara Kerja SageMaker Model Monitor:**
1. **Anda define monitoring schedule yang collects data dari endpoints Anda**
2. **Detects changes against baseline**
3. **Analyzes data berdasarkan built-in rules atau rules yang Anda define**

**Output dan Integration:**
- **Anda dapat melihat results di Amazon SageMaker Studio dan melihat rules mana yang violated**
- **Results juga dikirim ke Amazon CloudWatch, dimana Anda dapat configure alarms untuk mengambil remedial actions, seperti memulai re-training process**

## 6. MLOps (Machine Learning Operations) - Dari Material Transcript

### Konsep MLOps

**Pentingnya Automation:**
**Automation adalah bagian penting dari implementing dan operating repeatable dan reliable business processes. Jadi mari kita lihat bagaimana kita dapat menggunakan automation dalam ML pipelines kita.**

**Definisi MLOps:**
**MLOps adalah tentang menggunakan established best practices dari software engineering dan menerapkannya pada machine learning model development. Ini tentang:**
- **Automating manual tasks**
- **Testing dan evaluating code sebelum release**
- **Responding automatically ke incidents**

**Tujuan Utama:**
- **MLOps dapat streamline model delivery across machine learning development lifecycle**
- **Karena cloud menggunakan API based services, everything is treated as software**
- **Ini termasuk infrastructure yang digunakan dalam ML pipelines**
- **Entire infrastructure dapat described dalam software dan deployed dan redeployed dalam repeatable fashion**
- **Ini memungkinkan data scientists dengan cepat spin up infrastructure yang dibutuhkan untuk build dan test model sehingga mereka dapat run experiments dan make continual improvements**

### Key MLOps Principles

#### 1. Version Control
- **Seperti DevOps, version control critical untuk tracking lineage dan being able to inspect past configuration**
- **Dengan MLOps, everything gets versioned, termasuk training data**

#### 2. Monitoring Deployments
- **Key MLOps principles lainnya adalah monitoring deployments untuk detect potential issues**

#### 3. Automation
- **Automating re-training karena issues atau data dan code changes**

### Benefits of MLOps (Dari Material Transcript)

#### 1. Productivity
- **Salah satu benefits dari MLOps adalah productivity**
- **Automation dan providing self-service environments dan infrastructure memungkinkan data engineers dan data scientists move forward**

#### 2. Repeatability
- **Benefit lainnya adalah repeatability**
- **Automating all steps dalam ML lifecycle membantu ensure repeatable process, termasuk bagaimana model trained, evaluated, versioned, dan deployed**

#### 3. Reliability
- **Ini juga meningkatkan reliability karena menyediakan kemampuan untuk deploy tidak hanya dengan cepat, tetapi dengan increased quality dan consistency**

#### 4. Compliance
- **Untuk compliance, MLOps dapat improve auditability dengan versioning all inputs dan outputs**
- **Dari data science experiments ke source data ke trained models**
- **Ini berarti kita dapat demonstrate exactly bagaimana model dibangun dan dimana deployed**

#### 5. Data and Model Quality
- **Final benefit adalah improvements ke data dan model quality**
- **MLOps memungkinkan kita enforce policies yang guard against model bias**
- **Track changes ke data statistical properties, dan model quality over time**

### AWS Services untuk MLOps (Dari Material Transcript)

#### Amazon SageMaker Pipelines

**Kemampuan Utama:**
- **Amazon SageMaker Pipelines menawarkan kemampuan untuk orchestrate SageMaker jobs dan author reproducible ML pipelines**

**Fitur SageMaker Pipelines:**
- **SageMaker Pipelines dapat deploy custom built models untuk inference in real time dengan low latency**
- **Run offline inferences dengan batch transform**
- **Track lineage of artifacts**

**Operational Practices:**
- **Mereka dapat institute sound operational practices dalam deploying dan monitoring production workflows**
- **Deploying model artifacts**
- **Tracking artifact lineage through simple interface**

**Pipeline Creation:**
- **Anda dapat create pipeline menggunakan SageMaker SDK for Python atau define pipeline menggunakan JSON**
- **Pipeline dapat berisi all steps untuk build dan deploy model**
- **Dapat juga include conditional branches berdasarkan output dari previous step**
- **Pipelines dapat dilihat di SageMaker Studio**
- **Contoh pipeline ini untuk model yang infers age dari abalone berdasarkan size-nya**

#### Repositories untuk MLOps

**Penting untuk disebutkan beberapa services lain untuk MLOps. Repositories adalah tempat Anda menyimpan versions dari code dan models Anda.**

- **SageMaker Feature Store adalah repository untuk feature definitions dari training data Anda**
- **SageMaker Model Registry adalah centralized repository untuk trained models dan history Anda**

#### AWS Step Functions

**Alternative untuk Pipeline Orchestration:**
- **Kita telah melihat bagaimana SageMaker Pipelines dapat orchestrate ML pipeline Anda, tetapi ada beberapa opsi lain**
- **Salah satunya adalah AWS Step Functions, yang memungkinkan Anda define workflow dengan visual drag-and-drop interface**
- **Memberikan kemampuan untuk build serverless workflows yang integrate various AWS services dan custom application logic**

#### Amazon Managed Workflows for Apache Airflow

**Apache Airflow:**
- **Apache Airflow adalah open source tool yang digunakan untuk programmatically author, schedule, dan monitor sequences of processes dan tasks yang disebut sebagai workflows**

**Managed Service:**
- **Dengan Amazon Managed Workflows for Apache Airflow, Anda dapat menggunakan Apache Airflow dan Python untuk create workflows tanpa harus manage underlying infrastructure untuk scalability, availability, dan security**

## 7. Metrik Evaluasi Model (Dari Material Transcript)

### Confusion Matrix

#### Konsep Dasar

**Definisi dari Material Transcript:**
- **Kita telah menyebutkan bagaimana models perlu dievaluasi terhadap target metrics. Mari describe beberapa dari ini lebih detail**
- **Confusion matrix digunakan untuk summarize performance dari classification model ketika dievaluasi terhadap test data**
- **Cara paling sederhana adalah binary classification model dimana output adalah simple binary result, yes atau no, positive atau negative**

**Struktur:**
- **Confusion matrix adalah table dengan actual data biasanya across the top dan predicted values on the left**

#### Komponen Confusion Matrix

**Mari kita lanjutkan menggunakan fish classification model kita untuk illustrate:**

**1. True Positive (TP)**
- **Jika model melihat picture dari fish dan accurately predicts bahwa itu fish, itu disebut true positive**

**2. True Negative (TN)**
- **Jika model melihat picture dari something yang bukan fish dan accurately predicts bahwa itu bukan fish, itu disebut true negative**

**3. False Negative (FN)**
- **Jika model melihat picture dari something yang fish dan incorrectly predicts bahwa itu bukan fish, itu disebut false negative**

**4. False Positive (FP)**
- **Jika model melihat picture dari something yang bukan fish dan incorrectly predicts bahwa itu fish, itu disebut false positive**

**Contoh dari Material Transcript:**
**Mari kita buat contoh dimana kita menjalankan 100 labeled test images melalui model. Confusion matrix menunjukkan number dari true dan false positives dan negatives.**

### Metrik Klasifikasi (Dari Material Transcript)

#### 1. Accuracy

**Definisi dan Formula:**
- **Satu metric yang kadang digunakan untuk judge model performance adalah accuracy, yang simply percentage dari correct predictions**
- **Accuracy measures seberapa dekat predicted class values dengan actual values**
- **Values untuk accuracy metrics vary antara zero dan one. Value satu indicates perfect accuracy dan zero indicates complete inaccuracy**

**Formula:**
```
Accuracy = (TP + TN) / Total Predictions
```

**Contoh dari Material Transcript:**
- **Formula untuk accuracy adalah number dari true positives plus true negatives dibagi dengan total number dari predictions**
- **Menggunakan confusion matrix kita, itu works out ke 25 plus 40, yang adalah 65, dibagi dengan 100, yang memberikan accuracy 0.65 atau 65%**

**Keterbatasan Penting:**
- **Meskipun accuracy understandable, itu bukan good metric ketika dataset imbalanced**
- **Contoh: misalkan 90 dari 100 test images kita adalah fish, maka model hanya perlu predict bahwa semua images kita adalah fish dan akan mendapat accuracy 0.9 atau 90%**

#### 2. Precision

**Definisi dan Formula:**
- **Precision measures seberapa baik algorithm predicts true positives out of all positives yang diidentifikasi**
- **Formula adalah number dari true positives dibagi dengan number dari true positives, plus number dari false positives**

**Use Case:**
- **Ini good quality metric untuk digunakan ketika goal Anda adalah minimize number dari false positives**
- **Contoh: kita tidak ingin label legitimate email sebagai spam**

**Contoh:**
- **Menggunakan confusion matrix kita, kita mendapat precision 0.55 atau 55% untuk fish model kita**

#### 3. Recall (Sensitivity / True Positive Rate)

**Definisi dan Formula:**
- **Jika kita ingin minimize false negatives, maka kita dapat menggunakan metric yang dikenal sebagai recall**
- **Contoh: kita ingin make sure bahwa kita tidak miss jika seseorang memiliki disease dan kita bilang mereka tidak**
- **Formula adalah number dari true positives dibagi dengan number dari true positives, plus number dari false negatives**

**Contoh:**
- **Menggunakan confusion matrix kita, kita arrive pada recall 0.625 untuk model**

**Trade-off Penting:**
- **Ada tradeoff antara precision dan recall karena Anda tidak bisa optimize model untuk keduanya**
- **Contoh: misalkan kita ingin make sure kita diagnose everyone yang memiliki disease dan tidak miss anyone. Maka kita akan increase likelihood dari diagnosing people yang tidak memiliki disease sebagai having it**

#### 4. F1 Score

**Definisi dan Tujuan:**
- **Recall juga dikenal sebagai sensitivity atau true positive rate**
- **Namun, jika recall dan precision keduanya penting bagi kita, F1 score balances precision dan recall dengan combining mereka dalam single metric**

**Interpretasi:**
- **Fish model kita memiliki better recall daripada precision, yang berarti akan better dalam detecting true positives, tetapi juga akan memiliki some false negatives**
- **Dalam scenario ini, optimizing F1 score adalah best compromise**

#### 5. False Positive Rate (FPR)

**Definisi dari Material Transcript:**
- **Metric lain yang dapat kita calculate dari confusion matrix kita adalah false positive rate, yang adalah false positives dibagi dengan sum dari false positives dan true negatives**

**Interpretasi:**
- **Dalam contoh kita, metric ini menunjukkan bagaimana model handling images yang bukan fish**
- **Ini measure dari berapa banyak predictions yang fish out of images yang bukan fish**

#### 6. True Negative Rate (TNR)

**Definisi:**
- **Closely related dengan false positive rate adalah true negative rate, yang adalah ratio dari true negatives ke sum dari false positives dan true negatives**

**Interpretasi:**
- **Ini measure dari berapa banyak predictions yang bukan fish out of images yang bukan fish**

### Area Under the Curve (AUC) - Dari Material Transcript

#### Konsep

**Tujuan dan Aplikasi:**
- **Area under the curve, juga dikenal sebagai AUC metric, digunakan untuk compare dan evaluate binary classification oleh algorithms yang return probabilities, seperti logistic regression**

**Threshold Concept:**
- **Untuk map probabilities ke discrete predictions seperti true atau false, ini dibandingkan dengan threshold value**
- **Threshold adalah value yang model gunakan untuk make decision antara two possible classes**
- **Dapat converts probability dari sample being part of class ke binary decision**
- **Contoh: ketika threshold diset ke 0.6, anytime model 60% confident bahwa image adalah fish, akan classify sebagai fish**

#### Receiver Operating Characteristic (ROC) Curve

**Karakteristik:**
- **True positive rate di-plot against false positive rate untuk increasing threshold values**
- **Threshold values direpresentasikan oleh red dashed line dalam graph**
- **Relevant curve disebut receiver operating characteristic curve**
- **Anda dapat melihat bahwa increasing threshold menghasilkan fewer false positives, tetapi more false negatives**

**AUC Metric:**
- **AUC adalah area under receiver operating characteristic curve ini**
- **AUC menyediakan aggregated measure dari model performance across full range dari thresholds**

**Score Range:**
- **AUC scores vary antara zero dan one**
- **Score satu indicates perfect accuracy**
- **Score setengah, atau 0.5, indicates bahwa prediction no better daripada random classifier**

### Metrik Regresi (Dari Material Transcript)

#### 1. Mean Squared Error (MSE)

**Konsep dari Material Transcript:**
- **Recall bahwa dalam linear regression, kita fitting line ke points dalam dataset**
- **Distance antara line dan actual values adalah error**
- **Metric yang dapat kita gunakan untuk evaluate linear regression model disebut mean squared error (MSE)**

**Formula dan Perhitungan:**
- **Untuk compute, kita take difference antara prediction dan actual value, square the difference, dan kemudian compute average dari all square differences**

**Karakteristik:**
- **MSE values selalu positive**
- **Better model dalam predicting actual values, smaller MSE value**

#### 2. Root Mean Squared Error (RMSE)

**Definisi:**
- **Metric lain yang commonly used adalah root mean squared error, yang adalah square root dari mean squared error**

**Keuntungan:**
- **Advantage dari menggunakan square root dari MSE adalah bahwa units match dependent variable**
- **Dalam contoh kita, jika height diukur dalam inches, maka MSE akan dalam square inches, tetapi RMSE dalam inches, jadi RMSE lebih mudah untuk kita interpret**

**Karakteristik:**
- **Karena errors di-squared, mean squared error dan root mean squared error metrics emphasize impact dari outliers**
- **Ini good metrics, tetapi incorrect predictions dapat very costly**

#### 3. Mean Absolute Error (MAE)

**Definisi dan Keuntungan:**
- **Jika itu tidak diinginkan, different metric yang disebut mean absolute error averages absolute values dari errors, jadi tidak emphasize large errors**

**Kapan Menggunakan:**
- **Good ketika Anda tidak ingin emphasize outliers**

## 8. Business Metrics (Dari Material Transcript)

### Pentingnya Business Metrics

**Rooted in Business Problems:**
- **Kita telah melihat bahwa ML solutions perlu rooted dalam solving business problems, jadi mari kita akhiri domain ini dengan discussing business metrics**
- **Recall bahwa first step dalam ML pipeline adalah define business goal**
- **Dari sana, kita determine bagaimana measure successful achievement dari goal**

**Fungsi:**
- **Business metrics membantu kita quantify value dari machine learning model ke business**

### Jenis Business Metrics

#### Good Metrics Examples dari Material Transcript:
1. **Cost reduction**
2. **Percentage increase in users atau sales**
3. **Measurable improvement in customer feedback**
4. **Any measurable metric yang important ke business**

### Risk Assessment

**Pertimbangan Penting:**
- **Penting juga untuk estimate risks dari using AI dan ML dan potential costs incurred dari errors**
- **Contoh: satu potential cost bisa loss of sales atau customers**

### Post-Production Evaluation

**Data Collection dan Comparison:**
- **Setelah model dalam production, Anda perlu bisa collect data untuk support metrics dan compare actual results dengan original business goals**

**Cost Analysis:**
- **Juga, consider actual cost dari building dan operating model dan compare cost ini dengan initial cost benefit model**
- **Dengan cara ini Anda akan bisa calculate return on investment**

### AWS Cost Tracking

#### Cost Allocation Tags

**Implementasi dari Material Transcript:**
- **AWS memungkinkan Anda define cost allocation tags yang assigned ke resources yang Anda create**
- **Contoh: Anda dapat define tag dengan name dari ML project dan name dari project Anda sebagai value**
- **Anda add tag tersebut ke all resources yang digunakan dalam pipeline Anda**

**AWS Cost Explorer:**
- **Kemudian Anda dapat filter cost reports dalam AWS Cost Explorer untuk determine actual AWS charges incurred untuk project**
- **Ini memungkinkan tracking spending per ML project dengan akurat**

---

## Kesimpulan

**ML Development Lifecycle** adalah proses komprehensif yang memerlukan perencanaan matang, eksekusi yang teliti, dan monitoring berkelanjutan. Berdasarkan material transcript dari AWS Skill Builder course, setiap tahap dalam lifecycle memiliki tools dan services AWS yang dapat membantu mempercepat dan mempermudah proses pengembangan model ML.

### Kunci Sukses dalam ML Development (Dari Material Transcript):

1. **Clear Business Objectives** - Selalu mulai dengan mengidentifikasi business goal dan success criteria yang spesifik
2. **Appropriate Solution Selection** - Mulai dengan solusi paling sederhana (AI Services) sebelum kompleksitas lebih tinggi
3. **High-Quality Data** - Pastikan data training yang relevan dan berkualitas tinggi tersedia
4. **Iterative Experimentation** - Jalankan multiple training jobs secara parallel dengan different algorithms dan settings
5. **Proper Deployment Strategy** - Pilih antara batch atau real-time inference sesuai business requirements
6. **Continuous Monitoring** - Detect data drift dan concept drift untuk maintain model performance
7. **MLOps Implementation** - Gunakan automation, version control, dan repeatability untuk reliability
8. **Appropriate Metrics** - Gunakan classification metrics (accuracy, precision, recall, F1) atau regression metrics (MSE, RMSE, MAE) sesuai problem type
9. **Business Value Measurement** - Track business metrics dan calculate ROI dengan AWS cost allocation tags

### Tahapan Utama ML Pipeline:
1. **Define Business Goal** → 2. **Collect & Prepare Data** → 3. **Train & Tune Model** → 4. **Deploy Model** → 5. **Monitor Performance**

**Ingat:** ML models bersifat dinamis dan perlu di-retrain secara berkala, dievaluasi terus-menerus, dan disesuaikan sesuai kebutuhan bisnis yang berkembang.

---

## 9. AWS Services Mapping dan Exam Cues

### AWS Services untuk ML Pipeline dari Material Transcript

| Stage | AWS Service | Exam Cue | Key Capabilities |
|-------|-------------|-----------|------------------|
| **Data Ingestion** | AWS Glue | "fully managed ETL", "data catalog" | ETL jobs, data discovery, metadata management |
| | AWS Glue DataBrew | "visual data preparation", "250+ transformations" | No-code data cleaning, smart suggestions |
| | Amazon MSK | "managed Kafka", "streaming data" | Real-time data streaming |
| | Amazon Kinesis | "streaming services" | Real-time data processing |
| **Data Labeling** | SageMaker Ground Truth | "high-quality labeled dataset", "active learning" | Human + ML labeling, quality control |
| | Amazon Mechanical Turk | "500,000+ contractors" | Crowdsourced labeling workforce |
| **Data Preparation** | SageMaker Canvas | "visual interface", "feature engineering" | No-code data preparation |
| | SageMaker Data Wrangler | "300+ transformations", "single click import" | Data selection and transformation |
| | SageMaker Feature Store | "centralized store", "feature reuse" | Feature management and sharing |
| **Training** | Amazon SageMaker | "training jobs", "ML compute instances" | Model training and experimentation |
| | SageMaker Experiments | "manage experiments", "compare runs" | Experiment tracking and comparison |
| | SageMaker Automatic Model Tuning | "hyperparameter tuning", "best version" | Automated hyperparameter optimization |
| **Deployment** | SageMaker Hosting | "fully managed endpoints" | Model deployment and serving |
| | Amazon API Gateway | "REST API interface" | API management for model endpoints |
| | AWS Lambda | "serverless inference" | Serverless model hosting |
| | Amazon ECS/EKS | "container orchestration" | Container-based deployment |
| **Monitoring** | SageMaker Model Monitor | "detect drift", "baseline comparison" | Model performance monitoring |
| | Amazon CloudWatch | "metrics and alarms" | Infrastructure and application monitoring |
| **MLOps** | SageMaker Pipelines | "orchestrate jobs", "reproducible pipelines" | ML workflow automation |
| | SageMaker Model Registry | "centralized repository", "model history" | Model versioning and management |
| | AWS Step Functions | "visual workflow", "serverless orchestration" | Workflow orchestration |

### ML Lifecycle Phases dari Material Transcript

**1. Define Business Goal:**
- Identify problem and business value
- Align stakeholders on objectives
- Evaluate ML feasibility
- Assess data availability
- Perform cost-benefit analysis

**2. Data Collection & Preparation:**
- Configure ETL processes
- Label data (supervised learning)
- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Feature engineering
- Dataset splitting (80% train, 10% validation, 10% test)

**3. Training, Tuning & Evaluation:**
- Iterative training process
- Hyperparameter tuning
- Run experiments in parallel
- Model evaluation with metrics

**4. Model Deployment:**
- Choose inference type (batch vs real-time)
- Deploy to endpoints
- Configure scaling and monitoring

**5. Model Monitoring:**
- Detect data drift and concept drift
- Monitor model performance
- Automated retraining triggers

### Key Metrics dari Material Transcript

**Classification Metrics:**
- **Accuracy**: (TP + TN) / Total Predictions - percentage correct predictions
- **Precision**: TP / (TP + FP) - minimize false positives (e.g., spam detection)
- **Recall**: TP / (TP + FN) - minimize false negatives (e.g., disease detection)
- **F1 Score**: Balance precision and recall dalam single metric
- **False Positive Rate**: FP / (FP + TN) - measure false alarms
- **True Negative Rate**: TN / (FP + TN) - measure correct rejections
- **AUC**: Area under ROC curve untuk binary classification dengan probability thresholds

**Regression Metrics:**
- **MSE**: Mean Squared Error - emphasizes outliers, always positive
- **RMSE**: Root Mean Squared Error - same units sebagai dependent variable
- **MAE**: Mean Absolute Error - doesn't emphasize outliers

**Business Metrics:**
- Cost reduction yang measurable
- Percentage increase in users atau sales
- Measurable improvement dalam customer feedback
- ROI calculation dengan AWS Cost Explorer dan cost allocation tags

### MLOps Benefits dari Material Transcript

1. **Productivity**: Automation dan self-service environments memungkinkan data engineers dan scientists move forward
2. **Repeatability**: Automating all steps dalam ML lifecycle untuk ensure repeatable process
3. **Reliability**: Deploy dengan cepat dengan increased quality dan consistency
4. **Compliance**: Improved auditability dengan versioning all inputs dan outputs
5. **Quality**: Enforce policies against model bias, track data statistical properties changes

### Exam Tips dari Material Transcript

1. **ML Pipeline Understanding**: Know 5 tahapan utama - business goal → data collection → training → deployment → monitoring
2. **AWS Service Selection**: 
   - Start dengan AI Services (simplest)
   - Then Foundation Models (Bedrock)
   - Then Pre-trained Models (SageMaker JumpStart)
   - Finally custom training (most complex)
3. **Inference Types**: Understand batch vs real-time inference trade-offs
4. **Monitoring Importance**: Know data drift vs concept drift
5. **Metrics Selection**: Choose appropriate metrics berdasarkan problem type dan business goals
6. **Cost Management**: Understand AWS cost allocation tags untuk track ML project expenses
7. **MLOps Principles**: Version control, automation, monitoring untuk production ML systems

---

**Catatan:** Materi ini disusun berdasarkan material-transcript-1-3.txt dari AWS Skill Builder course untuk AWS Certified AI Practitioner (AIF-C01). Semua konsep dan AWS services mengikuti standar resmi AWS.
