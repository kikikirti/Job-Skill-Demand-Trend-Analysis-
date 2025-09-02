# Job Skill Demand — Trend Analysis & Forecasting  

**Author:** Kirti Gupta  
**Course:** Minor in Artificial Intelligence  
**Date:** August 2025  
**Dataset:** Kaggle — [LinkedIn Job Postings](https://www.kaggle.com/datasets/arshkon/linkedin-job-postings)  

---

## 📌 Project Overview  
This project analyzes **job skill demand trends** using LinkedIn job posting data.  
The pipeline includes:  

- **Data cleaning & salary harmonization**  
- **Series construction** (daily/weekly skill demand)  
- **Baselines**: Naive, Moving Average, SES, ARIMA  
- **Prophet forecasting** with short-horizon evaluation  
- **Classification mini-task**: predict if demand trends up next day  
- **Hyperparameter tuning demo**  
- **Visualization & saved artifacts**  

---

## 📂 Repository Structure  

```
.
├── trend-analysis.ipynb            # Main analysis notebook
├── PROJECT_CARD.json               # Project metadata (problem, objectives, deliverables)
├── requirements.txt                # Dependencies
├── ENVIRONMENT.json                # Environment info (optional, Kaggle/local reproducibility)
├── README_NOTEBOOK.md              # This file
├── artifacts/                      # Saved outputs
│   ├── metrics_multi_skill_D.csv
│   ├── advanced_adaptive_results.csv
│   ├── prophet_daily_metrics.csv
│   ├── prophet_daily_forecasts.csv
│   ├── prophet_weekly_metrics.csv
│   ├── prophet_weekly_forecasts.csv
│   ├── engineering_model_comparison_polished.csv
│   ├── engineering_forecast_vs_actuals_polished.png
│   ├── engineering_trend_classification_results.jsonl
│   ├── engineering_trend_classification_predictions.csv
│   └── engineering_tiny_holdout_probs.png
```

---

## 📊 Key Outputs  

### Baseline & Classical Models  
- `metrics_multi_skill_D.csv` — Daily baselines (Naive, MA, SES) across top skills  
- `advanced_adaptive_results.csv` — Rolling CV results (Naive, MA, SES, ARIMA)  

### Prophet Forecasting  
- `prophet_daily_metrics.csv` / `prophet_daily_forecasts.csv`  
- `prophet_weekly_metrics.csv` / `prophet_weekly_forecasts.csv`  

### Engineering Skill (focus example)  
- `engineering_model_comparison_polished.csv`  
- `engineering_forecast_vs_actuals_polished.png`  

### Classification  
- `engineering_trend_classification_results.jsonl`  
- `engineering_trend_classification_predictions.csv`  
- `engineering_tiny_holdout_probs.png`  

### Metadata  
- `PROJECT_CARD.json`  

---

## 📝 How to Reproduce  

1. Clone this repo / open in Kaggle  
2. Run `trend-analysis.ipynb` end-to-end (saves all artifacts into `/artifacts` or `/kaggle/working`)  
3. View saved CSVs & plots for analysis  

---

## 🎯 Conclusion  
- SES often rivals Prophet on short histories  
- Forecasting horizons are challenging with sparse data  
- Classification task is data-limited but demonstrates threshold tuning  
- All outputs are reproducible and packaged for submission (notebook + JSON + artifacts)  
