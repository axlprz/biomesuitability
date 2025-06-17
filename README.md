# Biome Suitability Prediction for Fauna Species

This project uses machine learning to predict suitable biomes for animal species based on environmental variables (BIOCLIM data). It was developed using species occurrence data from GBIF and bioclimatic variables (BIO1–BIO14).

## Project Structure
- `data/` – Processed datasets (no raw data uploaded)
- `notebooks/` – EDA and model training notebooks
- `src/` – Python scripts for preprocessing and training
- `models/` – Trained models (saved in .pkl or .joblib)
- `assets/` – Charts, maps, and visual outputs for the README

## Results
- SVM and KNN classifiers trained on bioclimatic variables
- Visualizations of predicted biome suitability

## Future Work
- Expand dataset
- Test ensemble models
