>>>>Predicting Daily Household Electricity Consumption
>KNN + 3-Layer MLP on the Smart Meters in London Dataset


>A predictive data analysis project comparing machine learning (KNN) and deep learning (Neural Network) approaches to forecast daily household electricity consumption using real smart meter data from 5,567 London households.


Results
>ModelMAE (kWh)RMSE (kWh)R²KNN (k=50, distance-weighted)2.7754.4800.792ANN (64-32-16, ReLU)2.5294.4150.798
Project Highlights

Dataset: Smart Meters in London — 167M half-hourly readings from 5,567 households, aggregated to daily level
ML Model: K-Nearest Neighbours with hyperparameter tuning (k = 3, 5, 10, 20, 50)
DL Model: 3-layer Multi-Layer Perceptron (64-32-16 neurons) with early stopping
Validation: 80/20 temporal split + 5-fold cross-validation on 50k subsample
Feature Analysis: Permutation importance + leave-one-feature-group-out ablation study

Key Findings

>Lag features dominate, previous day and previous week consumption are the strongest predictors
Weather matters and temperature, humidity, and wind speed add meaningful signal
ANN edges out KNN and hence the neural network achieves lower MAE and higher R², especially for high-consumption households
Both models generalise well. holdout and CV metrics are closely aligned

Repository Structure
├── README.md
├── notebooks/
│   ├── ml_and_dl.ipynb            # Main modelling notebook (KNN + ANN)
│   └── sampling_and_eda.ipynb     # EDA and data preparation
    └── .gitignore
Tech Stack

Python 3.10
scikit-learn (KNN, metrics, cross-validation)
TensorFlow / Keras (MLP)
pandas, NumPy (data wrangling)
matplotlib (visualisation)

Getting Started
1. Get the data
Download the Smart Meters in London dataset from Kaggle and place the CSV files in a data/ folder.
2. Install dependencies
bashpip install numpy pandas scikit-learn tensorflow matplotlib jupyter
3. Generate the modelling table
Run notebooks/sampling_and_eda.ipynb to produce daily_sample.csv.
4. Run the models
Open notebooks/ml_and_dl.ipynb and run all cells. Runtime: ~5-10 minutes on CPU.
Reproducibility
Random seeds are fixed (np.random.seed(50), tf.random.set_seed(50)). Results should reproduce within ~0.05 kWh RMSE across machines.
Dataset
Smart Meters in London by Jean-Michel Daignan - Kaggle - CC BY 4.0
Author
>Rahim - MSc student, Brunel University London
License
.Code released for educational use. Dataset: CC BY 4.0.
