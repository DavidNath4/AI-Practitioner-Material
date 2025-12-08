# Siklus Pengembangan Machine Learning (ML Development Lifecycle)

## Pengantar

Machine Learning Development Lifecycle adalah serangkaian tahapan yang saling terhubung, dimulai dari mendefinisikan tujuan bisnis hingga mengoperasikan model ML yang telah di-deploy. Siklus ini bersifat iteratif dan dinamis, di mana model terus dilatih ulang dengan data baru, dievaluasi terhadap metrik performa dan bisnis, serta dipantau untuk mendeteksi drift dan bias.

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

#### Langkah-langkah Penting:

**a. Identifikasi Masalah dan Nilai Bisnis**
- Organisasi harus memiliki pemahaman yang jelas tentang masalah yang akan diselesaikan
- Tentukan nilai bisnis yang akan diperoleh
- Ukur nilai bisnis terhadap objektif dan kriteria kesuksesan yang spesifik
- Tanpa kriteria kesuksesan yang jelas, Anda tidak akan bisa mengevaluasi model atau menentukan apakah ML adalah solusi terbaik

**b. Alignment dengan Stakeholder**
- Dapatkan konsensus dari stakeholder tentang tujuan proyek
- Pastikan target yang ditetapkan dapat dicapai
- Sediakan jalur yang jelas menuju production

**c. Evaluasi Kelayakan ML**
- Tentukan apakah ML adalah pendekatan yang tepat untuk mencapai tujuan bisnis
- Evaluasi semua opsi yang tersedia untuk mencapai tujuan
- Pertimbangkan akurasi hasil yang diharapkan
- Analisis biaya dan skalabilitas dari setiap pendekatan

**d. Evaluasi Ketersediaan Data**
- Pastikan tersedia data training yang relevan dan berkualitas tinggi dalam jumlah yang cukup
- Evaluasi data dengan cermat untuk memastikan sumber data yang tepat tersedia dan dapat diakses
- Formulasikan pertanyaan ML dalam bentuk: input, output yang diinginkan, dan metrik performa yang akan dioptimalkan

**e. Analisis Cost-Benefit**
- Lakukan analisis cost-benefit untuk menentukan apakah proyek layak dilanjutkan ke fase berikutnya
- Mulai dengan solusi paling sederhana sebelum menentukan bahwa kompleksitas lebih tinggi diperlukan

### Opsi Solusi ML di AWS

#### 1. AI Services (Fully Managed)
AWS menyediakan berbagai AI services yang sudah fully trained dan hosted:
- **Amazon Comprehend**: Untuk analisis teks dan NLP, dapat membuat custom classifier dengan data training sendiri
- Model pay-as-you-go yang mudah dievaluasi
- Banyak services yang memungkinkan customization output

#### 2. Foundation Models dengan Amazon Bedrock
- Untuk use case generative AI
- Mulai dengan foundation model yang sudah fully trained
- Dapat di-fine-tune dengan data sendiri menggunakan transfer learning

#### 3. Pre-trained Models dengan SageMaker JumpStart
- Menyediakan pre-trained AI foundation models
- Task-specific models untuk computer vision dan natural language processing
- Pre-trained pada large public datasets
- Opsi untuk fine-tuning dengan incremental training menggunakan dataset sendiri (transfer learning)
- Menghemat biaya dan waktu pengembangan dibanding membuat custom model dari awal

#### 4. Training dari Awal (Paling Kompleks)
- Pendekatan paling sulit dan mahal
- Paling menantang secara teknis
- Memerlukan tanggung jawab paling besar untuk security dan compliance

## 2. Pengumpulan dan Pemrosesan Data Training

### Tahap Pengumpulan Data

#### Identifikasi dan Pengumpulan Data

**Pertanyaan Kunci:**
- Data training apa yang dibutuhkan untuk mengembangkan model?
- Di mana data dihasilkan dan disimpan?
- Apakah data streaming atau batch process?
- Apakah data sudah dilabeli atau bagaimana cara melabelinya?

**Proses ETL (Extract, Transform, Load):**
- Konfigurasi proses ETL untuk mengumpulkan data dari berbagai sumber
- Simpan data di centralized repository
- Proses harus repeatable karena model perlu di-retrain secara berkala dengan data baru

**Labeling Data:**
- Salah satu bagian terpanjang dalam proses
- Data yang dilabeli dengan akurat kemungkinan belum tersedia
- Memerlukan waktu dan effort yang signifikan

### Tahap Persiapan Data

