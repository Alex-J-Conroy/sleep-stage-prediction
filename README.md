# 💤 Sleep Stage Prediction Using Consumer Wearable Data

## 📌 Project Overview

This project explores whether consumer-grade smartwatches (specifically the Apple Watch Gen 1) can reliably emulate the sleep detection accuracy of clinical-grade devices such as the Phillips Actiwatch. Using **accelerometer-derived ENMO data**, a custom transformation and weighted classification algorithm were used to determine **sleep vs. wake** states.

> **Goal:** Convert ENMO data into a clinical-equivalent format to classify sleep accurately using a transparent, interpretable ML pipeline.

---

## 🧠 Problem Context

Clinical sleep monitoring is effective but costly, making it inaccessible to many. This project applies **data science and machine learning** to create a low-cost, scalable solution using data from commercial wearables — opening up possibilities for future real-time health insights.

---

## 👥 Authors

- **Alex Conroy**  
- Nebojsa Ajdarevic  
- Karen Hau  

> Group Project — IFN646 Biomedical Data Science, Queensland University of Technology (QUT)

---

## 🧾 Data Source

- **Study Name:** ENMO-based Sleep Classification  
- **Participants:** 14 individuals across 27 nights  
- **Epoch Duration:** 15 seconds  
- **Features:**
  - Timestamp  
  - Clinical Activity Count  
  - Sleep/Wake Label (ground truth)  
  - ENMO Value from Apple Watch

🗂 Dataset: [DOI via QUT](https://doi.org/10.25912/5cc28f62e81ad16)

---

## 🔬 Methods

### Data Transformation
- Applied **linear regression** to convert ENMO values into Phillips Actiwatch-equivalent activity counts.

### Sleep Classification
- Implemented a **weighted moving average algorithm** mimicking clinical-grade classification.
- Adjusted thresholds to accommodate the ENMO-transformed values.

### Evaluation
- Compared predicted sleep labels to ground truth using classification metrics.

---

## 📈 Results

| Metric       | Score    |
|--------------|----------|
| Accuracy     | 96.4%    |
| Recall       | 83.5%    |
| Precision    | 89.8%    |
| F1 Score     | 86.5%    |
| Specificity  | 98.5%    |

✅ Shows ENMO-based sleep classification is highly accurate for normal sleep behaviour.  
⚠️ Less generalisable to fragmented or non-nighttime sleep sessions.

---

## 🗂️ Project Structure
sleep-stage-prediction/ ├── data/ │ └── combined_csv.csv # Aligned dataset with clinical labels & ENMO features │ ├── notebooks/ │ └── Wearables_v5.ipynb # End-to-end exploratory analysis and evaluation │ ├── src/ │ └── model.py # Classification model logic and evaluation functions │ ├── utils/ │ ├── processing.py # Data cleaning and ENMO-to-activity transformation │ └── visualisation.py # All visualisation functions (e.g., time series, histograms) │ ├── report/ │ ├── Project report FINAL.pdf # Full research report │ └── Presentation.pdf # Project summary slides │ ├── requirements.txt # Python dependencies └── README.md # Project summary and documentation
