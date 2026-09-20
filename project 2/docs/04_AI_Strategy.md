# AI Strategy

## 1. Why Use AI?

The main reason for introducing AI is the unstructured nature of customer feedback.

Customers can describe the same problem in very different ways.

For example:

> "I don't understand this charge."

and

> "Why was I billed this amount? Nobody told me about this fee."

A keyword-based system may treat these as different pieces of feedback even though they may represent the same underlying problem.

AI-based semantic analysis may help identify these relationships.

---

## 2. Where AI May Help

The initial areas being considered are:

### Semantic grouping

Group feedback that expresses similar ideas even when the wording is different.

### Theme discovery

Identify recurring topics within large volumes of customer narratives.

### Customer theme discovery

Identify recurring groups of complaints that may represent similar customer experiences.

### Problem refinement

Use representative complaints to translate broad themes into more specific candidate customer problems.

---

## 3. AI Is Not Automatically Better

Using AI does not automatically make the analysis better.

AI may:

* merge different problems,
* split the same problem into multiple groups,
* misunderstand customer context,
* generate incorrect summaries,
* or introduce assumptions that were not present in the original feedback.

Therefore, AI-generated groups and themes will be compared with the simpler text-analysis baseline and manually reviewed using representative complaints.

---

## 4. Non-AI Baseline

Before introducing AI, I will analyze what can be learned using simpler methods such as:

* Existing CFPB categories
* Keyword analysis
* Frequency analysis
* Basic text analysis
* Manual review of complaint samples

This creates a baseline against which the AI-assisted approach can be evaluated.

---

## 5. AI Evaluation Question

The key question is not simply:

> "How accurate is the AI model?"

The more relevant question for this project is:

> **"Does AI reveal useful customer themes that are difficult to see from simpler text analysis and existing categories?"**

The evaluation therefore focuses on the usefulness and consistency of the discovered themes rather than claiming a formal model-accuracy score.

---

## 6. Human Review

AI-generated insights will not be accepted automatically.

A sample of clusters and candidate themes will be reviewed against the original customer feedback.

The review will focus on whether the AI output:

* represents the original feedback reasonably well,
* groups genuinely similar customer experiences,
* avoids combining clearly unrelated experiences,
* and provides a useful basis for identifying a customer problem.

---

## 7. Expected AI Workflow

The planned workflow is:

**Customer Narratives**
        ↓
**Text Preparation**
        ↓
**Non-AI Baseline**
        ↓
**Semantic Representation**
        ↓
**AI-Assisted Grouping**
        ↓
**Human Validation**
        ↓
**Customer Problem Themes**
        ↓
**Product Opportunities**

The exact models and techniques will be selected after understanding the dataset rather than choosing a model first.
