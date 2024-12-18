# 🎢 Machine Failure Prediction System

## Overview
This project is about detecting machine failures before they break down. Using the power of Support Vector Machines (SVM) and a dataset filled with operational data, I built a highly accurate system to predict machine failure.

---

## The Dataset
The dataset (`ai4i2020.csv`) contains 10,000 operational records, each packed with details like temperatures, torque, speed, and tool wear. It also includes failure classifications across five categories:

- **TWF**: Tool Wear Failure  
- **HDF**: Heat Dissipation Failure  
- **PWF**: Power Failure  
- **OSF**: Overstrain Failure  
- **RNF**: Random Failure  

### Key Stats:
- **Total Records**: 10,000  
- **Failures Detected**: 339  
- **Non-Failures**: 9,661  
- **Machine Types**:  
  - Type L: 6,000  
  - Type M: 2,997  
  - 3 unclassified mystery-machines (called in sick for work or something).  

---

## Pipeline

### 1. Preprocessing
- **One-Hot Encoding**: Converted `Type` (L/M) into numerical values.  
- **Scaling**: Normalized all features to ensure fair treatment.  
- **Train-Test Split**: Split the dataset into 80% training and 20% testing data.  

### 2. Model Training
- **Algorithm**: Support Vector Machine with an RBF kernel.  
- **Goal**: Detect machine failures with high accuracy and reliability.  

### 3. Evaluation
- **Accuracy**: 99.9%  
- **Precision, Recall, and F1-Score**: Exceptional performance across all metrics.  
- Caught almost every failure while leaving non-failures untouched.  

### 4. Visualization
A heatmap revealed the strongest correlations between features. For example, **tool wear** and **torque** play key roles in predicting failures.

---

## Results

- **Failures Detected**: ✔️  
- **Innocent Machines Left Untouched**: ✔️  
- **Factory Chaos Avoided**: ✔️  

---

## How to Run

1. **Clone this repository**:
   ```bash
   git clone https://github.com/yourusername/machine-failure-prediction.git
   cd machine-failure-prediction
