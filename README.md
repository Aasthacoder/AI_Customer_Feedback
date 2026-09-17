# AI-Assisted Customer Feedback → Product Roadmap

A beginner-friendly **AI + Product Management** project that analyzes real customer complaint narratives, discovers recurring customer problems using NLP and semantic analysis, validates those patterns, and translates the findings into a product opportunity, MVP, metrics, experiment plan, and roadmap.

---

## Project Overview

Customer feedback contains valuable product insights, but large volumes of unstructured complaint narratives are difficult to analyze manually.

This project explores a simple question:

> **How can AI-assisted analysis of customer complaints help identify and validate product problems that can be translated into actionable product opportunities?**

The project uses the **Consumer Financial Protection Bureau (CFPB) Consumer Complaint Database** as a real-world source of customer feedback.

The workflow combines:

**Data Analysis → NLP Baseline → AI-Assisted Analysis → Validation → Problem Discovery → Product Management**

---

## Key Results

| Metric                                    |               Result |
| ----------------------------------------- | -------------------: |
| Complaints collected                      |           **10,000** |
| Usable complaint narratives               |            **9,995** |
| TF-IDF features                           |            **5,000** |
| Sentence embedding dimensions             |              **384** |
| Semantic clusters                         |               **10** |
| Top-5 semantic-neighbor issue consistency |            **47.0%** |
| Selected purchase-dispute cluster         | **1,222 complaints** |
| Share of analyzed complaints              |           **12.23%** |
| Leading related sub-issue concentration   |           **70.95%** |

The **47%** figure represents the average proportion of a complaint's top five semantic neighbors that shared its existing issue label. It is used as a **semantic-consistency baseline**, not as model accuracy.

The **70.95%** figure represents the concentration of the selected cluster in its leading related CFPB sub-issue. It is also not an accuracy measure.

---

# Project Architecture

The project is organized into three notebooks, with each notebook responsible for a different stage of the workflow.

```text
Customer Complaint Data
        │
        ▼
┌──────────────────────────┐
│ 01_Data_Discovery.ipynb  │
│                          │
│ • Data quality           │
│ • Complaint exploration  │
│ • Customer language      │
│ • Phrase analysis        │
│ • TF-IDF baseline        │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────────┐
│ 02_AI_Feedback_Analysis.ipynb│
│                              │
│ • Sentence embeddings        │
│ • Semantic similarity        │
│ • Clustering                 │
│ • Cluster inspection         │
│ • Theme discovery            │
│ • Theme validation           │
│ • Candidate problems         │
│ • Problem validation         │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│ 03_Product_Management.ipynb  │
│                              │
│ • Problem prioritization      │
│ • Product opportunity         │
│ • Root-cause hypothesis       │
│ • MVP definition              │
│ • Success metrics             │
│ • Experiment plan             │
│ • Rollout plan                │
│ • Product roadmap             │
└──────────────────────────────┘
```

This separation keeps **data analysis, AI analysis, and Product Management** independent and prevents unnecessary duplication between notebooks.

---

# 1. Data Discovery

The first notebook establishes the analytical foundation.

### Main activities

* Load and inspect the complaint dataset
* Understand dataset structure
* Check data quality
* Check duplicate complaint IDs
* Analyze complaint categories
* Analyze sub-issues
* Explore complaint narratives
* Analyze narrative length
* Examine common customer language
* Identify frequent words and phrases
* Compare language across complaint categories
* Analyze sub-issues within major complaint categories
* Build a TF-IDF text-analysis baseline

### Data quality

The project started with **10,000 complaint records**.

After inspecting the complaint narratives, **9,995 usable narratives** were retained for text-based analysis.

The project did not apply an arbitrary minimum-word threshold simply to increase the apparent quality of the text dataset.

---

# 2. Non-AI Baseline: TF-IDF

Before introducing semantic embeddings, a traditional NLP baseline was established using **TF-IDF**.

The TF-IDF representation used **5,000 features**.

TF-IDF was used as a baseline because it provides an interpretable representation of important words and phrases.

This creates a useful comparison:

```text
Traditional NLP
TF-IDF
   ↓
Word / phrase importance

vs.

Semantic NLP
Embeddings
   ↓
Meaning-based similarity
```

The goal was not to prove that one method is universally better than the other, but to establish a simple baseline before applying semantic analysis.

---

# 3. AI-Assisted Customer Feedback Analysis

The second notebook applies sentence embeddings to the complaint narratives.

## Sentence Embeddings

Each of the **9,995 usable complaint narratives** was converted into a **384-dimensional embedding**.

Embeddings represent the semantic meaning of text as numerical vectors.

This allows complaints to be compared based on meaning rather than only on shared words.

---

## Semantic Similarity

Semantic similarity was used to identify complaints that were close in embedding space.

For each complaint, the analysis examined its most similar complaints and compared their existing CFPB issue labels.

### Validation Result

The top five semantic neighbors shared the same issue **47.0% of the time on average**.

