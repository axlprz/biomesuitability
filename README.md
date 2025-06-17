# Clone Hero Chart Generator using Machine Learning

This project generates playable `.chart` files for Clone Hero based on input audio. It uses a machine learning pipeline with beat detection, instrument separation (Demucs), and fret classification using CNN or transfer learning with PANNs.

## Project Structure
- `data/` – Sample training data
- `notebooks/` – Model training and feature extraction notebooks
- `src/` – Chart writer, model trainer, and data processing scripts
- `models/` – Exported `.pt` or `.pkl` models
- `assets/` – Demo charts, screenshots, or spectrograms

## Usage
```bash
python main.py --audio "song.ogg" --output "output.chart"
