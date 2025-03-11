# ECG Heartbeat Categorization Using Deep Learning Models

## Project Overview
This is a student project aimed at classifying ECG signals to detect heart conditions. The project uses deep learning models like LSTM, CNN, and GRU to categorize heartbeats into five types using the MIT-BIH Arrhythmia Dataset. The goal is to create an efficient and accurate system for diagnosing arrhythmias.

## Dataset
We used the **MIT-BIH Arrhythmia Dataset**, a widely used dataset for ECG classification. The dataset includes:
- **Total Samples**: 109,446
- **Categories**:
  - Normal (N)
  - Supraventricular Ectopic (S)
  - Ventricular Ectopic (V)
  - Fusion (F)
  - Unclassifiable (Q)
- **Sampling Rate**: 125 Hz
- **Source**: PhysioNet's MIT-BIH Arrhythmia Database
- **Dataset Link**: [Kaggle](https://www.kaggle.com/datasets/shayanfazeli/heartbeat)

## Methodology
1. **Preprocessing**
   - Splitting raw ECG signals into 187 data points per heartbeat.
   - Normalization for better training.
   - One-hot encoding for class labels.
   - Using **SMOTE** to balance the dataset.

2. **Feature Extraction & Model Training**
   - **CNN**: Extracts important patterns from ECG signals.
   - **LSTM**: Captures patterns in sequential data.
   - **GRU**: Faster and more memory-efficient than LSTM.

3. **Training & Evaluation**
   - **Optimizer**: Adam
   - **Loss Function**: Categorical Cross-Entropy
   - **Epochs**: 50 (with early stopping)
   - **Metrics**: Accuracy, Precision, Recall, F1-score

## Results
At first, the models struggled with imbalanced data. After applying SMOTE, accuracy improved:

| Model | Accuracy | F1 Score | Precision | Recall |
|-------|----------|----------|-----------|--------|
| CNN   | 97.64%   | 0.9766   | 0.9768    | 0.9764 |
| LSTM  | 95.94%   | 0.9619   | 0.9668    | 0.9594 |
| GRU   | 96.40%   | 0.9665   | 0.9713    | 0.9640 |

## Conclusion
- **CNN performed the best**, achieving the highest accuracy.
- **SMOTE improved classification for less common heartbeat types.**
- Future improvements could involve using hybrid models and testing real-time applications on wearable devices.

