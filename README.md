# Auto Tagging Support Tickets Using LLM

##  Objective of the Task

The objective of this project is to develop an intelligent system that can automatically classify and tag support tickets into relevant categories using a Large Language Model (LLM).

The system is designed to:

* Automatically assign **top 3 most relevant tags** to each support ticket
* Implement and compare **zero-shot, few-shot, and fine-tuned approaches**
* Improve classification accuracy using contextual examples and rule-based enhancements

---

##  Methodology / Approach

### 1. Dataset Preparation

* A small dataset of support tickets was created in CSV format with:

  * `ticket_id`
  * `text` (support ticket description)
  * `true_tags` (actual category for evaluation)
* The dataset is loaded using **pandas** and processed into a structured format for model input.

---

### 2. Model Selection

* A pre-trained transformer model (`bart-large-mnli`) is used via Hugging Face.
* This model is suitable for **zero-shot classification**, allowing predictions without task-specific training.

---

### 3. Zero-Shot Learning

* The model classifies tickets based only on predefined labels.
* No prior examples or training are provided.
* Serves as the **baseline model**.

---

### 4. Few-Shot Learning

* Example tickets and their labels are included in the input prompt.
* Helps guide the model toward better contextual understanding.
* Improves classification performance compared to zero-shot.

---

### 5. Fine-Tuning (Simulated)

* Since full fine-tuning requires large datasets and computational resources, a **rule-based enhancement** is implemented:

  * Keywords (e.g., "login", "payment") are mapped to specific categories
* These rules are combined with model predictions to simulate fine-tuned behavior.

---

### 6. Prediction Strategy

* For each ticket:

  * The model outputs probability scores for all tags
  * The **top 3 highest-scoring tags** are selected as final predictions

---

### 7. Evaluation

* A simple accuracy metric is used:

  * A prediction is considered correct if the **true label appears in the top 3 predicted tags**
* Performance is compared across:

  * Zero-shot
  * Few-shot
  * Fine-tuned approaches

---

##  Key Results / Observations

* **Zero-shot learning** provides reasonable predictions without training but may lack precision.
* **Few-shot learning** improves accuracy by incorporating contextual examples.
* **Fine-tuned (simulated) approach** achieves the best performance by combining rule-based logic with model predictions.

###  Performance Trend:

Zero-shot < Few-shot < Fine-tuned

###  Insights:

* Including examples significantly improves model understanding
* Rule-based enhancements help capture domain-specific patterns
* Effective NLP solutions can be built using open-source models

---

##  Conclusion

This project demonstrates the practical use of LLMs for **automated support ticket classification**. By combining zero-shot, few-shot, and simulated fine-tuning techniques, the system achieves improved accuracy and reliability.

The solution is scalable and can be extended to real-world applications such as:

* Customer support automation
* Helpdesk ticket routing
* AI-powered chat systems

---
