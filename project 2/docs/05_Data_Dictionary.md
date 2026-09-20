# Data Dictionary

## Dataset

**CFPB Consumer Complaint Database**

The dataset contains structured information about consumer complaints submitted to the Consumer Financial Protection Bureau.

For this project, the initial focus is on **credit card complaints with consumer narratives**.

---

## Fields Used in the Analysis

| Field                        | Description                                   | How I Use It                            |
| ---------------------------- | ----------------------------------------------| ----------------------------------------|
| `complaint_id`               | Unique identifier for a complaint             | Identify individual complaints          |
| `date_received`              | Date the complaint was received               | Analyze trends over time                |
| `product`                    | Financial product associated with complaint   | Define the initial product scope        |
| `sub_product`                | More specific product category                | Understand product context              |
| `issue`                      | CFPB's classification of the main issue       | Compare existing categorization with discovered patterns   |
| `sub_issue`                  | More detailed issue classification            | Investigate specific complaint types    |
| `company`                    | Company associated with the complaint         | Compare patterns across companies where useful                |
| `state`                      | Consumer's state                              | Explore geographic patterns where relevant              |
| `submitted_via`              | Channel through which complaint was submitted | Understand how customers provide feedback              |
|`consumer_complaint_narrative`| Consumer's description of the problem         | Main source for qualitative and AI analysis              |
| `company_response`           | Company's response to the complaint           | Understand how complaints were addressed|
| `timely_response`            | Whether the company provided a timely response| Additional service-performance context  |

---

## Most Important Fields

Although the dataset contains many fields, three are particularly important for this project:

### Consumer Complaint Narrative

This is the most important field because it contains the customer's own description of their experience.

It will be used for:

* Theme discovery
* Problem identification
* Semantic analysis
* AI-assisted clustering
* Qualitative analysis

### Issue / Sub-Issue

These fields provide an existing structured classification.

They will be useful as a baseline for understanding how complaints are already categorized.

### Date Received

This allows me to investigate whether certain problems:

* remain consistent over time,
* increase,
* decrease,
* or appear to be emerging.

---

## Fields That May Be Used Later

Some fields may not be necessary for the initial analysis but could become useful later.

Examples include:

* Company
* State
* Submission channel
* Company response
* Timely response

These will only be incorporated into the product analysis if they help answer a relevant product question.

---

## Data Types

The main fields can broadly be grouped into:

### Identifiers

* Complaint ID

### Dates

* Date received

### Categorical Data

* Product
* Sub-product
* Issue
* Sub-issue
* Company
* State
* Submission channel
* Company response
* Timely response

### Unstructured Text

* Consumer complaint narrative

---

## Product Management Perspective

Not every available field automatically becomes a product metric.

The fields are first treated as potential sources of evidence.

The importance of a field will depend on whether it helps answer questions such as:

> Who is experiencing the problem?

> What problem are they experiencing?

> How frequently does it appear?

> Is the problem changing over time?

> Are different customer groups experiencing it differently?

> How significant does the problem appear to be?

This prevents the analysis from becoming a simple exercise in analyzing every column in the dataset.
