# Domain 1: Use Cases Praktis AI

## Task Statement 1.2: Mengidentifikasi Use Cases Praktis untuk AI

### Kapan Menggunakan AI dan ML

**Keuntungan AI untuk Bisnis:**

1. **Operasi 24/7 Tanpa Penurunan Performa**
   - AI dapat bekerja sepanjang hari tanpa menurun performanya
   - Ideal untuk tugas repetitif dan membosankan
   - Mengurangi workload karyawan
   - Streamline operasi bisnis

2. **Menyelesaikan Masalah Kompleks**
   - Menggunakan ML dan deep learning networks
   - Memecahkan masalah dengan humanlike intelligence
   - Menganalisis data dalam jumlah besar dengan kecepatan tinggi
   - Melakukan hal yang tidak mungkin dilakukan manusia

3. **Pattern Recognition dan Fraud Detection**
   - Sangat baik dalam mengenali pola
   - Mendeteksi deviasi dalam pola
   - Mengungkap fraud
   - Mengurangi waste dengan forecasting demand

4. **Better Decision Making**
   - Membantu perusahaan membuat pilihan yang lebih baik
   - Meningkatkan efisiensi
   - Lebih baik dalam memenuhi kebutuhan pelanggan

### Kapan TIDAK Menggunakan AI

**1. Cost vs Benefit Analysis**
- Training AI membutuhkan resources yang besar
- Processing power bisa sangat mahal
- Model mungkin perlu di-retrain secara frequent
- Pastikan benefits melebihi costs

**Contoh Evaluasi:**
- Tentukan target dollar amounts untuk fraud/waste reduction
- Estimasi cost untuk build model
- Jika costs melebihi savings, jangan proceed

**2. Interpretability Requirements**
- Model AI dapat membuat keputusan yang impact customers
- Complex neural networks sulit dipahami (model interpretability)
- Tradeoff antara compatibility dan interpretability
- Jika ada business/compliance requirements untuk complete transparency, gunakan less complex models atau rule-based system

**Contoh Rule-based:**
- "People dengan credit score di atas 750 automatically approved untuk loan $10,000 atau kurang"
- Deterministic (output sama untuk input yang sama)

**3. Determinism Requirements**
- Rule-based applications adalah deterministic
- ML models adalah probabilistic (menentukan likelihood)
- ML models learn dan adapt over time
- Incorporate randomness dalam approach
- Identical inputs dapat menghasilkan variety of results
- Jika determinism necessary, gunakan rule-based system

### Tipe Masalah Machine Learning

**1. Supervised Learning Problems**

Dataset terdiri dari:
- Features/attributes sebagai inputs
- Labeled target values sebagai outputs
- Train model dengan known inputs dan outputs

**A. Classification Problems**
Target values adalah categorical (discrete values)

**Binary Classification:**
- Assign input ke salah satu dari dua predefined mutually exclusive classes
- Contoh: medical diagnosis (has disease atau not)
- Contoh: fish atau not fish

**Multiclass Classification:**
- Assign input ke salah satu dari beberapa classes
- Contoh: klasifikasi topik dokumen (religion, politics, finance)
- Contoh: mengidentifikasi multiple categories sea creatures

**B. Regression Problems**
Target values adalah mathematically continuous

**Linear Regression:**
- Direct linear relationship antara inputs dan output
- Simple linear regression: single independent variable (contoh: weight untuk predict height)
- Multiple linear regression: multiple independent variables (contoh: weight dan age)
- Contoh: prediksi harga rumah menggunakan features (bathrooms, bedrooms, square footage)

**Logistic Regression:**
- Mengukur probability of event occurring
- Prediction adalah value antara 0 dan 1
- 0 = unlikely to happen, 1 = maximum likelihood
- Menggunakan logarithmic functions
- Contoh: prediksi heart disease berdasarkan BMI, smoking status, genetic predisposition
- Contoh: prediksi financial transaction fraud

**2. Unsupervised Learning Problems**

Dataset terdiri dari:
- Features/attributes sebagai inputs
- TIDAK mengandung labels atau target values
- Output diprediksi berdasarkan pattern dalam input data
- Goal: discover patterns seperti groupings

