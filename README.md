# Course Syllabus: ML for Domain Experts (ML-DX)

**Course Title:** Machine Learning for Domain Experts: Bridging the Gap between Subject Matter Expertise and Model Architecture  
**Course Level:** Graduate / Engineering MBA  
**Prerequisites:** Bachelor’s degree in any STEM field. (No prior deep learning experience required).

---

## 1. Course Description
This course is designed for STEM professionals and Engineering MBA students who possess deep domain expertise but lack the technical vocabulary and architectural understanding to collaborate effectively with Machine Learning (ML) engineers. 

Rather than focusing on how to *code* a model from scratch, this course focuses on the *mechanics* of how models work. The goal is to empower the "Domain Expert" to act as the critical link in the ML pipeline—ensuring that the data is representative, the architecture is suited to the problem, and the final output is scientifically and operationally valid. Students will learn to translate domain-specific constraints into technical requirements for LLMs, Diffusion models, and Computer Vision systems.

---

## 2. Learning Objectives
By the end of this course, students will be able to:
1. **Collaborate Architecturally:** Speak the "language" of ML engineers to guide the design of domain-specific models.
2. **Audit Data Pipelines:** Identify data quality issues, bias, and "leaks" that a generalist engineer might miss.
3. **Navigate the ML Stack:** Understand the trade-offs between different architectures (e.g., Dense vs. MoE) and optimization techniques (e.g., Quantization).
4. **Guide Model Alignment:** Lead instruction tuning and evaluation efforts to ensure model outputs are grounded in domain reality.

---

## 3. Course Curriculum

### Module 1: The Data Foundation (The Domain Expert's Primary Lever)
*Focus: Moving from "raw data" to "model-ready data."*
* **Data Engineering for Experts:** Understanding ETL pipelines and the role of the domain expert in feature engineering.
* **Data Quality & Curation:** Identifying noise, outliers, and "gold standard" data.
* **The Taxonomy of Datasets:** Structured vs. Unstructured; Synthetic data generation vs. Real-world data.
* **Bias and Representation:** How domain-specific blind spots lead to model failure.

### Module 2: From Signals to Tokens
*Focus: How machines "perceive" domain information.*
* **Vectorization & Embeddings:** Converting domain concepts into mathematical space.
* **Tokenization:** Byte-Pair Encoding (BPE), WordPiece, and the challenges of domain-specific vocabularies (e.g., chemical formulas, legal jargon, medical codes).
* **Vision & Diffusion Basics:** How images are decomposed into latent spaces (CNNs and the basics of denoising).

### Module 3: The Transformer Architecture & Beyond
*Focus: The "Engine" of modern AI.*
* **Attention Mechanisms:** Understanding "Self-Attention"—how models weigh the importance of different inputs.
* **The Transformer Stack:** Encoders, Decoders, and the architecture of GPT-style models.
* **Mixture-of-Experts (MoE):** Understanding sparse activation—how models use "specialist" sub-networks to handle diverse domain tasks.
* **Model Scaling Laws:** The relationship between compute, data size, and performance.

### Module 4: The Lifecycle of a Domain-Specific Model
*Focus: The process of building a specialized tool.*
* **Base Model Training:** Pre-training on massive corpora vs. domain-specific pre-training.
* **Instruction Tuning & RLHF:** How to create a "Gold Dataset" for tuning; the role of the expert in Reinforcement Learning from Human Feedback.
* **Fine-tuning Strategies:** Full fine-tuning vs. Parameter-Efficient Fine-Tuning (PEFT) like LoRA.

### Module 5: Deployment, Efficiency & Inference
*Focus: Making the model usable in a production engineering environment.*
* **Quantization:** Trading precision for speed (FP32 $\rightarrow$ FP16 $\rightarrow$ INT8).
* **Speculative Decoding:** Using a smaller "draft" model to speed up a larger "oracle" model.
* **KV Caching & Context Windows:** Understanding the memory limits of model "memory."
* **Hallucination vs. Grounding:** RAG (Retrieval-Augmented Generation) and using domain knowledge bases to anchor model outputs.

---

## 4. Pedagogical Approach & Assessment

### The "Architectural Translation" Project (Capstone)
Instead of a traditional exam, students will work in teams (Domain Expert + ML Engineer) to design a blueprint for a domain-specific model.
* **Deliverable:** A technical specification document that defines:
    * The data curation strategy.
    * The chosen architecture (e.g., "Why a MoE approach is better for this medical application").
    * The evaluation rubric (How do we know it actually works in the real world?).

### Assessment Criteria:
* **Vocabulary Mastery:** Ability to use terms like *quantization, tokenization, and latent space* correctly in a technical context.
* **Critical Analysis:** Ability to look at a model's failure and diagnose whether it was a *data* problem, an *architectural* limitation, or a *tuning* issue.
* **Communication Efficiency:** Ability to provide feedback to an engineering team that is actionable and technically grounded.