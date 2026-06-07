## Felipe Toro

**The bridge between executive strategy and production ML.**

I'm a cost & pricing strategist from a highly regulated industry now building production AI/ML systems. Eight years of executive-level finance experience, $300M+ in proposals defended against federal auditors, and an M.S. in Artificial Intelligence and Business Analytics underway at USF.

The audit-defensibility, schema-as-contract discipline, and cost-aware decision frameworks I built in that environment transfer directly to financial services AI/ML.

---

### Production work, audit-defensible by construction

**[AML Compliance Platform](https://github.com/FelipeToroG/aml-transaction-monitoring)**

End-to-end production AML transaction monitoring service for payments platforms. Hybrid scoring (Isolation Forest anomaly head plus calibrated XGBoost supervised classifier) on the IBM AML HI-Small dataset (~5M transactions). Cost-weighted Precision@k optimization tuned to investigator review capacity, not academic AUC. Claude-powered case narratives where every claim cites a specific transaction or feature value from the alert evidence bundle. FastAPI service with Pydantic v2 contracts, Streamlit investigator UI, Langfuse plus Prometheus observability, PSI drift detection, segment fairness audit. 35 pytest tests. Multi-stage Docker.

> The finding I didn't expect: production AML is rate-limited by investigator review capacity, not by model discrimination. A 0.92 AUC-PR model with 4x the alert volume is undeployable. The right metric is cost-weighted Precision@k at the team's daily review capacity. Standard ML literature ranks by AUC; production ranks by investigator hours.

| Outcome | Value |
|---------|-------|
| Test Precision@k | 0.547 at k=384 alerts/day |
| Lift over random alerting | ~270x |
| Test recall | 13.5% (capacity-bound by design) |
| Selected family | XGBoost (Optuna sweep across 4 families) |
| Salvage recovery time | 1.5 hours (vs 25 hours for clean restart) after a documented Optuna hang |
| Test suite | 35/35 passing |
| Inference target | < 150ms p99 on scoring path |

---

**[ML Fraud Detection Pipeline](https://github.com/FelipeToroG/ml-fraud-detection-pipeline)**

Production-grade ML system for credit card fraud detection. XGBoost selected on expected dollar cost rather than AUC-PR. Cost-optimized threshold tuning reduces expected loss by 20% on the held-out test set. FastAPI inference service with SHAP attribution per prediction. 19 pytest contract tests. Multi-stage Docker build.

> The finding I didn't expect: AUC-PR ranking and cost ranking diverged. A team selecting on AUC-PR alone could ship a model that costs more in production than a "weaker" alternative.

| Outcome | Value |
|---------|-------|
| Fraud caught | 86.1% (118 of 137 cases) |
| Precision | 81.9% |
| AUC-PR | 0.877 |
| Savings vs naive threshold | $646 per evaluation period (20% reduction) |
| API latency | < 100ms p99 |
| Test coverage | 19/19 passing |

---

### Tech stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-006ACC?style=flat&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-9ACD32?style=flat&logoColor=white)
![CatBoost](https://img.shields.io/badge/CatBoost-FFCC00?style=flat&logoColor=black)
![Optuna](https://img.shields.io/badge/Optuna-005F73?style=flat&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat&logo=mlflow&logoColor=white)
![SHAP](https://img.shields.io/badge/SHAP-8B0000?style=flat&logoColor=white)
![Claude](https://img.shields.io/badge/Claude-D97757?style=flat&logo=anthropic&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![Langfuse](https://img.shields.io/badge/Langfuse-2E2E2E?style=flat&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)

---

### What makes the work different

**Cost-aware model selection.** Industry default is to pick on F1 or AUC-PR. Operating under federal audit taught me that the right metric is always dollars or hours. The fraud project uses expected loss as the selection criterion; AML uses cost-weighted Precision@k at the team's daily review capacity. The model that wins on AUC-PR is not always the model that wins on cost.

**Zero-leakage by construction.** The preprocessing pipeline is fit inside cross-validation, not before. Feature engineering is causal-windowed and safe to compute before the temporal split. Data leakage is mathematically impossible. This is the engineering equivalent of an internal control. The system enforces correctness rather than relying on the engineer to remember it.

**Schema as contract.** API endpoints use Pydantic v2 with extra=forbid, so unknown fields are rejected at the boundary. Model artifacts are schema-versioned and refuse to load against a service running a different schema. LLM outputs are discriminated unions with XOR invariants. Drift between training, serving, and downstream consumers is impossible to ship by accident. This is what auditable software looks like.

**Explainability is not optional.** Every fraud prediction returns SHAP attribution. Every AML alert ships with a citation-grounded case narrative where every factual claim references a specific transaction ID or feature value from the evidence bundle. Production fraud systems, healthcare decisions, and credit models all face regulatory pressure to explain themselves. I built it in from the start because I've seen what happens when a model cannot.

**Failure response is a deliverable.** The AML project's Optuna sweep hung indefinitely on a Logistic Regression hyperparameter pathology at hour 19 of 25. I diagnosed it via MLflow run inspection, killed the process, and wrote a salvage driver that recovered the winning XGBoost hyperparameters and completed the downstream pipeline in 1.5 hours rather than restarting the full sweep. The incident is documented in the repository with five carry-forward lessons. Production ML systems must be able to recover from partial completion; the salvage script is now a permanent fixture of the repo.

---

### Education

**M.S. Artificial Intelligence and Business Analytics.** University of South Florida (expected 2027). Focus: production AI systems and applied ML.
**B.S. Industrial Engineering.** University of South Florida (2021)
**Six Sigma Green Belt.** American Society for Quality

---

### Currently evaluating opportunities

ML/AI Engineer, Data Scientist, and Applied AI roles where domain knowledge multiplies engineering work. Strongest fit with companies in fintech, SaaS, e-commerce, and manufacturing.

**Reach me:** [LinkedIn](https://linkedin.com/in/felipe-toro-g) · ftoro26@gmail.com

---

<a href="https://github.com/FelipeToroG">
  <img src="https://github-readme-stats.vercel.app/api?username=FelipeToroG&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&hide=stars&card_width=400" alt="Felipe Toro's GitHub stats"/>
</a>