**A. Clustering Problems**
- Data perlu dipisahkan ke discrete groups
- Classify data objects ke groups (clusters)
- Members dalam group similar satu sama lain
- Different dari members di groups lain
- Define features untuk determine similarity
- Select distance function untuk measure similarity
- Specify number of clusters
- Contoh: segmentasi customers berdasarkan purchase history atau clickstream activity

**B. Anomaly Detection Problems**
- Mencari outliers dalam data
- Identifikasi rare items, events, atau observations
- Differ significantly dari rest of data
- Contoh: detect failed sensors atau medical errors

### AWS Pre-trained AI Services

Sebelum build dan train custom model, investigate apakah existing service sudah ada untuk use case Anda.

**1. Amazon Rekognition**
Pre-trained deep learning service untuk computer vision

**Capabilities:**
- Face recognition dan verification
- Compare image dengan reference image (employee badge, driver's license)
- Detect dan label objects
- Make image/video library searchable
- Security system untuk detect objects dalam real-time streaming video
- Recognize custom/proprietary objects dengan labeled images
- Add labels untuk text (street signs)
- Detect dan filter explicit, inappropriate, violent content
- Flag content untuk human review

**Contoh Output:**
- Facial recognition dengan confidence score (99.8%)
- Detect multiple faces dan identify matches

**2. Amazon Textract**
- Lebih dari OCR
- Extract text, handwriting, forms, tabular data dari scanned documents
- Sering digunakan bersama Amazon Comprehend

**3. Amazon Comprehend**
Natural language processing service

**Capabilities:**
- Discover insights dan relationships dalam text
- Classify sentiment dari customer feedback
- Detect Personal Identifiable Information (PII)
- Find dan remove PII dari training data

**Contoh PII Detection:**
- Name, address, email, phone, credit card number
- Returns confidence score
- Set threshold untuk automatic removal

**4. Amazon Lex**
Build voice dan text interfaces

**Use Cases:**
- Customer service chatbots
- Interactive voice response systems
- Route calls ke proper agent dalam call center
- Menggunakan teknologi yang sama dengan Amazon Alexa

**5. Amazon Transcribe**
Automatic speech recognition service

**Features:**
- Support 100+ languages
- Process live dan recorded audio/video
- High quality transcriptions untuk search dan analysis
- Real-time captioning untuk streaming audio

**6. Amazon Polly**
Text-to-speech service

**Features:**
- Natural-sounding speech dalam dozens of languages
- Deep learning technologies untuk synthesize human speech
- Convert articles to speech
- Prompting callers dalam IVR systems
- Increase engagement dan accessibility

**Contoh Penggunaan:**
- Washington Post dan USA Today: audio dari breaking news dan headlines

**7. Amazon Kendra**
Intelligent search untuk enterprise systems

**Features:**
- Machine learning untuk intelligent search
- Natural language processing untuk understand questions
- Responds dengan results berdasarkan intelligent understanding
- Contoh: "How do I connect my Echo Plus to my network?"

**8. Amazon Personalize**
Automated personalized recommendations

**Use Cases:**
- Retail, media, entertainment
- "You might also like" sections
- Product recommendations berdasarkan customer interests
- Marketing campaigns dengan customer segmentation

**9. Amazon Translate**
Neural machine translation

**Features:**
- Fluently translate antara 75+ languages
- Neural network considers entire context
- More accurate dan fluent translations
- Real-time translation dalam online chat applications

**10. Amazon Fraud Detector**
Identify potentially fraudulent online activities

**Features:**
- Pre-trained data models untuk detect fraud
- Online payment fraud
- Creation of fake accounts
- Product reviews fraud
- Checkout dan payments fraud
- Account takeovers

**11. Amazon Bedrock**
Fully managed service untuk build generative AI applications

**Features:**
- Choose dari high-performing foundation models (Amazon, Meta, AI startups)
- Customize foundation model dengan own training data
- Create knowledge base untuk model query
- Retrieval Augmented Generation (RAG)

**Contoh:**
- Titan Image Generator foundation model
- Generate images dari prompts

**12. Amazon SageMaker**
Untuk customized ML models dan workflows

**Kapan Menggunakan:**
- Need more customized ML models
- Workflows beyond prebuilt functionalities
- Data preparation dan labeling
- Large-scale parallel training
- Model deployment
- Real-time inference endpoints

**Features:**
- Pre-trained models sebagai starting point
- Reduce resources untuk data preparation dan training
- ML capabilities untuk data scientists dan developers
- Prepare, build, train, deploy high quality ML models efficiently

### Real-World AI Applications

**1. MasterCard International Inc.**

**Challenge:**
- Second largest credit card network
- Need to detect fraud instantly

**Solution:**
- AI untuk score setiap transaction
- Determine probability of fraud
- Train fraud detection model dengan SageMaker

**Results:**
- Triple number of detected fraudulent transactions
- Reduce false positives by factor of 10
- 2024: Added generative AI
- 20% improvement dalam fraud detection
- LLM given customer transaction history sebagai prompt
- Predict if business adalah place customer would likely go

**2. DoorDash**

**Challenge:**
- Outdated IVR system
- Customers frustrated dengan touch tone navigation
- Customers press 0 untuk speak to agent
- Agents harus route ke someone else

**Solution:**
- Implement Amazon Lex
- Natural language processing
- Customers dapat speak instead of pressing buttons

**Results:**
- Improved customer experience
- Decreased hold times
- Increased self-service adoption

**3. Laredo Petroleum**

**Challenge:**
- Operate 1,300+ oil dan gas wells di west Texas
- Monitor pressure, temperature, flow rate sensors
- Need proactive maintenance

**Solution:**
- Data streaming solution pada AWS
- Build ML models dengan Amazon SageMaker
- Monitor data dalam real time

**Results:**
- Operations teams know where to focus maintenance
- Avoid potential issues
- Quickly identify dan remediate issues
- Reduce environmental impact (flaring/venting)
- Detect leaks dalam storage tanks dan corridor lines

**4. Booking.com**

**Challenge:**
- Travel marketplace untuk hotels, flights, rental cars, attractions
- 28 million accommodation listings
- Flight locations di 54+ countries
- Manage 150+ petabytes of data

**Solution:**
- Amazon SageMaker untuk build ML models
- Booking recommendations
- AI Trip Planner dengan generative AI
- Natural language engagement dengan customers
- Retrieval Augmented Generation (RAG)

**Process:**
- AI Trip Planner understand customer needs
- Call booking recommendation API
- Retrieve customer reviews
- Make recommendations

**Results:**
- Best customer experience
- More accurate dan current responses

**5. Pinterest**

**Challenge:**
- Visual discovery engine
- Billions of images
- 450+ million users
- Users explore, save, share pins

**Solution:**
- Pinterest Lens feature
- Computer vision untuk object recognition
- ML model trained dengan labeled product images di Amazon S3
- Frequent retraining untuk learn new objects
- Label images dengan Amazon Mechanical Turk dan SageMaker Ground Truth

**Process:**
- User take picture of object
- Pinterest immediately show similar items for sale
- Link directly ke product dalam online catalogs

**Results:**
- Seamless visual search experience
- Direct connection ke product purchases

### Kesimpulan

Task Statement 1.2 memberikan pemahaman tentang:

1. **Kapan menggunakan AI:**
   - Tugas repetitif dan complex problems
   - Pattern recognition dan fraud detection
   - 24/7 operations tanpa penurunan performa

2. **Kapan TIDAK menggunakan AI:**
   - Cost melebihi benefits
   - Interpretability requirements
   - Determinism requirements

3. **Tipe ML Problems:**
   - Supervised: Classification (binary/multiclass) dan Regression (linear/logistic)
   - Unsupervised: Clustering dan Anomaly Detection

4. **AWS Pre-trained Services:**
   - Investigate existing services sebelum build custom model
   - Banyak common use cases sudah ada solutionnya
   - Cost-effective dan faster time to market

5. **Real-world Applications:**
   - Fraud detection (MasterCard)
   - Customer service (DoorDash)
   - Predictive maintenance (Laredo Petroleum)
   - Personalized recommendations (Booking.com)
   - Visual search (Pinterest)

Pemahaman use cases praktis ini essential untuk exam dan real-world implementation.