#### Data Pre-processing

**Exploratory Data Analysis (EDA):**
- Gunakan visualization tools untuk memahami data lebih dalam
- Data wrangling tools untuk analisis data interaktif
- Persiapan data untuk model building

**Data Cleaning:**
- Filter atau perbaiki data dengan missing values atau anomalous values
- Mask atau hapus PII (Personally Identifiable Information) data

#### Pembagian Dataset

Rekomendasi umum untuk split data:
- **80%** untuk training model
- **10%** untuk evaluasi model
- **10%** untuk final test sebelum deploy ke production

#### Feature Engineering

**Tujuan:**
- Tentukan karakteristik dataset mana yang akan digunakan sebagai features untuk training
- Pilih subset yang relevan dan berkontribusi meminimalkan error rate
- Kurangi features hanya pada yang dibutuhkan untuk inference

**Manfaat:**
- Features dapat dikombinasikan untuk mengurangi jumlah features
- Mengurangi memory dan computing power yang dibutuhkan untuk training

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

### Proses Training Model

#### Konsep Dasar Training

**Iterative Process:**
- Mengajarkan model melalui proses iteratif training, tuning, dan evaluating
- Algorithm updates set of numbers (parameters atau weights)
- Tujuan: update parameters agar inference matches expected output

**Mengapa Iteratif?**
- Tidak bisa dilakukan dalam satu iterasi
- Algorithm belum belajar dan tidak tahu bagaimana changing weights akan shift output
- Algorithm watches weights dan outputs dari previous iterations
- Shifts weights ke arah yang menurunkan error

**Stopping Criteria:**
- Defined number of iterations telah dijalankan
- Change in error di bawah target value

#### Running Experiments

**Best Practice:**
- Run many training jobs secara parallel
- Gunakan different algorithms dan settings
- Membantu menemukan best-performing solution

**Hyperparameters:**
- External parameters yang mempengaruhi algorithm performance
- Diset oleh data scientists sebelum training
- Contoh: jumlah neural layers dan nodes dalam deep learning model
- Optimal values hanya bisa ditentukan dengan running multiple experiments

### Training dengan Amazon SageMaker

#### Membuat Training Job

**Spesifikasi yang Dibutuhkan:**
1. **URL S3 bucket** containing training data
2. **Compute resources** untuk training
3. **Output bucket** untuk model artifacts
4. **Algorithm** dengan memberikan path ke Docker container image:
   - SageMaker provided algorithms
   - Deep learning containers
   - Custom container dengan custom algorithm
5. **Hyperparameters** yang dibutuhkan algorithm

**Proses:**
- SageMaker launches ML compute instances
- Menggunakan training code dan training dataset untuk train model
- Menyimpan resulting model artifacts dan outputs di S3 bucket

#### Amazon SageMaker Experiments

**Tujuan:**
- ML adalah iterative process
- Perlu experiment dengan multiple combinations: data, algorithms, parameters
- Observe impact of incremental changes pada model accuracy
- Dapat menghasilkan thousands of model training runs dan versions

**Fitur:**
- Create, manage, analyze, dan compare ML experiments
- Experiment = group of training runs dengan different inputs, parameters, configurations
- Visual interface untuk browse active dan past experiments
- Compare runs pada key performance metrics
- Identify best-performing models

#### Amazon SageMaker Automatic Model Tuning (AMT)

**Juga Dikenal Sebagai:**
- Hyperparameter tuning

**Fungsi:**
- Find best version of model
- Running many training jobs pada dataset
- Menggunakan algorithm dan ranges of hyperparameters yang dispesifikasi
- Choose hyperparameter values yang create model dengan performa terbaik

**Cara Kerja:**
- Measured by metric yang Anda pilih
- Contoh: binary classification model - maximize area under the curve (AUC)

**Konfigurasi Tuning Job:**
- Runs several training jobs inside loop
- Specify completion criteria sebagai number of jobs yang no longer improving metric
- Job runs until completion criteria satisfied

## 4. Deployment Model untuk Inference

### Pilihan Deployment

#### Batch vs Real-time Inference

**Batch Inference:**
- Untuk large number of inferences
- Okay untuk wait for results
- Contoh: batch process runs overnight pada data dari previous day sales
- Most cost-effective approach
- Cloud computing resources hanya running once per day

**Real-time Inference:**
- Deploy model untuk respond to requests immediately
- Contoh: generative AI applications
- Clients interact via REST API (Application Programming Interface)

