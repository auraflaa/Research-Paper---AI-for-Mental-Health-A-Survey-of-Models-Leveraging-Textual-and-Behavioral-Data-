[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)  
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/auraflaa/AI-for-Mental-Health-A-Survey-of-Models-Leveraging-Textual-and-Behavioral-Data/pulls)

# AI for Mental Health: A Survey of Models Leveraging Textual and Behavioral Data

This repository contains the **complete reproducibility and governance package** for the systematic survey:

> **“AI for Mental Health: A Survey of Models Leveraging Textual and Behavioral Data”**

The study examines AI-based detection of **Anxiety, Depression, and Stress (ADS)** using textual and behavioral signals, with a deliberate emphasis on **methodological rigor**, **evaluation validit[...]

This repository is designed to function as a **self-auditing research artifact**, suitable for long-term archival, independent verification, and downstream meta-research.

---

## Abstract

Recent advances in deep learning for ADS detection frequently report substantial performance improvements over classical machine learning approaches. However, through a PRISMA-aligned systematic r[...]

Using paired contrasts across methodologically comparable studies, we observe statistically significant saturation:

* **Wilcoxon Signed-Rank Test:** p = 0.0244
* **Cliff’s Delta:** 0.5950 (large effect size)

To address the persistent gap between **research prototypes** and **deployable clinical systems**, we introduce an **Operational Readiness Checklist (ORC)**—a structured auditing framework for a[...]

---

## Repository Structure

```text
Research-Paper_AI-for-Mental-Health/
├── data/                         # Frozen data layer (archive-safe)
│   ├── screening_log.csv         # PRISMA screening records (N = 92)
│   ├── study_extraction.csv      # Structured extraction & metrics (N = 27)
│   ├── paired_comparisons.csv    # Paired contrasts for saturation testing
│   └── orc_report.csv            # Generated Operational Readiness audit
│
├── scripts/                      # Automation & analysis engine
│   ├── validate_prism.py         # Schema + ID + metric synchronization
│   ├── analyze_saturation.py     # Wilcoxon test, Cliff’s Delta, plots
│   └── generate_orc.py           # Operational Readiness scoring
│
├── figures/                      # Manuscript-ready assets
│   ├── saturation_plot.pdf       # Performance vs. dataset size
│   └── prisma_flow.pdf           # PRISMA 2020 flow diagram
│
├── documents/                    # Methodological governance artifacts
│   ├── QA_Scoring_Rubric.pdf     # Study-level quality assessment rubric
│   └── ORC_Scoring_Guide.pdf     # Operational Readiness Checklist guide
│
├── refs/                         # Primary study PDFs / metadata placeholders
├── requirements.txt              # Python dependencies
├── LICENSE                       # MIT License
└── README.md                     # Project overview & reproduction guide
```

---

## Reproduction Workflow

### 1. Environment Setup

## Environment Setup (All Operating Systems)

### 1. Clone the Repository

```bash
git clone https://github.com/auraflaa/Research-Paper_AI-for-Mental-Health-A-Survey-of-Models-Leveraging-Textual-and-Behavioral-Data.git
cd Research-Paper_AI-for-Mental-Health-A-Survey-of-Models-Leveraging-Textual-and-Behavioral-Data
```

---

### 2. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
```

#### macOS / Linux

```bash
python3 -m venv venv
```

---

### 3. Activate the Virtual Environment

#### Windows (PowerShell)

```bash
venv\Scripts\Activate.ps1
```

> If activation is blocked, run once:
>
> ```bash
> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

#### Windows (Command Prompt)

```bash
venv\Scripts\activate
```

#### macOS / Linux

```bash
source venv/bin/activate
```

You should now see `(venv)` in your terminal prompt.

---

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 5. Deactivate the Virtual Environment (Optional)

```bash
deactivate
```

### 6. PRISMA Data Integrity Validation

This step enforces schema locking, ID synchronization, and numeric consistency across all CSV artifacts.

```bash
python scripts/validate_prism.py
```

**Expected output:**

```
--- PRISMA Data Integrity Validation ---
[PASS] screening_log.csv: Column structure is correct.
[PASS] study_extraction.csv: Column structure is correct.
[PASS] paired_comparisons.csv: Column structure is correct.
[PASS] All paired IDs exist in the extraction ledger.
[PASS] Numeric metrics are synchronized (Baseline logic applied).
--- SUCCESS: All data artifacts verified for archive ---
```

---

### 7. Statistical Analysis — Saturation Hypothesis

Paired non-parametric tests are used to evaluate whether performance gains saturate across increasing model complexity.

```bash
python scripts/analyze_saturation.py
```

**Validated results:**

* Number of paired contrasts: **11**
* **Wilcoxon Signed-Rank Test:** p = 0.0244
* **Cliff’s Delta:** 0.5950 (large effect)

The generated saturation plot is saved to:

```
figures/saturation_plot.pdf
```

---

### 8. Operational Readiness Audit (ORC)

This step generates a machine-readable readiness assessment for each extracted model.

```bash
python scripts/generate_orc.py
```

The output file:

```
data/orc_report.csv
```

classifies models into **CLINICAL READY** or **RESEARCH PROTOTYPE** categories based on transparent, rule-based criteria.

---

## 🛠 Operational Readiness Checklist (ORC)

Each model is evaluated on a **5-point binary checklist**:

1. **Provenance** — Dataset source clearly disclosed
2. **Modality Transparency** — Input unit and granularity defined
3. **Evaluation Rigor** — Cross-validation or subject-independent testing
4. **Bias Mitigation** — No unsafe synthetic oversampling (e.g., SMOTE)
5. **Transparency** — Explicit reporting of sample size (N)

* **Score ≥ 4 / 5:** *CLINICAL READY*
* **Score < 4 / 5:** *RESEARCH PROTOTYPE*

> **Important:**
> “Clinical Ready” denotes **methodological deployability**, not regulatory approval or clinical certification.

---

## Citation

If you use this repository or its findings, please cite:

```bibtex
@misc{MukherjeePandey2025ADS,
  title        = {AI for Mental Health: A Survey of Models Leveraging Textual and Behavioral Data},
  author       = {Mukherjee, Priyangshu and Pandey, Khusboo},
  year         = {2025},
  note         = {Unpublished manuscript and reproducibility package},
  howpublished = {\\url{https://github.com/auraflaa/Research-Paper_AI-for-Mental-Health-A-Survey-of-Models-Leveraging-Textual-and-Behavioral-Data}}
}
```

---

## Maintainer

**Priyangshu Mukherjee**
B.Tech (Hons.), Computer Science & Engineering
RV University

* 📧 Email: **[priyangshumukherjeebtech24@rvu.edu.in](mailto:priyangshumukherjeebtech24@rvu.edu.in)**
* 🔗 LinkedIn: [https://www.linkedin.com/in/priyangshu-mukherjee/](https://www.linkedin.com/in/priyangshu-mukherjee/)
