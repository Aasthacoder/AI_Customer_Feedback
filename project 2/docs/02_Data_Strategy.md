# Data Strategy

## 1. Primary Data Source

### Consumer Financial Protection Bureau

**Dataset:** Consumer Complaint Database

Official source:

https://www.consumerfinance.gov/data-research/consumer-complaints/

API documentation:

https://cfpb.github.io/api/ccdb/

---

## 2. Why This Dataset?

The CFPB Consumer Complaint Database provides real-world customer complaints together with structured information about those complaints.

It provides two important types of information.

### Structured information

Examples include:

* Product
* Issue
* Sub-issue
* Company
* Date
* Submission channel
* Company response
* Timely response

### Unstructured information

Most importantly:

* Consumer complaint narratives

This combination makes the dataset useful for comparing traditional structured analysis with AI-assisted analysis of natural-language customer feedback.

---

## 3. Initial Dataset Scope

The initial analysis focuses on:

> **Credit card complaints containing consumer complaint narratives.**

The scope may be expanded later if the analysis indicates that additional product categories are required.

---

## 4. Reason for Narrow Initial Scope

Analyzing the entire database immediately could result in a large but shallow analysis.

A focused product category allows deeper investigation of:

* Customer problems
* Customer language
* Existing issue classifications
* Recurring themes
* Product opportunities
* AI-generated insights

The scope can be expanded after the initial findings are understood.

---

## 5. Important Data Fields

| Field                        | Product Management Use                  |
| ---------------------------- | --------------------------------------- |
| Complaint ID                 | Unique record identification            |
| Date received                | Trend analysis                          |
| Product                      | Product-level segmentation              |
| Sub-product                  | Detailed product context                |
| Issue                        | Existing problem classification         |
| Sub-issue                    | More detailed problem classification    |
| Company                      | Company-level analysis                  |
| Consumer complaint narrative | Customer voice and qualitative analysis |
| Submitted via                | Feedback-channel analysis               |
| Company response             | Resolution context                      |
| Timely response              | Service-performance context             |

---

## 6. Initial Data Questions

### Dataset size

* How many complaints are available?
* How many belong to the selected product?
* How many contain narratives?

### Data quality

* Are values missing?
* Are there duplicate records?
* Are narratives unusually short?
* Are there unusual records or categories?

### Customer problems

* Which existing issues dominate?
* Which sub-issues dominate?
* How do complaint patterns change over time?
* Do different structured categories contain similar customer problems?

### Feedback characteristics

* How long are customer narratives?
* What language do customers use?
* What recurring phrases appear?
* Do individual complaints contain multiple problems?

---

## 7. Data Processing Architecture

The analysis follows:

**Raw Data**
        ↓
**Cleaned Data**
        ↓
**Analysis Dataset**
        ↓
**AI Analysis Dataset**
        ↓
**Product Insights**

This separation preserves the original data and makes the analytical process reproducible.

---

## 8. Raw Data

Raw data remains unchanged after collection. It serves as the original evidence source for the analysis.

---

## 9. Working Dataset

The initial analysis uses a reproducible working dataset of 10,000 credit card complaint records returned from the CFPB API at the time of analysis.

This provides a manageable dataset for detailed exploration and manual validation while preserving enough records to identify recurring patterns.

The working dataset is treated as an analytical sample rather than as the complete CFPB complaint population.

---

## 10. Dataset Limitation

The CFPB Consumer Complaint Database is not a statistical sample of all consumer experiences.

Therefore, complaint counts cannot directly be interpreted as the prevalence of a problem across the entire customer population.

For example, the appropriate interpretation is:

> "X% of complaints in the analyzed dataset mention this problem."

rather than:

> "X% of customers experience this problem."

Complaint volume will therefore be treated as one signal among several when evaluating product opportunities.

---

## 11. Data Privacy Considerations

Customer narratives may contain sensitive information.

The analysis will:

* Avoid reproducing unnecessary personal information.
* Avoid attempting to identify individuals.
* Use aggregated findings where possible.
* Avoid publishing sensitive raw narratives unnecessarily.

---

## 12. Data-to-Decision Framework

The purpose of the dataset is to support a sequence of Product Management decisions:

**Customer Evidence**
        ↓
**Problem Discovery**
        ↓
**Opportunity Assessment**
        ↓
**Prioritization**
        ↓
**Product Decision**
