# Job Scam Detection AI: Predictive Modeling for the EMSCAD Dataset

## Project Overview
This project addresses the growing problem of fraudulent job postings using machine learning. Rather than relying solely on text analysis, this pipeline utilizes Adversarial EDA to identify "Trust Gaps"—behavioral red flags left by scammers, such as the intentional omission of corporate metadata.

In this dataset, we observed that the absence of a company profile or logo correlates with a 15x increase in the probability of fraud.

## Key Features
* Trust-Signal Engineering: Beyond standard NLP, the model evaluates "The Professionalism Paradox," checking for the presence of logos, profiles, and informal tone markers (sentiment/subjectivity).
* Imbalance Management: Implements Stratified K-Fold Cross-Validation and class_weight='balanced' to ensure high recall for the 4.8% minority (fraud) class without resorting to synthetic oversampling (SMOTE), which can distort text data.
* Multi-Model Benchmarking: Compares four distinct architectures:
    * Decision Trees: For baseline interpretability.
    * Linear SVM: For high-dimensional text efficiency.
    * XGBoost: For capturing complex feature interactions.
    * TabNet: For non-linear deep learning on tabular data.

## Exploratory Data Analysis (EDA)
Our EDA revealed that "missingness" is a primary feature. We categorized NaN values as "Not Specified" rather than dropping them, allowing the model to learn from the "Laziness Signal."

* Experience & Employment: Scammers disproportionately target Entry-Level roles and frequently omit employment type details to cast a wider net.
* Metadata Correlation: High-risk postings often lack both a brand logo and a company profile. A custom "Suspicion Score" was developed to quantify this risk staircase.

## Technical Pipeline
1. Preprocessing: A ColumnTransformer handles hybrid inputs—TfidfVectorizer for text descriptions and OneHotEncoder for categorical metadata.
2. Hyperparameter Tuning: Automated via GridSearchCV (using StratifiedKFold) to optimize parameters like scale_pos_weight and tree depth.
3. Evaluation: Metrics focused on Recall and F1-Score to prioritize catching scams while maintaining reasonable precision.

## Installation & Usage
```bash
# Clone the repository
git clone [https://github.com/doveleyy/exploratoryscamanalysis.git](https://github.com/doveleyy/exploratoryscamanalysis.git)

# Install dependencies
pip install -r requirements.txt

# Run the Jupyter Notebook
jupyter notebook scams.ipynb