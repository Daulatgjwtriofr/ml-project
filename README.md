# Song-Popularity-Prediction

[![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-blue)](https://www.kaggle.com/datasets/yasserh/song-popularity-dataset)

AIML Project predicting song popularity using audio features like energy, danceability, acousticness, liveness. Tackles multicollinearity via VIF/RFE/PCA; best model is Polynomial Regression (degree 2).[file:1]

## 📊 Dataset
- **Source**: [yasserh/song-popularity-dataset](https://www.kaggle.com/datasets/yasserh/song-popularity-dataset) (~18K samples).[file:1]
- **Target**: `song_popularity` (0-100, normal dist. ~60).[file:1]
- **Features**: 12+ (e.g., danceability, energy); post-preprocessing: ~12K samples retained (33% outliers dropped).[file:1]

## 🛠️ Workflow
1. **EDA**: Distributions, pairplots, correlation heatmap.[file:1]
2. **Preprocessing**: Outliers (IQR), encoding, StandardScaler.[file:1]
3. **Split**: 80/20 train/test.[file:1]
4. **Feature Selection**: RFE shortlisted top features.[file:1]
5. **Models**: Linear, Ridge, Lasso, ElasticNet, Polynomial.[file:1]

## 📈 Model Performance

| Model                  | Train R² | Test R² | Train RMSE | Test RMSE |
|------------------------|----------|---------|------------|-----------|
| MLR                   | 0.08    | 0.07   | ~20.0     | ~20.5    |
| Ridge                 | Similar | Similar| Similar   | Similar  |
| Lasso                 | Similar | Similar| Similar   | Similar  |
| ElasticNet            | Similar | Similar| Similar   | Similar  |
| **Polynomial (deg 2)**| **Best**| **Best**| **Lowest**| **Lowest**| [file:1]

**Key Insight**: Polynomial deg 2 tops R²/lowest RMSE, but MLR generalizes best (low overfitting).[file:1]

## 🚀 Quick Start
```bash
# Clone repo
git clone https://github.com/YOUR_USERNAME/Song-Popularity-Prediction.git
cd Song-Popularity-Prediction

# Install deps
pip install -r requirements.txt

# Run notebook (auto-downloads data)
jupyter notebook Song_Popularity_Prediction_-Best_ML_Models-checkpoint.ipynb
