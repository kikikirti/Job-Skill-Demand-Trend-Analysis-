# Job Skill Demand — Trend Analysis & Short-Horizon Forecasting

**Author:** Kirti Gupta • **Course:** Minor in AI • **Date:** Aug 2025

This project analyzes LinkedIn job postings to track skill demand and produce short-horizon forecasts.
Pipeline: cleaning & salary harmonization → daily/weekly series → baselines (Naive/MA/SES/ARIMA) vs Prophet → compact classification (“trend up” vs “not up”) with accuracy-tuned threshold and walk-forward CV fallback.

## Quick start
- Open `notebook.ipynb`, run all cells. Artifacts are written to `./artifacts/`.
- Data source: Kaggle dataset “LinkedIn Job Postings”.

## Key artifacts
- Forecast metrics: `metrics_multi_skill_D.csv`, `prophet_*_metrics.csv`
- Forecasts: `prophet_*_forecasts.csv`
- Engineering comparison: `engineering_model_comparison_polished.csv`
- Plot: `engineering_forecast_vs_actuals_polished.png`
- Classification: `engineering_trend_classification_results.jsonl`, `..._predictions.csv`, `..._tiny_holdout_probs.png`
- Project metadata: `PROJECT_CARD.json`

## Methods
- Baselines: Naive, moving average, SES, ARIMA (rolling CV).
- Prophet: daily & weekly tails; additive seasonality; changepoint prior tuning demo.
- Classification: logistic pipeline (standardize + class_weight balanced), accuracy-oriented threshold tuning, walk-forward CV when test is tiny.

## Results (summary)
- SES competitive with Prophet on short histories; Prophet improves with richer seasonality.
- Trend classification stable at small sample sizes using per-fold tuning in walk-forward CV.

## Limitations & next steps
- Limited history ⇒ high variance; consider weekly aggregation and longer lookbacks.
- Add features: weekday, region, holidays, macro signals.
- Try pooled/hierarchical models across skills.

## Reproducibility
- See `requirements.txt`. 
- All CSV/PNG outputs are deterministic given the dataset snapshot.