**API Interaction:**
- Set of actions available over HTTP connection
- Web application sends POST request dengan input data
- Endpoint passes request ke compute resource running model
- Model output sent back dalam response

**Contoh Arsitektur:**
- Amazon API Gateway: interface dengan clients
- Forward requests ke AWS Lambda function running model
- Inference code dan model artifacts deployed sebagai Docker container

### Compute Options untuk Inference

#### Docker Container Deployment

**Versatility:**
- Dapat run pada any compute resource dengan container runtime installed

**AWS Options:**
- AWS Batch
- Amazon ECS (Elastic Container Service)
- Amazon EKS (Elastic Kubernetes Service)
- AWS Lambda
- Amazon EC2 (Elastic Compute Cloud)

**Considerations:**
- Mungkin require configure dan manage inference endpoint
- Termasuk: updates, patches, scalability, network routing, security

#### Amazon SageMaker Hosting

**Keuntungan:**
- Reduced operational overhead
- Automatically deploy model pada hosted endpoints
- Fully managed oleh SageMaker

**Setup:**
- Point SageMaker ke model artifacts di S3 bucket
- Specify Docker container image di Amazon ECR
- Select inference option
- SageMaker creates endpoint dan installs model code

### SageMaker Inference Options

#### 1. Batch Transform
**Karakteristik:**
- Offline inference untuk large datasets
- Useful ketika persistent endpoint tidak required
- Dapat wait for results
- Support large datasets (gigabytes in size)

#### 2. Asynchronous Inference
**Ideal Untuk:**
- Queue requests
- Large payloads dengan processing times
- SageMaker scales endpoint down to zero
- Tidak charged untuk periods without requests

#### 3. Serverless Inference
**Karakteristik:**
- Serve model inference requests in real time
- Tanpa directly provisioning compute instances
- Tanpa configuring scaling policies
- Menggunakan Lambda
- Pay only when functions running atau pre-provisioned
- Good choice jika model memiliki periods without requests

#### 4. Real-time Inference
**Ideal Untuk:**
- Inference workloads yang need real-time interactive responses
- Persistent dan fully managed endpoint REST API
- Handle sustained traffic
- Backed by instance type pilihan Anda
- ML instances remain available untuk receive requests dan return responses in real time

**Considerations:**
- Pilih number dan instance type of ML instances
- Inference recommender tool dapat test different configuration options
- Auto scaling support

## 5. Monitoring Model di Production

### Pentingnya Monitoring

**Alasan Model Performance Degradation:**
- Data quality issues
- Model quality issues
- Model bias

**Komponen Monitoring System:**
1. Capture data
2. Compare data dengan training set
3. Define rules untuk detect issues
4. Send alerts

**Monitoring Schedule:**
- Defined schedule (daily, weekly, monthly)
- Initiated by event
- Initiated by human intervention

### Types of Drift

#### Data Drift
- Significant changes pada data distribution
- Dibandingkan dengan data used for training

#### Concept Drift
- Properties of target variables change
- Any kind of drift results in model performance degradation

### Amazon SageMaker Model Monitor

**Fungsi:**
- Monitor models in production
- Detect errors untuk take remedial actions

**Cara Kerja:**
1. Define monitoring schedule
2. Collects data dari endpoints
3. Detects changes against baseline
4. Analyzes data based on built-in rules atau custom rules

**Output:**
- View results di Amazon SageMaker Studio
- See which rules violated
- Results sent ke Amazon CloudWatch
- Configure alarms untuk take remedial actions (e.g., start re-training process)

## 6. MLOps (Machine Learning Operations)

### Konsep MLOps

**Definisi:**
- Applying established best practices of software engineering ke ML model development
- Automating manual tasks
- Testing dan evaluating code before release
- Responding automatically to incidents

**Tujuan:**
- Streamline model delivery across ML development lifecycle
- Treat everything as software (including infrastructure)
- Infrastructure described in software
- Deployed dan redeployed in repeatable fashion

### Key MLOps Principles

#### 1. Version Control
- Critical untuk tracking lineage
- Inspect past configurations
- Everything gets versioned, including training data

#### 2. Monitoring Deployments
- Detect potential issues
- Continuous evaluation

#### 3. Automation
- Automate re-training karena issues atau data/code changes
- Self-service environments dan infrastructure

### Benefits of MLOps

#### 1. Productivity
- Automation
- Self-service environments
- Data engineers dan data scientists dapat move forward

