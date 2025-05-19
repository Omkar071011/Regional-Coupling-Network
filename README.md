# Regional Coupling Network: A Novel Deep Learning Approach for ENSO Forecasting

This repository contains the implementation and findings of a novel deep learning model, the **Regional Coupling Network (RCN)**, developed for accurate and interpretable forecasting of the **El Niño-Southern Oscillation (ENSO)**.

## 📌 Project Summary

ENSO is a key climate phenomenon that causes global weather anomalies. Traditional models struggle to capture its long-term behavior due to the complexity of ocean-atmosphere interactions.

The **Regional Coupling Network** leverages **Graph Convolutional Networks (GCNs)** to model large-scale spatiotemporal dependencies in climate data, improving both accuracy and interpretability over state-of-the-art convolutional and dynamical models.

## 🧠 Model Highlights

- **Graph-based representation** of climate data with learnable connectivity.
- **Spatiotemporal graph convolutional architecture**.
- **Interpretable edge structures** aligning with known ENSO dynamics.
- Trained on NOAA ERSSTv5 data and validated using ONI predictions.

## 📊 Results

| Model                      | 1 Month Lead | 3 Months Lead | 6 Months Lead |
|---------------------------|--------------|----------------|----------------|
| SINTEX-F [34]             | 0.895        | 0.840          | 0.740          |
| CNN [8]                   | 0.9423       | 0.8761         | 0.7616         |
| **Proposed RCN (ours)**   | **0.9867**   | **0.8936**     | **0.6776**     |

**Visual Evaluation:**

- **1-Month Forecast**:
 ![image](https://github.com/user-attachments/assets/45db9a63-a124-4e02-935e-6c0e1194dd4c)  


- **3-Month Forecast**:  
  - RMSE: `0.3556`  
  - Correlation: `0.8936`

- **6-Month Forecast**:  
  - RMSE: `0.6034`  
  - Correlation: `0.6776`

*Figure 4.1: 1 lead month, RMSE 0.1278 , corr 0.9867* 
![3 Month Forecast](./figures/figure_4_2.png)  
![6 Month Forecast](./figures/figure_4_3.png)

> *Note: The model performs exceptionally well up to 3 months, with slight underestimation during extreme events.*

## 🧪 Dataset

- **NOAA ERSSTv5**
- **CMIP5 Historical Simulations**
- **SODA & GODAS Reanalysis**

All datasets were normalized and filtered to grid points over ocean (55°S–60°N and 0–360°W) at 5° resolution.

## 🛠️ Methodology

1. **Graph construction** via learnable adjacency matrix.
2. **Node features**: Historical SST & heat content anomalies.
3. **Forecasting target**: Oceanic Niño Index (ONI).
4. **Loss function**: Mean Squared Error (MSE).
5. **Optimization**: SGD with ELU activations.


---
