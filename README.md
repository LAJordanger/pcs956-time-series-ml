# PCS956 – Time Series for Machine Learning

From Forecasting to Classification, Anomalies, Drift, Multivariate Structure, and Robust Evaluation

Instructor: Lars Arne Jordanger, Western Norway University of Applied Sciences (HVL), Norway
Course level: PhD

This repository contains materials for the time series module of PCS956 – Research Trends in Applied Machine Learning.

---

## Course Overview

This module introduces time series for applied machine learning, with emphasis on:

- understanding temporal data and its structure,
- building and evaluating forecasting and classification models responsibly,
- detecting anomalies and concept drift,
- working with multivariate and nonlinear dependence,
- avoiding common pitfalls such as leakage, spurious correlations, and misleading transformations.

Many PhD projects work with temporal data from domains such as energy systems, environmental monitoring, industrial sensors, medical signals, and astrophysics. Standard ML tools often assume independent and identically distributed (i.i.d.) data, but time series break this assumption. Uncritically applying powerful models to temporal data can give misleading conclusions.

A central message of the module is:

> Time series models must be evaluated against strong baselines, under proper temporal validation, with explicit attention to data quality, anomalies, drift, transformations, and multivariate structure. High predictive scores alone are not enough.

For PhD-level work, high predictive scores are necessary but not sufficient; you must demonstrate robustness to temporal structure, drift, and anomalies, and show that your model outperforms strong baselines and appropriate random-walk-like reference models.

The course combines conceptual foundations, visual exploratory data analysis (EDA), decomposition, classical statistical models, ML models for forecasting and classification on time series, anomaly detection, multivariate tools, explainability, and project-based learning. High-level research trends (for example causal decompositions, nonlinear spectral methods, and Kolmogorov–Arnold Networks) are discussed for PhD inspiration, but not required for the mini-project.

We do **not** assume prior specialised training in time-series analysis. The module focuses on:

- intuitive understanding of trend, seasonality, residuals, stationarity, chaos vs randomness;
- practical use of transformations and decomposition, and careful mapping back to the original scale;
- robust baselines, temporal validation, and critical interpretation of results;
- awareness that **not all time-series work is about forecasting** – classification, anomaly detection, change-point analysis, and structural modelling are equally important.

---

## Learning Outcomes

By the end of the module, students should be able to:

- Describe basic time series concepts: temporal indexing, trend, seasonality, residuals, chaos vs randomness, and stationarity.
- Perform visual EDA and simple decomposition on univariate and multivariate time series.
- Construct and evaluate forecasting baselines (naive, persistence, seasonal, simple AR).
- Explain the structure and assumptions of classical forecasting models (ARIMA and related families) sufficiently to choose appropriate baselines and transformations, and to recognise when these models are misapplied.
- Frame time series forecasting as supervised learning with lagged and engineered features, and understand how to cast classification and anomaly-detection problems into supervised-learning form on temporal data.
- Design temporal train/validation/test splits and avoid leakage from the future.
- Evaluate models on levels vs differences, using baselines and residual analysis, and interpret $R^2$ and related metrics **critically** in temporal settings, including the effects of autocorrelation and non-stationarity. Understand that negative test $R^2$ implies the model is worse than simple mean or persistence baselines.
- Apply and track transformations (differences, logs, detrending, deseasonalising), and correctly connect predictions on transformed or residual scales back to the original series.
- Identify anomalies and concept drift, and discuss model maintenance and retraining strategies.
- Recognise multivariate and nonlinear dependence, and understand risks of spurious correlations and non-stationarity.
- Use basic tools for cross-correlation and Granger-style predictive “causality”, recognising that these are about predictive relationships rather than strong causal inference, and maintaining a sceptical view of causal claims.
- Reason critically about whether a series contains exploitable structure or is close to random-walk-like.
- Document data quality, assumptions, limitations, transformation chains, and drift considerations in a small time series project, including a short critical reflection on data limits and robustness of conclusions.

---

## Module Structure (Indicative)

### TS1 – Foundations, EDA, Decomposition, Transformations, and Modelling Pitfalls

- Time series basics, temporal indexing, univariate vs multivariate series.
- Visual EDA: raw plots, differences, anomalies, rare events, regime changes.
- Trend/seasonality/residual decomposition and simple parametric fits.
- Transformations (differences, logs) and the need to map predictions back to the original scale.
- Stationarity, random-walk intuition, chaos vs randomness.
- Modelling scepticism: why “data + model = publish” is not acceptable; illusions of skill on autocorrelated data; honest use of baselines and performance metrics (including $R^2$).

### TS2 – Forecasting Baselines, Classical/ML Models, Temporal Validation, Leakage

