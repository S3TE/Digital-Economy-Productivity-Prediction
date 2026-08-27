# Digital-Economy-Productivity-Prediction

## Analysis of Industrial Upgrading and Productivity Improvement Strategies Based on a Back-Propagation Neural Network Driven by the Digital Economy

This repository contains the computational notebook and supporting documentation for the study **“Analysis of Industrial Upgrading and Productivity Improvement Strategies Based on a Back-Propagation Neural Network Driven by the Digital Economy.”** The repository is intended to support transparent and reproducible execution of the empirical analysis.

The analysis uses the publicly available dataset **International Panel Data Analysis of the Effect of Digitalization on Economic Growth**, distributed through Mendeley Data. The dataset is used in its native annual country-year form rather than being treated as a monthly panel.

---

## 1. Repository Contents

```text
Digital-Economy-Productivity-Prediction/
│
├── README.md
├── LICENSE
├── requirements.txt
├── notebook/
│   └── Analysis of Industrial Upgrading and Productivity Improvement Strategies
│       Based on a Back-Propagation Neural Network Driven by the Digital Economy.ipynb
│
├── data/
│   └── README.md
│
└── outputs/
    ├── figures/
    └── tables/
```

### File descriptions

| File/Folder | Description |
|---|---|
| `README.md` | Reproducibility and execution instructions |
| `LICENSE` | License for the source code in this repository |
| `requirements.txt` | Python package and environment requirements |
| `notebook/` | Main analysis Jupyter notebook |
| `data/` | Location where the downloaded source dataset should be placed |
| `outputs/figures/` | Generated figures |
| `outputs/tables/` | Generated result tables |

The source dataset is not redistributed in this repository unless redistribution is separately permitted. Users should obtain the dataset from its persistent source and place the downloaded Excel file in the `data/` directory.

---

# 2. Dataset

## 2.1 Source dataset

The analysis uses:

**International Panel Data Analysis of the Effect of Digitalization on Economic Growth**

Source file:

**Data base International Panel Data Analysis of the Effect of Digitalization on Economic Growth.xlsx**

Dataset DOI:

**10.17632/ctm7vvpp7n.1**

Dataset version:

**Version 1**

Publication date:

**7 February 2024**

License of the source dataset:

**CC0 1.0 Universal (Public Domain Dedication)**

The persistent dataset record is:

https://doi.org/10.17632/ctm7vvpp7n.1

The dataset is distributed as an Excel workbook and contains the worksheet used for the analysis.

---

## 2.2 Native observation frequency

The source dataset is an **annual country-year panel**.

The original data should therefore be treated at their native annual frequency. The analysis does **not** create artificial country-month observations through interpolation.

The temporal identifier is the **Year** variable.

---

## 2.3 Dataset dimensions

The source dataset used for the revised analysis contains:

- **2,730 observations**
- **23 columns**
- Annual observations
- Country-year panel structure
- Source period: **2000–2020**

The final manuscript and notebook must use these values consistently. No alternative 18-country/2,808-country-month dataset definition is used in the revised analysis.

---

# 3. Variables

The source dataset contains the following principal variables.

| Variable | Description |
|---|---|
| `LGDPF` | GDP per capita / logged GDP-per-capita measure used as the economic-growth outcome |
| `FPS` | Fixed telephone subscriptions |
| `MPS` | Mobile cellular subscriptions |
| `BBS` | Fixed broadband subscriptions |
| `IU` | Individuals using the Internet |
| `DDI` | Digitalization index obtained using principal component analysis |
| `GFCF` | Gross fixed capital formation |
| `TO` | Trade openness |
| `Labor` | Labor-force participation measure |
| `LCPI` | Consumer price index / inflation measure |
| `LPOP` | Population |
| `consum` | Government consumption expenditure |
| `RD` | Research and development-related variable, where present in the distributed file |

The exact column names should be verified against the downloaded Excel file before running the notebook. No manuscript-generated variable name should be substituted for a source variable without documenting the transformation.

---

# 4. Data Preparation

The computational workflow consists of the following stages:

```text
Source Excel Dataset
        │
        ▼
Dataset Loading
        │
        ▼
Data Validation and Cleaning
        │
        ├── Duplicate checking
        ├── Missing-value inspection
        └── Column-name validation
        │
        ▼
Feature Preparation
        │
        ├── Digitalization variables
        ├── Economic/control variables
        └── Derived model features
        │
        ▼
Chronological Train/Validation/Test Split
        │
        ▼
Feature Scaling
        │
        ▼
Econometric Anchor
        │
        ▼
Back-Propagation Neural Network
        │
        ▼
EBFM Fusion
        │
        ▼
Prediction and Evaluation
        │
        ▼
Figures and Tables
```

