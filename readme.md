# Non-Invasive Glucose Tracking Device

A wearable, non-invasive glucose monitoring system using **Near-Infrared (NIR) spectroscopy** and machine learning to estimate blood glucose levels without skin penetration.

---

## Motivation

Conventional glucose monitoring solutions such as microneedle patches and Continuous Glucose Monitors (CGMs) are invasive, costly, and require frequent sensor replacement. These factors reduce long-term usability and accessibility.

This project explores a **light-based, reusable, and comfortable alternative** that continuously tracks glucose levels using NIR spectroscopy, improving convenience and affordability for users requiring frequent monitoring. :contentReference[oaicite:0]{index=0}

---

## Core Idea

Glucose absorbs light differently at specific wavelengths.  
At **~940 nm**, glucose exhibits higher absorption, resulting in lower reflected light intensity at higher glucose concentrations.

We leverage this property by:
- Capturing multi-channel NIR signals (410–940 nm)
- Processing and correlating them with ground-truth CGM readings
- Training regression models to estimate glucose levels

---

## System Overview

### Hardware
- Wrist-worn prototype mounted on a tennis band
- NIR LEDs and receivers covering 410–940 nm
- Bluetooth-enabled microcontroller
- Samsung 18650 rechargeable battery (≈2 days operation)

### Data Acquisition
- Sampling every **5 minutes** (~300 samples/day)
- Real-time transmission via **Bluetooth (NRF Connect)** and UART
- Prospective, continuous monitoring setup

---

## Data Processing Pipeline

1. **Raw Signal Collection**
2. **Z-Score Normalization**
3. **Outlier Detection & Removal**
4. **Feature Engineering**
5. **Correlation Analysis**
6. **Model Training & Evaluation**

Visualization techniques include:
- Correlation heatmaps
- Pair plots
- Box plots across channels
- Residual analysis

---

## Models Evaluated

- CLS Calibration
- Partial Least Squares (PLS) Regression
- Ridge Regression
- Polynomial Ridge Regression
- Support Vector Regression (SVR)
- Random Forests

Performance was evaluated using **R²**, **RMSE**, and residual diagnostics across channels and datasets.

---

##  Results

- Best models achieved **R² up to ~0.87** on curated data
- Feature engineering and normalization reduced noise variance significantly
- Strong correlation observed between select NIR channels and CGM readings
- Model performance degrades with larger, noisier datasets, highlighting sensor and data-quality constraints

---

## Challenges & Limitations

- Sensor sensitivity and placement consistency
- Thermal effects during initial operation
- Motion artifacts and sweating
- Limited dataset size
- Generalization across users

---


##  References & Resources

- 📓 Kaggle Notebook:  
  https://www.kaggle.com/code/attrishubham/non-invasive-glucose-tracking/notebook

---


