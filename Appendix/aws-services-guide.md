# AWS Services Guide untuk AWS Certified AI Practitioner

## Analytics

### AWS Data Exchange
**Penjelasan Singkat:** Layanan untuk menemukan, berlangganan, dan menggunakan data pihak ketiga di cloud.

**Kata Kunci di Ujian:**
- Butuh data eksternal untuk training model
- Akses dataset pihak ketiga
- Monetisasi data

**Capability & Usage:**
- Subscribe ke dataset dari provider eksternal
- Publish dan monetize data sendiri
- Integrasi dengan S3, Redshift, dan layanan analytics lainnya

---

### Amazon EMR (Elastic MapReduce)
**Penjelasan Singkat:** Platform big data untuk memproses dan menganalisis data dalam skala besar menggunakan framework seperti Apache Spark, Hadoop.

**Kata Kunci di Ujian:**
- Big data processing
- Distributed computing untuk ML
- Data preprocessing skala besar
- Apache Spark/Hadoop workloads

**Capability & Usage:**
- Preprocessing data training dalam skala petabyte
- Feature engineering untuk dataset besar
- Distributed machine learning dengan Spark MLlib
- ETL (Extract, Transform, Load) untuk data pipeline

---

### AWS Glue
**Penjelasan Singkat:** Serverless ETL service untuk data preparation dan integration.

**Kata Kunci di Ujian:**
- ETL automation
- Data catalog dan metadata management
- Serverless data preparation
- Schema discovery

**Capability & Usage:**
- Otomatis discover dan catalog data
- Transform data untuk ML training
- Crawlers untuk metadata extraction
- Job scheduling untuk data pipeline

---

### AWS Glue DataBrew
**Penjelasan Singkat:** Visual data preparation tool untuk membersihkan dan normalize data tanpa coding.

**Kata Kunci di Ujian:**
- No-code data preparation
- Data cleaning dan normalization
- Visual data profiling
- Data quality improvement

**Capability & Usage:**
- Clean dan normalize data dengan UI visual
- 250+ pre-built transformations
- Data quality rules dan anomaly detection
- Profile data untuk understand patterns

---

### AWS Lake Formation
**Penjelasan Singkat:** Service untuk membangun, secure, dan manage data lake dengan mudah.

**Kata Kunci di Ujian:**
- Data lake setup dan management
- Centralized data access control
- Data governance
- Fine-grained permissions

**Capability & Usage:**
- Centralized data catalog
- Row dan column-level security
- Data ingestion dari berbagai sources
- Audit dan compliance tracking

---

### Amazon OpenSearch Service
**Penjelasan Singkat:** Managed service untuk search, analyze, dan visualize data secara real-time.

**Kata Kunci di Ujian:**
- Log analytics
- Real-time search
- Vector search untuk embeddings
- Semantic search

**Capability & Usage:**
- Full-text search untuk aplikasi
- Vector database untuk RAG (Retrieval Augmented Generation)
- Log dan metrics analysis
- Real-time monitoring dashboards

---

### Amazon QuickSight
**Penjelasan Singkat:** Business intelligence service untuk membuat visualisasi dan dashboard interaktif.

**Kata Kunci di Ujian:**
- BI dan data visualization
- ML-powered insights
- Dashboard untuk stakeholders
- Anomaly detection dalam data

**Capability & Usage:**
- Create interactive dashboards
- ML Insights untuk anomaly detection
- Natural language queries (Q)
- Share insights dengan stakeholders

---

### Amazon Redshift
**Penjelasan Singkat:** Data warehouse untuk analytics dan query data dalam skala petabyte.

**Kata Kunci di Ujian:**
- Data warehousing
- OLAP queries
- Historical data analysis
- Feature store untuk ML

**Capability & Usage:**
- Store dan query structured data
- Integration dengan SageMaker untuk training
- Redshift ML untuk in-database ML
- Fast queries untuk large datasets

---

## Cloud Financial Management

### AWS Budgets
**Penjelasan Singkat:** Set custom budgets dan alerts untuk AWS costs dan usage.

**Kata Kunci di Ujian:**
- Cost control untuk ML projects
- Budget alerts
- Training cost monitoring
- Resource usage tracking

**Capability & Usage:**
- Set budget thresholds untuk ML workloads
- Alerts saat mendekati budget limit
- Track SageMaker training costs
- Forecast future spending

---

### AWS Cost Explorer
**Penjelasan Singkat:** Visualize dan analyze AWS costs dan usage patterns.

**Kata Kunci di Ujian:**
- Cost analysis dan optimization
- ML training cost breakdown
- Resource utilization patterns
- Cost forecasting

**Capability & Usage:**
- Analyze costs per service (SageMaker, Bedrock, dll)
- Identify cost optimization opportunities
- Forecast future costs
- Custom cost reports

