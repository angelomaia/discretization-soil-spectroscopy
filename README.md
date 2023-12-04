## Binary classification of soil contamination by heavy metals using mid-infrared spectroscopy coupled with machine learning methods

---

## Table of Contents

1. [Data Acquisition](#data-acquisition)
2. [Data Analysis](#data-analysis)
3. [Partial Least Squares Regression](#partial-least-squares-regression)
4. [Threshold Setting and Dataset Splitting](#threshold-setting-and-dataset-splitting)
5. [Machine Learning Methods](#machine-learning-methods)
   - [Random Forest (RF)](#random-forest-rf)
   - [XGBoost](#xgboost)
   - [Convolutional Neural Network (CNN)](#convolutional-neural-network-cnn)
6. [Evaluation Metrics](#evaluation-metrics)

---

## Data Acquisition<a name="data-acquisition"></a>

### 2.1 Data Acquisition

The dataset used in this study was obtained from the [Open Soil Spectral Library (OSSL)](https://explorer.soilspectroscopy.org/), containing over 20,000 samples from the Kellogg Soil Survey Laboratory (KSSL) of the Natural Resources Conservation Service of the United States Department of Agriculture (USDA). Details about the dataset and laboratory procedures can be found in the Kellogg Soil Survey Laboratory methods manual. The dataset includes MIR spectra (600 – 4000 cm⁻¹) and elemental concentrations for heavy metals. The dataset was filtered for samples with consistent data, resulting in 1,165 samples.

---

## Data Analysis<a name="data-analysis"></a>

### 2.2 Data Analysis

With the filtered dataset, elemental concentrations were analyzed using descriptive statistics. Spearman correlation analyses were conducted between elemental concentrations and various soil properties. Monotonic relationships with MIR spectra were identified using Spearman correlation analysis. MIR data consisted of 1701 data points per sample. Soil samples were categorized into topsoil and subsoil, resulting in three sample sets (All samples, Topsoil, and Subsoil) with distinct elemental and spectral characteristics.

---

## Partial Least Squares Regression<a name="partial-least-squares-regression"></a>

### 2.3 Partial Least Squares Regression

Partial Least Squares (PLS) regression was employed for predicting elemental concentrations. PLS models were built for each element with 10-fold cross-validation and grid search for the best number of components. Model performance was evaluated using Root Mean Squared Error (RMSE), Coefficient of Determination (R²), Ratio of Prediction to Deviation (RPD), and Ratio of Prediction to Interquartile distance (RPIQ).

---

## Threshold Setting and Dataset Splitting<a name="threshold-setting-and-dataset-splitting"></a>

### 2.3 Threshold Setting and Dataset Splitting

To enable robust performance comparison among binary classification models, a standardized methodology was established. The classification threshold was set to the third quartile (Q3) of each element. Positive samples (contaminated) were the top 25%, and negative samples (non-contaminated) were the bottom 75%. Models were developed for each element with 80% of samples for training and 20% for testing, ensuring a stratified representative split between positive and negative samples.

---

## Machine Learning Methods<a name="machine-learning-methods"></a>

### 2.4 Machine Learning Methods

Aiming for robust binary classification models, three machine learning algorithms were employed: Random Forest, XGBoost, and Convolutional Neural Network (CNN). Each method was optimized using grid search for hyperparameters. Model performance was evaluated using well-established metrics such as Accuracy, Precision, and Recall.

---

### Random Forest (RF)<a name="random-forest-rf"></a>

#### 2.4.1 Random Forest (RF)

Random Forest is an ensemble learning method employing decision trees for classification. Model optimization was done with 10-fold cross-validation and grid search for hyperparameters.

---

### XGBoost<a name="xgboost"></a>

#### 2.4.2 XGBoost

XGBoost is an efficient tree boosting framework with regularization terms and column sampling. Model optimization was done with 10-fold cross-validation and grid search for hyperparameters.

---

### Convolutional Neural Network (CNN)<a name="convolutional-neural-network-cnn"></a>

#### 2.4.3 Convolutional Neural Network (CNN)

To harness the potential of deep learning for our binary classification task, we employed a Convolutional Neural Network (CNN). CNNs are able to process multidimensional data arrays by applying a mathematical operation known as convolution. The CNN architecture utilized in this study is the depthwise separable convolution proposed by Yang et al. (2020). Model optimization was done using the 'Adam' optimizer and trained for 200 epochs.

---

## Evaluation Metrics<a name="evaluation-metrics"></a>

### 2.5 Evaluation Metrics

The performance of the developed classification models was assessed using a set of well-established evaluation metrics, including Accuracy, Precision, and Recall. These metrics collectively provide a nuanced perspective on the performance of the developed binary classification models, allowing for a general assessment of their quality.
