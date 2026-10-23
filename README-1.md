# Suspicious Login Detection Using Machine Learning

**IBM SkillsBuild Cyber Security 2026 | BharatCares**

## Project overview
An educational cybersecurity prototype that reviews authentication-event features and flags potentially suspicious logins. It combines an Isolation Forest anomaly detector with transparent rule-based triage.

## Important scope note
The notebook generates a **synthetic dataset**. It does not ingest live logs or contain real user data. Its metrics demonstrate the workflow only and must not be presented as validated real-world performance.

## Features
- Reproducible synthetic login-event generation
- Basic exploratory analysis and visualization
- Isolation Forest anomaly detection
- Classification report and confusion matrix
- Explainable risk score with human-review flags
- CSV export of synthetic data and example triage results

## Technology
Python, pandas, NumPy, Matplotlib, scikit-learn, Jupyter Notebook.

## Setup
Python 3.10 or newer is recommended.

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

Open `AdityaKumar_SuspiciousLoginDetection.ipynb` and run all cells from top to bottom. The notebook saves `synthetic_login_events.csv` and `example_triage_results.csv` in the current working directory.

## Dataset
No external dataset is required. The notebook creates 1,000 synthetic records with fields for failed attempts, login hour, new device, unfamiliar IP, geographic distance, account age, and a demonstration label.

## How it works
1. Generate synthetic normal and suspicious examples.
2. Inspect feature distributions.
3. Fit Isolation Forest on training features.
4. Evaluate predictions on a held-out split.
5. Apply simple triage rules and show reasons for review.
6. Export synthetic records and example results.

## Limitations and responsible use
This is a learning prototype, not a production SOC tool. Synthetic examples are simplified and can make the classes easier to separate than real-world activity. A review flag is not proof of an attack. Any real deployment requires authorization, privacy safeguards, representative data, threshold calibration, monitoring for false positives/negatives, and human analyst review.

## Project files
- `AdityaKumar_SuspiciousLoginDetection.ipynb` — complete notebook and code
- `requirements.txt` — Python dependencies
- `AdityaKumar_ProjectReport.docx` — project report
- `README.md` — setup and project overview
