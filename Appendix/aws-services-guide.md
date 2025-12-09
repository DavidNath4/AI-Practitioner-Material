<!--
Filename suggestion: AIF-C01-services-by-domain.md
Source: AWS Certified AI Practitioner (AIF-C01) Exam Guide v1.4
-->

# AWS Certified AI Practitioner (AIF-C01) — AWS Services by Domain + Exam Cues

> Catatan: Ini **hanya** layanan/fitur AWS yang **eksplisit disebut** di task statement Domain 1–5 pada Exam Guide.  
> Exam juga punya **Appendix "In-scope AWS services and features"** (non-exhaustive) di bagian bawah file ini.

---

## Domain 1 — Fundamentals of AI and ML (services yang disebut)

### 1) Amazon SageMaker
**Kapan kepake di soal (cues):**
- "build / train / deploy ML model", "managed ML platform", "endpoint hosting", "pipeline ML"
- "MLOps", "eksperimen", "monitoring model" (sering nyambung ke Model Monitor)

### 2) Amazon Transcribe
**Cues:**
- "speech-to-text", "ubah audio jadi teks", "transkrip call center/meeting", "subtitle"

### 3) Amazon Translate
**Cues:**
- "machine translation", "terjemahkan antar bahasa", "multilingual translation"

### 4) Amazon Comprehend
**Cues:**
- NLP klasik: "sentiment analysis", "entity extraction", "key phrases", "topic detection", "text classification"

### 5) Amazon Lex
**Cues:**
- "chatbot / conversational interface", "intent", "slot filling", "bot untuk customer service"

### 6) Amazon Polly
**Cues:**
- "text-to-speech", "voice output", "ubah teks jadi suara", "IVR/voice assistant output"

### 7) Amazon SageMaker Data Wrangler
**Cues:**
- "data prep / cleaning", "feature engineering", "ETL untuk ML", "preprocessing dataset"

### 8) Amazon SageMaker Feature Store
**Cues:**
- "central feature repository", "reuse features", "online/offline feature store", "konsistensi feature training vs inference"

### 9) Amazon SageMaker Model Monitor
**Cues:**
- "data drift / concept drift", "model quality monitoring", "monitoring setelah deploy", "alert saat distribusi data berubah"

---

## Domain 2 — Fundamentals of Generative AI (services yang disebut)

### 1) Amazon SageMaker JumpStart
**Cues:**
- "pre-built models/solutions", "quickly deploy a model", "starter templates", "jumpstart model catalog"

### 2) Amazon Bedrock
**Cues:**
- "foundation models", "genAI managed service", "akses FM via API", "build genAI apps without managing infra/model hosting"

### 3) PartyRock (Amazon Bedrock Playground)
**Cues:**
- "no-code/low-code genAI app prototyping", "playground", "build and share simple genAI apps cepat"

### 4) Amazon Q
**Cues:**
- "AI assistant" untuk pekerjaan/dev/business, "chat assistant", "productivity assistant", "tanya-jawab berbasis konteks kerja"

---

## Domain 3 — Applications of Foundation Models (services yang disebut)

### 1) Amazon Bedrock (knowledge base / RAG)
**Cues:**
- "RAG", "ground responses on private data", "knowledge base", "augment model with your documents" (tanpa full training)

### 2) Agents for Amazon Bedrock
**Cues:**
- "agent", "multi-step task", "tool use/function calling", "orchestrate steps", "plan + act"

### 3) Amazon OpenSearch Service (vector/embeddings store)
**Cues:**
- "vector search", "semantic search", "kNN", "store embeddings", "retrieval layer untuk RAG"

### 4) Amazon Aurora (dipakai sebagai penyimpanan embeddings/vector use case di guide)
**Cues:**
- "relational database + (vector/embedding) storage", "RAG storage option in DB", "Aurora as backend store"

### 5) Amazon Neptune
**Cues:**
- "graph", "relationships", "knowledge graph", atau disebut sebagai opsi penyimpanan embeddings di guide

### 6) Amazon DocumentDB (with MongoDB compatibility)
**Cues:**
- "document database", "MongoDB-compatible", atau disebut sebagai opsi penyimpanan embeddings di guide

### 7) Amazon RDS for PostgreSQL
**Cues:**
- "PostgreSQL", "RDS Postgres", "store embeddings in Postgres (vector extension use cases)", "RAG storage option in DB"

---

## Domain 4 — Guidelines for Responsible AI (services yang disebut)

### 1) Guardrails for Amazon Bedrock
**Cues:**
- "safety", "content policy", "filter harmful content", "guardrails", "reduce hallucination risk via constraints"

### 2) Amazon SageMaker Clarify
**Cues:**
- "bias detection", "fairness metrics", "explainability", "feature attribution / explanations"

