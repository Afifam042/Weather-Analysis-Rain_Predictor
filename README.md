# 🌧️ PrecipPredict: Smarter Rainfall Forecasting with ML & DL

## Project Summary

PrecipPredict is an end-to-end weather analytics solution built to forecast precipitation with high accuracy using both traditional and deep learning techniques. By leveraging a combination of meteorological features and cutting-edge models like Random Forest and LSTM, this project aims to provide reliable rainfall predictions—essential for agriculture, climate research, and environmental planning.

---

## Highlights

- **Dual Modeling Approach**: Implements both Random Forest and LSTM for robust comparison between machine learning and deep learning methods.
- **Smart Feature Selection**: Extracts the most informative weather variables using Random Forest importance scores and PCA for dimensionality reduction.
- **Deep Learning Optimization**: Fine-tunes a 3-layer LSTM network with dropout, learning rate decay, and early stopping for generalization.
- **Performance Benchmarks**:
  - Random Forest RMSE: 0.760 | R²: 0.567
  - LSTM RMSE: 0.641 | R²: 0.697
- **Insightful Visuals**: Includes detailed plots for feature importances, model comparisons, and training diagnostics.

---

## Modeling Breakdown

### Feature Engineering

- **Top Influential Variables**:
  - Specific Humidity at 2 Meters (g/kg)
  - Dew/Frost Point (°C)
  - Relative Humidity (%)
  - Max & Min Temperatures at 2 Meters (°C)

- **Dimensionality Reduction**:
  - PCA reduced 7 input features to 3 principal components while retaining 95% of data variance.

### Random Forest Regressor

- Base Model → RMSE: 0.787, R²: 0.535  
- After Tuning (Grid Search) → RMSE: 0.760, R²: 0.567  
- Best Parameters: `n_estimators=300`, `min_samples_split=10`

### LSTM Neural Network

- Input shape: `(929, 1, 8)`
- Tuned Architecture: [64, 32, 16] LSTM units, 0.2 dropout, LR=0.0005
- Final Test RMSE: 0.641 | R²: 0.697

---

## Key Learnings & Insights

- LSTM outperforms Random Forest by **15.7% in RMSE** and **23% in R²**, demonstrating the benefit of capturing temporal dynamics.
- Humidity-related features dominate the predictive power.
- Dimensionality reduction with PCA offers a more efficient model pipeline with minimal loss of accuracy.

---

## Real-World Application

### Agriculture Decision Support System (ADSS)

**Objective**: Enable data-driven decisions for farmers and agronomists.

- **Functionality**:
  - Predicts short-term rainfall to optimize irrigation
  - Guides planting and harvesting based on weather patterns
- **Tech Stack**:
  - Automated data ingestion → ML inference → User dashboard
- **Benefits**:
  - Water conservation
  - Increased crop yields
  - Risk mitigation for extreme weather


