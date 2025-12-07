# Domain 1: ML Development Lifecycle

## Task Statement 1.3: Menjelaskan ML Development Lifecycle

### Pengenalan ML Pipeline

Machine Learning Pipeline adalah serangkaian langkah-langkah yang saling terhubung (interconnected steps) yang dimulai dengan mendefinisikan business goal dan berakhir dengan mengoperasikan deployed ML model dalam production environment. Pipeline ini bukan proses linear sederhana, melainkan workflow yang kompleks dan iteratif.

**Tahapan Utama ML Pipeline:**

1. **Define the Problem** - Mendefinisikan masalah bisnis dan tujuan
2. **Collect and Prepare Training Data** - Mengumpulkan dan mempersiapkan data training
3. **Train the Model** - Melatih model dengan data yang sudah dipersiapkan
4. **Deploy the Model** - Men-deploy model ke production environment
5. **Monitor the Model** - Memonitor performa model secara berkelanjutan

**Karakteristik Fundamental ML Pipeline:**

**Sifat Iteratif:**
- Beberapa steps dalam pipeline adalah iterative process yang perlu diulang berkali-kali
- Iterasi dilakukan hingga objectives dan performance targets tercapai
- Setiap iterasi memberikan insights untuk improvement di iterasi berikutnya
- Feedback loops memungkinkan continuous refinement

**Dynamic Nature:**
- ML models adalah dynamic by design, bukan static artifacts
- Models perlu di-retrain dengan new data secara berkala
- Continually evaluated terhadap performance metrics dan business KPIs
- Monitoring dilakukan untuk detect drifts (data drift dan concept drift) serta bias
- Models di-adjust atau bahkan di-rebuild as needed berdasarkan monitoring results

**Continuous Improvement:**
- Pipeline mendukung continuous improvement cycle
- Learning dari production performance
- Incorporating new data dan patterns
- Adapting to changing business requirements

**ML Lifecycle vs Pipeline Concept:**

Lebih tepat untuk menyebut ini sebagai "lifecycle" daripada "pipeline" karena:

**Lifecycle Characteristics:**
- **Cyclical Nature:** Parts atau bahkan seluruh pipeline di-repeat setelah model deployed
- **Never Truly Complete:** Model terus di-improve dan di-update
- **Continuous Process:** Bukan one-time project, tapi ongoing initiative
- **Feedback Integration:** Production results inform future iterations
- **Adaptive:** Responds to changes dalam data, business, dan environment

**Why This Matters:**
- Organizations harus plan untuk long-term maintenance, bukan just initial deployment
- Resources perlu dialokasikan untuk ongoing monitoring dan retraining
- Success metrics harus include both initial performance dan sustained performance over time
- Team structure harus support continuous operation, bukan just project-based work

**Visual Representation:**
```
Business Goal → Data Collection → Training → Deployment → Monitoring
                      ↑                                        ↓
                      ←────────── Feedback & Retraining ──────┘
```

Setiap phase dalam lifecycle ini memiliki objectives, challenges, dan best practices yang spesifik. Mari kita explore setiap phase secara mendalam.

### Phase 1: Define the Business Goal

Phase pertama dan paling krusial dalam ML development lifecycle adalah mendefinisikan business goal dengan jelas. Development dari ML model harus selalu dimulai dengan identifying business goal yang spesifik dan terukur. Tanpa foundation yang kuat di phase ini, seluruh project berisiko gagal atau tidak memberikan value yang diharapkan.

**Langkah-Langkah Fundamental:**

**1. Identify Business Goal dengan Clear dan Specific**

Organization yang mempertimbangkan ML harus memiliki clear idea tentang:
- **Problem Statement:** Masalah bisnis apa yang ingin diselesaikan?
- **Business Value:** Value apa yang akan diperoleh dari solving problem ini?
- **Stakeholder Alignment:** Siapa yang akan benefit dan siapa yang perlu involved?

**Contoh Problem Statements:**
- ❌ Buruk: "Kita ingin menggunakan AI"
- ✅ Baik: "Kita ingin mengurangi customer churn sebesar 20% dalam 6 bulan dengan memprediksi customers yang berisiko tinggi untuk churn"

**2. Measure Business Value Terhadap Specific Objectives**

More than just an idea, Anda harus be able to measure business value against specific business objectives dan success criteria:

**Quantifiable Metrics:**
- Revenue impact (increase atau cost savings)
- Efficiency improvements (time saved, resources optimized)
- Customer satisfaction scores
- Error rate reduction
- Process automation percentage

**Example Metrics:**
- "Reduce fraud losses by $500K annually"
- "Decrease customer support response time by 40%"
- "Improve product recommendation click-through rate by 15%"
- "Reduce inventory waste by 25%"

**3. Define Success Criteria**

**Pentingnya Success Criteria:**

Tanpa clear success criteria:
- ❌ Tidak bisa objectively evaluate apakah model successful
- ❌ Tidak bisa determine apakah ML adalah best solution untuk problem
- ❌ Sulit untuk gain buy-in dari stakeholders
- ❌ Tidak ada clear stopping point untuk development

**Components of Good Success Criteria:**

**A. Performance Metrics:**
- Model accuracy targets (e.g., "95% precision dalam fraud detection")
- Latency requirements (e.g., "predictions dalam <100ms")
- Throughput needs (e.g., "handle 10,000 requests per second")

**B. Business Metrics:**
- ROI targets (e.g., "break even dalam 12 months")
- Cost constraints (e.g., "infrastructure cost <$10K per month")
- Timeline expectations (e.g., "deploy to production dalam 6 months")

**C. Quality Metrics:**
- False positive rate (e.g., "<5% false positives")
- False negative rate (e.g., "<2% false negatives")
- Bias metrics (e.g., "no significant disparity across demographic groups")

**4. Align Stakeholders untuk Gain Consensus**

**Critical Stakeholders:**
- **Business Leaders:** Provide funding dan strategic direction
- **Data Scientists:** Technical feasibility dan approach
- **Engineering Teams:** Implementation dan infrastructure
- **End Users:** Requirements dan usability
- **Compliance/Legal:** Regulatory requirements

**Alignment Process:**
- Regular meetings dan updates
- Clear communication of goals dan constraints
- Documented requirements dan acceptance criteria
- Risk assessment dan mitigation plans

**Evaluasi Kelayakan (Feasibility Assessment):**

**1. Organizational Capability:**
- Evaluate organization's ability untuk move toward target
- Assess available resources (people, budget, infrastructure)
- Identify skill gaps dan training needs
- Determine timeline realism

**2. Target Achievability:**
- Target harus achievable given constraints
- Not too ambitious (unrealistic expectations)
- Not too conservative (insufficient business value)
- Provide clear path to production

**3. ML Appropriateness:**
- Determine apakah ML adalah appropriate approach untuk delivering business goal
- Consider alternatives (rule-based systems, traditional analytics)
- Assess if problem is suitable untuk ML (pattern recognition, prediction, classification)

**Pertimbangan Teknis dan Bisnis:**

**1. Evaluate All Available Options:**

**Option Analysis:**
- **Do Nothing:** What's the cost of not solving this problem?
- **Manual Process:** Can humans do this effectively?
- **Rule-Based System:** Are rules sufficient dan maintainable?
- **Traditional Analytics:** Will statistical methods suffice?
- **Machine Learning:** Is ML necessary dan justified?

**2. Determine Expected Accuracy:**
- What level of accuracy is required untuk business value?
- What's the cost of errors (false positives vs false negatives)?
- Is perfect accuracy necessary atau is "good enough" acceptable?

**3. Cost dan Scalability Considerations:**

**Cost Factors:**
- Development costs (team, tools, infrastructure)
- Training costs (compute resources, data labeling)
- Deployment costs (hosting, maintenance)
- Operational costs (monitoring, retraining)

**Scalability Factors:**
- Data volume growth projections
- User/request volume expectations
- Geographic expansion plans
- Feature expansion roadmap

**4. Data Availability Assessment:**

