# Predicting Customer Complaints: A Proactive Approach to Service Delivery

> **Disclaimer:** This project is a personal case study that replicates the methodology from a project I completed in a professional capacity. The code has been rewritten, and the original proprietary data has been replaced with a synthetic, anonymized dataset to protect confidentiality and intellectual property.

## 1. The Business Problem

In the property management sector, a rising number of repair-related complaints presents a significant operational and financial challenge. This trend indicates resident dissatisfaction often driven by delays and unresolved issues.

This project moves beyond a reactive complaint management model. By leveraging machine learning on historical repair and complaint data, the goal is to **proactively identify repair jobs at high risk of becoming a formal complaint**. The developed model assigns a "Complaint Risk Score" to open repair jobs, enabling the business to:

* **Intervene early** with targeted support for high-risk cases.
* **Enhance resident satisfaction** and experience.
* **Improve operational efficiency** by allocating resources effectively.
* **Reduce the volume and cost** associated with formal complaints.

---
## 2. Methodology

The project followed a structured machine learning workflow from feature engineering to model evaluation.

#### **a. Feature Engineering**
The initial dataset was enriched with features designed to capture signals of potential customer friction:
* **`Time_to_Resolution`**: The total duration a repair job was open.
* **`Chaser_Count`**: The total number of follow-up calls or emails for a specific repair job.
* **`SLA_Breach_Flag`**: A binary flag indicating if the resolution time exceeded internal targets.
* **`Property_Complaint_History`**: The number of prior complaints associated with the property.

#### **b. Model Selection**
Several models were evaluated to find the best balance between performance and interpretability. Given the imbalanced nature of the dataset (complaints are rare), **XGBoost was ultimately selected**. It significantly outperformed a baseline Logistic Regression model by capturing complex, non-linear interactions between features, providing a **15% uplift in AUC-ROC score**.

#### **c. Evaluation**
The model's performance was measured using metrics suited for imbalanced classification:
* **AUC-ROC:** 0.88
* **Recall:** 0.72 (Successfully identified 72% of all actual complaints)
* **Precision:** 0.76 (76% of jobs flagged as high-risk resulted in a complaint)

---
## 3. Results & Business Impact 🚀

The model provided critical, data-driven insights that directly informed business strategy.

* **Key Insight**: The analysis revealed that the complaint risk increased by over **200% after the second "chaser" call** from a resident. This identified a clear, critical window for proactive intervention.

* **Business Impact**: A simulation based on the model's performance on the test data predicted that a proactive intervention program could **prevent up to 400 formal complaints per year**. This translates to a projected annual saving of **£120,000** in administrative and resolution costs, while significantly improving the resident experience.