---

## Compute

### Amazon EC2
**Penjelasan Singkat:** Virtual servers di cloud untuk berbagai workloads.

**Kata Kunci di Ujian:**
- Custom ML environments
- GPU instances untuk training
- Inference endpoints
- Self-managed ML infrastructure

**Capability & Usage:**
- P4/P5 instances untuk deep learning training
- G5 instances untuk inference
- Custom ML frameworks dan libraries
- Flexible compute untuk experimentation

---

## Containers

### Amazon ECS (Elastic Container Service)
**Penjelasan Singkat:** Fully managed container orchestration service.

**Kata Kunci di Ujian:**
- Containerized ML applications
- Microservices untuk ML
- Model deployment dengan containers
- Scalable inference

**Capability & Usage:**
- Deploy ML models dalam containers
- Auto-scaling untuk inference workloads
- Integration dengan ECR untuk container images
- Serverless dengan Fargate

---

### Amazon EKS (Elastic Kubernetes Service)
**Penjelasan Singkat:** Managed Kubernetes service untuk container orchestration.

**Kata Kunci di Ujian:**
- Kubernetes-based ML workflows
- Complex ML pipelines
- Multi-model deployment
- Kubeflow integration

**Capability & Usage:**
- Run Kubeflow untuk ML workflows
- Distributed training dengan Kubernetes
- Multi-tenant ML platforms
- GPU scheduling untuk training

---

## Database

### Amazon DocumentDB
**Penjelasan Singkat:** MongoDB-compatible document database.

**Kata Kunci di Ujian:**
- Semi-structured data storage
- JSON document storage
- Training data dengan flexible schema
- NoSQL untuk ML applications

**Capability & Usage:**
- Store training metadata
- Flexible schema untuk varied data
- Integration dengan ML pipelines
- Scalable document storage

---

### Amazon DynamoDB
**Penjelasan Singkat:** Fully managed NoSQL database dengan performance tinggi.

**Kata Kunci di Ujian:**
- Real-time inference data
- Feature store
- Low-latency data access
- Serverless database

**Capability & Usage:**
- Store features untuk real-time inference
- Session data untuk personalization
- Metadata storage untuk ML models
- Millisecond latency

---

### Amazon ElastiCache
**Penjelasan Singkat:** In-memory caching service (Redis/Memcached).

**Kata Kunci di Ujian:**
- Cache inference results
- Low-latency data access
- Session management
- Real-time recommendations

**Capability & Usage:**
- Cache frequent predictions
- Store embeddings untuk fast retrieval
- Session state untuk chatbots
- Reduce inference latency

---

### Amazon MemoryDB
**Penjelasan Singkat:** Redis-compatible in-memory database dengan durability.

**Kata Kunci di Ujian:**
- Durable in-memory database
- Real-time applications
- Microservices data store
- Ultra-fast data access

**Capability & Usage:**
- Primary database untuk real-time ML apps
- Store feature vectors
- Durable cache untuk predictions
- Sub-millisecond latency

---

### Amazon Neptune
**Penjelasan Singkat:** Fully managed graph database.

**Kata Kunci di Ujian:**
- Graph-based ML
- Relationship analysis
- Knowledge graphs
- Fraud detection networks

**Capability & Usage:**
- Build knowledge graphs untuk RAG
- Fraud detection dengan graph analysis
- Recommendation systems
- Social network analysis

---

### Amazon RDS
**Penjelasan Singkat:** Managed relational database service.

**Kata Kunci di Ujian:**
- Structured data storage
- Transactional data
- Application database
- SQL queries untuk features

**Capability & Usage:**
- Store structured training data
- Application backend database
- Feature extraction dengan SQL
- Integration dengan SageMaker

---

## Machine Learning

### Amazon Augmented AI (A2I)
**Penjelasan Singkat:** Human review workflows untuk ML predictions.

**Kata Kunci di Ujian:**
- Human-in-the-loop
- Low confidence predictions review
- Quality assurance untuk ML
- Human validation

**Capability & Usage:**
- Review low-confidence predictions
- Human validation workflows
- Integration dengan Rekognition, Textract, Comprehend
- Improve model accuracy dengan human feedback

---

### Amazon Bedrock
**Penjelasan Singkat:** Fully managed service untuk foundation models (FMs) dari berbagai providers.

**Kata Kunci di Ujian:**
- Foundation models
- Generative AI applications
- Model customization tanpa infrastructure
- Claude, Llama, Titan models
- RAG (Retrieval Augmented Generation)
- Knowledge bases

**Capability & Usage:**
- Access FMs via API (Claude, Llama, Titan, dll)
- Fine-tune models dengan private data
- Build RAG applications dengan Knowledge Bases
- Agents untuk complex tasks
- Guardrails untuk responsible AI
- Model evaluation dan comparison

