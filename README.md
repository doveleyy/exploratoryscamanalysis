# Exploratory Job Scam Analysis: The EMSCAD Dataset

## Project Overview
This repository contains an exploratory data analysis (EDA) of the EMSCAD dataset to identify patterns in fraudulent job postings. The analysis focuses on how missing information and specific structural markers distinguish scams from legitimate employment opportunities.

Key findings indicate that the absence of a company profile or brand logo is a strong indicator of fraud, correlating with a 15-fold increase in the probability of a posting being fraudulent.

## Key Insights from EDA
* **Missing Metadata Analysis:** Investigation of how the absence of logos and company profiles serves as a primary indicator of non-legitimate postings.
* **Information Gaps as Signals:** Analysis of missing values (NaNs) not as data errors, but as behavioral markers in scammer postings.
* **Targeting Patterns:** Observations on how fraudulent posts often target Entry-Level roles and frequently omit specific employment type details.
* **Tone and Subjectivity:** Examining how informal language or high subjectivity in job descriptions relates to the authenticity of the post.

## Technical Methodology
* **Dimensionality Reduction:** Utilizing UMAP (Uniform Manifold Approximation and Projection) to cluster and visualize high-dimensional text data.
* **Text Vectorization:** Using TF-IDF to extract and compare the importance of specific terms used in fraudulent vs. legitimate postings.
* **Feature Relationship Mapping:** Analyzing the cumulative risk when multiple fields (profile, logo, and requirements) are left blank simultaneously.
* **Data Visualization:** Using Seaborn and Matplotlib to illustrate the distribution of fraud across different categories and levels of missing information.

## Installation & Usage
```bash
# Clone the repository
git clone [https://github.com/doveleyy/exploratoryscamanalysis.git](https://github.com/doveleyy/exploratoryscamanalysis.git)

# Install dependencies
pip install -r requirements.txt

# Run the Jupyter Notebook
jupyter notebook scams.ipynb