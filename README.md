# ECG Heartbeat Categorization Using Deep Learning Models

## Overview
This project focuses on classifying ECG signals to help detect heart conditions. It uses deep learning models like LSTM, CNN, and GRU to categorize heartbeats into five types based on the MIT-BIH Arrhythmia Dataset. The aim is to build an accurate system for detecting arrhythmias automatically.

## Dataset
The project uses the **MIT-BIH Arrhythmia Dataset**, which is widely used for ECG signal classification. The dataset includes:
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
### Preprocessing
- ECG signals are split into individual heartbeats (each 187 data points long).
- The data is normalized to improve training.
- Labels are one-hot encoded for better classification.
- **SMOTE** is applied to handle class imbalance.

### Model Training
- **CNN**: Detects important patterns in ECG signals.
- **LSTM**: Captures sequential relationships in the data.
- **GRU**: A faster alternative to LSTM with similar accuracy.

### Training & Evaluation
- **Optimizer**: Adam
- **Loss Function**: Categorical Cross-Entropy
- **Epochs**: 50 (with early stopping)
- **Metrics**: Accuracy, Precision, Recall, F1-score

## Results
Before applying SMOTE, the models struggled with imbalanced data. After applying SMOTE, accuracy improved:

| Model | Accuracy | F1 Score | Precision | Recall |
|-------|----------|----------|-----------|--------|
| CNN   | 97.64%   | 0.9766   | 0.9768    | 0.9764 |
| LSTM  | 95.94%   | 0.9619   | 0.9668    | 0.9594 |
| GRU   | 96.40%   | 0.9665   | 0.9713    | 0.9640 |

## Conclusion
- **CNN performed the best**, achieving the highest accuracy.
- **SMOTE helped balance the dataset**, improving classification for less common heartbeat types.
- Future work could explore hybrid models and real-time applications on wearable devices.

## License
This project is licensed under the MIT License. See `LICENSE` for details.