---

# 5. Reproducibility Principle

The analysis follows a **single dataset definition** throughout the manuscript, notebook, tables, and repository.

The following alternative descriptions are **not used**:

- 18 countries with 2,808 country-month observations
- 2010–2022 monthly panel
- 2012–2023 panel
- 216 observations per country per year
- Random 70–15–15 splitting when a chronological split is specified

The final notebook and manuscript should report the same:

1. source dataset;
2. source filename;
3. observation frequency;
4. study period;
5. number of observations;
6. variables;
7. train/validation/test periods; and
8. preprocessing operations.

---

# 6. Train/Validation/Test Procedure

Because the source data are annual panel observations, temporal ordering is preserved during model evaluation.

The final repository must use the **same chronological split reported in the revised manuscript**.

For the revised implementation, the split should be defined explicitly by calendar year in the notebook rather than by random sampling.

Example configuration:

```python
TRAIN_START = 2000
TRAIN_END   = 2014

VAL_START   = 2015
VAL_END     = 2017

TEST_START  = 2018
TEST_END    = 2020
```

This produces:

- Training: 2000–2014
- Validation: 2015–2017
- Testing: 2018–2020

The exact calendar split used for the published results must be identical in the manuscript, notebook, tables, and README. If the final manuscript adopts a different chronological partition, these values must be changed consistently in all four locations.

No future test-period observations should be used during model training or hyperparameter selection.

---

# 7. Software Environment

## Recommended environment

- Python: **3.10**
- Jupyter Notebook / JupyterLab
- TensorFlow 2.x
- NumPy
- Pandas
- Scikit-learn
- SciPy
- Statsmodels
- Matplotlib
- OpenPyXL

Install the pinned dependencies with:

```bash
pip install -r requirements.txt
```

The `requirements.txt` file should contain the exact versions used to generate the reported results.

> **Reproducibility requirement:** The Python and TensorFlow versions reported in the manuscript, the notebook metadata, and `requirements.txt` must agree. Before release, the notebook should be executed in the declared Python 3.10 environment and the resulting package versions should be recorded in `requirements.txt`.

---

# 8. Installation

Clone the repository:

```bash
git clone https://github.com/S3TE/Digital-Economy-Productivity-Prediction.git
cd Digital-Economy-Productivity-Prediction
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate the environment.

### Windows

```bash
.venv\Scripts\activate
```

### Linux/macOS

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# 9. Obtain and Place the Dataset

Download the source dataset using its persistent DOI:

**https://doi.org/10.17632/ctm7vvpp7n.1**

Place the Excel file in:

```text
data/
└── Data base International Panel Data Analysis of the Effect of Digitalization on Economic Growth.xlsx
```

The repository does not require the dataset to be renamed if the notebook is configured with the exact source filename.

---

# 10. Notebook Execution

The main notebook is:

```text
notebook/
└── Analysis of Industrial Upgrading and Productivity Improvement Strategies
    Based on a Back-Propagation Neural Network Driven by the Digital Economy.ipynb
```

Run the notebook sequentially from the first cell to the last cell.

### Execution order

### Step 1 — Dataset Loading

The first stage:

- loads the Excel dataset;
- reports the dataset dimensions;
- displays the first observations;
- reports column names;
- checks missing values;
- checks duplicate observations; and
- saves the loaded data for subsequent processing.

### Step 2 — Data Preprocessing

The preprocessing stage:

- removes duplicate records;
- standardizes column names;
- identifies numeric and categorical variables;
- handles missing observations;
- encodes categorical variables where required;
- performs outlier treatment;
- applies feature scaling; and
- saves the processed dataset.

### Step 3 — Feature Preparation

The feature-preparation stage identifies digital-economy and economic variables and constructs model-ready derived features where specified by the final methodology.

Any derived feature must be documented in the manuscript and must not be presented as an original source variable.

### Step 4 — EBFM Model

The proposed analysis combines an econometric component with a neural-network component.

The computational workflow includes:

1. feature preparation;
2. econometric anchor estimation;
3. generation of econometric predictions;
4. fusion of econometric predictions with neural-network inputs;
5. BPNN training;
6. validation-based model selection; and
7. final test-set prediction.

### Step 5 — Evaluation

The evaluation stage reports:

- R²;
- RMSE;
- MAE where implemented; and
- the additional evaluation statistics specified in the manuscript.

All final reported values should be generated directly from the notebook rather than manually entered into manuscript tables.

---

# 11. Output Files

Generated outputs should be stored under:

```text
outputs/
├── figures/
└── tables/
```

Examples include:

```text
outputs/
├── figures/
│   ├── training_validation_loss.png
│   ├── prediction_comparison.png
│   └── feature_attribution.png
│
└── tables/
    ├── model_performance.csv
    ├── ablation_results.csv
    └── statistical_tests.csv
