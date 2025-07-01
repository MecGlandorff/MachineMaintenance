# 🎢 Machine Failure Prediction System

This small project explores whether Support Vector Machines (SVM) can learn from historical machine behaviour and help prevent failures before they happen.

---

## The Dataset

The dataset (`ai4i2020.csv`) contains 10,000 records from machines operating under various conditions. Each row includes:

- Sensor data: air temperature, process temperature  
- Machine performance: torque, rotational speed, tool wear  
- Machine type: L or M  
- Failure labels:  
  - TWF (Tool Wear Failure)  
  - HDF (Heat Dissipation Failure)  
  - PWF (Power Failure)  
  - OSF (Overstrain Failure)  
  - RNF (Random Failure)  

### Summary:

- Total records: 10,000  
- Failures: 339  
- Non-failures: 9,661  
- Type L machines: 6,000  
- Type M machines: 2,997  
- 3 machines with no type recorded (they didn’t say)  

---

## Approach

1. **Preprocessing**  
   - One-hot encoded machine types  
   - Scaled features to similar ranges  
   - Split data 80/20 into train/test  

2. **Model**  
   - Support Vector Machine with RBF kernel  
   - Trained to distinguish failure vs. non-failure  

3. **Evaluation**  
   - Accuracy: 99.9%  
   - Catches almost every failure without false alarms  

---

## Results

The model performed well on the test set:

| Class             | Precision | Recall | F1-Score | Amount  |
|------------------:|----------:|-------:|---------:|--------:|
| Non-Failure (0)   | 0.999     | 1.000  | 0.999    | 1939    |
| Failure (1)       | 1.000     | 0.967  | 0.983    | 61      |

- **Accuracy**: 0.999  
- **Macro Avg F1-Score**: 0.991  
- **Weighted Avg F1-Score**: 0.999  

Translation: the model correctly identified almost all failures, and didn’t flag healthy machines by mistake.

---

## Observations

- Tool wear and torque showed the strongest correlation with failure  
- Failures are relatively rare (~3.4% of data), but the model handled the imbalance well

---


## Future Plans

- Experiment with other models like Random Forest and Neural Networks.  
- Deploy the system for real-time factory monitoring.  
- Add more insightful visualizations.

# DATA & CREDITS
Data doesn't belong to me so thanks to UC IRVINE: 
https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset
This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.
