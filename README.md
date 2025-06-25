# Biome Suitability Prediction for Fauna Species using Machine Learning

This project uses machine learning models to predict suitable biomes for various fauna species based on environmental and climatic data. It combines GBIF species occurrence records with BIOCLIM variables and applies classification algorithms to estimate biome suitability across regions.

---

## Overview

The goal is to help identify potential habitats for selected animal species by analyzing known occurrences and environmental patterns. This can support conservation planning, ecological research, and biodiversity management.

---

## Project Structure

```text
biomesuitability/
├── data/           # Processed CSV files
│   ├── species_biome_env_dataset.csv
│   └── biome_labels.csv
├── notebooks/      # Jupyter notebooks for EDA, training, evaluation
│   ├── 1_dataset_merge_and_cleaning.ipynb
│   ├── 2_model_training_knn_svm_dt_rf.ipynb
│   ├── 3_model_evaluation_comparison.ipynb
│   └── 4_biome_prediction_visualization.ipynb
├── src/            # Python scripts for data merging, cleaning, modeling
│   ├── preprocessing.py
│   ├── model_utils.py
│   └── evaluation.py
├── models/         # Trained model files
│   ├── tuned_rf.pkl
│   ├── tuned_xgb.pkl
│   ├── tuned_knn.pkl
│   └── tuned_logreg.pkl
├── assets/         # Visual outputs (charts, maps, confusion matrices)
│   ├── confusion_matrix_rf.png
│   ├── biome_map_ocelot.png
│   └── feature_importance.png
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Data Sources

- **GBIF**: Species occurrence data downloaded as CSV
- **BIOCLIM**: Bioclimatic variables (BIO1 to BIO14) representing temperature and precipitation
- **Biome Labels**: Based on occurrence location polygons or manual region classification

Each row in the final dataset represents one occurrence, annotated with:
- Species name
- Bioclimatic feature values
- Target biome class label

---

## Preprocessing

- Combined GBIF records with BIOCLIM values using spatial joins
- Filtered out landless and outlier coordinates using a landmask
- Removed species with insufficient occurrence data
- Encoded categorical features and normalized numerical ones
- Final dataset size: ~20,000 records, 14 features, multi-class target

---

## Models Used

- **K-Nearest Neighbors (KNN)**
- **Support Vector Machine (SVM)**
- **Decision Tree Classifier**
- **Random Forest Classifier**
- Models were evaluated using train/test splits with accuracy, F1-score, and confusion matrices.

---

## Results

- Accuracy: ~70–85% depending on model and species
- Best performance achieved with Random Forest and SVM
- Confusion matrix revealed common misclassifications between neighboring biomes
- Visual maps of predicted vs. actual biomes for species like axolotl, ocelot, and blue macaw

---

## How to Run

```bash
# Step 1: Install required libraries
pip install -r requirements.txt

# Step 2: Launch notebooks
jupyter notebook notebooks/eda_and_model_training.ipynb
```

---

## Future Work

1. Integrate NDVI and elevation as additional features
2. Include species traits (e.g., body size, diet) as predictors
3. Predict multiple suitable biomes instead of just one
4. Train on global rather than regional subsets
5. Explore deep learning models (e.g., tabular transformers)

---

## References

1. GBIF: Global Biodiversity Information Facility
2. WorldClim / BIOCLIM Variables
3. scikit-learn Documentation
4. Folium for interactive maps

---