This result was used as a **semantic-neighbor consistency baseline**.

It does not represent:

* classification accuracy,
* prediction accuracy,
* model precision,
* or model recall.

---

# 4. Customer Theme Discovery

The complaint embeddings were clustered into **10 semantic groups**.

The clusters were then inspected using:

* cluster size,
* dominant complaint issues,
* representative complaints,
* distinctive language,
* and existing complaint categories.

The purpose of clustering was exploratory:

> **Identify recurring groups of semantically similar customer complaints that may represent broader customer themes.**

The clusters were not automatically treated as ground-truth customer problems.

---

# 5. Theme Validation

Candidate themes were compared against existing CFPB complaint sub-issues to determine how consistently the discovered themes aligned with the existing complaint taxonomy.

Five major candidate themes were investigated:

| Candidate Theme                | Complaints |
| ------------------------------ | ---------: |
| Purchase disputes / refunds    |      1,222 |
| Late payments / billing errors |        785 |
| Promotions / rewards           |        786 |
| Fees / interest                |      1,243 |
| Fraud / unauthorized charges   |      1,248 |

The validation showed different levels of alignment across these themes.

Purchase disputes/refunds showed particularly strong concentration in the leading related sub-issue, with **70.95%** of the relevant cluster concentrated there.

---

# 6. From AI Themes to Customer Problems

The project does not treat an AI-generated cluster as automatically equivalent to a product problem.

The workflow is:

```text
Semantic Cluster
      ↓
Theme
      ↓
Theme Validation
      ↓
Candidate Customer Problem
      ↓
Problem Validation
      ↓
Product Opportunity
```

This distinction is important because a frequently occurring topic is not automatically a product problem.

---

# 7. Selected Product Opportunity

The analysis selected **purchase-dispute resolution** as the primary product opportunity.

The selected cluster contained:

**1,222 complaints**

representing:

**12.23% of the 9,995 usable complaint narratives.**

The cluster also showed **70.95% concentration in its leading related sub-issue**.

Complaint narratives within the selected area include examples involving unresolved purchase disputes, disputed charges, unauthorized transactions, and repeated attempts to obtain resolution.

---

# 8. Customer Problem Hypothesis

The analysis suggests a potential customer problem around friction and uncertainty during purchase-dispute resolution.

### Problem Hypothesis

> **Customers may experience uncertainty and additional effort while trying to understand the progress, required actions, next steps, and outcome of a purchase dispute.**

This is treated as a **hypothesis**, not as a directly measured statement about the complete customer journey.

The complaint dataset provides evidence of reported customer experiences, but it does not contain every stage of the customer's interaction with the dispute system.

---

# 9. Product Opportunity

The identified opportunity is to improve transparency during the existing dispute process.

The proposed experience focuses on helping customers understand:

* Current dispute status
* Information required from the customer
* Next steps
* Dispute outcome

The objective is not to replace the dispute investigation process.

---

# 10. MVP — Dispute Tracker

## MVP Concept

The proposed MVP is a **Dispute Tracker**.

The MVP provides a centralized view of the customer's active dispute.

### Core Features

* Current dispute status
* Required-information notifications
* Next-step guidance
* Dispute outcome information

### Explicitly Out of Scope

The MVP does not attempt to:

* automatically approve or reject disputes,
* replace human investigation,
* build an automated fraud-detection system,
* or replace the existing dispute-submission process.

Keeping the first version narrow makes the product hypothesis easier to test.

---

# 11. Product Metrics

### Primary Metric

**Repeat contact rate for the same dispute**

### Supporting Metrics

* Average dispute resolution time
* Percentage of disputes requiring additional customer contact
* Customer satisfaction after dispute resolution

### Guardrail Metric

**Dispute outcome quality**

The goal is not simply to reduce customer contacts.

A successful product should reduce unnecessary effort **without negatively affecting dispute outcomes or access to support.**

---

# 12. Experiment Plan

### Hypothesis

> If customers receive clearer information about their dispute status, required information, and next steps, then unnecessary repeated contact about the same dispute will decrease.

### Experiment Design

**Control:** Existing purchase-dispute experience

**Treatment:** Existing experience with the Dispute Tracker

### Primary Metric

Repeat contact rate for the same dispute

### Supporting Metrics

* Resolution time
* Customer satisfaction

### Guardrail

Dispute outcome quality

The experiment would compare the existing experience with the MVP before considering wider rollout.

---

# 13. Rollout Plan

The proposed rollout follows a gradual validation approach.

```text
Usability Testing
       ↓
Limited Rollout
       ↓
Metric Evaluation
       ↓
Wider Rollout
```

### Stage 1 — Usability Testing

Test the experience with a small group of relevant customers and identify usability problems.

### Stage 2 — Limited Rollout

Release the MVP to a small percentage of eligible customers and measure the defined success metrics.

### Stage 3 — Evaluate Results

Compare the MVP experience with the existing experience.

### Stage 4 — Wider Rollout

Expand availability if the results support the product hypothesis.

---