#### 2. Repeatability
- Automating all steps dalam ML lifecycle
- Ensure repeatable process
- Includes: how model trained, evaluated, versioned, deployed

#### 3. Reliability
- Deploy quickly dengan increased quality dan consistency
- Improved reliability

#### 4. Compliance
- Improve auditability
- Versioning all inputs dan outputs
- Track from data science experiments ke source data ke trained models
- Demonstrate exactly how model was built dan where deployed

#### 5. Data and Model Quality
- Enforce policies against model bias
- Track changes ke data statistical properties
- Monitor model quality over time

### AWS Services untuk MLOps

#### Amazon SageMaker Pipelines

**Kemampuan:**
- Orchestrate SageMaker jobs
- Author reproducible ML pipelines
- Deploy custom built models untuk inference in real time dengan low latency
- Run offline inferences dengan batch transform
- Track lineage of artifacts

**Operational Practices:**
- Institute sound operational practices
- Deploy dan monitor production workflows
- Deploy model artifacts
- Track artifact lineage through simple interface

**Pipeline Creation:**
- Create using SageMaker SDK for Python
- Define pipeline using JSON
- Include all steps untuk build dan deploy model
- Conditional branches based on output of previous step
- View pipelines di SageMaker Studio

#### SageMaker Feature Store
- Repository untuk feature definitions of training data

#### SageMaker Model Registry
- Centralized repository untuk trained models dan history

#### AWS Step Functions

**Karakteristik:**
- Define workflow dengan visual drag-and-drop interface
- Build serverless workflows
- Integrate various AWS services dan custom application logic

#### Amazon Managed Workflows for Apache Airflow

**Apache Airflow:**
- Open source tool
- Programmatically author, schedule, dan monitor workflows
- Sequences of processes dan tasks

**Managed Service:**
- Use Apache Airflow dan Python
- Create workflows tanpa manage underlying infrastructure
- Scalability, availability, dan security managed

## 7. Metrik Evaluasi Model

### Confusion Matrix

#### Konsep Dasar

**Definisi:**
- Summarize performance of classification model
- Evaluated against test data
- Simplest: binary classification model (yes/no, positive/negative)

**Struktur:**
- Table dengan actual data across top
- Predicted values on left

#### Komponen Confusion Matrix

Menggunakan contoh fish classification model:

**1. True Positive (TP)**
- Model sees picture of fish
- Accurately predicts it is fish

**2. True Negative (TN)**
- Model sees picture of not fish
- Accurately predicts it is not fish

**3. False Negative (FN)**
- Model sees picture of fish
- Incorrectly predicts it's not fish

**4. False Positive (FP)**
- Model sees picture of not fish
- Incorrectly predicts it is fish

### Metrik Klasifikasi

#### 1. Accuracy

**Formula:**
```
Accuracy = (TP + TN) / Total Predictions
```

**Karakteristik:**
- Measures how close predicted class values are to actual values
- Values vary between 0 and 1
- 1 = perfect accuracy
- 0 = complete inaccuracy

**Contoh:**
- 100 test images
- TP = 25, TN = 40
- Accuracy = (25 + 40) / 100 = 0.65 atau 65%

**Keterbatasan:**
- Not good metric when dataset is imbalanced
- Contoh: 90 dari 100 images adalah fish
- Model predict all images as fish = 90% accuracy (misleading)

#### 2. Precision

**Formula:**
```
Precision = TP / (TP + FP)
```

**Tujuan:**
- Measures how well algorithm predicts true positives
- Out of all positives identified

**Use Case:**
- Good quality metric untuk minimize false positives
- Contoh: don't want to label legitimate email as spam

**Contoh:**
- Precision = 0.55 atau 55% untuk fish model

#### 3. Recall (Sensitivity / True Positive Rate)

**Formula:**
```
Recall = TP / (TP + FN)
```

**Tujuan:**
- Minimize false negatives

**Use Case:**
- Make sure tidak miss if someone has disease
- Don't want to say they don't have it when they do

**Contoh:**
- Recall = 0.625 untuk fish model

**Trade-off:**
- Trade-off between precision dan recall
- Can't optimize model for both
- Contoh: diagnose everyone with disease → increase likelihood of false positives

#### 4. F1 Score

**Tujuan:**
- Balance precision dan recall
- Combine them in single metric

**Use Case:**
- When both recall dan precision are important

**Interpretasi Contoh:**
- Fish model has better recall than precision
- Better at detecting true positives
- Will have some false negatives
- Optimizing F1 score balances both metrics

#### 5. False Positive Rate (FPR)