---

### Amazon Comprehend
**Penjelasan Singkat:** NLP service untuk text analysis dan insights extraction.

**Kata Kunci di Ujian:**
- Sentiment analysis
- Entity recognition
- Language detection
- Topic modeling
- PII detection

**Capability & Usage:**
- Analyze customer feedback sentiment
- Extract entities dari documents
- Detect PII untuk compliance
- Custom entity recognition
- Document classification

---

### Amazon Fraud Detector
**Penjelasan Singkat:** Fully managed fraud detection service menggunakan ML.

**Kata Kunci di Ujian:**
- Online fraud detection
- Account takeover prevention
- Suspicious activity detection
- Pre-built fraud models

**Capability & Usage:**
- Detect online payment fraud
- Identify fake accounts
- Prevent account takeover
- Custom fraud detection rules
- Real-time fraud scoring

---

### Amazon Kendra
**Penjelasan Singkat:** Intelligent search service powered by ML.

**Kata Kunci di Ujian:**
- Enterprise search
- Natural language queries
- Document search
- Semantic search
- FAQ retrieval

**Capability & Usage:**
- Search internal documents
- Natural language question answering
- Integration dengan S3, SharePoint, databases
- Relevance tuning
- Incremental learning

---

### Amazon Lex
**Penjelasan Singkat:** Service untuk build conversational interfaces (chatbots).

**Kata Kunci di Ujian:**
- Chatbots dan virtual assistants
- Voice dan text interfaces
- Intent recognition
- Slot filling
- Multi-turn conversations

**Capability & Usage:**
- Build customer service chatbots
- Voice-enabled applications
- Integration dengan contact centers
- Multi-language support
- Automated Speech Recognition (ASR)

---

### Amazon Personalize
**Penjelasan Singkat:** Managed service untuk personalized recommendations.

**Kata Kunci di Ujian:**
- Recommendation systems
- Personalization
- User behavior analysis
- Real-time recommendations
- Similar items

**Capability & Usage:**
- Product recommendations
- Personalized content ranking
- Similar items suggestions
- User segmentation
- Real-time personalization

---

### Amazon Polly
**Penjelasan Singkat:** Text-to-speech service dengan natural-sounding voices.

**Kata Kunci di Ujian:**
- Text-to-speech (TTS)
- Voice synthesis
- Multiple languages dan voices
- SSML support
- Neural voices

**Capability & Usage:**
- Convert text ke audio
- Create voice-enabled applications
- Accessibility features
- Content narration
- IVR systems

---

### Amazon Q
**Penjelasan Singkat:** Generative AI-powered assistant untuk business.

**Kata Kunci di Ujian:**
- Business AI assistant
- Code generation
- Data analysis
- Enterprise knowledge search
- QuickSight integration

**Capability & Usage:**
- Answer business questions
- Generate code dan documentation
- Data insights dalam QuickSight
- Connect ke enterprise data sources
- Secure dan compliant

---

### Amazon Rekognition
**Penjelasan Singkat:** Computer vision service untuk image dan video analysis.

**Kata Kunci di Ujian:**
- Image analysis
- Face detection dan recognition
- Object detection
- Content moderation
- Celebrity recognition
- PPE detection

**Capability & Usage:**
- Detect objects dalam images/videos
- Face comparison dan verification
- Content moderation untuk UGC
- Text detection dalam images (OCR)
- Custom labels untuk specific use cases

---

### Amazon SageMaker
**Penjelasan Singkat:** Comprehensive ML platform untuk build, train, dan deploy models.

**Kata Kunci di Ujian:**
- End-to-end ML platform
- Model training dan deployment
- Jupyter notebooks
- AutoML
- MLOps
- Custom models

**Capability & Usage:**
- Build custom ML models
- Distributed training
- Hyperparameter tuning
- Model hosting dan inference
- ML pipelines
- Experiment tracking

**SageMaker Components:**

#### SageMaker Data Wrangler
- Visual data preparation
- 300+ built-in transformations
- Data quality insights
- Export ke training pipelines

#### SageMaker Feature Store
- Centralized feature repository
- Online dan offline feature stores
- Feature versioning
- Reduce feature engineering duplication

#### SageMaker Model Monitor
- Monitor model performance
- Detect data drift
- Model quality metrics
- Automated alerts

#### SageMaker JumpStart
- Pre-trained models dan solutions
- One-click deployment
- Foundation models access
- Solution templates

#### SageMaker Clarify
- Bias detection dalam data dan models
- Model explainability
- Feature importance
- Fairness metrics

#### SageMaker Model Cards
- Model documentation
- Intended use dan limitations
- Performance metrics
- Responsible AI documentation

#### SageMaker Ground Truth
- Data labeling service
- Human labeling workflows
- Active learning
- Automated labeling

