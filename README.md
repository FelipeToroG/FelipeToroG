## Felipe Toro

**The bridge between executive strategy and production ML.**

I'm a defense aerospace pricing strategist building production AI/ML systems. Eight years of executive-level finance experience, $200M+ in proposals defended against federal auditors, and an M.S. in Artificial Intelligence underway at the University of South Florida.

I spent 8+ years operating at the intersection of executive finance, business intelligence, and high-stakes decision-making in aerospace and defense before transitioning into production AI/ML engineering.

---

### Production work, audit-defensible by construction

**[ML Fraud Detection Pipeline](https://github.com/FelipeToroG/ml-fraud-detection-pipeline)**

End-to-end production ML system. XGBoost selected on expected dollar cost rather than AUC-PR. Cost-optimized threshold tuning reduces expected loss by 20% on the held-out test set. FastAPI inference service with SHAP attribution per prediction. 19 pytest contract tests. Multi-stage Docker build.

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
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)

---

### What makes the work different

**Cost-aware model selection.** Industry default is to pick on F1 or AUC-PR. Defense aerospace taught me that the right metric is always dollars. The fraud project uses expected loss as the selection criterion, not academic score. The model that wins on AUC-PR is not always the model that wins on cost. 

**Zero-leakage by construction.** The preprocessing pipeline is fit inside cross-validation, not before. Data leakage is mathematically impossible. This is the engineering equivalent of an internal control. The system enforces correctness rather than relying on the engineer to remember it.

**Schema as contract.** The API rejects unknown fields. The training pipeline imports the same feature list the API validates against. Drift between training and serving is impossible to ship by accident. This is what auditable software looks like.

**Explainability is not optional.** Every prediction returns SHAP attribution. Production fraud systems, healthcare decisions, and credit models all face regulatory pressure to explain themselves. I built it in from the start because I've seen what happens when a model cannot.

---

### The roadmap

Five production-grade projects through 2026. Each one targeted at a different AI & ML engineering competency, each one solving a problem from a domain I actually know.

1. ✅ **ML Fraud Detection Pipeline.** sklearn + XGBoost + FastAPI + Docker + SHAP *(shipped)*
2. **Internal Meeting AI Tool.** Air-gapped transcription using Whisper + Ollama + Streamlit
3. **Contract Intelligence Agent.** LangChain + RAG + Ollama for proposal and contract review
4. **Proposal Cost Model.** Predictive cost estimation from real aerospace pricing patterns
5. **BI Pipeline + Dashboard.** End-to-end ETL with monitoring and alerting
Projects 2 through 5 ship between June and September 2026.

---

### Track record

- **$200M+ in proposals defended** through federal audit. 100% pass rate across 25+ TINA-compliant submissions.
- **Sole pricing analyst and audit POC** for a defense electronics manufacturer. Single source of truth on cost-and-pricing data for the company.
- **Built the BI function from scratch.** Promoted into Sypris Electronics' first-ever Business Intelligence Engineer role in 2025. Architected the Power BI dashboards and SharePoint catalog the C-suite now uses for strategic review.
- **Co-founded and scaled a services business** to 25+ remote staff before joining aerospace. Achieved 35% YoY revenue growth for three consecutive years.
- **450+ compliant proposal submissions** managed end-to-end.

---

### Education

**M.S. Artificial Intelligence and Business Analytics.** University of South Florida (expected 2027)
**B.S. Industrial Engineering.** University of South Florida (2021)
**Six Sigma Green Belt.** American Society for Quality

---

### Currently evaluating opportunities

ML/AI Engineer, Data Scientist & Applied AI roles. Strongest fit with companies in fintech, SaaS, e-commerce & manufacturing.

**Reach me:** [LinkedIn](https://linkedin.com/in/felipe-toro-g) · ftoro26@gmail.com

---

<a href="https://github.com/FelipeToroG">
  <img src="https://github-readme-stats.vercel.app/api?username=FelipeToroG&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&hide=stars&card_width=400" alt="Felipe Toro's GitHub stats"/>
</a>
