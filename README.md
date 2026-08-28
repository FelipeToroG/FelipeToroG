## Felipe Toro

*M.S. in AI & Business Analytics (May 2027)*

The bridge between executive strategy, analytics & AI/ML implementation.

I'm a Business Intelligence Engineer and Pricing Team Lead with 8+ years across analytics, pricing, and finance. Built the BI function at an aerospace and defense manufacturer, present pricing strategy and analytics to the CEO and executive team, and defended 30+ TINA-compliant cost packages through federal audits with a 100% pass rate. Secured $300M+ in revenue through proposal pipeline work.

The audit-defensibility, schema-as-contract discipline, and cost-aware decision frameworks I built in that environment transfer directly to fintech, SaaS analytics, and any environment where a number has to survive scrutiny.

---

**[Claude-Powered AML Transaction Monitoring & Alert Triage Platform](https://github.com/FelipeToroG/aml-transaction-monitoring)**

End-to-end production AML transaction monitoring service for payments platforms. Hybrid scoring stacks an Isolation Forest anomaly score as a feature into a calibrated LightGBM classifier, trained on the IBM AML HI-Small dataset (~5M transactions). Cost-weighted Precision@k optimization tuned to investigator review capacity, not academic AUC. Claude-powered case narratives where every claim cites a specific transaction or feature value from the alert evidence bundle. FastAPI service with Pydantic v2 contracts, Streamlit investigator UI, Langfuse plus Prometheus observability, PSI drift detection, segment fairness audit. 53 pytest tests. Multi-stage Docker.

> The finding I didn't expect: production AML is rate-limited by investigator review capacity, not by model discrimination. A 0.92 AUC-PR model with 4x the alert volume is undeployable. The right metric is cost-weighted Precision@k at the team's daily review capacity. Standard ML literature ranks by AUC; production ranks by investigator hours.

| Outcome | Value |
|---------|-------|
| Test Precision@k | 0.91 at k=384 alerts/day |
| Lift over random alerting | ~445x |
| Test recall | 22.4% (capacity-bound by design) |
| Selected family | LightGBM (Optuna sweep: XGBoost + LightGBM) |
| Test suite | 53/53 passing |
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

- **Cost-aware model selection**
- **Zero-leakage by construction**
- **Schema as contract**
- **Explainability is not optional**
- **Failure response is a deliverable**

Full reasoning behind each principle is in the project READMEs.

---

### AI-augmented practice

I don't just build AI systems, I use AI as a daily development partner and lead its adoption at my company.

- **Building with AI:** Ship production ML and GenAI systems with Claude API, FastAPI, Docker, and full observability. Details in the projects above.
- **Working with AI:** Use Claude daily as a collaborative development partner for DAX authoring, Python analytics, Power Query optimization, ERD documentation, and system design. Ship faster, document better, catch more edge cases.
- **Driving AI adoption:** Coordinating Microsoft Copilot GCC High rollout at a federal contractor with CMMC compliance constraints. Trained executives and 10+ managers on Copilot for meeting minutes and process documentation, and on Claude for proposal narratives and action-item extraction.

The interesting problem isn't whether to use AI. It's how to use it responsibly in environments where every output has to survive audit.

---

### Education

- **M.S. Artificial Intelligence and Business Analytics**<br>University of South Florida (expected May 2027)<br>Focus: AI & Machine Learning Modeling, AI Strategy & Analytics Engineering
- **B.S. Industrial Engineering**<br>University of South Florida (2021)<br>Focus: applied ML, quantitative analysis, statistics, process improvement
- **Six Sigma Green Belt**<br>American Society for Quality

---

### Currently evaluating opportunities

Business Intelligence, Analytics Engineering, Pricing Analytics, and Applied ML roles across fintech, SaaS, and defense.

**Reach me:** [LinkedIn](https://linkedin.com/in/felipe-toro-g) · <ftoro26@gmail.com>
