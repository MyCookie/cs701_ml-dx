# Grading Guide: Module 1 Assignments

## 1. Philosophy of Assessment
This course evaluates students on their ability to act as the **bridge** between domain expertise and technical implementation. We are not grading for "the one right answer," but for the **rigor of the translation**.

A high-scoring student is one who can take a vague domain intuition ("the data feels off") and turn it into a technical specification that an ML engineer can implement without further clarification.

---

## 2. Rubric: The Data Audit Report

### Core Evaluation Criteria

| Criteria | Poor (Fail/C) | Satisfactory (B) | Exceptional (A) |
| :--- | :--- | :--- | :--- |
| **Categorization** | Fails to distinguish between Noise and Bias. Misidentifies Missing Signals. | Correctly identifies most issues but struggles to explain *why* they are Bias vs. Noise. | Perfectly categorizes all issues with clear, domain-grounded justifications. |
| **Technical Specification** | Vague instructions (e.g., "Clean the temperature data"). | Actionable but imprecise instructions (e.g., "Remove the zeros"). | Precise, algorithmic instructions (e.g., "Filter $\le 0$; impute using 1-hour windowed median"). |
| **Domain Insight** | Misses the "Missing Signal" (Humidity) entirely. | Identifies the missing signal but cannot explain its physical impact on the model. | Identifies the missing signal and explains exactly how its absence creates a blind spot. |
| **Communication** | Unstructured; uses non-technical language. | Clear, but requires the engineer to "fill in the gaps." | Professional "Clean-up Specification" format; zero ambiguity. |

### "Red Flags" for Grading
- **The "Magical Fix" Error:** The student suggests "just using a better model" to fix a data bias problem. (Penalty: Severe. This indicates a failure to understand that models cannot fix unrepresentative data).
- **The "Over-Cleaning" Error:** The student suggests removing all outliers without checking if they are domain-valid. (Penalty: Moderate).

---

## 3. Rubric: Dataset Taxonomy & Strategy

### Core Evaluation Criteria

| Criteria | Poor (Fail/C) | Satisfactory (B) | Exceptional (A) |
| :--- | :--- | :--- | :--- |
| **Taxonomy Accuracy** | Confuses Structured and Unstructured data. | Correctly classifies most sources; basic understanding of the "Translation Challenge." | Precise classification; identifies "Semi-structured" nuances and provides deep architectural insight. |
| **Synthetic Strategy** | Suggests synthetic data without any validation method. | Proposes synthetic data but lacks a clear plan for domain validation. | Proposes a robust synthetic plan with a defined "Expert-in-the-Loop" validation loop. |
| **Risk Awareness** | Unaware of Model Collapse or the risks of synthetic data. | Mentions Model Collapse but cannot explain the mechanism or how to prevent it. | Clearly explains the feedback loop of Model Collapse and proposes a "Real-world Anchor" strategy. |
| **Strategy Map** | Incomplete; missing key sources or processing paths. | Complete but generic; lacks domain-specific detail. | Comprehensive "Data Strategy Map" that serves as a professional blueprint for an engineer. |

### "Red Flags" for Grading
- **The "Synthetic Silver Bullet" Error:** The student believes synthetic data can completely replace real-world data without any risk. (Penalty: Severe).
- **The "Format Blindness" Error:** The student ignores the "Translation Challenge" (e.g., assuming a PDF can be read as a CSV). (Penalty: Moderate).

---

## 4. Rubric: Case Study Analysis (Post-Mortems)

### Core Evaluation Criteria

| Criteria | Poor (Fail/C) | Satisfactory (B) | Exceptional (A) |
| :--- | :--- | :--- | :--- |
| **Diagnostic Rigor** | Fails to identify the core failure (e.g., confuses shortcut with noise). | Correctly identifies the failure but cannot explain the technical mechanism. | Precisely identifies the root cause (Shortcut vs. Bias) with a detailed technical explanation. |
| **Architectural Translation** | Proposes vague fixes (e.g., "get more data"). | Proposes relevant tools (e.g., "use a saliency map") but lacks a specific implementation plan. | Translates the failure into actionable technical requirements (e.g., "Perform Stratified Performance Analysis across 5 skin-tone tiers"). |
| **Prevention Strategy** | Suggests "better luck next time" or generic solutions. | Proposes a reasonable audit step but misses the "Gold Standard" validation. | Designs a comprehensive prevention pipeline (e.g., Ablation $\rightarrow$ Saliency Audit $\rightarrow$ Clinical Ground-Truth Validation). |
| **Critical Analysis** | Simply summarizes the case study without adding insight. | Analyzes the case but fails to connect it to the broader "Garbage In, Garbage Out" principle. | Synthesizes the case study into a generalizable rule for future domain-specific ML projects. |

### "Red Flags" for Grading
- **The "Architectural Fallacy":** The student suggests that changing the model architecture (e.g., "use a larger LLM") would have prevented a data-driven failure. (Penalty: Severe).
- **The "Superficial Fix":** The student suggests a fix that doesn't address the underlying bias/shortcut (e.g., "just remove the wrong images"). (Penalty: Moderate).

---

## 5. Final Grade Calculation

**Module 1 Total Grade = (Audit Report Score $\times$ 0.5) + (Taxonomy Strategy Score $\times$ 0.5)**

- **A (90-100%):** Student is "Ready to Lead." Can provide specifications that an engineer can execute immediately.
- **B (80-89%):** Student is "Competent." Understands the concepts but needs a bit more practice in technical translation.
- **C (70-79%):** Student is "Learning." Understands the terminology but struggles to apply it to a technical blueprint.
- **Fail (<70%):** Student lacks a fundamental understanding of the "Garbage In, Garbage Out" principle.