```

The exact output names may vary according to the final notebook implementation.

---

# 12. Random Seed and Reproducibility

Where stochastic neural-network training is used, the random seed should be fixed.

Recommended configuration:

```python
import os
import random
import numpy as np
import tensorflow as tf

SEED = 42

os.environ["PYTHONHASHSEED"] = str(SEED)
random.seed(SEED)
np.random.seed(SEED)
tf.random.set_seed(SEED)
```

The seed used for the published results must be the same seed reported in the manuscript.

---

# 13. Important Reproducibility Checks

Before submitting the repository, verify the following:

- [ ] The notebook loads the same dataset described in Section 4.1.
- [ ] The exact source filename is documented.
- [ ] The dataset is treated as annual country-year data.
- [ ] The source period is consistently reported as 2000–2020.
- [ ] The observation count is consistently reported as 2,730.
- [ ] The same variables are used in the manuscript and notebook.
- [ ] No unsupported monthly interpolation is performed.
- [ ] The chronological train/validation/test split is identical across manuscript and notebook.
- [ ] No test-period data are used for model fitting.
- [ ] The Python version is consistent with the manuscript.
- [ ] The TensorFlow version is consistent with `requirements.txt`.
- [ ] All package versions required for reproduction are pinned.
- [ ] The README explains dataset acquisition and placement.
- [ ] The repository contains an OSI-approved software license.
- [ ] The notebook executes from the first cell to the final cell without changing local absolute paths.
- [ ] Reported tables can be regenerated from the notebook.

---

# 14. Data Leakage Prevention

To avoid information leakage:

1. The test period must remain completely isolated until final evaluation.
2. Scaling parameters must be fitted using training data only.
3. Any transformation involving model fitting must be estimated on the training partition and then applied to validation/test data.
4. Hyperparameters must be selected using training/validation data only.
5. Test-set performance must be calculated only once the final model configuration has been fixed.
6. Temporal ordering must be preserved for the country-year panel.

---

# 15. Source and Data Availability

The source dataset is:

**Elkhaldi, Abderrazek; Sghaier, Nadia; Chikhaoui, Monia (2024). International Panel Data Analysis of the Effect of Digitalization on Economic Growth. Mendeley Data, Version 1. DOI: 10.17632/ctm7vvpp7n.1.**

The source dataset is released under **CC0 1.0 Universal**.

The dataset contains the original country-year observations and variables distributed by the data authors. Any variables derived during this study are generated by the analysis code and are not part of the original source dataset.

---

# 16. Code License

The source code in this repository should be released under an OSI-approved open-source license.

Recommended:

**MIT License**

The code license applies to the repository's source code and does not replace the license governing the external dataset.

---

# 17. Citation

If you use the source dataset, please cite:

> Elkhaldi, A., Sghaier, N., & Chikhaoui, M. (2024). *International Panel Data Analysis of the Effect of Digitalization on Economic Growth*. Mendeley Data, Version 1. https://doi.org/10.17632/ctm7vvpp7n.1

If you use the computational implementation in this repository, please also cite the associated research article.

---

# 18. Reproduction Checklist

A complete reproduction should follow:

```text
1. Clone repository
        ↓
2. Create Python 3.10 environment
        ↓
3. Install requirements.txt
        ↓
4. Obtain source Excel dataset
        ↓
5. Place Excel file in data/
        ↓
6. Open the analysis notebook
        ↓
7. Execute cells sequentially
        ↓
8. Verify dataset dimensions
        ↓
9. Verify preprocessing
        ↓
10. Verify chronological split
        ↓
11. Train econometric component
        ↓
12. Train EBFM neural model
        ↓
13. Evaluate on held-out test period
        ↓
14. Generate figures/tables
        ↓
15. Compare generated results with manuscript
```

---

# 19. Reproducibility Statement

The repository is designed so that an independent researcher can obtain the same source dataset, recreate the preprocessing pipeline, execute the analysis notebook in the documented software environment, reproduce the chronological data partition, train the proposed model, and regenerate the reported evaluation outputs.

The repository intentionally separates the **original source data** from **derived analysis outputs**. The source dataset is identified by its persistent DOI, while all derived datasets, features, predictions, figures, and tables are generated by the analysis notebook.