**Critical Questions:**
- Is enough relevant high-quality training data available?
- Where is data generated dan stored?
- Is data accessible dan usable?
- Are there privacy atau compliance constraints?
- Is data labeled atau will labeling be required?

**Data Quality Checks:**
- Completeness (missing values?)
- Accuracy (errors dalam data?)
- Consistency (conflicting information?)
- Timeliness (is data current?)
- Relevance (does data relate to problem?)

**Formulate ML Question:**

Transform business problem menjadi ML problem dengan clearly defining:

**1. Inputs (Features):**
- What data will model receive?
- What format will data be in?
- What preprocessing is needed?

**Example:**
- Business: "Predict customer churn"
- ML Inputs: Customer demographics, purchase history, support interactions, usage patterns

**2. Desired Outputs:**
- What should model predict atau classify?
- What format should output be?
- What confidence level is needed?

**Example:**
- Output: Probability of churn (0-1)
- Threshold: >0.7 = high risk
- Action: Trigger retention campaign

**3. Performance Metric to Optimize:**
- What metric best represents success?
- How will we measure model quality?
- What's the target value?

**Example:**
- Primary: F1 Score >0.85
- Secondary: Recall >0.90 (don't miss churners)
- Constraint: Precision >0.75 (limit false alarms)

**Investigate Options dan Decision Framework:**

**1. Start dengan Simplest Solution:**

**Principle:** Always start dengan simplest solution before determining bahwa more complexity is required.

**Progression:**
```
Simple Rules → Statistical Methods → Traditional ML → Deep Learning → Custom Architecture
```

**Why Start Simple:**
- Faster to implement dan test
- Easier to understand dan explain
- Lower cost dan resource requirements
- Provides baseline untuk comparison
- May be sufficient untuk business needs

**2. Complexity Assessment:**

**When to Increase Complexity:**
- Simple solution doesn't meet performance targets
- Problem has complex patterns
- Large amounts of data available
- High-value use case justifies investment

**When to Stay Simple:**
- Simple solution meets requirements
- Limited data available
- Interpretability is critical
- Resource constraints
- Quick time to market needed

**3. Cost-Benefit Analysis:**

**Comprehensive Analysis:**

**Costs:**
- Development: $X
- Infrastructure: $Y per month
- Maintenance: $Z per year
- Opportunity cost: Time to market

**Benefits:**
- Direct savings: $A per year
- Revenue increase: $B per year
- Efficiency gains: $C per year
- Strategic value: Competitive advantage

**Decision:**
- If (Benefits - Costs) > Threshold → Proceed
- If marginal → Reconsider scope atau approach
- If negative → Don't proceed atau find alternative

**4. Go/No-Go Decision:**

**Proceed to Next Phase If:**
- ✅ Clear business value identified
- ✅ Success criteria defined
- ✅ Stakeholders aligned
- ✅ Sufficient data available
- ✅ Positive cost-benefit analysis
- ✅ ML is appropriate approach
- ✅ Resources available
- ✅ Clear path to production

**Don't Proceed If:**
- ❌ Unclear business value
- ❌ Insufficient data
- ❌ Costs exceed benefits
- ❌ Simpler solution would suffice
- ❌ Lack of stakeholder support
- ❌ No clear success criteria

**Key Takeaway:**

Phase 1 adalah foundation dari entire ML project. Investing time untuk properly define business goal, assess feasibility, dan align stakeholders akan significantly increase chances of success. Rushing through this phase adalah common mistake yang leads to failed projects.

### Opsi Solusi ML

Setelah mendefinisikan business goal, langkah berikutnya adalah menentukan approach apa yang akan digunakan untuk build solution. AWS telah introduced number of AI services untuk democratize ML dan make it accessible to anyone. Penting untuk investigate all available options sebelum memutuskan approach.

**Decision Framework: Pilih Approach yang Tepat**

```
Start Here → AWS AI Services (Pre-trained)
              ↓ (If insufficient)
           Existing Models + Fine-tuning
              ↓ (If insufficient)
           Train from Scratch
```

**Prinsip Fundamental:** Always start dengan simplest solution dan only increase complexity jika necessary.

---

**Opsi 1: AWS AI Services (Pre-trained) - Simplest Approach**

**Karakteristik:**

AWS telah mengidentifikasi many common use cases dan developed easy, consumable, dan fully trained ML models yang fully hosted oleh mereka. Ini adalah starting point yang ideal untuk most projects.

**Key Advantages:**

**A. Democratization of ML:**
- Makes ML accessible to anyone, tanpa ML expertise
- No need untuk data scientists atau ML engineers
- Business analysts dapat use these services
- Rapid prototyping dan deployment

**B. Fully Managed:**
- AWS handles all infrastructure
- Automatic scaling
- High availability
- Security dan compliance
- Regular updates dan improvements

**C. Pay-as-you-go Pricing:**
- No upfront investment
- Pay only untuk what you use
- No infrastructure costs
- Predictable pricing
- Free tier available untuk testing

**D. Quick Time to Market:**
- Deploy dalam hours atau days, bukan months
- No training required
- Immediate results
- Fast iteration

**When to Use:**

✅ **Use AWS AI Services When:**
- Use case matches available service
- Standard functionality sufficient
- Quick deployment needed
- Limited ML expertise
- Budget constraints
- Proof of concept phase

**Available Services dan Use Cases:**

**Computer Vision:**
- **Amazon Rekognition:** Image/video analysis, face recognition, object detection
- Use case: Content moderation, security systems, media asset management

**Natural Language Processing:**
- **Amazon Comprehend:** Sentiment analysis, entity recognition, PII detection
- **Amazon Translate:** Language translation
- **Amazon Transcribe:** Speech-to-text
- Use case: Customer feedback analysis, multilingual support, transcription services

**Speech:**
- **Amazon Polly:** Text-to-speech
- **Amazon Lex:** Conversational interfaces
- Use case: Voice assistants, IVR systems, accessibility

**Search dan Recommendations:**
- **Amazon Kendra:** Intelligent search
- **Amazon Personalize:** Personalized recommendations
- Use case: Enterprise search, e-commerce recommendations

**Fraud Detection:**
- **Amazon Fraud Detector:** Fraud detection
- Use case: Payment fraud, fake accounts, review fraud

**Customization Options:**

Many services allow customization untuk better fit your specific needs:

**Example - Amazon Comprehend:**
- **Standard:** Use pre-trained models untuk common tasks
- **Custom:** Create custom classifier dengan your own categories
- **Process:** Supply training data dengan your labels
- **Result:** Model trained specifically untuk your domain

**Benefits of Customization:**
- Better accuracy untuk your specific use case
- Domain-specific terminology
- Industry-specific patterns
- Proprietary categories

**Evaluation Process:**

Before moving ke more complex options:
1. **Identify** relevant AWS AI service
2. **Test** dengan your data (use free tier)
3. **Measure** performance against success criteria
4. **Evaluate** cost at expected scale
5. **Decide** if meets business goals

**Cost-Benefit Analysis:**
- Development time: Minimal (days)
- Development cost: Very low
- Operational cost: Pay-per-use
- Maintenance: Handled by AWS
- **Decision:** If meets requirements, this is optimal choice

---

**Opsi 2: Start dengan Existing Model (Pre-trained + Fine-tuning) - Medium Complexity**

**When to Use This Approach:**

Jika hosted service tidak achieve objectives, next consideration adalah building your own model dengan starting dari existing one. Ini adalah middle ground antara fully managed services dan training from scratch.

**Karakteristik:**

**Transfer Learning Concept:**
- Start dengan model yang already trained pada large dataset
- Fine-tune model dengan your specific data
- Leverage existing knowledge
- Significantly reduce training time dan cost

**A. Generative AI Use Cases:**

**Amazon Bedrock Approach:**

**Foundation Models:**
- Start dengan fully trained foundation model
- Models trained pada massive datasets
- General knowledge dan capabilities
- Multiple model options (Titan, Claude, Llama, etc.)

**Fine-tuning Process:**
1. **Select** base foundation model
2. **Prepare** your training data
3. **Fine-tune** model dengan your data
4. **Evaluate** performance
5. **Deploy** customized model

**Benefits:**
- Model understands your domain better
- Improved accuracy untuk your use case
- Maintains general capabilities
- Faster than training from scratch
- Lower cost than custom development

**Example Use Case:**
```
Base Model: General language understanding
Your Data: Company-specific documents, terminology, processes
Fine-tuned Model: Understands your business context
Result: Better responses untuk your specific domain
```

**B. Other ML Use Cases:**

**Amazon SageMaker JumpStart:**

**What It Provides:**
- Pre-trained AI foundation models
- Task-specific models untuk computer vision dan NLP
- Open source pre-trained models
- One-click deployment
- Fine-tuning capabilities

**Model Categories:**

**1. Foundation Models:**
- Large language models
- Vision models
- Multimodal models

**2. Task-Specific Models:**
- **Computer Vision:** Object detection, image classification, segmentation
- **NLP:** Text classification, named entity recognition, summarization
- **Tabular Data:** Regression, classification

**Transfer Learning Process:**

**Traditional Approach (Expensive):**
```
Collect massive dataset → Train from scratch → Weeks/months → High cost
```

**Transfer Learning Approach (Efficient):**
```
Pre-trained model → Fine-tune dengan your data → Days → Lower cost
```

**Technical Benefits:**

**1. Reduced Data Requirements:**
- Pre-trained model already learned general features
- Need less data untuk fine-tuning
- Example: Might need 1,000 images instead of 1,000,000

**2. Faster Training:**
- Start dengan learned weights
- Only adjust untuk your specific task
- Training time: days instead of weeks

**3. Better Performance:**
- Leverage knowledge dari large datasets
- Often better than training from scratch dengan limited data
- Especially effective untuk specialized domains

**4. Cost Savings:**
- Less compute time
- Smaller datasets
- Faster iteration
- Lower infrastructure costs

**When to Choose This Approach:**

✅ **Use Pre-trained + Fine-tuning When:**
- AWS AI services insufficient
- Need customization beyond what services offer
- Have some labeled data (but not massive amounts)
- Want balance of performance dan cost
- Need faster development than from scratch
- Domain-specific requirements

**Cost-Benefit Analysis:**
- Development time: Moderate (weeks)
- Development cost: Medium
- Requires: Some ML expertise
- Data needs: Moderate (thousands of samples)
- **Decision:** Good balance untuk many use cases

---

**Opsi 3: Train from Scratch - Most Difficult Approach**

**When to Use This Approach:**

This is most difficult dan costly approach dan should only be considered when other options are insufficient.

**Karakteristik:**

**Complete Custom Development:**
- Design model architecture from scratch
- Collect dan label massive datasets
- Train model completely from beginning
- Full control over every aspect
- Maximum flexibility

**Challenges:**

**1. Technical Complexity:**
- **Most technically challenging** approach
- Requires deep ML expertise
- Need experienced data scientists
- Complex architecture decisions
- Extensive experimentation required

**2. Responsibility:**
- **Most responsibility** untuk security dan compliance
- Must handle all aspects:
  - Data privacy dan protection
  - Model security
  - Compliance dengan regulations
  - Audit trails
  - Bias detection dan mitigation
  - Explainability

**3. Cost:**
- **Most costly** approach
- Massive compute requirements
- Large datasets needed
- Extensive labeling costs
- Long development cycles
- High infrastructure costs

**4. Time:**
- **Longest development time**
- Months atau even years
- Multiple iterations
- Extensive testing
- Gradual improvement

**Resource Requirements:**

**Team:**
- Senior data scientists
- ML engineers
- Data engineers
- DevOps engineers
- Domain experts

**Infrastructure:**
- High-performance compute (GPUs/TPUs)
- Large-scale storage
- Distributed training systems
- Monitoring dan logging
- CI/CD pipelines

**Data:**
- Millions of labeled samples
- High-quality annotations
- Diverse dan representative
- Continuous data collection

**When Justified:**

✅ **Train from Scratch When:**
- Unique problem dengan no existing solutions
- Proprietary approach is competitive advantage
- Specific requirements tidak dapat be met otherwise
- Have necessary resources (team, budget, time)
- Long-term strategic investment
- Cutting-edge research needed

**Examples:**
- Novel computer vision tasks
- Proprietary algorithms
- Specialized domains dengan no pre-trained models
- Competitive differentiation through ML

**Cost-Benefit Analysis:**
- Development time: Long (months to years)
- Development cost: Very high
- Requires: Expert ML team
- Data needs: Massive (millions of samples)
- Infrastructure: Expensive
- **Decision:** Only when absolutely necessary

---

**Decision Matrix: Choosing the Right Approach**

| Factor | AWS AI Services | Pre-trained + Fine-tuning | Train from Scratch |
|--------|----------------|---------------------------|-------------------|
| **Time to Market** | Days | Weeks | Months |
| **Cost** | Low | Medium | High |
| **ML Expertise** | None | Moderate | Expert |
| **Data Needed** | None | Moderate | Massive |
| **Customization** | Limited | Good | Complete |
| **Performance** | Good | Better | Best (potentially) |
| **Maintenance** | AWS | Shared | You |

**Recommendation:**

1. **Always start** dengan AWS AI Services
2. **Move to fine-tuning** if services insufficient
3. **Only train from scratch** if absolutely necessary
4. **Re-evaluate** as AWS adds new services dan capabilities

**Key Principle:** Use simplest solution yang meets your requirements. Complexity should be justified by business value.

**SageMaker JumpStart:**
- Pre-trained AI foundation models
- Task-specific models untuk computer vision dan NLP
- Pre-trained pada large public datasets
- Option untuk fine-tune dengan incremental training
- Transfer learning process
- Large savings dalam cost dan development time

### Phase 2: Collect dan Process Training Data

**Data Collection:**

1. **Identify Data Needed**
   - Determine training data requirements
   - Know where data is generated dan stored
   - Understand data sources

2. **Collection Options**
   - Streaming data atau batch process
   - Configure ETL (Extract, Transform, Load)
   - Collect dari multiple sources
   - Store dalam centralized repository
   - Process harus repeatable (untuk re-training)

3. **Data Labeling**
   - Know apakah data sudah labeled
   - Determine how to label data
   - Bisa menjadi longest part of process
   - Accurately labeled data likely tidak already exist

**Data Preparation:**

1. **Data Pre-processing**
   - Exploratory Data Analysis (EDA) dengan visualization tools
   - Gain deeper understanding of data
   - Data wrangling tools untuk interactive analysis
   - Prepare data untuk model building

2. **Data Cleaning**
   - Filter atau repair data dengan missing values
   - Handle anomalous values
   - Mask atau remove PII data

3. **Data Splitting**
   - Typical recommendation:
     - 80% untuk training
     - 10% untuk evaluation
     - 10% untuk final test sebelum production

4. **Feature Engineering**
   - Determine characteristics untuk use sebagai features
   - Select subset yang relevant
   - Contribute to minimizing error rate
   - Reduce features ke only those needed untuk inference
   - Combine features untuk further reduce number
   - Reducing features = reduce memory dan computing power

### AWS Services untuk Data Ingestion dan Preparation

**1. AWS Glue**
Fully managed ETL service

**Features:**
- Create dan run ETL job dengan few clicks
- Point AWS Glue ke data stored pada AWS
- Glue discovers data dan stores metadata
- Table definition dan schema dalam AWS Glue Data Catalog
- Data immediately searchable, queryable, available untuk ETL
- Generate code untuk execute transformations dan loading

**Built-in Transformations:**
- Drop duplicate records
- Fill in missing values
- Split dataset

**Data Sources:**
- Relational databases
- Data warehouses
- Cloud services
- Streaming services (Amazon MSK, Amazon Kinesis)

**AWS Glue Data Catalog:**
- Contains references to data
- Used as sources dan targets untuk ETL jobs
- Tables include index to location, schema, runtime metrics
- Use information untuk create dan monitor ETL jobs
- Run crawler untuk take inventory of data
- Manually enter information dalam tables

**Crawlers:**
- Automatically determine data schema
- Use classifiers
- Write schema to tables dalam Data Catalog
- Source data itself NOT written to catalog
- Only metadata (location, schema) stored
- ETL jobs use information untuk collect, transform, store data
- Target data store typically S3 bucket

**2. AWS Glue DataBrew**
Visual data preparation tool

**Features:**
- Clean dan normalize data tanpa writing code
- Interactively discover, visualize, clean, transform raw data
- Smart suggestions untuk identify data quality issues
- Save transformation steps dalam recipe
- Update atau reuse recipes dengan other datasets
- Deploy on continuing basis

**Built-in Transformations (250+):**
- Remove nulls
- Replace missing values
- Fix schema inconsistencies
- Create column-based functions
- Visual point-and-click interface

**Data Quality:**
- Define rule sets
- Run profiling jobs
- Evaluate data quality

**3. SageMaker Ground Truth**
Build high-quality training datasets

**Features:**
- Active learning uses ML model untuk label data
- Automatically label data yang dapat di-label
- Rest given to human workforce

**Human Workforce Options:**
- Amazon Mechanical Turk (500,000+ independent contractors)
- Internal private workforce (own employees/contractors)

**4. Amazon SageMaker Canvas**
Prepare, featurize, analyze data

**Features:**
- Simplify feature engineering process
- Single visual interface
- SageMaker Data Wrangler data selection tool
- Choose raw data dari various sources
- Import dengan single click
- 300+ built-in transformations
- Normalize, transform, combine features tanpa code

**5. Amazon SageMaker Feature Store**
Centralized store untuk features

**Features:**
- Features dan associated metadata
- Easy discovery dan reuse
- Accelerate feature creation, sharing, management
- Reduce repetitive data processing
- Convert raw data into features untuk training
- Create workflow pipelines
- Add features ke feature groups

### Phase 3: Train, Tune, dan Evaluate Model

**Training Process:**

1. **Iterative Learning**
   - Teaching model through iterative process
   - Training, tuning, evaluating
   - ML algorithm updates parameters/weights
   - Goal: update parameters agar inference matches expected output

2. **Why Iterative?**
   - Algorithm belum learned
   - No knowledge bagaimana changing weights shift output
   - Watch weights dan outputs dari previous iterations
   - Shift weights ke direction yang lower error

3. **Stopping Criteria**
   - Defined number of iterations completed
   - Change dalam error below target value

**Running Experiments:**

**Best Practice:**
- Run many training jobs in parallel
- Use different algorithms dan settings
- Land on best-performing solution

**Hyperparameters:**
- External parameters yang affect algorithm performance
- Set oleh data scientists sebelum training
- Contoh: number of neural layers dan nodes dalam deep learning
- Optimal values determined dengan running multiple experiments

**Amazon SageMaker Training:**

**Create Training Job:**
1. Specify URL dari S3 bucket containing training data
2. Specify compute resources untuk training
3. Specify output bucket untuk model artifacts
4. Specify algorithm dengan Docker container image path
5. Set hyperparameters required oleh algorithm

**Container Options:**
- Amazon ECR untuk SageMaker provided algorithms
- Deep learning containers
- Custom container dengan custom algorithm

**Training Execution:**
- SageMaker launches ML compute instances
- Uses training code dan training dataset
- Train the model
- Save model artifacts dan outputs ke S3

**Amazon SageMaker Experiments:**

**Purpose:**
- ML adalah iterative process
- Need to experiment dengan multiple combinations
- Data, algorithms, parameters
- Observe impact dari incremental changes
- Can result dalam thousands of training runs

**Features:**
- Create, manage, analyze, compare experiments
- Experiment = group of training runs
- Different inputs, parameters, configurations
- Visual interface untuk browse experiments
- Compare runs pada key performance metrics
- Identify best-performing models

**Amazon SageMaker Automatic Model Tuning (AMT):**

**Also Known As:**
- Hyperparameter tuning

**Purpose:**
- Find best version of model
- Run many training jobs pada dataset
- Use algorithm dan ranges of hyperparameters
- Choose hyperparameter values yang create best model
- Measured oleh metric yang you choose

**Example:**
- Binary classification model
- Find combination yang maximizes area under curve (AUC)

**Configuration:**
- Configure tuning job
- Runs several training jobs dalam loop
- Specify completion criteria
- Number of jobs yang no longer improving metric
- Job runs until criteria satisfied

### Phase 4: Deploy Model

**Deployment Decisions:**

**1. Batch Inference**
- Need large number of inferences
- Okay to wait untuk results
- Batch process runs overnight
- Data collected dari previous day
- Most cost-effective approach
- Computing resources only running once per day

**2. Real-time Inference**
- Deploy model untuk respond immediately
- Example: generative AI
- Clients interact via REST API
- API = set of actions over HTTP connection
- Web application send POST request dengan input data
- Endpoint pass request ke compute resource running model
- Model output sent back dalam response

**Architecture Example:**
- Amazon API Gateway sebagai interface dengan clients
- Forward requests ke AWS Lambda function
- Lambda running the model

**Container Deployment:**
- Inference code dan model artifacts deployed sebagai Docker container
- Docker containers very versatile
- Can run pada any compute resource dengan container runtime

**AWS Compute Options:**
- AWS Batch
- Amazon ECS (Elastic Container Service)
- Amazon EKS (Elastic Kubernetes Service)
- AWS Lambda
- Amazon EC2 (Elastic Compute Cloud)

**Management Considerations:**
- Configure dan manage inference endpoint
- Manage updates, patches
- Scalability
- Network routing
- Security

**Amazon SageMaker Hosting:**

**Benefits:**
- Reduced operational overhead
- Automatically deploy model pada hosted endpoints
- Fully managed on your behalf

**Setup:**
- Point SageMaker ke model artifacts dalam S3
- Point ke Docker container image dalam Amazon ECR
- Select inference option
- SageMaker creates endpoint dan installs model code

**Inference Options:**

**1. Batch Transform**
- Offline inference untuk large datasets
- No persistent endpoint required
- Can wait untuk results
- Support datasets gigabytes in size

**2. Asynchronous Inference**
- Queue requests
- Large payloads dengan processing times
- SageMaker scales endpoint down to zero
- Not charged untuk periods without requests

**3. Serverless Inference**
- Real-time model inference requests
- No direct provisioning compute instances
- No configuring scaling policies
- Handle traffic variations
- Uses Lambda
- Only pay when functions running atau pre-provisioned
- Good choice jika model has periods without requests

**4. Real-time Inference**
- Real-time interactive responses
- Persistent dan fully managed endpoint
- REST API handle sustained traffic
- Backed oleh instance type of your choice
- ML instances remain available
- Receive requests dan return responses dalam real time

**Inference Recommender:**
- Tool within SageMaker
- Test different configuration options
- Pick best one untuk your model

### Phase 5: Monitor Model

**Why Monitor?**
- Model performance bisa degrade over time
- Reasons: data quality, model quality, model bias
- Need continuous monitoring

**Monitoring System Requirements:**
1. Capture data
2. Compare data ke training set
3. Define rules untuk detect issues
4. Send alerts

**Monitoring Schedule:**
- Repeats on defined schedule
- Initiated by event
- Initiated by human intervention
- Most ML models: simple scheduled approach (daily, weekly, monthly)

**Types of Drift:**

**1. Data Drift**
- Significant changes to data distribution
- Compared to data used untuk training
- Results dalam model performance degradation

**2. Concept Drift**
- Properties of target variables change
- Results dalam model performance degradation

**Detection dan Response:**
- Monitoring system detect drifts
- Initiate alert
- Send to alarm manager system
- Could automatically start re-training cycle

**Amazon SageMaker Model Monitor:**

**Features:**
- Monitor models dalam production
- Detect errors
- Take remedial actions
- Define monitoring schedule
- Collect data dari endpoints
- Detect changes against baseline
- Analyze data based on built-in rules atau custom rules

**Integration:**
- View results dalam Amazon SageMaker Studio
- See which rules violated
- Results sent ke Amazon CloudWatch
- Configure alarms untuk remedial actions
- Example: start re-training process

### MLOps: ML Operations

**What is MLOps?**
- Apply software engineering best practices ke ML development
- Automate manual tasks
- Test dan evaluate code sebelum release
- Respond automatically ke incidents

**Benefits:**

**1. Productivity**
- Automation
- Self-service environments dan infrastructure
- Data engineers dan scientists move forward faster

**2. Repeatability**
- Automate all steps dalam ML lifecycle
- Ensure repeatable process
- How model is trained, evaluated, versioned, deployed
- Improve reliability
- Deploy quickly dengan increased quality dan consistency

**3. Compliance**
- Improve auditability
- Version all inputs dan outputs
- Data science experiments ke source data ke trained models
- Demonstrate exactly how model was built
- Track where deployed

**4. Data dan Model Quality**
- Enforce policies against model bias
- Track changes ke data statistical properties
- Track model quality over time

**Infrastructure as Code:**
- Cloud uses API-based services
- Everything treated as software
- Infrastructure described dalam software
- Deploy dan redeploy dalam repeatable fashion
- Data scientists quickly spin up infrastructure
- Run experiments
- Make continual improvements

**Version Control:**
- Critical untuk tracking lineage
- Inspect past configuration
- Everything gets versioned including training data

**Key Principles:**
- Monitor deployments untuk detect issues
- Automate re-training
- Respond to data dan code changes

### MLOps Tools pada AWS

**1. Amazon SageMaker Pipelines**

**Features:**
- Orchestrate SageMaker jobs
- Author reproducible ML pipelines
- Deploy custom built models untuk inference
- Real time dengan low latency
- Run offline inferences dengan batch transform
- Track lineage of artifacts
- Sound operational practices
- Deploy dan monitor production workflows
- Track artifact lineage
- Simple interface

**Pipeline Creation:**
- Use SageMaker SDK untuk Python
- Define pipeline menggunakan JSON
- Contain all steps untuk build dan deploy model
- Include conditional branches based on previous step output
- View pipelines dalam SageMaker Studio

**Example:**
- Pipeline untuk model infer age of abalone based on size

**2. Repositories**

**SageMaker Feature Store:**
- Repository untuk feature definitions
- Training data features
- Version control

**SageMaker Model Registry:**
- Centralized repository untuk trained models
- Model history
- Version tracking

**3. Workflow Orchestration**

**AWS Step Functions:**
- Define workflow dengan visual drag-and-drop
- Build serverless workflows
- Integrate various AWS services
- Custom application logic

**Amazon Managed Workflows untuk Apache Airflow:**
- Open source tool
- Programmatically author, schedule, monitor workflows
- Use Apache Airflow dan Python
- Create workflows tanpa managing infrastructure
- Scalability, availability, security managed

### Model Evaluation Metrics

Evaluating model performance adalah critical step dalam ML development lifecycle. Kita perlu metrics yang objektif untuk measure seberapa baik model performs dan whether it meets business requirements. Mari kita explore berbagai metrics secara mendalam.

---

**Confusion Matrix: Foundation of Classification Metrics**

Confusion matrix adalah tool fundamental untuk summarize performance dari classification model ketika evaluated against test data. Ini adalah starting point untuk calculating hampir semua classification metrics.

**Konsep Dasar:**

Confusion matrix adalah table yang membandingkan actual values dengan predicted values. Simplest form adalah untuk binary classification (dua possible outcomes: yes/no, positive/negative, 1/0).

**Matrix Structure:**

```
                    Predicted
                 Negative  Positive
Actual Negative    TN        FP
       Positive    FN        TP
```

**Atau dalam format yang lebih visual:**

```
                      PREDICTED
                   Not Fish  |  Fish
              ________________|_________
ACTUAL  Not Fish |    TN     |   FP    |
              ________________|_________
        Fish     |    FN     |   TP    |
              ________________|_________
```

**Four Fundamental Outcomes:**

Mari kita gunakan contoh fish classification untuk memahami setiap outcome:

**1. True Positive (TP) - Correct Positive Prediction**

**Scenario:**
- **Actual:** Image IS a fish
- **Predicted:** Model says it IS a fish
- **Result:** ✅ CORRECT prediction

**Interpretation:**
- Model correctly identified positive case
- This is what we want untuk positive cases
- High TP count indicates good detection capability

**Real-world Impact:**
- Disease detection: Correctly identified sick patient
- Fraud detection: Correctly flagged fraudulent transaction
- Spam filter: Correctly identified spam email

**2. True Negative (TN) - Correct Negative Prediction**

**Scenario:**
- **Actual:** Image is NOT a fish
- **Predicted:** Model says it is NOT a fish
- **Result:** ✅ CORRECT prediction

**Interpretation:**
- Model correctly identified negative case
- This is what we want untuk negative cases
- High TN count indicates good specificity

**Real-world Impact:**
- Disease detection: Correctly identified healthy patient
- Fraud detection: Correctly approved legitimate transaction
- Spam filter: Correctly allowed legitimate email

**3. False Negative (FN) - Missed Positive (Type II Error)**

**Scenario:**
- **Actual:** Image IS a fish
- **Predicted:** Model says it is NOT a fish
- **Result:** ❌ INCORRECT prediction (MISS)

**Interpretation:**
- Model FAILED to detect positive case
- This is "missing" something important
- Also called "Type II Error" dalam statistics

**Real-world Impact:**
- Disease detection: Missed sick patient (very dangerous!)
- Fraud detection: Missed fraudulent transaction (financial loss)
- Spam filter: Missed spam email (user annoyance)

**Why This Matters:**
- Can have serious consequences
- In medical diagnosis, missing disease can be life-threatening
- In fraud detection, missing fraud means financial losses
- Cost of FN varies by application

**4. False Positive (FP) - False Alarm (Type I Error)**

**Scenario:**
- **Actual:** Image is NOT a fish
- **Predicted:** Model says it IS a fish
- **Result:** ❌ INCORRECT prediction (FALSE ALARM)

**Interpretation:**
- Model incorrectly identified negative case as positive
- This is "crying wolf" - false alarm
- Also called "Type I Error" dalam statistics

**Real-world Impact:**
- Disease detection: Told healthy patient they're sick (anxiety, unnecessary treatment)
- Fraud detection: Blocked legitimate transaction (customer frustration)
- Spam filter: Blocked legitimate email (missed important message)

**Why This Matters:**
- Can damage user trust
- Creates unnecessary work (investigating false alarms)
- May cause customer dissatisfaction
- Cost of FP varies by application

**Example Confusion Matrix:**

Mari kita buat concrete example dengan 100 labeled test images:

```
                      PREDICTED
                   Not Fish  |  Fish   | Total
              ________________|_________|_______
ACTUAL  Not Fish |    40     |   20    |  60
              ________________|_________|_______
        Fish     |    15     |   25    |  40
              ________________|_________|_______
        Total    |    55     |   45    | 100
```

**Interpretation:**
- **True Negatives (TN) = 40:** Correctly identified 40 non-fish images
- **False Positives (FP) = 20:** Incorrectly labeled 20 non-fish as fish
- **False Negatives (FN) = 15:** Missed 15 fish (labeled as non-fish)
- **True Positives (TP) = 25:** Correctly identified 25 fish

**Key Insights dari Matrix:**
- Model correctly classified 65 out of 100 images (40 TN + 25 TP)
- Model made 35 errors (20 FP + 15 FN)
- Model struggles more dengan non-fish (20 FP) than fish (15 FN)
- Need to improve specificity (reducing false positives)

**Understanding the Tradeoffs:**

Confusion matrix reveals fundamental tradeoff dalam classification:
- Increasing sensitivity (catching more positives) → More false positives
- Increasing specificity (reducing false alarms) → More false negatives
- Perfect balance is rare; must choose based on business needs

---

**Accuracy: Overall Correctness**

Accuracy adalah metric yang paling intuitive dan mudah dipahami, tetapi juga paling sering disalahgunakan.

**Formula:**
```
Accuracy = (TP + TN) / (TP + TN + FP + FN)
         = Correct Predictions / Total Predictions
```

**Menggunakan Example Kita:**
```
Accuracy = (25 + 40) / 100
         = 65 / 100
         = 0.65 atau 65%
```

**Interpretation:**
- Model correctly classified 65% of all images
- 35% of predictions were incorrect
- Values range dari 0 (completely wrong) to 1 (perfect)

**Characteristics:**

**Strengths:**
- ✅ Easy to understand dan explain
- ✅ Single number summary
- ✅ Intuitive interpretation
- ✅ Good untuk balanced datasets

**Critical Limitation - The Imbalanced Dataset Problem:**

Accuracy can be **highly misleading** untuk imbalanced datasets. Ini adalah pitfall yang sangat common!

**Example Scenario:**

Suppose kita memiliki dataset dengan 90 fish images dan 10 non-fish images (total 100).

**Naive Model Strategy:**
```
Model: "I'll just predict EVERYTHING is a fish!"
```

**Results:**
- Correctly predicted 90 fish (TP = 90)
- Incorrectly predicted 10 non-fish as fish (FP = 10)
- Accuracy = 90/100 = 90%

**Problem:**
- Model has 90% accuracy!
- But model is USELESS - it doesn't actually learn anything
- Just predicts majority class
- This is called "accuracy paradox"

**Real-World Examples:**

**1. Fraud Detection:**
- 99% of transactions are legitimate
- Model that predicts "all legitimate" gets 99% accuracy
- But completely fails at actual task (detecting fraud)!

**2. Disease Screening:**
- 95% of population is healthy
- Model that predicts "all healthy" gets 95% accuracy
- Misses ALL sick patients!

**3. Spam Detection:**
- 80% of emails are legitimate
- Model that predicts "all legitimate" gets 80% accuracy
- Lets all spam through!

**When to Use Accuracy:**

✅ **Use Accuracy When:**
- Dataset is balanced (roughly equal classes)
- All types of errors have similar cost
- Need simple metric untuk general audience
- Baseline comparison

❌ **Don't Use Accuracy When:**
- Dataset is imbalanced
- Different error types have different costs
- Need to optimize specific aspect (precision atau recall)
- Reporting to technical audience

---

**Precision: Quality of Positive Predictions**

Precision measures "ketika model predicts positive, seberapa sering model benar?"

**Formula:**
```
Precision = TP / (TP + FP)
          = True Positives / All Predicted Positives
```

**Menggunakan Example Kita:**
```
Precision = 25 / (25 + 20)
          = 25 / 45
          = 0.556 atau 55.6%
```

**Interpretation:**
- Dari 45 images yang model predicted sebagai "fish"
- Only 25 actually were fish
- 20 were false alarms (non-fish predicted as fish)
- Model is correct 55.6% of time ketika it says "fish"

**What Precision Tells Us:**

**High Precision (e.g., 95%):**
- Ketika model says "positive", it's almost always correct
- Very few false alarms
- High confidence dalam positive predictions
- But might miss many actual positives (low recall)

**Low Precision (e.g., 30%):**
- Many false alarms
- Positive predictions not trustworthy
- Lots of wasted effort investigating false positives
- But might catch most actual positives (high recall)

**When to Optimize for Precision:**

**Prioritize Precision When:**

**1. False Positives are Costly:**
- **Spam Filter:** Don't want to block legitimate emails
  - FP = Important email goes to spam (very bad!)
  - FN = Spam gets through (annoying but not critical)
  - **Solution:** High precision - only block when very confident

**2. Limited Resources untuk Follow-up:**
- **Medical Screening:** Limited doctors untuk follow-up
  - FP = Healthy person gets unnecessary tests (waste resources)
  - FN = Sick person missed (bad, but screening is first step)
  - **Solution:** High precision - only flag when confident

**3. User Trust is Critical:**
- **Product Recommendations:** Don't want to recommend irrelevant items
  - FP = Bad recommendation (user loses trust)
  - FN = Missed good recommendation (user doesn't know)
  - **Solution:** High precision - only recommend when confident

**4. Action on Positive is Expensive:**
- **Fraud Investigation:** Each investigation costs money
  - FP = Waste investigator time
  - FN = Fraud goes through (but might catch later)
  - **Solution:** High precision - investigate only strong signals

**Real-World Example:**

**Email Spam Filter:**
```
Scenario: 1000 emails, 100 are spam

Low Precision Model:
- Flags 300 emails as spam
- 100 actual spam (TP)
- 200 legitimate emails (FP) ← PROBLEM!
- Precision = 100/300 = 33%
- Result: Users miss important emails!

High Precision Model:
- Flags 80 emails as spam
- 75 actual spam (TP)
- 5 legitimate emails (FP) ← Much better!
- Precision = 75/80 = 94%
- Result: Users trust spam folder
```

---

**Recall (Sensitivity / True Positive Rate): Completeness of Detection**

Recall measures "dari semua actual positives, berapa banyak yang model successfully detect?"

**Formula:**
```
Recall = TP / (TP + FN)
       = True Positives / All Actual Positives
```

**Menggunakan Example Kita:**
```
Recall = 25 / (25 + 15)
       = 25 / 40
       = 0.625 atau 62.5%
```

**Interpretation:**
- Ada 40 actual fish images dalam test set
- Model successfully detected 25 of them
- Model missed 15 fish (false negatives)
- Model catches 62.5% of all fish

**What Recall Tells Us:**

**High Recall (e.g., 95%):**
- Model catches almost all positive cases
- Very few misses
- Comprehensive detection
- But might have many false alarms (low precision)

**Low Recall (e.g., 30%):**
- Model misses many positive cases
- Incomplete detection
- Many false negatives
- But predictions might be accurate (high precision)

**When to Optimize for Recall:**

**Prioritize Recall When:**

**1. False Negatives are Dangerous:**
- **Cancer Screening:** Cannot miss sick patients
  - FN = Sick patient told they're healthy (VERY DANGEROUS!)
  - FP = Healthy patient gets more tests (inconvenient but safe)
  - **Solution:** High recall - catch all potential cases

**2. Cost of Missing is High:**
- **Fraud Detection (High-Value):** Cannot miss large fraud
  - FN = Fraud goes undetected (major financial loss)
  - FP = Legitimate transaction flagged (minor inconvenience)
  - **Solution:** High recall - flag anything suspicious

**3. Follow-up Process Exists:**
- **Airport Security:** Cannot miss threats
  - FN = Threat gets through (catastrophic)
  - FP = Extra screening (acceptable delay)
  - **Solution:** High recall - screen anything questionable

**4. Finding All Instances is Goal:**
- **Legal Discovery:** Must find all relevant documents
  - FN = Miss relevant document (legal problems)
  - FP = Review irrelevant document (extra work but acceptable)
  - **Solution:** High recall - include anything potentially relevant

**Real-World Example:**

**Disease Screening:**
```
Scenario: 1000 patients, 50 have disease

Low Recall Model:
- Identifies 30 patients as potentially sick
- 25 actually have disease (TP)
- 25 patients missed (FN) ← DANGEROUS!
- Recall = 25/50 = 50%
- Result: Half of sick patients go untreated!

High Recall Model:
- Identifies 200 patients as potentially sick
- 48 actually have disease (TP)
- 2 patients missed (FN) ← Much better!
- Recall = 48/50 = 96%
- Result: Almost all sick patients get treatment
- (152 false positives get additional tests, but that's acceptable)
```

---

**The Precision-Recall Tradeoff: Fundamental Tension**

Ini adalah salah satu konsep paling penting dalam machine learning: **you cannot optimize both precision and recall simultaneously**. Ada inherent tradeoff.

**Why the Tradeoff Exists:**

**To Increase Recall (catch more positives):**
- Lower threshold untuk positive prediction
- Be more "generous" dengan positive predictions
- Cast wider net
- **Result:** Catch more true positives BUT also more false positives
- **Effect:** Recall ↑, Precision ↓

**To Increase Precision (reduce false alarms):**
- Raise threshold untuk positive prediction
- Be more "strict" dengan positive predictions
- Only predict positive when very confident
- **Result:** Fewer false positives BUT also miss more true positives
- **Effect:** Precision ↑, Recall ↓

**Visual Representation:**

```
Threshold Low (Liberal)          Threshold High (Conservative)
├─────────────────────────────────────────────────────────┤
High Recall                                      High Precision
Low Precision                                    Low Recall
Many False Positives                             Many False Negatives
```

**Concrete Example - Medical Diagnosis:**

**Scenario:** Diagnosing disease based on test score (0-100)

**Approach 1: Low Threshold (Score > 30)**
```
Result: Diagnose many people as sick
- Catch almost all sick patients (High Recall: 95%)
- But many healthy people diagnosed as sick (Low Precision: 40%)
- 60% of positive diagnoses are false alarms
```

**Approach 2: High Threshold (Score > 80)**
```
Result: Diagnose only very clear cases
- Very few false alarms (High Precision: 95%)
- But miss many sick patients (Low Recall: 40%)
- 60% of sick patients told they're healthy
```

**Approach 3: Balanced Threshold (Score > 55)**
```
Result: Middle ground
- Moderate recall (75%)
- Moderate precision (70%)
- Balanced tradeoff
```

**Which to Choose?**

**Decision Framework:**

| Scenario | Optimize For | Reasoning |
|----------|-------------|-----------|
| Cancer Screening | **Recall** | Cannot miss sick patients; follow-up tests available |
| Spam Filter | **Precision** | Cannot block important emails; spam is just annoying |
| Fraud Detection (High-Value) | **Recall** | Cannot miss large fraud; investigation cost acceptable |
| Product Recommendations | **Precision** | Bad recommendations hurt trust; missed recommendations invisible |
| Airport Security | **Recall** | Cannot miss threats; extra screening acceptable |
| Credit Card Approval | **Balanced** | Both false approvals and false rejections costly |

**Key Insight:**

The choice between precision dan recall depends on:
1. **Relative cost** of false positives vs false negatives
2. **Business context** dan consequences
3. **Available resources** untuk handling errors
4. **User expectations** dan trust factors

Tidak ada "correct" answer - it's always business decision, bukan purely technical decision.

---

**F1 Score: Harmonic Mean of Precision and Recall**

Ketika both precision AND recall are important, kita need single metric yang balances keduanya. F1 Score adalah solution.

**Formula:**
```
F1 Score = 2 × (Precision × Recall) / (Precision + Recall)
```

**Why Harmonic Mean?**

F1 uses harmonic mean (bukan arithmetic mean) karena:
- Harmonic mean penalizes extreme values
- If either precision OR recall is low, F1 will be low
- Cannot "cheat" dengan high precision but low recall (atau vice versa)
- Forces balance between both metrics

**Comparison:**

```
Scenario 1: Balanced Model
Precision = 0.80, Recall = 0.80
Arithmetic Mean = (0.80 + 0.80) / 2 = 0.80
F1 Score = 2 × (0.80 × 0.80) / (0.80 + 0.80) = 0.80
Result: Same value ✓

Scenario 2: Imbalanced Model
Precision = 0.90, Recall = 0.10
Arithmetic Mean = (0.90 + 0.10) / 2 = 0.50 (misleading!)
F1 Score = 2 × (0.90 × 0.10) / (0.90 + 0.10) = 0.18 (reflects poor recall!)
Result: F1 penalizes imbalance ✓
```

**Menggunakan Example Kita:**

```
Precision = 0.556 (55.6%)
Recall = 0.625 (62.5%)

F1 = 2 × (0.556 × 0.625) / (0.556 + 0.625)
   = 2 × 0.3475 / 1.181
   = 0.695 / 1.181
   = 0.588 atau 58.8%
```

**Interpretation:**

Our fish model has:
- **Recall (62.5%) > Precision (55.6%)**
- Model is better at detecting true positives (catching fish)
- But has more false positives (non-fish labeled as fish)
- F1 Score (58.8%) reflects this imbalance
- Model will catch most fish but with some false alarms

**When to Use F1 Score:**

✅ **Use F1 Score When:**
- Both precision AND recall are important
- Need single metric untuk model comparison
- Dataset is imbalanced
- Want balanced performance
- Reporting to stakeholders

**Real-World Applications:**

**1. Information Retrieval:**
- Search engines need both precision (relevant results) and recall (find all relevant)
- F1 balances finding everything vs showing only relevant

**2. Medical Diagnosis (Moderate Risk):**
- Need to catch diseases (recall) but avoid unnecessary treatment (precision)
- F1 helps find optimal balance

**3. Customer Churn Prediction:**
- Want to identify churners (recall) without annoying loyal customers (precision)
- F1 optimizes retention efforts

**Limitations:**

- Assumes precision dan recall are equally important (not always true)
- Doesn't consider true negatives
- May not reflect business priorities
- Consider using weighted F1 if one metric more important

**Variants:**

**F-Beta Score:**
```
F-Beta = (1 + β²) × (Precision × Recall) / (β² × Precision + Recall)
```

- **β < 1:** Emphasizes precision
- **β = 1:** F1 Score (balanced)
- **β > 1:** Emphasizes recall

**Example:**
- F2 Score: Weighs recall 2× more than precision
- F0.5 Score: Weighs precision 2× more than recall

---

**False Positive Rate (FPR): Rate of False Alarms**

FPR measures "dari semua actual negatives, berapa banyak yang incorrectly predicted as positive?"

**Formula:**
```
FPR = FP / (FP + TN)
    = False Positives / All Actual Negatives
```

**Menggunakan Example Kita:**

```
FPR = 20 / (20 + 40)
    = 20 / 60
    = 0.333 atau 33.3%
```

**Interpretation:**
- Ada 60 actual non-fish images
- Model incorrectly labeled 20 of them as fish
- 33.3% false alarm rate untuk non-fish images
- Model struggles dengan specificity

**What FPR Tells Us:**

**Low FPR (e.g., 5%):**
- Very few false alarms
- Model is specific (good at identifying negatives)
- High confidence dalam negative predictions
- Good specificity

**High FPR (e.g., 40%):**
- Many false alarms
- Model lacks specificity
- Incorrectly flags many negatives as positive
- Poor at identifying true negatives

**Relationship dengan Other Metrics:**

```
FPR + TNR = 1
(False Positive Rate + True Negative Rate = 100%)
```

If FPR = 0.333, then TNR = 0.667

---

**True Negative Rate (TNR / Specificity): Correct Negative Identification**

TNR measures "dari semua actual negatives, berapa banyak yang correctly identified?"

**Formula:**
```
TNR = TN / (TN + FP)
    = True Negatives / All Actual Negatives
    = 1 - FPR
```

**Menggunakan Example Kita:**

```
TNR = 40 / (40 + 20)
    = 40 / 60
    = 0.667 atau 66.7%
```

**Interpretation:**
- Model correctly identified 66.7% of non-fish images
- This is model's specificity
- Complement of false positive rate

**Sensitivity vs Specificity:**

| Metric | Formula | Measures | Also Known As |
|--------|---------|----------|---------------|
| **Sensitivity** | TP/(TP+FN) | Ability to detect positives | Recall, TPR |
| **Specificity** | TN/(TN+FP) | Ability to detect negatives | TNR |

**Both are important untuk complete picture of model performance!**

---

**Area Under the ROC Curve (AUC-ROC): Comprehensive Performance Metric**

AUC-ROC adalah one of most important metrics untuk evaluating binary classification models, especially ketika comparing different models atau algorithms.

**What is ROC Curve?**

**ROC = Receiver Operating Characteristic**

ROC curve adalah plot yang shows tradeoff between:
- **True Positive Rate (TPR / Recall)** on Y-axis
- **False Positive Rate (FPR)** on X-axis

...across all possible classification thresholds.

**Understanding Thresholds:**

Most classification models don't directly output "yes" atau "no". Instead, they output **probability** (0 to 1).

**Example:**
```
Model Output: 0.73 (73% confident this is fish)
Question: Is this fish atau not fish?
Answer: Depends on threshold!
```

**Threshold Decision:**
- If threshold = 0.5: 0.73 > 0.5 → Classify as FISH
- If threshold = 0.8: 0.73 < 0.8 → Classify as NOT FISH

**How Threshold Affects Performance:**

**Low Threshold (e.g., 0.3):**
```
Effect: Classify as positive if probability > 0.3
Result:
- More predictions as positive
- Higher TPR (catch more positives) ✓
- Higher FPR (more false alarms) ✗
- High Recall, Low Precision
```

**High Threshold (e.g., 0.8):**
```
Effect: Classify as positive only if probability > 0.8
Result:
- Fewer predictions as positive
- Lower TPR (miss more positives) ✗
- Lower FPR (fewer false alarms) ✓
- Low Recall, High Precision
```

**ROC Curve Construction:**

1. Calculate TPR dan FPR untuk many different thresholds
2. Plot TPR (y-axis) vs FPR (x-axis)
3. Connect points to form curve

**Example Points:**

| Threshold | TPR (Recall) | FPR | Point on Graph |
|-----------|--------------|-----|----------------|
| 0.9 | 0.20 | 0.02 | (0.02, 0.20) |
| 0.7 | 0.60 | 0.15 | (0.15, 0.60) |
| 0.5 | 0.80 | 0.30 | (0.30, 0.80) |
| 0.3 | 0.95 | 0.60 | (0.60, 0.95) |

**Visual Representation:**

```
TPR
1.0 |     ___----****
    |   _/
0.8 |  /
    | /
0.6 |/
    |
0.4 |
    |
0.2 |
    |
0.0 |________________
    0   0.2  0.4  0.6  0.8  1.0  FPR
```

**Interpreting ROC Curve:**

**Perfect Classifier:**
```
- Goes straight up (TPR=1) then straight right
- Catches all positives with no false positives
- AUC = 1.0
```

**Random Classifier:**
```
- Diagonal line from (0,0) to (1,1)
- No better than guessing
- AUC = 0.5
```

**Good Classifier:**
```
- Curve bows toward top-left corner
- High TPR with low FPR
- AUC between 0.5 and 1.0
```

**AUC Score Interpretation:**

**Area Under Curve (AUC):**
- Aggregated measure of performance across ALL thresholds
- Single number summary
- Values between 0 dan 1

**AUC Value Meanings:**

| AUC Score | Interpretation | Model Quality |
|-----------|----------------|---------------|
| **1.0** | Perfect classification | Perfect |
| **0.9 - 1.0** | Excellent discrimination | Excellent |
| **0.8 - 0.9** | Good discrimination | Good |
| **0.7 - 0.8** | Acceptable discrimination | Fair |
| **0.6 - 0.7** | Poor discrimination | Poor |
| **0.5 - 0.6** | Very poor discrimination | Fail |
| **0.5** | No discrimination (random) | Useless |
| **< 0.5** | Worse than random | Inverted |

**Probabilistic Interpretation:**

AUC = Probability bahwa model ranks random positive example higher than random negative example.

**Example:**
- AUC = 0.85
- Meaning: 85% chance model will rank random positive higher than random negative
- Good discrimination ability

**Why AUC is Valuable:**

**Advantages:**

1. **Threshold-Independent:**
   - Evaluates model across all thresholds
   - Don't need to choose threshold first
   - Comprehensive view of performance

2. **Scale-Invariant:**
   - Measures how well predictions are ranked
   - Not affected by absolute probability values
   - Focuses on relative ordering

3. **Classification-Threshold-Invariant:**
   - Useful when threshold will be tuned later
   - Compares models independently of threshold choice

4. **Handles Imbalanced Data:**
   - Better than accuracy untuk imbalanced datasets
   - Considers both TPR dan FPR

**When to Use AUC:**

✅ **Use AUC When:**
- Comparing multiple models
- Don't know optimal threshold yet
- Dataset is imbalanced
- Care about ranking quality
- Need threshold-independent metric

❌ **Don't Use AUC When:**
- Specific threshold is required
- Only care about performance at one threshold
- Need to optimize specific metric (precision atau recall)
- Interpretability is critical

**Limitations:**

1. **Doesn't reflect specific threshold performance**
2. **May be misleading untuk highly imbalanced data**
3. **Doesn't show precision-recall tradeoff**
4. **Treats all misclassification costs equally**

**Alternative: Precision-Recall AUC:**

Untuk highly imbalanced datasets, consider:
- **PR Curve:** Precision vs Recall
- **PR-AUC:** Area under PR curve
- Often more informative than ROC-AUC untuk imbalanced data

**Summary:**

AUC-ROC adalah powerful metric yang provides comprehensive view of binary classifier performance across all possible thresholds. It's particularly useful untuk model comparison dan when optimal threshold hasn't been determined yet.

**Regression Metrics:**

**Mean Squared Error (MSE):**

**Formula:**
```
MSE = Average of (Prediction - Actual)²
```

**Characteristics:**
- Distance between line dan actual values
- Always positive values
- Smaller MSE = better model
- Units are squared (inches → square inches)

**Root Mean Squared Error (RMSE):**

**Formula:**
```
RMSE = √MSE
```

**Advantage:**
- Units match dependent variable
- Easier to interpret
- Example: height dalam inches → RMSE dalam inches

**Limitation:**
- Errors are squared
- Emphasize impact of outliers
- Good jika incorrect predictions very costly

**Mean Absolute Error (MAE):**

**Formula:**
```
MAE = Average of |Prediction - Actual|
```

**Advantage:**
- Averages absolute values of errors
- Doesn't emphasize large errors
- Better jika don't want to emphasize outliers

### Business Metrics

**Importance:**
- ML solutions rooted dalam solving business problems
- First step: define business goal
- Determine how to measure success

**Types of Business Metrics:**
1. Cost reduction
2. Percentage increase dalam users atau sales
3. Measurable improvement dalam customer feedback
4. Any measurable metric important to business

**Risk Assessment:**
- Estimate risks of using AI dan ML
- Potential costs dari errors
- Example: loss of sales atau customers

**Post-Production Evaluation:**
- Collect data untuk support metrics
- Compare actual results dengan original goals
- Compare actual cost dengan initial cost benefit model
- Calculate return on investment (ROI)

**AWS Cost Tracking:**

**Cost Allocation Tags:**
- Define tags untuk resources
- Example: tag name = ML project, value = project name
- Add tag ke all resources dalam pipeline
- Filter cost reports dalam AWS Cost Explorer
- Determine actual AWS charges untuk project

### Kesimpulan

Task Statement 1.3 mencakup complete ML development lifecycle:

**Key Phases:**
1. Define business goal dengan clear success criteria
2. Collect dan prepare high-quality training data
3. Train, tune, evaluate model dengan experiments
4. Deploy model dengan appropriate inference option
5. Monitor model untuk detect drift dan maintain performance

**AWS Services:**
- Data: AWS Glue, DataBrew, SageMaker Ground Truth, Feature Store
- Training: SageMaker Training, Experiments, Automatic Model Tuning
- Deployment: SageMaker Hosting dengan multiple inference options
- Monitoring: SageMaker Model Monitor dengan CloudWatch integration
- MLOps: SageMaker Pipelines, Step Functions, Managed Airflow

**Evaluation:**
- Classification metrics: Accuracy, Precision, Recall, F1, AUC
- Regression metrics: MSE, RMSE, MAE
- Business metrics: ROI, cost reduction, customer satisfaction

**Best Practices:**
- Start dengan simplest solution
- Use pre-trained models when possible
- Automate dengan MLOps
- Version everything
- Monitor continuously
- Measure business value

Pemahaman mendalam tentang ML lifecycle essential untuk successfully implement dan maintain ML solutions pada AWS.
