# Pneumonia Detection from Chest X-Rays

**Course:** Data Analysis — Project S2 2025-2026, Université Antonine

## Research question
Can pneumonia be detected from chest X-rays using a neural network (supervised learning),
and what natural groupings appear in the X-rays when no labels are given (unsupervised learning)?
Does the model rely on the disease itself, or on shortcuts such as how the X-ray was taken?

## Dataset
RSNA Pneumonia Detection Challenge (2018) — chest X-rays from the US National Institutes of Health
(NIH) Clinical Center, annotated by radiologists (Radiological Society of North America,
Society of Thoracic Radiology, MD.ai). Used under RSNA's terms of use with attribution.
https://www.rsna.org/artificial-intelligence/ai-image-challenge/rsna-pneumonia-detection-challenge-2018

The images are NOT stored in this repository (several GB). They are downloaded in Google Colab
and stored in a shared Google Drive folder. Only small files (labels, metadata, results) are committed.

Classes:
- Lung Opacity (signs of pneumonia)
- No Lung Opacity / Not Normal
- Normal

## Tools
- **Google Colab (GPU):** image loading, preprocessing, CNN training, Grad-CAM, feature extraction.
- **VS Code (local):** metadata exploration, clustering on extracted features, charts, report.

## Project structure
```
notebooks/
  01_download_explore.ipynb     (Colab)  download data, labels, metadata
  02_preprocess.ipynb           (Colab)  resize subset, save to Drive
  03_supervised_cnn.ipynb       (Colab)  baseline + transfer learning CNN, metrics, Grad-CAM
  04_feature_extraction.ipynb   (Colab)  CNN embeddings for clustering
  05_unsupervised.ipynb         (local)  PCA + K-Means, comparison with classes and metadata
data/processed/                 small CSVs only (labels, metadata, embeddings)
figures/                        charts exported for the report
report/                         report draft (draft.md) and final version
```

## Methods
- **Supervised:** baseline model vs. CNN with transfer learning (pretrained network).
  Metrics: accuracy, precision, recall, F1, confusion matrix. Grad-CAM heatmaps for interpretation.
- **Unsupervised:** PCA and K-Means on features extracted by the network,
  compared with the real classes and with metadata (age, sex, X-ray view position).

## Local setup
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate   |   macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```