**Formula:**
```
FPR = FP / (FP + TN)
```

**Interpretasi:**
- Shows how model handles images that are not fish
- Measure of how many predictions were fish out of images that were not fish

#### 6. True Negative Rate (TNR)

**Formula:**
```
TNR = TN / (FP + TN)
```

**Interpretasi:**
- Ratio of true negatives to sum of false positives and true negatives
- Measure of how many predictions were not fish out of images that were not fish

### Area Under the Curve (AUC)

#### Konsep

**Tujuan:**
- Compare dan evaluate binary classification
- For algorithms that return probabilities (e.g., logistic regression)

**Threshold:**
- Value model uses untuk make decision between two possible classes
- Converts probability of sample being part of class into binary decision
- Contoh: threshold 0.6 = 60% confident image is fish → classify as fish

#### Receiver Operating Characteristic (ROC) Curve

**Karakteristik:**
- True positive rate plotted against false positive rate
- For increasing threshold values
- Increasing threshold = fewer false positives, more false negatives

**AUC Metric:**
- Area under ROC curve
- Provides aggregated measure of model performance
- Across full range of thresholds

**Score Range:**
- Values between 0 and 1
- 1 = perfect accuracy
- 0.5 = prediction no better than random classifier

### Metrik Regresi

#### 1. Mean Squared Error (MSE)

**Konsep:**
- For linear regression models
- Fitting line to points in dataset
- Distance between line and actual values = error

**Formula:**
```
MSE = Average of (Prediction - Actual)²
```

**Karakteristik:**
- Always positive values
- Better model = smaller MSE value
- Emphasizes impact of outliers (karena squared)

#### 2. Root Mean Squared Error (RMSE)

**Formula:**
```
RMSE = √MSE
```

**Keuntungan:**
- Units match dependent variable
- Contoh: height in inches → MSE in square inches, RMSE in inches
- Easier to interpret

**Karakteristik:**
- Emphasizes impact of outliers (karena squared)
- Good metric when incorrect predictions can be very costly

#### 3. Mean Absolute Error (MAE)

**Formula:**
```
MAE = Average of |Prediction - Actual|
```

**Keuntungan:**
- Averages absolute values of errors
- Doesn't emphasize large errors
- Good when you don't want to emphasize outliers

## 8. Business Metrics

### Pentingnya Business Metrics

**Rooted in Business Problems:**
- ML solutions harus solve business problems
- First step ML pipeline: define business goal
- Determine how to measure successful achievement

**Fungsi:**
- Quantify value of ML model to business
- Compare actual results dengan original business goals

### Jenis Business Metrics

#### Good Metrics Examples:
1. **Cost reduction**
2. **Percentage increase in users atau sales**
3. **Measurable improvement in customer feedback**
4. **Any measurable metric important to business**

### Risk Assessment

**Pertimbangan:**
- Estimate risks of using AI dan ML
- Potential costs incurred from errors
- Contoh potential cost: loss of sales atau customers

### Post-Production Evaluation

**Data Collection:**
- Collect data untuk support metrics
- Compare actual results dengan original business goals

**Cost Analysis:**
- Consider actual cost of building dan operating model
- Compare dengan initial cost benefit model
- Calculate return on investment (ROI)

### AWS Cost Tracking

#### Cost Allocation Tags

**Fungsi:**
- Define tags assigned ke resources yang dibuat
- Contoh: tag name "ML project" dengan project name sebagai value
- Add tag ke all resources used in pipeline

**AWS Cost Explorer:**
- Filter cost reports
- Determine actual AWS charges incurred for project
- Track spending per ML project

---

## Kesimpulan

ML Development Lifecycle adalah proses komprehensif yang memerlukan perencanaan matang, eksekusi yang teliti, dan monitoring berkelanjutan. Setiap tahap dalam lifecycle memiliki tools dan services AWS yang dapat membantu mempercepat dan mempermudah proses pengembangan model ML.

Kunci sukses dalam ML development adalah:
1. **Clear business objectives** dan success criteria
2. **High-quality data** yang well-prepared
3. **Iterative experimentation** untuk find best model
4. **Proper deployment strategy** sesuai use case
5. **Continuous monitoring** dan improvement
6. **MLOps practices** untuk automation dan repeatability
7. **Appropriate metrics** untuk evaluate model dan business value

Dengan memahami setiap tahap dan memanfaatkan AWS services yang tepat, Anda dapat membangun dan mengoperasikan ML solutions yang effective dan scalable.