### 3) SageMaker Model Monitor
**Cues:**
- "monitor bias/trustworthiness over time", "drift monitoring" (di konteks responsible AI)

### 4) Amazon Augmented AI (Amazon A2I)
**Cues:**
- "human-in-the-loop review", "human audit", "manual review workflow", "send low-confidence predictions to humans"

### 5) Amazon SageMaker Model Cards
**Cues:**
- "model documentation", "transparency", "document model purpose/risks/metrics", "data lineage/citation context"

---

## Domain 5 — Security, Compliance, and Governance for AI Solutions (services yang disebut)

### 1) AWS Artifact
**Cues:**
- "download compliance reports", "SOC/ISO/PCI reports", "ISV compliance report", "agreement", "on-demand access", "email notification untuk update compliance docs"

### 2) AWS Audit Manager
**Cues:**
- "collect audit evidence", "otomatisasi pengumpulan evidence", "prepare for audit", "continuous audit", "framework mapping", "audit readiness"

### 3) AWS Config
**Cues:**
- "configuration compliance", "resource auditing", "track changes", "configuration drift", "resource compliance", "rules/recording", "evaluasi compliance rule"

### 4) AWS CloudTrail
**Cues:**
- "API activity logging", "who did what/when", "audit trail", "governance logging", "investigasi aktivitas", "API call tracking"

### 5) Amazon Inspector
**Cues:**
- "vulnerability management", "scan for CVEs", "security findings", "hardening workloads", "vulnerability scanning", "assessment celah keamanan"

### 6) AWS Trusted Advisor
**Cues:**
- "best-practice checks", "security/cost/limits", "recommendations to improve posture", "rekomendasi best practices"

### 7) AWS Identity and Access Management (IAM)
**Cues:**
- "least privilege", "roles/policies/permissions", "who can access model/data", "access control", "kontrol akses"

### 8) Amazon Macie
**Cues:**
- "discover sensitive data", "PII detection", "PII discovery", "data classification (biasanya S3)", "privacy risk scanning", "S3 sensitive data"

### 9) AWS Key Management Service (KMS)
**Cues:**
- "encryption at rest", "key management", "KMS keys", "manajemen key untuk enkripsi", "customer managed keys"

### 10) AWS Secrets Manager
**Cues:**
- "secret rotation", "DB credentials", "API keys", "simpan dan rotasi secrets", "automated rotation"

### 11) AWS PrivateLink
**Cues:**
- "private connectivity", "avoid public internet", "VPC endpoint to service", "data exfiltration risk reduction", "VPC endpoint", "no public internet", "akses private ke service"

### 12) Amazon CloudWatch
**Cues:**
- "monitoring", "metrics", "alarms", "operational visibility", "log monitoring", "performance tracking"

### 13) AWS Well-Architected Tool
**Cues:**
- "well-architected review", "pillar checks", "best practices review", "security pillar", "framework assessment"

### 14) Amazon S3 / S3 Glacier
**Cues:**
- "log retention", "archive", "data lifecycle", "long-term storage", "compliance storage", "immutable storage (Object Lock)"

### 15) (Konsep yang sering jadi jawaban) Encryption + Shared Responsibility Model
**Cues:**
- "encryption at rest/in transit", "who is responsible for what on AWS", "security responsibilities split"

---

# Appendix (Exam Guide) — In-scope AWS services & features (non-exhaustive)

## Analytics
- AWS Data Exchange
- Amazon EMR
- AWS Glue
- AWS Glue DataBrew
- AWS Lake Formation
- Amazon OpenSearch Service
- Amazon QuickSight
- Amazon Redshift

## Cloud Financial Management
- AWS Budgets
- AWS Cost Explorer

## Compute
- Amazon EC2

## Containers
- Amazon ECS
- Amazon EKS

## Database
- Amazon DocumentDB (with MongoDB compatibility)
- Amazon DynamoDB
- Amazon ElastiCache
- Amazon MemoryDB
- Amazon Neptune
- Amazon RDS

## Machine Learning
- Amazon A2I
- Amazon Bedrock
- Amazon Comprehend
- Amazon Fraud Detector
- Amazon Kendra
- Amazon Lex
- Amazon Personalize
- Amazon Polly
- Amazon Q
- Amazon Rekognition
- Amazon SageMaker
- Amazon Textract
- Amazon Transcribe
- Amazon Translate

## Management and Governance
- AWS CloudTrail
- Amazon CloudWatch
- AWS Config
- AWS Trusted Advisor
- AWS Well-Architected Tool

## Networking and Content Delivery
- Amazon CloudFront
- Amazon VPC

## Security, Identity, and Compliance
- AWS Artifact
- AWS Audit Manager
- AWS IAM
- Amazon Inspector
- AWS KMS
- Amazon Macie
- AWS Secrets Manager

## Storage
- Amazon S3
- Amazon S3 Glacier
