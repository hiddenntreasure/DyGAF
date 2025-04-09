# Dynamic Gene Attention Focus (DyGAF): Enhancing Biomarker Identification Through Dual-Model Attention Networks
**Article DOI:** [https://doi.org/10.1177/11779322251325390](https://doi.org/10.1177/11779322251325390)

DyGAF is a novel model designed to address biomarker detection, disease progression reporting, and diagnostics by analyzing gene expression data. It leverages dual-model attention-based neural networks and machine learning algorithms to enhance biomarker identification and ranking. By utilizing attention mechanisms, DyGAF not only identifies critical genes but also ranks them by significance, providing a comprehensive list of top genes for disease detection and prognosis.
DyGAF also showed promise in classifying gene expression profiles for diagnosing COVID-19 patients, outperforming conventional models. It represents a significant advancement in genomic research, offering a precise tool for identifying key genetic markers and uncovering complex biological insights.

DyGAF is a Python package that implements attention-based model pipelines for analyzing tabular datasets. It supports both dependent and independent attention models, enabling tasks like disease classification and feature selection. With built-in Stratified K-Fold Cross-Validation, it integrates smoothly with TensorFlow and other machine learning libraries for efficient model training and analysis.

## Features

- **Disease Diagnosis and Classification**: Effectively classifies diseases such as COVID-19 by analyzing gene expression profiles, aiding in biomarker discovery and diagnostic predictions.
- **Attention-Based Feature Selection**: Utilizes attention mechanisms to rank genes or features, facilitating more accurate selection for further biological or diagnostic interpretation.
- **Dependent and Independent Attention Models**: Train and evaluate models using attention-based mechanisms for more nuanced data interpretation.
- **Stratified K-Fold Cross-Validation**: Ensures robust performance evaluation by splitting the dataset into multiple folds while preserving the distribution of the target variable.
- **Seamless Integration**: Built on top of TensorFlow, scikit-learn, and XGBoost, ensuring smooth integration with established machine learning pipelines and support for Python 3.10.

# Installation

Follow these steps to install DyGAF in a new conda environment.

## Step 1: Create a Conda Environment

Create and activate a new conda environment with Python 3.10 to ensure compatibility with DyGAF's dependencies.

```sh
conda create --name dygaf_env python=3.10
conda activate dygaf_env
```
## Step 2: Create requirements.txt
```sh
echo "numpy==1.24.0" > requirements.txt
echo "pandas==1.5.3" >> requirements.txt
echo "scikit-learn==1.5.1" >> requirements.txt
echo "tensorflow==2.10.0" >> requirements.txt
echo "xgboost==2.1.1" >> requirements.txt
```
## Step 3: Install Dependencies
### Install all dependencies listed in requirements.txt using pip:
```sh
pip install -r requirements.txt
```

## Step 4: Install DyGAF
### Finally, install DyGAF using pip:
```sh
pip install DyGAF
```
## Step 5: Usage

DyGAF can be used either via the command line interface (CLI) or in a Python environment such as Jupyter notebooks.

### Command Line Interface (CLI)

Run DyGAF from the command line by specifying the dataset path, target column, random seed, and number of splits for cross-validation.

```sh
DyGAF --df_path "/path/to/csvfile.csv" --target_column Target --seed 4 --n_splits 2
```

### Python Environment / Jupyter Notebook
### You can also use DyGAF within a Python script or Jupyter notebook to have more flexibility in your analysis.
```sh
# Import DyGAF function from the package
from DyGAF import DyGAF

# Set parameters for the pipeline
df_path = "/input/csvfile.csv"
target_column = "Target"  # Name of the target column
seed = 4  # Seed for reproducibility
n_splits = 5  # Number of splits for Stratified K-Fold

# Run DyGAF with the parameters
features_df, accuracy = DyGAF(df_path, target_column, seed, n_splits)

# Display results
print("Feature Importance (Top 5):")
print(features_df.head())
print(f"Model Accuracy: {accuracy:.4f}")
```

### Output folder would look like below:
```sh
output/
│
├── features_importance_seed4.csv                # Contains the feature importance analysis
├── output_seed4_dependent_attention_weights.csv  # Stores attention weights from the dependent attention model
└── output_seed4_independent_attention_weights.csv # Stores attention weights from the independent attention model
```

# Thank you for using our package!


