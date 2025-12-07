# Domain 1: ML Development Lifecycle

## Task Statement 1.3: Menjelaskan ML Development Lifecycle

### Pengenalan ML Pipeline

Machine Learning Pipeline adalah series of interconnected steps yang dimulai dengan business goal dan berakhir dengan operating deployed ML model.

**Tahapan ML Pipeline:**
1. Define the problem
2. Collect dan prepare training data
3. Train the model
4. Deploy the model
5. Monitor the model

**Karakteristik ML Pipeline:**
- Beberapa steps adalah iterative process
- Repeated hingga objectives tercapai
- ML models adalah dynamic by design
- Re-trained dengan new data
- Continually evaluated terhadap performance dan business metrics
- Monitoring untuk drifts dan bias
- Adjusted atau rebuilt as needed

**ML Lifecycle Concept:**
- Lebih tepat disebut lifecycle daripada pipeline
- Parts atau bahkan all of it repeated setelah model deployed
- Continuous improvement process

### Phase 1: Define the Business Goal

**Langkah Awal:**
1. Identify business goal dengan clear
2. Understand problem yang akan diselesaikan
3. Measure business value terhadap specific objectives
4. Define success criteria

**Pentingnya Success Criteria:**
- Tanpa clear success criteria, tidak bisa evaluate model
- Tidak bisa determine apakah ML adalah best solution
- Need to align stakeholders untuk gain consensus

**Evaluasi Kelayakan:**
- Evaluate organization's ability untuk move toward target
- Target harus achievable
- Provide clear path to production
- Determine apakah ML adalah appropriate approach

**Pertimbangan Penting:**
- Evaluate all available options untuk achieving goal
- Determine accuracy dari resulting outcomes
- Consider cost dan scalability dari each approach
- Ensure enough relevant high-quality training data available
- Data sources harus available dan accessible

**Formulate ML Question:**
- Define dalam terms of input
- Define desired outputs
- Define performance metric yang akan dioptimized

**Investigate Options:**
- Start dengan simplest solution
- Determine apakah more complexity required
- Perform cost-benefit analysis
- Decide apakah project should move to next phase

### Opsi Solusi ML

**1. AWS AI Services (Simplest)**
- Democratize ML dan make it accessible to anyone
- Identify common use cases
- Fully trained ML models
- Fully hosted oleh AWS
- Pay as you go
- Evaluate untuk see if dapat meet business goals
- Many services allow customization

**Contoh Customization:**
- Amazon Comprehend: create custom classifier dengan own categories
- Supply training data untuk customize

**2. Start dengan Existing Model (Medium)**
- Jika hosted service tidak achieve objectives
- Build own model dengan starting dari existing one

**Generative AI:**
- Amazon Bedrock: start dengan fully trained foundation model
- Fine-tune model dengan own data
- Use transfer learning

**Other Use Cases:**
- Amazon SageMaker: open source pre-trained models
- SageMaker JumpStart untuk jumpstart development

**3. Train dari Scratch (Most Difficult)**
- Most technically challenging
- Requires most responsibility untuk security dan compliance
- Most costly approach
- Longest development time

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

**Confusion Matrix:**

**Purpose:**
- Summarize performance dari classification model
- Evaluated against test data
- Binary classification: yes/no, positive/negative

**Matrix Structure:**
- Actual data across top
- Predicted values on left

**Four Outcomes (Fish Example):**

1. **True Positive (TP)**
   - Model sees fish
   - Predicts fish
   - Correct prediction

2. **True Negative (TN)**
   - Model sees not fish
   - Predicts not fish
   - Correct prediction

3. **False Negative (FN)**
   - Model sees fish
   - Predicts not fish
   - Incorrect prediction

4. **False Positive (FP)**
   - Model sees not fish
   - Predicts fish
   - Incorrect prediction

**Example:**
- 100 labeled test images
- Matrix shows number of TP, TN, FP, FN

**Accuracy:**

**Formula:**
```
Accuracy = (TP + TN) / Total Predictions
```

**Characteristics:**
- Percentage of correct predictions
- Values between 0 dan 1
- 1 = perfect accuracy
- 0 = complete inaccuracy

**Example:**
- (25 + 40) / 100 = 0.65 atau 65%

**Limitation:**
- Not good metric untuk imbalanced datasets
- Example: 90 dari 100 images adalah fish
- Model predict all fish = 90% accuracy (misleading)

**Precision:**

**Formula:**
```
Precision = TP / (TP + FP)
```

**Purpose:**
- Measure how well algorithm predicts true positives
- Out of all positives identified
- Good untuk minimize false positives
- Example: don't label legitimate email as spam

**Example:**
- Fish model precision = 0.55 atau 55%

**Recall (Sensitivity/True Positive Rate):**

**Formula:**
```
Recall = TP / (TP + FN)
```

**Purpose:**
- Minimize false negatives
- Example: don't miss disease diagnosis
- Make sure detect everyone who has disease

**Example:**
- Fish model recall = 0.625

**Tradeoff:**
- Can't optimize untuk both precision dan recall
- Example: diagnose everyone dengan disease (high recall)
- Increase likelihood diagnose people tanpa disease (low precision)

**F1 Score:**

**Purpose:**
- Balance precision dan recall
- Combine dalam single metric
- Use when both precision dan recall important

**Interpretation:**
- Fish model: better recall than precision
- Better at detecting true positives
- Will have some false negatives
- F1 score adalah best compromise

**False Positive Rate:**

**Formula:**
```
FPR = FP / (FP + TN)
```

**Purpose:**
- Measure how model handles non-fish images
- How many predictions were fish out of non-fish images

**True Negative Rate:**

**Formula:**
```
TNR = TN / (FP + TN)
```

**Purpose:**
- Ratio of true negatives
- How many predictions were not fish out of non-fish images

**Area Under Curve (AUC):**

**Purpose:**
- Compare dan evaluate binary classification
- Algorithms yang return probabilities (logistic regression)

**Threshold:**
- Value model uses untuk make decision
- Convert probability into binary decision
- Example: threshold 0.6 = 60% confident → classify as fish

**ROC Curve:**
- Receiver Operating Characteristic curve
- True positive rate vs false positive rate
- For increasing threshold values
- Increasing threshold = fewer false positives, more false negatives

**AUC Score:**
- Area under ROC curve
- Aggregated measure of model performance
- Across full range of thresholds
- Values between 0 dan 1
- 1 = perfect accuracy
- 0.5 = no better than random classifier

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
