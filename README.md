# ODLID: Multiclass Intrusion Detection

This repository contains code for the ODLID framework, which combines anomaly-based feature augmentation (FA) with model-specific Optuna hyperparameter optimization for multiclass intrusion detection. The experiments use CICIoT2023 and NSL-KDD and consider both imbalanced and balanced training settings.

The classifiers include a deep neural network (DNN), long short-term memory (LSTM), and gated recurrent unit (GRU). Feature augmentation appends continuous anomaly scores from Isolation Forest (IForest), an autoencoder (AE), and a SUOD ensemble to the original input features.

## Execution Order

1. **Construct the CICIoT2023 subset.** Download the original CSV files from the [official CICIoT2023 dataset page](https://www.unb.ca/cic/datasets/iotdataset-2023.html). Update the input paths and run `CICIoT2023_Subset_Construction_and_Representativeness_Analysis.ipynb`.

2. **Clean the data and generate anomaly scores.** Run `CICIoT2023_Data_Cleaning_and_Anomaly_Score_Generation.ipynb` to prepare the cleaned and feature-augmented datasets. Fit preprocessing operations and anomaly detectors on the training data only.

3. **Train and evaluate the classifiers.** Run the relevant notebooks in `Intrusion_Detection_Models/CICIoT2023_Code/` or `Intrusion_Detection_Models/NSL_KDD_Code/`, using the prepared data in `Cleaned_dataset/` and the corresponding settings in `Selected_Hyperparameters/`. Update dataset paths before execution. For NSL-KDD, follow the preparation instructions in its notebooks; the original dataset description is available [here](https://www.kaggle.com/code/abdellahmdn/high-precision-ids-on-nsl-kdd-dataset).
