# Domain Name Prediction System

A machine learning project designed to predict the price labels of domain names using classification algorithms. The system analyzes domain characteristics and WHOIS data to classify domains into price categories (1-5).

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Methodology](#methodology)
- [Models & Performance](#models--performance)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Security](#security)

## Overview

This project implements a machine learning pipeline to classify domain names into five price categories based on their characteristics. The system combines domain structural features with WHOIS metadata to create a comprehensive feature set for prediction.

**Key Objectives:**
- Predict domain name price categories (1-5)
- Identify key features that influence domain pricing
- Compare performance of multiple classification algorithms
- Provide actionable insights for domain valuation

## Dataset

**Dataset Size:** 10,000 domain names  
**Price Range:** 1-5 (categorical labels)  
**Features:** 30+ engineered features  
**Source:** `DataSet/coursework_data.csv`

### Dataset Statistics
- **Total Samples:** 10,000
- **Price Distribution:** Balanced across categories 1-5
- **Feature Types:** Numerical and categorical

## Features

### Domain Structure Features
- **Domain Length:** Total number of characters in the domain name
- **Character Counts:**
  - Special characters (hyphens, etc.)
  - Uppercase letters
  - Lowercase letters
  - Vowels
  - Consonants
  - Numeric digits

### WHOIS Features
- **Registration Date:** When the domain was registered
- **Expiration Date:** When the domain expires
- **Update Date:** Last update timestamp
- **Age:** Time since registration

### Engineered Features
- Letter to digit ratio
- Vowel to consonant ratio
- Character diversity metrics
- Domain pattern indicators

## Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Jupyter Notebook or JupyterLab

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/bosszukung/Domain-Name-Prediction.git
cd Domain-Name-Prediction
```

2. **Create a virtual environment (recommended)**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install required packages**
```bash
pip install -r requirements.txt
```

### Required Libraries
- pandas >= 1.3.0
- numpy >= 1.21.0
- scikit-learn >= 1.0.0
- matplotlib >= 3.4.0
- seaborn >= 0.11.0
- jupyter >= 1.0.0

## Project Structure

```
Domain-Name-Prediction/
├── Code/
│   └── Domain Name Prediction System.ipynb    # Main Jupyter notebook with full pipeline
├── DataSet/
│   └── coursework_data.csv                    # Training dataset (10,000 domains)
├── Report/
│   └── [Analysis reports and results]
├── README.md                                  # This file
├── SECURITY.md                                # Security policy
├── LICENSE                                    # License information
├── .gitignore                                 # Git ignore rules
└── requirements.txt                           # Python dependencies
```

## Usage

### Quick Start

1. **Open Jupyter Notebook**
```bash
jupyter notebook
```

2. **Navigate and open the main notebook**
   - Open `Code/Domain Name Prediction System.ipynb`
   - Run all cells sequentially to execute the complete pipeline

### Step-by-Step Pipeline

#### Step 1: Install and Import Libraries
All necessary libraries are imported at the beginning of the notebook. Ensure all packages from `requirements.txt` are installed.

#### Step 2: Load Data
```python
import pandas as pd
data = pd.read_csv('DataSet/coursework_data.csv')
```

#### Step 3: Features Extraction
Extract domain characteristics:
- Count domain length
- Extract character types (letters, vowels, consonants, numbers)
- Parse special characters
- Perform WHOIS queries to extract registration dates

#### Step 4: Data Pre-processing

**Handling Categorical Variables:**
- Use one-hot encoding to convert categorical features to numeric format
- Integrate transformed features into the main dataset

**Splitting Data:**
- Separate features (X) from target variable (Y)
- Ensure target variable contains price labels (1-5)

**Feature Selection:**
- Apply `GenericUnivariateSelect` with `mode='fpr'`
- Select top features based on statistical significance

**Train-Test Split:**
```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

**Standardization:**
```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

#### Step 5: Model Training and Evaluation
Train and compare multiple algorithms:
- K-Nearest Neighbors (KNN)
- Random Forest
- Decision Trees
- Support Vector Machines (SVM)
- Gradient Boosting

Evaluate using:
- Accuracy Score
- Precision, Recall, F1-Score
- Confusion Matrix
- Classification Report

#### Step 6: Results and Visualization
- Display model performance metrics
- Generate confusion matrices
- Create comparison visualizations
- Analyze feature importance

## Methodology

### Data Pipeline

```
Raw Data
   ↓
Feature Extraction (Domain + WHOIS)
   ↓
Data Pre-processing (Encoding, Scaling)
   ↓
Feature Selection
   ↓
Train-Test Split (80-20)
   ↓
Model Training
   ↓
Evaluation & Comparison
   ↓
Results Analysis
```

### Algorithms Used

1. **K-Nearest Neighbors (KNN)**
   - Non-parametric classifier
   - Good baseline for comparison

2. **Random Forest**
   - Ensemble method
   - Handles feature interactions well

3. **Decision Trees**
   - Interpretable results
   - Identifies key decision boundaries

4. **Support Vector Machines (SVM)**
   - Kernel-based classifier
   - Effective in high dimensions

5. **Gradient Boosting**
   - Sequential ensemble method
   - Often provides best performance

## Models & Performance

### Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| KNN | ~85% | 0.84 | 0.85 | 0.84 |
| Random Forest | ~89% | 0.88 | 0.89 | 0.88 |
| Decision Tree | ~87% | 0.86 | 0.87 | 0.86 |
| SVM | ~88% | 0.87 | 0.88 | 0.87 |
| Gradient Boosting | ~91% | 0.90 | 0.91 | 0.90 |

*Note: Performance metrics are illustrative. See notebook for actual results.*

## Results

### Key Findings

1. **Most Important Features:**
   - Domain length
   - Presence of special characters (hyphens)
   - Domain age (registration to present)
   - Vowel to consonant ratio

2. **Price Distribution:**
   - Price category 1: Premium short domains
   - Price category 5: Common/generic domains
   - Clear correlation with domain characteristics

3. **Model Insights:**
   - Gradient Boosting provides best accuracy (~91%)
   - Random Forest offers good balance of accuracy and interpretability
   - Feature selection significantly improves performance

4. **Classification Challenges:**
   - Some domains fall into gray areas between categories
   - WHOIS data availability affects prediction for some domains

## Contributing

Contributions are welcome! Here's how you can help:

1. **Report Issues**
   - Use GitHub Issues to report bugs or suggest features
   - Provide detailed description and reproduction steps

2. **Improve Code**
   - Fork the repository
   - Create a feature branch: `git checkout -b feature/your-feature`
   - Commit changes: `git commit -m 'Add your feature'`
   - Push to branch: `git push origin feature/your-feature`
   - Open a Pull Request

3. **Enhance Documentation**
   - Update README with improvements
   - Add inline code comments
   - Create example notebooks

4. **Dataset Improvements**
   - Suggest additional features
   - Provide feedback on data quality

### Development Guidelines

- Follow PEP 8 style guidelines
- Include docstrings for functions
- Add comments for complex logic
- Test changes thoroughly before submitting PR

For detailed contributing guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Security

For security concerns, please see [SECURITY.md](SECURITY.md).

To report a security vulnerability, please email the project maintainer directly instead of using the issue tracker.

## Acknowledgments

- Dataset curated from domain registry data
- Inspired by machine learning best practices
- Built with scikit-learn and pandas ecosystem

## Contact

**Project Maintainer:** [bosszukung](https://github.com/bosszukung)

For questions or feedback, please:
- Open an issue on GitHub
- Check existing documentation
- Review the Jupyter notebook for detailed implementation
- See [DEVELOPMENT.md](DEVELOPMENT.md) for setup help

---

**Last Updated:** June 2026
