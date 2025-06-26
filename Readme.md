🏦 Credit Risk Classification Engine with Explainability & Fairness Audits
🔍 Project Summary
This project builds a full-stack, explainable AI pipeline to assess credit risk using real-world-like features from the UCI Credit Approval dataset. It includes:

Binary classification (Approve/Deny) via XGBoost

SHAP-based interpretability

Risk bucketing + business rule overrides

Fairness auditing & disparate impact analysis

Anomaly detection + temporal features

Cluster-based risk insights & cost-sensitive retraining

🚀 Key Features
Feature	Description
🧠 Models	Logistic Regression, Random Forest, XGBoost
📈 Performance	Accuracy: 90.6% · F1: 89.1% · ROC AUC: 94.6%
🪄 Explainability	SHAP beeswarm + waterfall plots + top-3 feature logging
⚖️ Fairness	Disparate impact check by demographic proxy (A1)
📊 Risk Logic	Probability → Risk Bucket → Override (business logic)
🕵️‍♂️ Anomaly Detection	Isolation Forest on feature signals
🕰 Temporal Intelligence	Time since last high-risk, rolling 24h approval avg
🧪 Custom Features	Credit utilization, new customer flag, missed payment flag
🧠 Clustering	KMeans clusters for behavioral grouping
💸 Cost-Sensitive Modeling	XGBoost tuned with scale_pos_weight to balance approvals

📁 File Structure
r
Copy
Edit
📦 credit-risk-model/
│
├── Credit_risk.ipynb         <- Main notebook (Jupyter pipeline)
├── crx.data                  <- Raw UCI dataset
├── crx.names                 <- Dataset metadata
├── credit.lisp / credit.names / Index  <- Dataset docs
├── Credit_risk.pdf           <- Exported notebook for offline viewing
├── README.md                 <- You're here :)
🛠️ Tech Stack
Language: Python 3.10+

ML Models: XGBoost, Random Forest, Logistic Regression

Explainability: SHAP

Visualization: Matplotlib, Seaborn

Preprocessing: scikit-learn (LabelEncoder, StandardScaler, SimpleImputer)

Extras: KMeans, IsolationForest, StratifiedKFold, datetime

🧪 Example Outputs
📊 SHAP Beeswarm

💧 SHAP Waterfall (Sample Prediction)

📋 Classification Report
yaml
Copy
Edit
Accuracy: 0.906
Precision: 0.91
Recall: 0.87
F1 Score: 0.89
📈 Business Rules Logic
python
Copy
Edit
if approval_prob >= 0.6:
    decision = "Approve"
else:
    decision = "Manual Review"

# Override for high risk
if risk_bucket == "High Risk":
    final_decision = "Deny"
📉 Fairness Evaluation
Disparate impact was measured on the A1 feature:

python
Copy
Edit
Disparate Impact (A1): 0.028
A low disparity suggests minimal bias between demographic groups.

🧠 Future Improvements
Streamlit UI for credit officer decision-support

Deployment via Docker + REST API

Integration with vector DB for audit trail storage

LLM summarizer for SHAP explanations

👤 Author
Anirudh Reddy Ninganpally
GitHub Portfolio
💼 Open to Data Analyst / ML Engineer roles

📜 License
This project is released under the MIT License.