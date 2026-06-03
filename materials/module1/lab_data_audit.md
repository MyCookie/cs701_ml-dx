# Assignment: The Data Audit Report (Module 1)

## 1. Overview
In this assignment, you will step into the role of the "Lead Domain Expert" auditing a dataset intended for a new ML project. 

A common mistake in AI development is for ML engineers to assume that if data is "digitized," it is "correct." As the Domain Expert, your task is to perform a **Data Audit**. You are looking for the invisible gaps—the biases, the missing context, and the noise—that can lead to catastrophic model failure in a real-world engineering environment.

### Learning Objectives
By the end of this assignment, you will be able to:
- Identify and categorize common types of data bias.
- Distinguish between a "statistical outlier" and "domain noise."
- Identify "missing signals" (critical information absent from the dataset).
- Draft a **Clean-up Specification** that provides actionable instructions to a data engineer.

### Prerequisites
Before starting this assignment, please review:
- **Textbook Chapter 3:** Data Engineering & Curation.
- **Lab: The Data Foundation** (completed previously).

---

## 2. The Scenario: "Project Aegis"

**The Goal:** Your company is building an AI model to predict the "Remaining Useful Life" (RUL) of industrial turbines. If the model is accurate, you can perform maintenance *just before* a failure, saving millions in downtime.

**The Data:** You have been given a dataset containing 5,000 turbine logs. Each log includes:
- `timestamp` (Date/Time)
- `vibration_level` (Measured in mm/s)
- `temperature` (Celsius)
- `operator_id` (Employee ID)
- `maintenance_flag` (Boolean: True if maintenance was performed)
- `failure_event` (Boolean: True if the turbine failed)

### The "Dirty" Dataset Findings
Upon a preliminary review, you notice the following:
1. **The Temperature Gap:** For 20% of the logs, the `temperature` is listed as `0.0`. You know that a turbine operating at 0°C is physically impossible in this environment.
2. **The "Expert" Bias:** You notice that the `maintenance_flag` is only set to `True` when a Senior Engineer performed the work. Junior technicians' maintenance logs were not digitized.
3. **The Sensor Noise:** The `vibration_level` shows spikes of `999.9` mm/s. You know the sensor saturates at `100.0` mm/s; anything above that is a sensor error, not a physical vibration.
4. **The Missing Signal:** The dataset contains no information about the *ambient humidity* of the facility, which you know is a primary driver of corrosion and failure.

---

## 3. The Audit Process

### Step 1: Categorize the Issues
For each finding above, determine if it is **Noise**, **Bias**, or a **Missing Signal**.

| Finding | Category | Explanation |
| :--- | :--- | :--- |
| Temperature = 0.0 | **Noise** | This is an impossible value (Measurement Error). |
| Missing Junior Tech logs | **Bias** | This is "Sampling Bias." The data only represents a subset of maintenance events. |
| Vibration = 999.9 | **Noise** | This is "Sensor Saturation." The value is a technical artifact, not a real measurement. |
| No Humidity Data | **Missing Signal** | This is a "Latent Variable." The model is blind to a key physical driver of failure. |

**Summary for Non-Experts: Bias vs. Noise**
- **Noise:** Random or systematic errors in the data (e.g., a broken sensor, a typo). Noise can usually be "cleaned" or "filtered."
- **Bias:** A systematic distortion in the data that makes it unrepresentative of the real world (e.g., only collecting data from the most successful projects). Bias is much harder to fix and often requires collecting *new* data.

---

## 4. The Deliverable: The Clean-up Specification

An ML engineer cannot "fix" the data based on a comment like "the data feels wrong." They need a **Clean-up Specification**. This is a technical document that translates your domain intuition into an algorithmic instruction.

### How to Write a Clean-up Specification
Instead of: *"The temperature data is weird,"*
Write: *"Filter out all `temperature` values $\le 0$. Replace them with the median temperature of the 1-hour window surrounding the timestamp."*

### Exercise: Drafting the Spec
Based on the scenario in Section 2, draft the specifications for the following:

1. **The Temperature Problem:**
   - **Instruction:** [e.g., Remove values $\le 0$; impute using windowed average]
2. **The Vibration Problem:**
   - **Instruction:** [e.g., Clip all values $> 100$ to $100$ or mark as NaN]
3. **The Maintenance Bias:**
   - **Instruction:** [e.g., Flag the `maintenance_flag` as "incomplete" and seek manual logs from Junior Techns]
4. **The Missing Humidity Signal:**
   - **Instruction:** [e.g., Cross-reference with Facility Environmental Logs and merge datasets on `timestamp`]

---

## 5. Summary Checklist
- [ ] I can distinguish between Noise, Bias, and Missing Signals.
- [ ] I can identify a "Sampling Bias" in a dataset.
- [ ] I can translate a "feeling" about data into a technical "Clean-up Specification."
- [ ] I understand that "cleaning" data is a collaborative effort between the SME and the Engineer.