- Baselines (naive, persistence, seasonal, simple AR) as mandatory benchmarks.
- Classical forecasting models (AR/MA/ARIMA) and ML models with lagged features and exogenous variables.
- Time series as supervised learning; feature engineering, windowing, and handling exogenous inputs.
- Temporal validation, leakage, and robust evaluation on levels vs differences (including careful use of $R^2$, RMSE, MAE, MAPE).
- Evaluating models relative to baselines and on appropriate transformed/original scales. Students are expected to compare ML models not only against each other but against simple statistical baselines and random-walk-like reference models.

### TS3 – Anomaly Detection, Concept Drift, Multivariate/Nonlinear Dependence, Explainability, Research Trends

- Point, contextual, and collective anomalies in time series; examples from domains such as energy systems and seismic data (e.g. earthquakes vs underground nuclear tests).
- Concept drift, monitoring, and retraining strategies; “maintenance, not train-once-and-forget”.
- Multivariate and nonlinear dependence; spurious correlations, cross-correlation, Granger-style tools.
- Tags, metadata, and contextual features; explainability for time-series models and cross-module links (Causal Intelligence, Explainable AI, Evaluation & Uncertainty).
- High-level research trends (causal decompositions, nonlinear spectral/time-series-to-image methods, Kolmogorov–Arnold Networks) and sceptical evaluation of new methods.

### Time-Series Mini-Project

- One dataset, one main question — **not necessarily forecasting**. Acceptable topics include forecasting, classification (e.g. seismic event type), anomaly/change-point detection, or simple structural modelling.
- At least one baseline + one main model.
- Focus on narrative: data quality, transformations and how predictions are mapped back to the original series, assumptions, drift, multivariate/contextual features, and whether the model truly beats persistence and seasonal baselines (or other simple classifiers, in classification tasks).
- Include a short critical reflection on the limits of the data, possible concept drift, and how sensitive conclusions are to assumptions about stationarity and transformations.

---

## Repository Contents

This public repository is intended to host:

- Selected lecture notebooks and example code for time-series ML (including TS1 and companion notebooks such as `PCS956-TS-companion_A/B/C`).
- Minimal datasets or pointers to open datasets used in examples (for instance, publicly available climate, energy, or seismic data).
- Project guidelines and templates for the time-series mini-project.
- Optional further-reading and online resources.

Additional SOURCE files, generator scripts, and instructor notes live in a separate private
teaching repository. This public repo contains only the materials intended for open use.

### Current Status of Materials

The materials for this module are being developed and refined during Spring 2026.

- The main lecture notebook **TS1** is essentially ready for teaching, although minor tuning may still occur.
- The companion notebook **PCS956-TS-companion_A** (basic EDA on time series) is expected to be available for the first lecture.

Additional lectures (TS2, TS3) and companion notebooks (B/C) will be added or updated as the module progresses. Students should expect occasional updates to notebooks and example code, but the core methodological stance and learning outcomes are stable.

---

### Companion Notebooks and Code Templates

The main lecture notebook TS1 focuses on concepts and short illustrative examples. Reusable code
and project-oriented workflows are provided in companion notebooks, as referenced in Section 10 of
TS1:

- `PCS956-TS-companion_A`
  Inspection and exploratory analysis of time-series data: plotting, basic transformations,
  simple decomposition, and data-quality checks.

- `PCS956-TS-companion_B`
  Classical time-series models and simple forecasting baselines: AR/MA/ARIMA fits, persistence
  baselines, and examples of evaluation on levels vs differences.

- `PCS956-TS-companion_C`
  Machine-learning methods for time series and time-aware validation schemes: supervised-learning
  formulations with lagged features, walk-forward validation, and comparisons against baselines.

These notebooks contain code templates for:

- applying transformations and decomposition,
- fitting models on residuals or transformed series,
- reconstructing forecasts and diagnostic plots on the original scale,

and are intended as starting points for the time-series mini-project rather than complete solutions.
Students are encouraged to adapt and extend them for their own datasets and research questions.

---

## Suggested Reading (Indicative)

Suggested reading and references will be provided **inside the lecture and companion notebooks**
(TS1, TS2, TS3, and `PCS956-TS-companion_A/B/C`). Each notebook will include:

- topic-specific references (classical time-series texts, ML-oriented resources, survey papers),
- optional further reading aligned with the examples and exercises in that notebook.

This README does not list specific books or papers; students should consult the individual notebooks
for up-to-date, context-specific reading suggestions.

---

## Notes

The course materials are actively maintained and may be updated before or during teaching.
Examples, notebooks, references, and project instructions may change to reflect
student backgrounds, available time, and recent developments in time-series ML.

---

## Authoring and Tools

Parts of these materials (including the README and lecture notebooks) were drafted or refined with
the assistance of large language models (for example ChatGPT), based on existing lecture notes and
domain expertise. The instructor is responsible for all content, and AI-generated text has been
reviewed and edited for accuracy, coherence, and alignment with the module’s methodological stance.
