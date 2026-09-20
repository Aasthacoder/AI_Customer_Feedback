# AI Customer Feedback → Product Roadmap

## Project Objective

Build a Product Management workflow that turns real-world customer complaints into evidence-backed product opportunities and a prioritized product recommendation.

This project uses the **Consumer Financial Protection Bureau (CFPB) Consumer Complaint Database** as a real-world source of customer feedback.

The project explores the following question:

> What recurring customer problems can be identified from customer complaints, and how can AI help turn these findings into product decisions?

---

## PM Scenario

The scenario is that I am working as a Product Manager / Product Insights Analyst at a consumer-finance company.

I have access to thousands of publicly available customer complaints and need to:

- understand what customers are complaining about,
- identify recurring customer problems,
- use AI to discover additional patterns in unstructured feedback,
- validate the identified patterns,
- prioritize a customer problem,
- and translate the selected problem into a product opportunity and MVP.

---

## Data Source

The project uses the **CFPB Consumer Complaint Database**.

The dataset contains information such as:

- Product
- Issue
- Sub-issue
- Customer complaint narrative
- Company
- State
- Submission method
- Company response
- Dates and other complaint metadata

### Important Data Limitation

The CFPB complaint database is a public source of consumer complaints and should not be treated as a statistical sample of all consumers.

Therefore, the analysis uses the dataset as an **evidence source for identifying recurring customer problems**, rather than as proof of total market demand.

---

## Project Workflow

### Phase 1 — Data Discovery

The first phase focuses on understanding the dataset and the language customers use in their complaints.

Key activities include:

- Data acquisition through the CFPB API
- Dataset structure and data-quality checks
- Complaint and sub-issue exploration
- Company and submission-channel analysis
- Time coverage analysis
- Customer narrative analysis
- Narrative-length analysis
- Basic customer language analysis
- Common phrase analysis
- Language analysis across complaint categories
- Exploration of problems within major issue categories
- TF-IDF text-similarity baseline

---

### Phase 2 — AI-Assisted Customer Feedback Analysis

The second phase uses AI/NLP techniques to identify semantic patterns in customer complaints.

The analysis includes:

- Complaint embeddings
- Semantic similarity
- Comparison of similar complaints with existing issue categories
- Customer complaint clustering
- Cluster inspection
- Distinctive cluster language
- Candidate theme identification
- Candidate theme validation
- Theme quantification
- Theme refinement
- Candidate customer problems
- Problem validation

The purpose of AI is to assist the analysis of large amounts of unstructured customer feedback and identify patterns that can support product decision-making.

---

### Phase 3 — Product Management

The final phase converts the validated customer problems into a product recommendation.

The analysis includes:

- Problem prioritization
- Selected customer problem
- Root-cause hypothesis
- Product opportunity
- Solution direction
- MVP definition
- Success metrics
- Experiment and validation plan
- Rollout plan
- Product roadmap
- Final product hypothesis
- Conclusion

---

## Selected Product Opportunity

The analysis selected **purchase-dispute resolution** as the primary product opportunity.

The proposed MVP is a **Dispute Tracker** that helps customers understand:

- the current status of their dispute,
- whether additional information is required,
- what happens next,
- and the final outcome of the dispute.

The product hypothesis is that improving visibility and guidance during dispute resolution can reduce unnecessary repeated contact while maintaining appropriate dispute outcomes.

---

## AI Approach

The AI-assisted analysis follows a simple progression:

**Customer complaints**

→ **Embeddings**

→ **Semantic similarity**

→ **Clustering**

→ **Theme discovery**

→ **Theme validation**

→ **Candidate customer problems**

→ **Problem validation**

The project focuses on using AI as an analytical aid rather than building a complex production machine-learning system.

---

## Tools & Technologies

- Python
- pandas
- Jupyter Notebook
- scikit-learn
- TF-IDF
- Sentence embeddings
- NLP / text analysis
- Clustering
- matplotlib
- SQL concepts for analytical thinking

The project intentionally uses simple and explainable techniques so that the complete workflow can be understood and communicated clearly.

---

## Project Structure

```text
project/
│
├── notebooks/
│   ├── 01_Data_Discovery.ipynb
│   ├── 02_AI_Feedback_Analysis.ipynb
│   └── 03_Product_Management.ipynb
│
├── data/
│
├── docs/
│
└── README.md
```
