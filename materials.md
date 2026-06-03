Since this is a graduate-level course intended for an Engineering MBA, the focus should shift away from traditional "academic" testing (like rote memorization) and toward **applied competency**. The goal is to produce a professional who can sit in a high-stakes technical meeting and provide expert guidance.

Here is the list of required materials, divided by category:

### 1. Applied Assignments (The "Translation" Work)
These assignments focus on the student's ability to translate domain knowledge into technical specifications.
* **The Data Audit Report:** Students are given a "dirty" domain-specific dataset. They must identify biases, missing signals, and quality issues, then write a "Clean-up Specification" for a data engineer.
* **Tokenization Analysis:** An assignment where students analyze how a standard tokenizer (like GPT-4's) handles their specific domain's terminology (e.g., how it breaks down a complex chemical formula) and propose a custom vocabulary strategy.
* **Evaluation Rubric Design:** Instead of a test, students create a "Gold Standard" evaluation set. They must define 20 "edge case" prompts and the exact criteria for what constitutes a "perfect" vs. "fail" answer in their field.
* **Architecture Trade-off Memo:** A business-style memo where students argue for a specific architectural choice (e.g., "Why we should use a Mixture-of-Experts model instead of a Dense model for this specific engineering problem").

### 2. "No-Code" Labs (Conceptual Simulation)
Since the prerequisite is any STEM degree, labs should focus on *conceptual* flow and *tool-assisted* exploration rather than writing PyTorch/TensorFlow code from scratch.
* **The Prompt-Engineering Lab:** Using existing LLMs to test the limits of "Zero-shot" vs. "Few-shot" prompting for domain tasks.
* **The RAG Prototype Lab:** Using a no-code tool (like LangChain or a vector database GUI) to upload a domain document and observe how "Retrieval-Augmented Generation" changes the model's accuracy.
* **Weights & Biases Visualization Lab:** Using visualization tools to look at "Attention Maps"—seeing which tokens the model is actually focusing on when processing a domain-specific sentence.
* **Quantization Impact Lab:** Comparing the outputs of a full-precision model vs. a heavily quantized model (e.g., 4-bit) to determine the "point of failure" where domain accuracy drops.

### 3. Case Studies (Critical Analysis)
These are "Post-Mortems" of real-world ML implementations.
* **The "Model Failure" Analysis:** A study of a high-profile AI failure in a specialized field (e.g., a medical AI that relied on a "shortcut" in the data). Students must identify exactly where the domain expert failed to guide the engineer.
* **The "SOTA" Review:** Analyzing a recent research paper (e.g., a new Diffusion model for protein folding) and extracting the architectural "levers" that made it successful.

### 4. The Capstone Project (The "Blueprints")
The final deliverable is not a model, but a **Technical Design Document (TDD)**.
* **Project Scope:** Design a domain-specific model from the ground up.
* **Required Components:**
    * **Data Strategy:** Where is the data coming from? How will it be curated?
    * **Architectural Selection:** Which base model? MoE or Dense? Tokenization strategy?
    * **Training Plan:** Pre-training $\rightarrow$ SFT $\rightarrow$ RLHF.
    * **Inference Optimization:** Quantization and deployment strategy.
    * **Verification Plan:** How will the domain expert validate the output?

### 5. Assessment & Exams
* **The "Vocabulary Viva" (Oral Exam):** A 15-minute technical interview. The professor acts as the ML Engineer, and the student must explain their domain requirements using the correct architectural vocabulary.
* **Mid-term conceptual quiz:** A short, multiple-choice quiz focusing on the "Mechanics" (e.g., "What happens to a model's memory if we double the context window?").

### Summary Table for Course Planning

| Material Type | Frequency | primary Goal | Skill Tested |
| :--- | :--- | :--- | :--- |
| **Assignments** | Weekly | Translation | Technical Writing / Specification |
| **Labs** | Bi-weekly | Exploration | System Intuition / Tools |
| **Case Studies** | Monthly | Critical Thinking | Diagnostics / Analysis |
| **Viva/Quiz** | Twice/Term | Knowledge Check | Vocabulary / Theory |
| **Capstone** | End of Term | Synthesis | End-to-End Architecture Design |