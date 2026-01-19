# FreshRetailNet-50K: Demand Forecasting & Stockout Detection

A comprehensive machine learning pipeline for retail demand forecasting and stockout detection using the FreshRetailNet-50K dataset.

---

## 📊 Dataset

**Source:** [Dingdong-Inc/FreshRetailNet-50K](https://huggingface.co/datasets/Dingdong-Inc/FreshRetailNet-50K)

The dataset contains 50,000+ retail transactions with rich features including:
- **Geographic**: City and store identifiers
- **Temporal**: Daily timestamps with hourly sales profiles
- **Product**: Category hierarchies and product IDs
- **Stockouts**: Hour-by-hour stock status (6 AM - 10 PM)
- **Promotions**: Discount levels and promotional flags
- **Context**: Holiday and activity indicators

---

## 🎯 Project Objectives

### 1. Demand Forecasting
Predict daily sales amounts (`sale_amount`) for each store-product combination to optimize inventory planning and reduce waste.

### 2. Stockout Detection
Identify patterns and signals that precede stockout events to enable proactive inventory management.

---

## 🔍 Exploratory Data Analysis

The analysis notebook provides comprehensive visualizations across 8 key dimensions:

1. **Geographic Analysis**: Sales distribution across cities and stores
2. **Temporal Patterns**: Daily trends and day-of-week seasonality
3. **Stockout Analysis**: Rates, distributions, and temporal evolution
4. **Demand vs Availability**: Impact of stockouts on sales
5. **Promotions**: Discount effectiveness and correlation analysis
6. **Holiday & Activity Impact**: External factors on demand
7. **Hourly Profiles**: Intraday sales patterns and stockout timing
8. **Product & Store Heterogeneity**: Variance in demand and stockout rates

### Key Findings
- Clear day-of-week patterns with weekend effects
- Stockout events significantly impact sales performance
- Strong heterogeneity across products and stores
- Promotional discounts show complex interactions with demand

---

## 🤖 Machine Learning Models

### Demand Forecasting Models

We implemented and compared four regression models:

### Stockout Detection

- **Model**: LightGBM Classifier
- **Target**: Binary stockout indicator (`is_stockout`)
- **Features**: Lag features, rolling statistics, temporal patterns
- **Application**: Early warning system for inventory managers

---

## 📈 Model Evaluation

### Metrics Used
- **MAE** (Mean Absolute Error): Interpretable average error
- **RMSE** (Root Mean Squared Error): Penalizes large errors
- **R²** (Coefficient of Determination): Explained variance

### Results Visualization
- Predicted vs Actual scatter plots
- Residual distribution analysis
- Residuals vs Predictions diagnostic plots
- Feature importance rankings
  
### Model Interpretability
- SHAP values for feature importance
- Partial dependence plots
- Feature interaction analysis

---

## 📊 Key Results Summary

| Model | MAE | RMSE | R² | 
|-------|-----|------|-----|
| **XGBoost** | **0.3654** | **0.8361** | 0.8568 |
| **LightGBM** | 0.3698 | 0.9297 | 0.9159 | 
| **MLP** | 0.4386 | 0.7880 | **0.9219** |
| **Random Forest** | 0.4680 | 0.9754 | 0.9075 |

**🎯 Key Insights:**
- **MLP** achieves the highest R² (0.9219), explaining 92.19% of variance
- **XGBoost** offers superior practical performance with lowest prediction errors
- **LightGBM** provides strong results with faster training time
- **Random Forest** serves as a solid baseline but is outperformed by gradient boosting methods

**📈 Performance Comparison:**
- XGBoost reduces MAE by **21%** compared to Random Forest
- MLP achieves lowest RMSE (0.7880) but with higher MAE
- Top 3 models all exceed 85% R² threshold

## 📝 Source
@article{2025freshretailnet-50k,
      title={FreshRetailNet-50K: A Stockout-Annotated Censored Demand Dataset for Latent Demand Recovery and Forecasting in Fresh Retail},
      author={Yangyang Wang, Jiawei Gu, Li Long, Xin Li, Li Shen, Zhouyu Fu, Xiangjun Zhou, Xu Jiang},
      year={2025},
      eprint={2505.16319},
      archivePrefix={arXiv},
      primaryClass={cs.LG},
      url={https://arxiv.org/abs/2505.16319},
}

**Last Updated**: January 2026
