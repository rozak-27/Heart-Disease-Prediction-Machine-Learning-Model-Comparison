# Dataset Documentation

## Heart Disease UCI Dataset

### Overview

This project uses the **Heart Disease dataset** from the UCI Machine Learning Repository. The dataset combines clinical data from four medical institutions to predict the presence of heart disease.

- **Source**: [UCI ML Repository - Heart Disease](https://archive.ics.uci.edu/ml/datasets/heart+disease)
- **Total Instances**: 920 samples (before preprocessing)
- **Features**: 14 clinical attributes
- **Target**: Binary classification (0 = No disease, 1 = Disease)
- **Data Type**: Medical/Clinical data

---

##  How to Download

### Option 1: Automated Download (Recommended)

Run the download script from the project root:

```bash
python scripts/download_data.py
```

This will download all 4 files into `data/raw/` automatically.

### Option 2: Manual Download

1. Visit: https://archive.ics.uci.edu/ml/datasets/heart+disease
2. Download these 4 files:
   - `processed.cleveland.data`
   - `processed.hungarian.data`
   - `processed.switzerland.data`
   - `processed.va.data`
3. Place them in the `data/raw/` folder


### Missing Values

Missing values are denoted by `?` in the original files.

**Statistics**:
- Total missing values: ~304 across all features
- Most affected features: `ca` and `thal`

**Handling Strategy**:
- Imputation method: **Median replacement**
- Implementation: `df.fillna(df.median())`
- Result: **0 missing values** after preprocessing

### Duplicates

- Original: 920 samples
- After removing duplicates: **918 samples**
- Removed: 2 duplicate rows

---

##  Preprocessing Pipeline

The raw data goes through these steps:

```
Raw Data (920 samples)
    ↓
Remove Duplicates → 918 samples
    ↓
Fill Missing Values (median) → 0 missing
    ↓
Binary Encode Target (0/1) → 508 no disease, 410 disease
    ↓
SMOTE Resampling → 1016 samples (balanced 508:508)
    ↓
Train-Test Split (80/20) → Train: 812, Test: 204
```

See `notebooks/02_individual_models.ipynb` for detailed implementation.

---



##  Important Notes

1. **Do NOT commit raw data files to Git** 
   - Files are listed in `.gitignore`
   - Download using the script or manually

2. **Reproducibility**
   - Same preprocessing with `random_state=42`
   - Exact results guaranteed with provided scripts

3. **Data Privacy**
   - Dataset is anonymized
   - No patient identifiable information

---

**Last Updated**: March 2026  
**Dataset Version**: Original UCI repository files (1988)