#### SageMaker Model Registry
- Model versioning
- Model lineage tracking
- Approval workflows
- Centralized model catalog

#### SageMaker Canvas
- No-code ML
- Visual interface untuk ML
- AutoML capabilities
- Business analysts friendly

---

### Amazon Textract
**Penjelasan Singkat:** OCR service untuk extract text dan data dari documents.

**Kata Kunci di Ujian:**
- Document processing
- OCR (Optical Character Recognition)
- Form extraction
- Table extraction
- ID document processing

**Capability & Usage:**
- Extract text dari scanned documents
- Parse forms dan tables
- Process invoices dan receipts
- ID verification
- Handwriting recognition

---

### Amazon Transcribe
**Penjelasan Singkat:** Automatic speech recognition (ASR) service.

**Kata Kunci di Ujian:**
- Speech-to-text
- Audio transcription
- Real-time transcription
- Speaker identification
- Custom vocabulary

**Capability & Usage:**
- Transcribe audio files
- Real-time streaming transcription
- Medical transcription
- Call analytics
- Subtitle generation

---

### Amazon Translate
**Penjelasan Singkat:** Neural machine translation service.

**Kata Kunci di Ujian:**
- Language translation
- Multi-language support
- Real-time translation
- Batch translation
- Custom terminology

**Capability & Usage:**
- Translate text antar 75+ languages
- Localize content
- Real-time translation
- Custom terminology untuk domain-specific terms
- Batch document translation

---

## Management and Governance

### AWS CloudTrail
**Penjelasan Singkat:** Service untuk audit dan logging API calls.

**Kata Kunci di Ujian:**
- Audit logging
- Compliance tracking
- Security analysis
- API call history
- Governance

**Capability & Usage:**
- Track semua API calls untuk ML services
- Security audit trails
- Compliance reporting
- Detect unauthorized access
- Integration dengan CloudWatch

---

### Amazon CloudWatch
**Penjelasan Singkat:** Monitoring dan observability service.

**Kata Kunci di Ujian:**
- Monitoring ML workloads
- Metrics dan logs
- Alarms dan notifications
- Performance tracking
- Resource utilization

**Capability & Usage:**
- Monitor SageMaker training jobs
- Track inference endpoint metrics
- Set alarms untuk anomalies
- Log aggregation
- Custom metrics untuk ML applications

---

### AWS Config
**Penjelasan Singkat:** Service untuk assess, audit, dan evaluate AWS resource configurations.

**Kata Kunci di Ujian:**
- Configuration compliance
- Resource inventory
- Change tracking
- Compliance rules
- Configuration history

**Capability & Usage:**
- Track ML resource configurations
- Compliance dengan security policies
- Configuration change notifications
- Automated remediation
- Resource relationship tracking

---

### AWS Trusted Advisor
**Penjelasan Singkat:** Automated recommendations untuk cost optimization, security, dan performance.

**Kata Kunci di Ujian:**
- Best practices recommendations
- Cost optimization
- Security checks
- Performance improvements
- Resource utilization

**Capability & Usage:**
- Identify underutilized ML resources
- Security vulnerability checks
- Cost optimization recommendations
- Performance improvement suggestions
- Service limit monitoring

---

### AWS Well-Architected Tool
**Penjelasan Singkat:** Tool untuk review workloads terhadap AWS best practices.

**Kata Kunci di Ujian:**
- Architecture review
- Best practices assessment
- ML workload optimization
- Six pillars review
- Risk identification

**Capability & Usage:**
- Review ML architecture
- Identify architectural risks
- Best practices untuk ML workloads
- Improvement recommendations
- Documentation dan reporting

---

## Tips Ujian

### Service Selection Strategy:
1. **Data Preparation:** Glue, DataBrew, EMR
2. **Training:** SageMaker, Bedrock (fine-tuning)
3. **Pre-built AI:** Rekognition, Comprehend, Textract, Transcribe, Translate, Polly, Lex
4. **Generative AI:** Bedrock, Q
5. **Specialized ML:** Personalize, Fraud Detector, Kendra
6. **Monitoring:** CloudWatch, SageMaker Model Monitor
7. **Governance:** CloudTrail, Config, Trusted Advisor
8. **Cost Management:** Cost Explorer, Budgets

### Common Exam Scenarios:
- **Butuh generative AI tanpa training:** → Bedrock
- **Custom ML model:** → SageMaker
- **No-code ML:** → SageMaker Canvas
- **Image analysis:** → Rekognition
- **Text analysis:** → Comprehend
- **Document extraction:** → Textract
- **Chatbot:** → Lex
- **Recommendations:** → Personalize
- **Search:** → Kendra
- **Human review:** → A2I
- **Data labeling:** → Ground Truth
- **Bias detection:** → SageMaker Clarify
- **Model monitoring:** → SageMaker Model Monitor
