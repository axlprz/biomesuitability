# Biome Suitability Prediction for Fauna Species using Machine Learning

This project uses machine learning models to predict suitable biomes for various fauna species based on environmental and climatic data. It combines GBIF species occurrence records with BIOCLIM variables and applies classification algorithms to estimate biome suitability across regions.

---

## Overview

The goal is to help identify potential habitats for selected animal species by analyzing known occurrences and environmental patterns. This can support conservation planning, ecological research, and biodiversity management.

---

## Project Structure

    biomesuitability/
    ├── data/
        ├── species_biome_env_dataset.csv
    ├── notebooks/
        ├── 1_DF_Merger_BiomeSuitability.ipynb
        ├── 2_ModelComparison_BiomeSuitability.ipynb
    ├── models/
        ├── TunedRF.ipynb
        ├── TunedXGB.ipynb
        ├── TunedKNN.ipynb
        └── TunedLogREG.ipynb
    ├── resources/
        ├── wc2.1_10m_bio .tif files
        ├── ne_110m_land.shp
        └── wwf_terr_ecos.shp file (too large to upload)
    ├── .gitignore
    ├── README.md
    └── requirements.txt

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
- Final dataset size: ~4,000 records, 19 features, multi-class target

---

## Models Used

- **K-Nearest Neighbors (KNN)**
- **Logistic Regression (LogReg)**
- **XGBoost Classifier**
- **Random Forest Classifier**
- Models were evaluated using train/test splits with accuracy, F1-score, and confusion matrices.

---

## Results

- Accuracy: ~70–85% depending on model and species
- Best performance achieved with Random Forest and Logistic Regression
- Confusion matrix revealed common misclassifications between neighboring biomes
- Visual maps of predicted vs. actual biomes for species like axolotl, ocelot, and blue macaw

---

## Future Work

1. Integrate NDVI (vegetation index) and elevation as additional features
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