# 14. Product Roadmap

| Phase                   | Focus                                               | Outcome                                            |
| ----------------------- | --------------------------------------------------- | -------------------------------------------------- |
| Phase 1 — MVP           | Status, required information, next-step guidance    | Customers can follow an active dispute more easily |
| Phase 2 — Communication | Clearer updates and outcome explanations            | Better information throughout the dispute process  |
| Phase 3 — AI Assistance | Simpler explanations of complex dispute information | Easier understanding of dispute information        |

The roadmap prioritizes validation of the core experience before introducing additional AI capabilities.

---

# Engineering Decisions

## Why use a separate data-analysis notebook?

The data-discovery notebook establishes the baseline and documents the dataset before AI techniques are introduced.

This makes the workflow easier to understand and reproduce.

## Why establish a TF-IDF baseline?

TF-IDF provides a simple and interpretable text-analysis baseline before moving to semantic embeddings.

## Why use sentence embeddings?

Customer complaints can describe similar problems using different words.

Embeddings allow semantic similarity to be analyzed beyond exact keyword overlap.

## Why cluster the embeddings?

Clustering provides an exploratory way to group semantically similar complaints and identify broader themes.

## Why validate the clusters?

AI-generated patterns should not automatically be treated as customer problems.

Comparing clusters with the existing CFPB taxonomy provides an additional consistency check.

## Why separate AI and Product Management?

The AI notebook focuses on **finding and validating patterns**.

The Product Management notebook focuses on **turning validated evidence into product decisions**.

This separation keeps the analytical and strategic reasoning clear.

---

# Project Structure

```text
AI-Customer-Feedback-Product-Roadmap/
│
├── README.md
│
├── notebooks/
│   ├── 01_Data_Discovery.ipynb
│   ├── 02_AI_Feedback_Analysis.ipynb
│   └── 03_Product_Management.ipynb
│
├── data/
│   └── README.md
│
├── docs/
│
├── requirements.txt
│
└── .gitignore
```

The repository intentionally does not include the Python virtual environment, notebook caches, temporary files, or other unnecessary generated files.

---

# Setup

## Requirements

* Python 3.10+
* Jupyter Notebook / JupyterLab
* pip

## Installation

Clone the repository and move into the project directory:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd AI-Customer-Feedback-Product-Roadmap
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Start Jupyter:

```bash
jupyter notebook
```

Open the notebooks in this order:

```text
01_Data_Discovery.ipynb
        ↓
02_AI_Feedback_Analysis.ipynb
        ↓
03_Product_Management.ipynb
```

---

# Reproducibility

The notebooks are designed to show the complete analytical progression.

To reproduce the analysis:

1. Install the required Python packages.
2. Obtain the CFPB complaint data used for the project.
3. Place the required data in the expected project location.
4. Run the notebooks sequentially.
5. Review the generated tables, similarity results, clusters, validation results, and PM analysis.

The project separates the stages so that the AI analysis can be understood as an extension of the initial data analysis rather than as an isolated model.

---

# Limitations

## Dataset Representation

CFPB complaints represent reported consumer experiences and should not be interpreted as a statistically representative sample of all customers.

## Complaint Narratives

The narratives capture what customers reported but do not provide the complete customer journey or all operational events behind a complaint.

## Unsupervised Clustering

Clustering is exploratory. The resulting groups require human interpretation and validation.

## Semantic Similarity

The **47%** result is a semantic-neighbor consistency baseline, not a formal model-accuracy measurement.

## Theme Validation

The **70.95%** concentration measures alignment with the leading related sub-issue within the selected cluster. It does not prove that the underlying product hypothesis is correct.

## Product Hypothesis

The Dispute Tracker is a proposed solution based on the identified evidence and hypotheses. Customer research and product/operational data would be required before treating the solution as validated.

---

# What I Learned

This project demonstrated a complete workflow from unstructured customer feedback to a product decision:

```text
Customer Feedback
       ↓
Data Understanding
       ↓
NLP Baseline
       ↓
AI-Assisted Analysis
       ↓
Pattern Discovery
       ↓
Validation
       ↓
Customer Problem
       ↓
Product Opportunity
       ↓
MVP
       ↓
Metrics
       ↓
Experiment
       ↓
Roadmap
```

The main learning was that **finding a pattern is not the same as finding a product problem**.

AI can help surface patterns in large volumes of feedback, but those patterns still need validation and product reasoning before they are converted into a product decision.

---

# Technologies

* Python
* pandas
* NumPy
* scikit-learn
* TF-IDF
* Sentence Transformers
* NLP
* Sentence Embeddings
* Cosine Similarity
* K-Means Clustering
* matplotlib
* Jupyter Notebook

---

# Project Outcome

The final outcome is an evidence-backed product concept:

> **Purchase-dispute resolution → Dispute Tracker MVP**

The project demonstrates how customer feedback can be transformed from raw narratives into:

**quantified evidence → validated customer themes → product problem → MVP → measurable product hypothesis.**
