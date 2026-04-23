# AI-Assisted Emergency Triage System

## Overview

This project builds an AI-assisted triage system that analyzes patient vital signs to predict admission risk. It combines machine learning, rule-based safety checks, and explainable AI to support faster and safer triage decisions.

## Problem

Emergency departments face delays, overcrowding, and inconsistent triage. These issues increase the risk of under-triaging critical patients.

## Solution

The system:

* Collects patient vitals through a UI
* Computes clinical indicators (Shock Index, Hypoxia, Fever)
* Predicts admission risk using ML models
* Applies safety overrides for critical conditions
* Requires nurse confirmation for high-risk cases

## Models

* Logistic Regression (primary, interpretable)
* Decision Tree
* XGBoost

Explainability is handled using SHAP.

## Features

* Real-time vital analysis
* Derived indicators:

  * Shock Index (HR / SBP)
  * Hypoxia flag (SpO₂ < 92)
  * Fever flag (Temp ≥ 38)
* Safety rules:

  * SBP < 90
  * SpO₂ < 90
  * Shock Index > 1
* Human-in-the-loop validation
* SHAP-based explanations

## Tech Stack

Python, pandas, numpy, scikit-learn, XGBoost, SHAP, Streamlit, HTML/CSS

## Explainability

SHAP is used to explain predictions:

* Blue values decrease risk
* Red values increase risk

![SHAP Force Plot](images/shap_plot.png)

## Feature Importance

Key predictors include SBP, SpO₂, and temperature. Abnormal values push predictions toward higher risk.

![SHAP Summary](images/shap_summary.png)

## Screenshots

Vitals input interface:
![Input](images/input.png)

Model output dashboard:
![Output](images/output.png)

## Project Structure

```id="3q6qjy"
ai-triage-bot/
├── data/
├── notebooks/
├── app/
├── docs/
├── images/
├── models/
├── requirements.txt
├── README.md
└── .gitignore
```

## Model Artifacts

* models/triage_logreg_model.pkl
* models/triage_scaler.pkl

Used for inference without retraining.

## Run

```id="m1oz0u"
git clone https://github.com/YOUR_USERNAME/ai-triage-bot.git
cd ai-triage-bot
pip install -r requirements.txt
jupyter notebook
```

## Author

Komala Belur Srinivas
MS Computer Science (AI), Hofstra University
